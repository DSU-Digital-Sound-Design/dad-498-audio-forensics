---
title: "Lab: Identifying Edits in Audio Recordings"
date: 2026-02-09
draft: false
---

<!--
================================================================
INSTRUCTOR PREPARATION NOTES — Not visible to students
================================================================

## Audio Files to Prepare

Create the following six WAV files and place them in:
/static/media/splices-and-edit-detection-lab/

All files should be 44.1 kHz, 16-bit, mono WAV.

### Source Material

Record (or have a colleague record) 2–3 minutes of continuous speech in
two different environments:

1. **Dry environment** — a treated studio, closet, or small carpeted room
   with minimal reflections. Record 60–90 seconds of natural speech
   (reading a news article works well).

2. **Reverberant environment** — a hallway, stairwell, bathroom, or large
   empty room. Record 60–90 seconds of the SAME speaker reading
   DIFFERENT text.

Alternatively, use public-domain speech recordings from:
- LibriVox (librivox.org) — public domain audiobooks
- Open Speech Repository (openslr.org)
- Your own recordings from previous semesters

Make sure background noise is present in at least one recording (HVAC hum,
electrical buzz, or outdoor ambiance). If your recording environment is
too quiet, you can add a subtle 60 Hz hum + harmonics using
Effects > Generate > Tones in Audition.

### File 1: edit_butt_splice.wav

**Purpose:** Obvious butt splice with audible click and visible discontinuity.

Steps in Adobe Audition:
1. Open your dry speech recording
2. File > Save As > "edit_butt_splice.wav"
3. Select a 0.3–0.5 second segment in the middle of a word or phrase
4. Edit > Delete (NOT Ripple Delete — use standard Delete which does a
   butt splice, or cut the segment and paste the remaining pieces together
   with zero crossfade)
   - Alternatively: select the segment, Edit > Cut, then place cursor at
     the cut point and Edit > Paste to join. Make sure "Crossfade" is OFF
     in Audition's clipboard preferences (Edit > Preferences > General,
     uncheck "Auto Crossfade Enabled")
5. The result should have an audible click at the edit point
6. Total file length: 15–30 seconds is plenty
7. Note the timestamp of the edit for the answer key

### File 2: edit_crossfade_short.wav

**Purpose:** Cross-fade edit (5–10 ms) — harder to detect, no audible click.

Steps in Adobe Audition:
1. Open your dry speech recording
2. File > Save As > "edit_crossfade_short.wav"
3. Enable crossfade: Edit > Preferences > General, check
   "Auto Crossfade Enabled"
4. Select a 0.3–0.5 second segment in the middle of a sentence
5. Edit > Ripple Delete
   - Audition automatically applies a short crossfade at the edit boundary
6. If you need more control: manually select the segment, delete it, then
   select a few milliseconds around the edit point and use
   Effects > Fade Envelope to create a 5–10 ms crossfade
7. Verify: zoom in to sample level at the edit point — there should be
   no discontinuity, but the speech rhythm or content should sound slightly
   unnatural if you listen carefully
8. Note the timestamp for the answer key
   1. at "field" in "come up from the field"

### File 3: edit_crossfade_long.wav

**Purpose:** Cross-fade edit (50–100 ms) — very smooth, minimal artifacts.

Steps in Adobe Audition:
1. Open your dry speech recording
2. File > Save As > "edit_crossfade_long.wav"
3. Delete a segment of speech as above, but this time apply a 50–100 ms
   crossfade at the edit boundary
4. To do this manually: after deleting, select ~100 ms around the
   edit point, then apply Effects > Amplitude and Compression >
   Fade Envelope, creating a smooth blend
5. Alternatively: use Multitrack view — place the two segments on the
   same track with 50–100 ms overlap, and Audition will auto-crossfade
6. This edit should be very difficult to detect visually in the waveform
7. Note the timestamp for the answer key
8.  before "born so by"

### File 4: edit_reverb_mismatch.wav

