---
title: "Lab: ENF Analysis and Metadata Consistency"
date: 2026-02-18
draft: false
---

<!--
================================================================
INSTRUCTOR PREPARATION NOTES — Not visible to students
================================================================

## Before Class

1. Test openENF on your own machine before the lab session.
   Run `enf --help` to confirm the CLI is working.

2. Test a known European indoor recording through openENF to verify
   that the .freqdb files download and load correctly.

## ENF Trace File Workaround

openENF stores frequency database files at:
  Windows: %APPDATA%\OpenENF\

Files: GB.freqdb (downloaded automatically on first run)

Known issue: Zenodo (the hosting service) blocks the automatic download
with a 403 Forbidden error, leaving corrupted .freqdb files. Students
must manually download the database file. The student-facing instructions
are included in Part 1 below.

## Important Constraints

- openENF only has reference data for European grids (GB and DE).
  Students MUST find recordings from Europe — North American
  recordings (60 Hz grid) will not match.

- Recordings need to be at least ~3 minutes for meaningful results.

- openENF only supports WAV files.

## Freesound Search Tips for Students Who Get Stuck

Good searches (likely to contain ENF):
  "room tone London", "office ambience UK", "indoor recording Germany",
  "studio noise Europe", "room tone Berlin", "office hum"

Bad searches (unlikely to contain ENF):
  "forest ambience", "ocean waves", "outdoor wind", "bird song",
  "mountain stream", "rain outdoors"

================================================================
END INSTRUCTOR NOTES
================================================================
-->

## Overview

**Duration**: ~60 minutes

**Objective**: Use openENF to extract and analyze Electrical Network Frequency traces from audio recordings, and use ImHex to examine raw file metadata and WAV header structures. This lab reinforces the "two pillars of digital authentication" from the lecture: ENF as a physical truth anchor and metadata as a digital integrity check.

**What to submit:** Each exercise ends with a **Turn in** block telling you what to screenshot and what to answer. When you're done, submit a folder of your screenshots and a single Word document (.docx) with your answers, organized by exercise number.

> **Screenshot tip:** Capture the full application window so context is visible (terminal command + output, or ImHex with the file name and byte offsets showing). Label each file with the exercise number (e.g., `Ex1_freesound_indoor.png`).

---

## Part 1: Install Tools (~10 minutes)

### Exercise 0: Setting Up Your Environment

#### Step 1: Install Node.js

openENF is a command-line tool built with Node.js. If you don't already have Node.js installed:

