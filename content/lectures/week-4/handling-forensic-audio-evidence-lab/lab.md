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

- [forensic_speech_clean.wav](../audio/forensic_speech_clean.wav) - A clean speech recording
- [forensic_speech_clean.mp3](../audio/forensic_speech_clean.mp3) - The same recording encoded as MP3
- [forensic_background_noise.wav](../audio/forensic_background_noise.wav) - Recording with background noise
- [forensic_with_artifacts.wav](../audio/forensic_with_artifacts.wav) - Recording with audio artifacts
- [forensic_tones.wav](../audio/forensic_tones.wav) - Test tones for spectrogram analysis
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

## Wrap-Up and Reflection

### What You've Learned

- How to install and navigate Adobe Audition
- Using waveform view to identify discontinuities and artifacts
- Using spectrogram view to analyze frequency content
- Understanding the time-frequency trade-off
- The difference between lossy and lossless formats
- Basic forensic audio handling procedures

### Going Further

As you continue in this course, you'll learn:
- Advanced audio enhancement techniques
- Authentication and tampering detection
- Speaker identification
- Detailed spectral analysis techniques
- Preparing forensic reports

### Practice Tip

The best way to develop forensic audio skills is practice. Try analyzing:
- Different types of recordings (phone calls, surveillance, interviews)
- Various quality levels (high-quality vs. poor-quality recordings)
- Different acoustic environments (indoors, outdoors, vehicles)

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
- Go to Edit > Preferences > Audio Hardware
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