**Purpose:** Dry speech inserted into a reverberant recording —
reverberation mismatch visible in spectrogram.

Steps in Adobe Audition:
1. Open your REVERBERANT speech recording
2. File > Save As > " .wav"
3. Open your DRY speech recording in a separate tab
4. From the dry recording, select a 1–2 second speech segment
5. Edit > Copy
6. Switch to the reverberant file
7. Place the cursor at a pause or between words
8. Edit > Paste (with crossfade enabled so there is no click)
   - Use a short crossfade (10–20 ms) so the splice itself is not
     obvious, but the reverb mismatch IS obvious
9. The inserted dry segment should lack the reverb tails visible
   throughout the rest of the recording
10. Total file length: 15–30 seconds
11. Note the timestamp range of the inserted segment
    1.  "single broad window"
   

### File 5: edit_noise_inconsistency.wav

**Purpose:** Background noise floor changes at edit points —
continuous tones (hum) disappear in the inserted segment.

Steps in Adobe Audition:
1. Take a 20–30 second speech recording
2. Add a subtle background hum to the ENTIRE file:
   - Effects > Generate > Tones: 60 Hz sine wave, amplitude around -40 dB
   - Mix this with your speech recording using Multitrack view
     (or Effects > Generate directly into the waveform)
3. Also add a subtle broadband noise floor:
   - Effects > Generate > Noise at around -50 dB
4. File > Save As > "edit_noise_inconsistency.wav"
5. Now select a 2–3 second segment in the middle and REPLACE it with
   a speech segment that does NOT have the 60 Hz hum and has a
   different noise floor level
   - You can prepare this replacement segment from a clean recording
     with just a different noise generator applied (different level or
     no 60 Hz tone)
6. Use short crossfades so the edit boundary itself is smooth
7. The telltale sign: the 60 Hz horizontal line in the spectrogram
   disappears during the inserted segment, and the noise floor texture
   changes
8. Note the timestamp range of the altered segment
   1. "worn smooth by..."

### Summary of Files

| File | Type | Key Feature |
|------|------|-------------|
| edit_butt_splice.wav | Butt splice deletion | Click/discontinuity |
| edit_crossfade_short.wav | Short crossfade (5–10 ms) | Subtle spectral artifact |
| edit_crossfade_long.wav | Long crossfade (50–100 ms) | Nearly invisible |
| edit_reverb_mismatch.wav | Dry insertion in reverb | Missing reverb tails |
| edit_noise_inconsistency.wav | Noise floor change | Missing hum, changed noise |

================================================================
END INSTRUCTOR NOTES
================================================================
-->

## Overview

**Duration**: ~35 minutes

**Objective**: Apply visual and auditory techniques to detect splices, cross-fade edits, reverberation mismatches, and background noise inconsistencies in audio recordings using Adobe Audition and a web-based edit detection tool.

This lab reinforces the concepts from today's lecture on splices and edit detection (Chapter 5). You will progress from identifying obvious edits to analyzing subtle forgeries, building a systematic approach to audio authenticity assessment.

**What to submit:** Each exercise ends with a **Turn in** block telling you what to screenshot and what to answer. When you're done, submit a folder of your screenshots and a single Word document (.docx) with your answers, organized by exercise number.

> **Screenshot tip:** Capture the full Adobe Audition window so the file name, view mode, and any markers or zoom level are visible. Label each file with the exercise number (e.g., `Ex1_butt_splice_waveform.png`).

---

## Part 1: Download Lab Materials

Download the following audio files and save them to a folder on your desktop called `EditDetectionLab`:

### Required Files

- [edit_butt_splice.wav](/media/splices-and-edit-detection-lab/edit_butt_splice.wav) - Speech with a butt splice edit
- [edit_crossfade_short.wav](/media/splices-and-edit-detection-lab/edit_crossfade_short.wav) - Speech with a short cross-fade edit
- [edit_crossfade_long.wav](/media/splices-and-edit-detection-lab/edit_crossfade_long.wav) - Speech with a long cross-fade edit
- [edit_reverb_mismatch.wav](/media/splices-and-edit-detection-lab/edit_reverb_mismatch.wav) - Reverberant speech with a dry insertion
- [edit_noise_inconsistency.wav](/media/splices-and-edit-detection-lab/edit_noise_inconsistency.wav) - Speech with background noise changes
---