1. Go to [https://nodejs.org/](https://nodejs.org/) and download the **LTS** (Long Term Support) version for Windows
2. Run the installer and follow the prompts (accept all defaults)
3. Open **Command Prompt** and verify the installation:

```
node --version
npm --version
```

Both commands should print a version number (e.g., `v20.11.0` and `10.2.0`).

#### Step 2: Install openENF

In Command Prompt, run:

```
npm install --global openenf
```

Verify it installed correctly:

```
enf --help
```

You should see usage information and available options.

#### Step 2b: Download the ENF Reference Databases

openENF needs frequency database files to compare recordings against. The automatic download is currently broken, so you need to download them manually. You need **both** databases — GB (Great Britain) and DE (Germany) — because the lab exercises search both grids.

1. **Download the GB database** (505 MB) from Zenodo. Click the link below and wait for the download to complete:

   [Download GB_50_2014-2021.freqdb from Zenodo](https://zenodo.org/records/7741427/files/GB_50_2014-2021.freqdb?download=1)

2. **Download the DE database** from Zenodo. Click the link below and wait for the download to complete:

   [Download DE_50_2010-2021.freq.freqdb from Zenodo](https://zenodo.org/records/7809233/files/DE_50_2010-2021.freq.freqdb?download=1)

3. **Open the OpenENF data folder.** In File Explorer, paste this into the address bar and press Enter:

   `%APPDATA%\OpenENF`

   If the folder doesn't exist yet, create it: navigate to `%APPDATA%` first, then create a new folder called `OpenENF`.

4. **Delete any existing `.freqdb` files** in that folder (they may be corrupted from the failed auto-download).

5. **Move both downloaded files** from your Downloads folder into the `OpenENF` folder.

6. **Rename the files** so openENF can find them — it expects these exact names:
   - `GB_50_2014-2021.freqdb` → **`GB.freqdb`**
   - `DE_50_2010-2021.freq.freqdb` → **`DE.freqdb`**

7. **Verify it works** by running `enf --help` in Command Prompt. You should no longer see any database errors.

#### Step 3: Install ImHex

ImHex is a hex editor for examining the raw bytes of files.

1. Go to [https://imhex.werwolv.net/](https://imhex.werwolv.net/) and download the Windows installer
2. Run the installer and follow the prompts
3. Launch ImHex to verify it opens correctly

No screenshots needed for this part — just make sure both tools are working before you continue.

---

## Part 2: Finding Audio for ENF Analysis (~15 minutes)

### Exercise 1: Browsing Freesound for ENF-Compatible Recordings

ENF analysis only works on recordings that captured the power grid's hum. Your goal is to find one recording where ENF **should** be present and one where it **should not**.

1. Go to [Freesound.org](https://freesound.org/) and create a free account (or log in if you already have one)

2. **Find a recording where ENF should work.** Search for indoor recordings made in Europe (UK or continental Europe). Try search terms like "room tone," "office ambience," "indoor recording," or "studio noise." Look for recordings that:
   - Were recorded **indoors** (near electrical wiring and appliances)
   - Are at least **3 minutes long** (openENF needs sufficient duration)
   - Are in **WAV format** (openENF only supports WAV)
   - Were recorded in **Europe** (openENF only has European grid reference data — GB or DE grids)

3. Download the recording. Note the Freesound URL and any description or tags provided by the uploader.

4. **Find a recording where ENF should NOT work.** Search for outdoor or isolated recordings. Try "forest ambience," "ocean waves," "mountain wind," "bird song," or "outdoor field recording." Download one that is at least 3 minutes long and in WAV format.

5. Create a folder on your desktop called `ENFLab` and save both files there.

> **Turn in:**
>
> - **Screenshots:**
>   1. The Freesound page for your "should work" recording (showing the title, description, and tags)
>   2. The Freesound page for your "should not work" recording
> - **Word doc questions:**
>   1. For each recording, list: the Freesound URL, the uploader's description, and why you predicted ENF would or would not be present.
>   2. Based on the lecture, what are the three pathways by which ENF enters audio recordings? Which pathway(s) do you think apply to your "should work" recording?

---

## Part 3: Running openENF (~15 minutes)

### Exercise 2: Extracting and Comparing ENF Traces

1. Open **Command Prompt**

2. Run openENF on your indoor/European recording:

```
enf /path/to/your/indoor-recording.wav --grids GB DE --start 2020-01-01 --end 2025-12-31
```

Replace `/path/to/your/indoor-recording.wav` with the actual file path. You can drag the file from File Explorer into the Command Prompt window to paste its path.

Adjust the `--start` and `--end` dates if you know when the recording was made. A narrower date range will process faster.

3. Wait for the analysis to complete. This may take several minutes — it is computationally intensive. The tool will output:
   - An estimated timestamp
   - A match score (lower = stronger match)
   - The grid it matched against (GB or DE)

4. Record the results.

5. Now run openENF on your outdoor/isolated recording using the same command:

```
enf /path/to/your/outdoor-recording.wav --grids GB DE --start 2020-01-01 --end 2025-12-31
```

6. Compare the two results.

> **Turn in:**
>
> - **Screenshots:**
>   1. Terminal output from running openENF on your indoor recording (showing the full command and results)
>   2. Terminal output from running openENF on your outdoor recording
> - **Word doc questions:**
>   1. What timestamp and match score did openENF report for your indoor recording? Which grid did it match?
>   2. What happened when you ran openENF on your outdoor recording? Was the match score meaningfully different? What does this tell you?
>   3. Based on the lecture's discussion of ENF limitations, explain why outdoor recordings typically lack a usable ENF signal. Reference at least two specific limitations.
>   4. If you were a forensic examiner and received a recording claimed to be from a specific date and location, but openENF returned a very weak match, what would you conclude? What other evidence would you look for?

---

## Part 4: Examining WAV Headers with ImHex (~12 minutes)

### Exercise 3: The Anatomy of a WAV File

Now you'll examine the raw bytes of your WAV files to understand how audio metadata is stored at the binary level.

1. Open **ImHex**
2. Go to **File > Open** and open your indoor recording WAV file
3. You will see the raw bytes displayed as hexadecimal values on the left and ASCII text on the right

**Finding the RIFF Header**

4. Look at the very first bytes of the file. You should see `52 49 46 46` in hex, which reads as `RIFF` in ASCII. This is the "magic bytes" signature that identifies this as a RIFF container.
5. Bytes 4–7 contain the file size (minus 8 bytes for the header). This is stored in **little-endian** byte order (least significant byte first).
6. Bytes 8–11 should read `57 41 56 45` = `WAVE`, confirming this is a WAV file.

**Finding the Format Chunk**

7. Look for the bytes `66 6D 74 20` = `fmt ` (note the trailing space). This is the format chunk that describes the audio encoding.
8. After the `fmt ` marker and its 4-byte size field, the next bytes encode:
   - **Audio format** (2 bytes): see the format tag key below
   - **Number of channels** (2 bytes): `01 00` = mono, `02 00` = stereo
   - **Sample rate** (4 bytes): e.g., `44 AC 00 00` = 44,100 Hz in little-endian
   - **Bit depth** (at byte offset 14–15 within the chunk): e.g., `10 00` = 16-bit

   **Audio format tag key** — ImHex may label yours differently depending on the file:

   | Hex bytes | Decimal | ImHex label | Meaning |
   |-----------|---------|-------------|---------|
   | `01 00` | 1 | `PCM` | Uncompressed integer PCM — the standard for most recordings |
   | `03 00` | 3 | `IEEEFloatingPoint` | 32-bit float PCM — common from DAWs and professional software |
   | `06 00` | 6 | `ALaw` | A-law compressed — telephone/broadcast encoding |
   | `07 00` | 7 | `MuLaw` | μ-law compressed — telephone/broadcast encoding |
   | `11 00` | 17 | `ADPCM` | Adaptive differential PCM — older compressed format |
   | `FF FE` | 65534 | `Extensible` | Extended format — check the sub-format GUID for the actual type; common for multichannel or high-res audio |

   Any of these are valid WAV files. For forensic purposes, the format tag tells you something about the recording workflow — for example, `IEEEFloatingPoint` often indicates the file came from a DAW or was exported by audio editing software, while `PCM` is more typical of field recorders and consumer devices.

9. Use ImHex's **Data Inspector** panel to help interpret values. If it's not visible, enable it via **View > Data Inspector**. Click on any byte and the inspector will show its value interpreted as different data types (uint16, uint32, etc.).

**Finding the Data Chunk**

10. Search for `64 61 74 61` = `data`. Everything after this chunk header and its 4-byte size field is the actual audio sample data.

> **Turn in:**
>
> - **Screenshots:**
>   1. ImHex showing the RIFF/WAVE header at the beginning of the file (first ~50 bytes visible)
>   2. ImHex showing the `fmt ` chunk with the Data Inspector panel visible, highlighting the sample rate or bit depth
> - **Word doc questions:**
>   1. What sample rate, bit depth, and channel count does your WAV file use? Show how you decoded at least one of these values from the raw hex bytes (explain the little-endian byte order conversion).
>   2. Why does the WAV format use a chunked structure (RIFF, fmt, data) rather than just storing raw audio bytes? What forensic advantage does this provide?
>   3. From the lecture, you learned that manufacturer devices like Olympus recorders embed proprietary signatures in file headers. If this WAV file came from such a device, where in the hex data would you look for manufacturer signatures? (Hint: think about additional RIFF chunks beyond `fmt` and `data`.)

---

## Part 5: Timestamps and Software Fingerprints (~8 minutes)

### Exercise 4: Detecting Modification History

1. In ImHex, with your WAV file still open, use **Edit > Find** (or `Ctrl+F` / `Cmd+F`) to search for text strings.

2. Search for these common software signatures one at a time:
   - `Audacity` or `audacity`
   - `Adobe` or `Audition`
   - `LAVF` (FFmpeg/libavformat)
   - `Xmp` or `XMP` (Adobe's metadata format)
   - `LIST` (RIFF LIST chunk — often contains metadata like artist, title, creation date)
   - `bext` (Broadcast Wave Format extension — contains origination date and time)

3. Document any strings you find and their byte offset (shown at the bottom or side of ImHex).

4. Now open your **outdoor recording** in ImHex and repeat the same searches. Compare what metadata each file contains.

5. If either file contains a `LIST` or `bext` chunk, examine the ASCII text visible in that region — it may contain creation dates, software names, or other provenance information.

**Connecting ENF and Metadata**

6. Consider both of your files together. For each file, you now have:
   - ENF analysis results (from Exercise 2)
   - File structure and encoding details (from Exercise 3)
   - Software and metadata signatures (from this exercise)

> **Turn in:**
>
> - **Screenshots:**
>   1. ImHex search results showing any software signature strings you found (or showing a search that returned no results)
>   2. Any `LIST`, `bext`, or other metadata chunk you found with readable ASCII text visible. If neither file had these, screenshot the `fmt ` chunk of your second file instead.
> - **Word doc questions:**
>   1. What software signatures or metadata strings did you find in each file? If none were found, what does the *absence* of metadata tell you about the file's history?
>   2. The lecture described the Olympus example where editing in Adobe Audition replaced manufacturer hex strings with XMP metadata. Based on your hex examination, do your files appear to be original recordings or have they been processed by editing software? What evidence supports your conclusion?
>   3. **Synthesis question:** You now have ENF results and metadata analysis for two recordings. Write a brief (3–5 sentence) forensic summary for ONE of your files, as if you were preparing an expert report. State what the ENF analysis revealed, what the metadata examination revealed, and whether these two lines of evidence are consistent or contradictory. Reference the lecture's concept of "two pillars of digital authentication."

---

## Submission Checklist

Use this checklist before you submit to make sure you have everything:

- [ ] Exercise 1 — 2 screenshots (Freesound pages) + 2 answers
- [ ] Exercise 2 — 2 screenshots (terminal output) + 4 answers
- [ ] Exercise 3 — 2 screenshots (RIFF header, fmt chunk) + 3 answers
- [ ] Exercise 4 — 2 screenshots (software signatures, metadata chunks) + 3 answers

**Total: 8 screenshots and 12 written answers**

Submit your screenshot folder and Word document to D2L.

---

## Troubleshooting

**`enf` command not found?**
- Close and reopen Command Prompt after installing — the PATH update requires a fresh terminal. If it still doesn't work, try running `npm config get prefix` to see where npm installed it, then run the `enf` command using the full path (e.g., `C:\Users\YourName\AppData\Roaming\npm\enf`).

**openENF errors about `.freqdb` files?**
- Follow the manual download steps in Step 2b above. Make sure the file is named exactly `GB.freqdb` (not `GB_50_2014-2021.freqdb`) and is in the `%APPDATA%\OpenENF\` folder.

**openENF is taking a very long time?**
- This is normal for wide date ranges. Narrowing the `--start` and `--end` range reduces processing time significantly. If you know the approximate recording date, use a range of a few months instead of several years.

**Freesound only has MP3 or FLAC files?**
- openENF requires WAV format. Use Freesound's filters to search for WAV files specifically. If you can only find compressed formats, convert to WAV using Audacity (File > Export > Export as WAV) or an online converter — but note this adds a processing step that will be visible in metadata.

**ImHex shows garbled text in the ASCII column?**
- This is expected. You are looking at raw binary data. Readable text like `RIFF`, `WAVE`, `fmt`, and `data` only appears at specific header locations. The rest of the file is audio sample data, which looks like random characters.

**Node.js installation issues?**
- If `npm install --global` fails with a permissions error, try running Command Prompt as Administrator (right-click > "Run as administrator") and retry the install command.

---

## Additional Resources

- Course textbook: Chapter 5 — Authenticity Assessment
- [openENF GitHub repository](https://github.com/openENF/openenf)
- [ImHex documentation](https://docs.werwolv.net/)
- [Freesound.org](https://freesound.org/)
- [Resource Interchange File Format (RIFF) — Microsoft Learn](https://learn.microsoft.com/en-us/windows/win32/xaudio2/resource-interchange-file-format--riff-) — official RIFF/WAV chunk structure reference
- [FNET/GridEye public data](https://fnetpublic.utk.edu/) — public ENF reference database

**Questions?** Bring them to the next class session or office hours.
