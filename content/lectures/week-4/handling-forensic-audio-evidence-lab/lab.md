---
title: "Lab: Introduction to Adobe Audition for Forensic Audio Analysis"
date: 2024-01-15
draft: false
---

## Overview

**Duration**: ~30 minutes
**Objective**: Learn to use Adobe Audition's essential tools for forensic audio examination: waveform view, spectrographic view, and critical listening techniques.

This lab provides hands-on practice with the concepts covered in the lecture on handling forensic audio evidence. You'll learn to identify audio artifacts, analyze spectrograms, and understand the importance of working with proper file formats.

---

## Part 1: Installing Adobe Audition (5-10 minutes)

### Installation Steps

**Access Adobe Creative Cloud**

- Go to [https://creativecloud.adobe.com/](https://creativecloud.adobe.com/)
- Click "Sign In" in the top right corner
- Select "Company or School Account"
- Enter your school email address
- Sign in with your institutional credentials

**Install Adobe Audition**

- Once logged into Creative Cloud, find "Adobe Audition" in the list of apps
- Click the "Install" button next to Adobe Audition
- Wait for the download and installation to complete (this may take 5-10 minutes depending on your connection)
- Launch Adobe Audition once installation is complete

**Initial Setup**

- When you first launch Audition, it may ask you to choose a workspace
- Select "Default" or "Edit Audio to Video" workspace
- You can always change this later via Window > Workspace

---

## Part 2: Download Lab Materials

Download the following audio files and save them to a folder on your desktop called `AudioForensicsLab`:

### Required Files

- [forensic_speech_clean.wav](/media/handling-forensic-audio-lab/forensic_speech_clean.wav) - A clean speech recording
- [forensic_speech_clean.mp3](/media/handling-forensic-audio-lab/forensic_speech_clean.mp3) - The same recording encoded as MP3
- [forensic_background_noise.wav](/media/handling-forensic-audio-lab/forensic_background_noise.wav) - Recording with background noise
- [forensic_with_artifacts.wav](/media/handling-forensic-audio-lab/forensic_with_artifacts.wav) - Recording with audio artifacts
- [forensic_tones.wav](/media/handling-forensic-audio-lab/forensic_tones.wav) - Test tones for spectrogram analysis
**Setup**: Create a folder on your desktop called `AudioForensicsLab` and save all downloaded files there.

---

## Part 3: Adobe Audition Interface Overview (3 minutes)

### Opening Your First File

1. Launch Adobe Audition
2. Go to **File > Open** (or press `Ctrl+O`)
3. Navigate to your `AudioForensicsLab` folder
4. Open `forensic_speech_clean.wav`

### Understanding the Interface

Adobe Audition has three main views for forensic work:

- **Waveform View** (time domain) - Shows amplitude over time
- **Spectral Frequency Display** (frequency domain) - Shows frequency content over time
- **Editor Panel** - Where you'll see your audio displayed

**Key Interface Elements:**

- **Top**: Menu bar 
- **Left**: Files panel (shows open files)
- **Center**: Main editor window (waveform or spectrogram)
- **Bottom**: Selection/timeline information and transport controls (play, pause, stop)
- **Right**: Properties and effects panels

---

## Part 4: Waveform Analysis (7 minutes)

### Exercise 1: Basic Waveform Navigation

With `forensic_speech_clean.wav` open, you should see the waveform display

- **Horizontal axis**: Time
- **Vertical axis**: Amplitude

**Zoom Controls**:

- **Horizontal zoom**: Use the zoom slider at the bottom, or press `=` to zoom in, `-` to zoom out
- **Vertical zoom**: Scrolling the mouse wheel
- **Fit to window**: Press `\` (backslash) to see the entire waveform

**Practice Navigation**:

- Zoom in until you can see individual samples (dots with lines connecting them)
- Zoom out to see the overall envelope of the audio

**Audio Playback**:

- Press the **Spacebar** to play/pause
- Click anywhere in the waveform to place the playhead
- Press `Home` to return to the beginning

### Exercise 2: Identifying Discontinuities

Open `forensic_with_artifacts.wav`

**Task**: Find and identify audio artifacts

- Look for abrupt changes in the waveform
- Zoom in on suspicious areas
- Click to place markers where you find artifacts

**What to Look For**:

- **Clicks**: Sharp vertical spikes
- **Dropouts**: Sudden drop to silence/zero amplitude
- **Discontinuities**: Abrupt waveform changes that don't match the surrounding audio
- **Edits**: Unnatural transitions or cuts

**Document Your Findings**:

- Write down the time locations (shown at bottom) where you find artifacts
- In real forensic work, you would document these with screenshots and detailed notes

### Exercise 3: Critical Listening

Open `forensic_background_noise.wav`

**First Listen**: Play through once focusing on the foreground (speech)
- What is being said?
- Is the speech clear and intelligible?

**Second Listen**: Play again focusing on the background
- What background sounds can you identify?
- Constant noise (HVAC, traffic)?
- Intermittent sounds (doors, other voices)?

**Practice Tip**: Use good headphones if available
 - This reduces room noise and helps you hear subtle details
 - Keep volume at a moderate level to avoid ear fatigue

---

## Part 5: Spectrographic Analysis (10 minutes)

### Exercise 4: Opening the Spectrogram View

Open `forensic_tones.wav` 

Switch to Spectral Frequency Display:
   - **View > Spectral Frequency Display** (or press `Shift+D`)
   - This shows the spectrogram

**Understanding the Spectrogram**:
   - **Horizontal axis**: Time (left to right)
   - **Vertical axis**: Frequency (Hz, low at bottom, high at top)
   - **Color/Brightness**: Signal energy (brighter = more energy)

### Exercise 5: Identifying Sounds in the Spectrogram

With `forensic_tones.wav` displayed in spectrogram view:

**Pure Tone**:
- Look for a horizontal line
- This represents a single frequency sustained over time
- Note the frequency (check the vertical axis)

**Click/Impulse**:
- Look for a vertical line
- This shows energy across all frequencies for a brief instant
- This is characteristic of transient/impulsive sounds

**Frequency Sweep**:
- Look for a diagonal line moving from low to high frequency
- This shows how frequency changes over time

### Exercise 6: Time-Frequency Trade-off

**Adjust Spectrogram Settings**:
   - Right-click in the spectrogram area
   - Select **Settings > Spectral Displays...** 

**Window Settings**:
   - Try different **FFT Size** (also called block length):
     - **Smaller FFT** (e.g., 1024): Better time resolution, worse frequency resolution
     - **Larger FFT** (e.g., 8192): Better frequency resolution, worse time resolution

**Observe the Differences**:
   - With small FFT: Clicks are sharp/vertical, but tones are blurry/wide
   - With large FFT: Tones are sharp/horizontal, but clicks are blurred in time

**Try Different Window Functions**:
   - In the same settings, try different **Window** types: Hamming, Hann, Blackman-Harris
   - Notice subtle differences in how the spectrum appears
   - For most forensic work, **Hamming** or **Hann** windows are standard

### Exercise 7: Real-World Spectrogram Analysis

Open `forensic_background_noise.wav` in spectrogram view

**Analyze the frequency content**:
   - Can you see the speech? (Usually appears as horizontal bands that change over time)
   - Can you identify background noise patterns?
     - HVAC hum: Often appears as horizontal lines at specific frequencies (60 Hz and harmonics)
     - Traffic: Broadband noise at lower frequencies
     - Other voices: Similar patterns to the main speech

**Practice Zooming**:
   - Zoom in on sections with interesting frequency content
   - Use the zoom tools to examine specific time ranges
   - Compare what you see to what you hear

---

## Part 6: Lossy vs. Lossless Formats (5 minutes)

### Exercise 8: Comparing WAV and MP3

This exercise demonstrates why we never re-encode lossy formats in forensic work.

**Open both files**:
   - `forensic_speech_clean.wav`
   - `forensic_speech_clean.mp3`

 **Visual Comparison in Waveform**:
   - Drag both into the files panel 
   - Notice: They may look similar in waveform view
   - Small differences might be visible if you zoom in very close

**Spectrogram Comparison**:
   - View both files in spectrogram mode
   - Look at the high frequency content (above 8-10 kHz)
   - **MP3 artifacts**:
     - High frequencies may be completely missing (cutoff)
     - "Shimmer" or "swoosh" artifacts in the upper frequencies
     - Less sharp definition in transients

**Listen Carefully**:
   - Play short sections of each file
   - While the MP3 may sound similar, it has permanently lost information
   - This is why we **never** edit and re-save MP3 files in forensic work

**Key Takeaway**:
   - Always work with original, uncompressed files (WAV, AIFF)
   - If you receive MP3 files, convert to WAV first, work with the WAV, but preserve the original MP3
   - Never save edited audio back to MP3 format - this creates "generation loss"

---

## Part 7: Best Practices and Documentation

### Evidence Handling Protocol

Even in this practice lab, get in the habit of proper forensic procedures:

**Never Edit Originals**:
   - In Audition: File > Save As and create a working copy
   - Always preserve the original file unchanged

**Document Everything**:
   - Create a text file or lab notebook
   - Note the time and location of any interesting findings
   - In real forensic work, include screenshots

**Use Moderate Volume Levels**:
   - Avoid the temptation to turn volume up very high
   - This can cause ear fatigue (acoustic reflex) and make you less sensitive
   - Take breaks if listening for extended periods

**Systematic Approach**:
   - Listen to the full recording first (overview)
   - Then analyze in detail (zoom in)
   - Alternate between visual (waveform/spectrogram) and aural analysis

---

## Assessment — What to Turn In

Submit **two** items before the next class:

1. **A folder of screenshots** — one or more per exercise, as described below
2. **A Word document (.docx)** — answers to the questions listed below, organized by exercise number

> **Screenshot tips:** Capture the full Adobe Audition window so the file name, view mode (waveform/spectrogram), and any markers or zoom level are visible. Label each screenshot with the exercise number and a short description (e.g., `Ex2_artifact_at_3.4s.png`).

---

### Exercise 1 — Basic Waveform Navigation

**Screenshots:**
- One screenshot zoomed in far enough to see individual samples
- One screenshot zoomed out showing the full waveform envelope

**Word document questions:**
1. What does the vertical axis represent in waveform view, and what unit is it measured in?
2. Describe what changed visually as you zoomed from the full envelope down to individual samples.

---

### Exercise 2 — Identifying Discontinuities

**Screenshots:**
- At least **two** screenshots zoomed in on artifacts you identified, with the playhead or marker placed at the artifact location

**Word document questions:**
1. How many artifacts did you find, and at what time positions (timestamps) are they located?
2. Classify each artifact you found (click, dropout, discontinuity, or edit). Explain how the waveform shape told you which type it was.

---

### Exercise 3 — Critical Listening

**Screenshots:**
- Not required for this exercise

**Word document questions:**
1. Find a 30 second section with speech. What is being said in the recording? Transcribe as much as you can.
2. Describe the background sounds you identified. Are they constant or intermittent? Give specific examples.

---

### Exercise 4 — Opening the Spectrogram View

**Screenshots:**
- One screenshot of `forensic_tones.wav` displayed in spectrogram view

**Word document questions:**
1. What do the three axes (horizontal, vertical, and color/brightness) represent in a spectrogram?

---

### Exercise 5 — Identifying Sounds in the Spectrogram

**Screenshots:**
- One screenshot for each of the three sound types you identified: the pure tone, the click/impulse, and the frequency sweep. Annotate or label each one.

**Word document questions:**
1. At what frequency does the pure tone appear? How did you determine this?
2. Explain why a click/impulse appears as a vertical line in the spectrogram.
3. Describe the shape of the frequency sweep and the direction it moves.

---

### Exercise 6 — Time-Frequency Trade-off

**Screenshots:**
- One screenshot with a **small** FFT size (e.g., 1024)
- One screenshot with a **large** FFT size (e.g., 8192)

**Word document questions:**
1. How did the appearance of the clicks change between the small and large FFT sizes?
2. How did the appearance of the tones change?
3. In your own words, explain the time-frequency trade-off. Why can't you get perfect resolution in both dimensions at the same time?

---

### Exercise 7 — Real-World Spectrogram Analysis

**Screenshots:**
- One screenshot of `forensic_background_noise.wav` in spectrogram view, zoomed into a region where you can clearly see both speech and background noise

**Word document questions:**
1. Describe how the speech appears in the spectrogram. What visual pattern does it form?
2. Identify at least one background noise source visible in the spectrogram. At what frequencies does it appear, and is it constant or intermittent?

---

### Exercise 8 — Comparing WAV and MP3

**Screenshots:**
- One side-by-side or paired screenshot of the **waveform** view for both `forensic_speech_clean.wav` and `forensic_speech_clean.mp3`
- One side-by-side or paired screenshot of the **spectrogram** view for both files, zoomed into the high-frequency region (above 8 kHz)

**Word document questions:**
1. What differences, if any, did you notice in the waveform view between the WAV and MP3 files?
2. What did you observe in the high-frequency region of the spectrogram for the MP3 file? Describe any artifacts or missing content.
3. Why is re-encoding an MP3 a problem in forensic audio work?

---

## Troubleshooting

**Adobe Audition won't launch?**
- Make sure you're signed into Creative Cloud
- Check that your school account is active
- Try signing out and back in to Creative Cloud

**Can't see the spectrogram?**
- Make sure you're in Waveform Editor (not Multitrack)
- Press `Shift+D` to toggle spectral view
- Check that a file is actually open

**Audio playback issues?**
- Go to Adobe Audition 2026 > Settings > Audio Hardware
- Make sure the correct audio device is selected
- Check that your headphones/speakers are connected

**Files won't open?**
- Make sure files are in a supported format (WAV, MP3, AIFF)
- Check that files aren't corrupted
- Try dragging the file directly into Audition's interface

---

## Additional Resources

- [Adobe Audition User Guide](https://helpx.adobe.com/audition/user-guide.html)
- [Forensic Audio Analysis Best Practices (SWGDE)](https://www.swgde.org/)
- Course textbook: Chapter 4 - Handling Forensic Evidence

**Questions?** Bring them to the next class session or office hours.