## Part 2: Detecting Butt Splices (8 minutes)

### Exercise 1: Finding an Obvious Edit

Open `edit_butt_splice.wav` in Adobe Audition.

**First Listen**

1. Press `\` (backslash) to fit the entire waveform in the window
2. Press **Spacebar** to play the recording from start to finish
3. Listen for anything that sounds unnatural: a click, a pop, or an abrupt jump in the speech

**Visual Inspection — Waveform View**

4. Look at the waveform for any abrupt discontinuity — a place where the waveform appears to "jump" rather than flow smoothly
5. Once you spot a suspicious area, click on it to place the playhead there
6. Zoom in using `=` until you can see the shape of individual waveform cycles (approximately 5–10 ms visible on screen)
7. The butt splice will appear as a sharp discontinuity where the waveform on the left side of the edit does not connect smoothly to the waveform on the right side

**Visual Inspection — Spectrogram View**

8. Switch to spectral view: **View > Spectral Frequency Display** (or press `Shift+D`)
9. Zoom back out to see the full file (`\`)
10. Look for a thin vertical line of energy spanning all frequencies — this is the broadband click artifact caused by the splice discontinuity
11. Zoom in on the vertical line until you can see it clearly

**Confirm with Listening**

12. Place the playhead a second before the suspected edit point
13. Press Spacebar to play through the edit
14. You should hear a distinct click or pop at the splice point

> **Turn in:**
> - **Screenshots:**
>   1. Waveform view zoomed in on the discontinuity (close enough to see the waveform shape break)
>   2. Spectrogram view showing the vertical broadband artifact at the edit point
> - **Word doc questions:**
>   1. At what timestamp (to the nearest 0.01 seconds) is the edit located?
>   2. Describe what the butt splice looks like in the waveform. How does the waveform on the left side of the edit differ from the right side?
>   3. Why does a butt splice create a vertical line in the spectrogram? (Hint: think about what an abrupt discontinuity in the time domain means in the frequency domain.)

---

## Part 3: Detecting Cross-Fade Edits (8 minutes)

### Exercise 2: When the Click Disappears

Open `edit_crossfade_short.wav` in Adobe Audition.

**Compare to the Butt Splice**

1. Play the recording all the way through. Can you hear a click like in Exercise 1?
2. View the waveform at full zoom-out. Can you see an obvious discontinuity?
3. Switch to spectrogram view (`Shift+D`). Is there a clear vertical broadband line?

The edit in this file uses a short cross-fade (just a few milliseconds) instead of a butt splice. This eliminates the click artifact but may leave subtler clues.

**Closer Examination**

4. In spectrogram view, slowly scrub through the file looking for any subtle change in the spectral pattern — a brief smearing of energy, a slight irregularity in the speech formants, or a moment where the background noise texture shifts
5. Listen again with headphones, paying attention to speech rhythm and naturalness. Does any transition between words or syllables sound slightly rushed or awkward?
6. When you find a suspicious region, zoom in to the sample level in waveform view. Even with a cross-fade, you may notice a subtle change in the waveform envelope or a slight irregularity

**Now Compare**

7. Open `edit_crossfade_long.wav` in a second tab
8. Repeat the same examination. This file has a much longer cross-fade (50–100 ms)
9. Is this edit easier or harder to find than the short cross-fade?

> **Turn in:**
> - **Screenshots:**
>   1. Spectrogram view of `edit_crossfade_short.wav` zoomed into the region where you believe the edit is located
>   2. Spectrogram view of `edit_crossfade_long.wav` zoomed into the suspected edit region (if you found it; if not, screenshot your best guess area)
> - **Word doc questions:**
>   1. Were you able to hear either cross-fade edit during playback? What (if anything) sounded unnatural?
>   2. At what timestamp do you believe each edit is located? How confident are you (high/medium/low) for each?
>   3. Explain why a cross-fade makes an edit harder to detect than a butt splice. What acoustic evidence does the cross-fade eliminate?
>   4. Which was harder to find: the short cross-fade or the long cross-fade? Why do you think that is?

---

## Part 4: Reverberation Mismatch (8 minutes)

### Exercise 3: The Room Tells a Story

Open `edit_reverb_mismatch.wav` in Adobe Audition.

**Critical Listening — Focus on the Room**

1. Play the full recording. Pay attention not to what is being said, but to the *sound of the room*. Listen for the reverberant decay (the "tail") after each word or phrase
2. Does the reverb sound consistent throughout, or does one segment sound noticeably drier (closer, more intimate, less echoey)?
3. Note the approximate time range where the reverberation character changes

**Spectrogram Analysis**

4. Switch to spectrogram view (`Shift+D`)
5. Adjust your spectrogram settings for better visibility:
   - Right-click the spectrogram > **Spectrogram Display Settings**
   - Set FFT Size to **4096** or **8192** (larger FFT gives better frequency resolution for seeing reverb tails)
6. Look at the gaps between words and phrases. In the reverberant portions of the recording, you should see energy trailing off gradually after each speech segment (the reverb tail)
7. Find the inserted segment — it will show clean, dark gaps between words with no trailing energy
8. The contrast between "bright trailing energy after words" and "dark clean gaps after words" is the reverberation mismatch

**Document the Mismatch**

9. Zoom in so the inserted segment and some surrounding reverberant speech are both visible
10. Note the start and end timestamps of the mismatched segment

> **Turn in:**
> - **Screenshots:**
>   1. Spectrogram view showing the reverberant section with visible reverb tails after speech
>   2. Spectrogram view showing the dry inserted section (same zoom level — try to include both in one wide screenshot if possible)
> - **Word doc questions:**
>   1. At what time range (start and end timestamps) is the inserted dry segment?
>   2. Describe the visual difference between the reverberant and dry portions of the spectrogram. What specifically did you look for?
>   3. Could you hear the mismatch during playback, or did you need the spectrogram to find it? Which method (listening or visual) was more effective for this type of edit?

---

## Part 5: Background Noise Inconsistencies (7 minutes)

### Exercise 4: Listening to the Silence

Open `edit_noise_inconsistency.wav` in Adobe Audition.

**Spectrogram Analysis — Finding the Hum**

1. Switch to spectrogram view (`Shift+D`)
2. Look at the low-frequency region of the spectrogram (below 500 Hz). You should see one or more horizontal lines running through the recording — these are continuous tones from electrical equipment (60 Hz mains hum and its harmonics at 120 Hz, 180 Hz, 240 Hz, etc.)
3. Follow these horizontal lines across the full duration of the recording. Do they remain continuous and unbroken, or do they disappear at some point?
4. If the lines disappear and reappear, mark those timestamps — this indicates an edit where material from a different environment was inserted

**Noise Floor Examination**

5. Look at the overall brightness/darkness of the "quiet" portions of the spectrogram (between speech segments)
6. Is the noise floor consistent throughout, or does one section appear brighter or darker than the rest?
7. Zoom in on any region where the noise floor appears to change

**Critical Listening**

8. Play the recording with headphones at moderate volume
9. Focus on the background sounds during pauses in speech. Listen for any moment where the quality of the background noise changes (becomes quieter, louder, or changes in character)

> **Turn in:**
> - **Screenshots:**
>   1. Full spectrogram view with annotations or markers showing where the continuous tone(s) disappear
>   2. Zoomed-in spectrogram comparing the noise floor in the original section versus the inserted section
> - **Word doc questions:**
>   1. What continuous tones did you identify in the recording, and at approximately what frequencies?
>   2. At what time range do the tones disappear, indicating an edit?
>   3. Besides the tones, did you notice any other differences in the background noise between the original and inserted segments?
>   4. Why are background sounds particularly useful for detecting edits, even when the foreground speech sounds natural?

---

## Part 6: Verify with the Edit Detection Tool (4 minutes)

### Exercise 5: Automated Analysis

Pick one of the files from Exercises 1–4 where you had the hardest time finding the edit. We'll use a web-based tool to see if automated analysis can help.

1. Open the [Edit Detection Tool](https://audio-discontinuity-finder.fly.dev) in your browser
2. Upload the file you chose
3. The tool analyzes the file using six detection algorithms:
   - Waveform discontinuity detection
   - Zero-crossing rate anomaly detection
   - Spectral flux analysis
   - Short-time energy analysis
   - Phase coherence analysis
   - Background noise floor change detection
4. Examine the results:
   - Look at the **timeline markers** — each marker indicates a detected edit point
   - Check the **confidence scores** (0–100%) for each detection
   - Note which **detection method** flagged each point
5. Try adjusting the **sensitivity slider** — higher sensitivity finds more potential edits but may include more false positives
6. Compare the tool's findings with your own manual analysis from earlier

> **Turn in:**
> - **Screenshots:**
>   1. The web-based tool's results page showing detected edit points
> - **Word doc questions:**
>   1. Which file did you upload, and why did you choose it?
>   2. Did the tool correctly identify the edit? What confidence score and detection method did it report?
>   3. Did the tool flag any points that you believe are NOT edits (false positives)? If so, how would you verify?
>   4. Based on today's lab, why is combining manual analysis (Adobe Audition) with automated tools more effective than using either one alone?

---

## Submission Checklist

Use this checklist before you submit to make sure you have everything:

- [ ] Exercise 1 — 2 screenshots (waveform discontinuity, spectrogram artifact) + 3 answers
- [ ] Exercise 2 — 2 screenshots (short crossfade spectrogram, long crossfade spectrogram) + 4 answers
- [ ] Exercise 3 — 2 screenshots (reverberant section, dry inserted section) + 3 answers
- [ ] Exercise 4 — 2 screenshots (full spectrogram with tones marked, zoomed noise floor comparison) + 4 answers
- [ ] Exercise 5 — 1 screenshot (web tool results) + 4 answers

**Total: 9 screenshots and 19 written answers**

Submit your screenshot folder and Word document to D2L.

---

## Troubleshooting

**Can't see the spectrogram?**
- Make sure you're in Waveform Editor (not Multitrack)
- Press `Shift+D` to toggle spectral view
- Check that a file is actually open

**Spectrogram looks too dark or too bright?**
- Right-click the spectrogram > Spectrogram Display Settings
- Adjust the "Range" (dB) — try -120 dB to -20 dB for a good range
- Increase FFT Size to 4096 or 8192 for better frequency detail

**Can't hear subtle edits?**
- Use headphones — they reveal details that speakers miss
- Keep volume at a moderate level to avoid ear fatigue
- Try listening to the same section multiple times, focusing on different aspects each time (foreground vs. background)

**Web-based tool won't load the file?**
- Make sure the file is in a supported format (WAV, MP3, FLAC, OGG, M4A, AAC, WMA, AIFF)
- Try a different browser (Chrome or Firefox recommended)
- If the file is very large, the upload may take a moment — wait for the progress indicator

**Audio playback issues in Audition?**
- Go to Adobe Audition 2026 > Settings > Audio Hardware
- Make sure the correct audio device is selected
- Check that your headphones/speakers are connected

---

## Additional Resources

- Course textbook: Chapter 5 — Authenticity Assessment
- [Adobe Audition User Guide](https://helpx.adobe.com/audition/user-guide.html)
- [Forensic Audio Analysis Best Practices (SWGDE)](https://www.swgde.org/)

**Questions?** Bring them to the next class session or office hours.
