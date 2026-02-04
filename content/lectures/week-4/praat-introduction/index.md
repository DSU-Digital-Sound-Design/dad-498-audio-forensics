---
title: "Introduction to Praat"
---


## Overview

**Duration:** 60 minutes  
**Objective:** Install Praat, navigate its interface, explore acoustic features of speech, and create a labeled annotation with formant measurements  
**Deliverable:** A TextGrid file with labeled phonetic segments, completed discovery questions, and a formant measurement table
**Answer sheet:** [📄 Praat Introduction — Answer Sheet](praat-intro-answer-sheet.docx) — download this now and fill it in as you go

Praat (Dutch for "talk") is free, open-source software developed by Paul Boersma and David Weenink at the University of Amsterdam. It's a standard tool in phonetics research and sees regular use in forensic speaker comparison, voice analysis, and audio authentication work. Today we're getting comfortable with the software itself—later we'll apply these skills to forensic contexts.

---

## Part 1: Installation (10 minutes)

### Download and Install

1. Go to [praat.org](https://www.praat.org)
2. Click the download link for your operating system (Mac or Windows)
3. **Mac users:** Drag the Praat application to your Applications folder
4. **Windows users:** Praat runs as a standalone executable—no installation required. Just place it somewhere you can find it (Desktop or a dedicated folder)

### Launch and Orient

Open Praat. You'll see two windows appear:

- **Praat Objects** — Your file manager and command center. All audio files, annotations, and analysis objects live here.
- **Praat Picture** — Used for creating publication-ready figures. We won't use this today so you can close it. 

---

## Part 2: Recording Your Sample (10 minutes)

We'll work with your own voice throughout this activity. This keeps things simple and gives you a personal reference point for the acoustic features we'll examine.

### Record a Short Phrase

1. In the Praat Objects window, go to **New → Record mono Sound...**
2. A recording window opens. Set your sample rate to **44100 Hz**
3. Click **Record** and speak the phrase: **"She sells seashells by the seashore"**
   - Speak at a natural pace
   - Keep consistent distance from the microphone
4. Click **Stop**, then **Save to list & Close**

Your recording now appears in the Objects list as "Sound untitled" (or similar). 

### Rename and Save

1. Select your sound in the Objects list
2. Click **Rename...** and give it something meaningful: `seashells_yourname`
3. To save: **Save → Save as WAV file...** — put it somewhere you can find it

*Why this phrase?* It contains a nice variety of phonetic material: fricatives (/s/, /ʃ/), vowels across the formant space, voiced and unvoiced segments. Good practice material.

---

## Part 3: The Editor Window (15 minutes)

### Open the Editor

With your sound selected in the Objects list, click **View & Edit**. 

A new window opens showing:
- **Waveform** (top) — amplitude over time
- **Spectrogram** (bottom) — frequency content over time

### Navigation Essentials

| Action | Method |
|--------|--------|
| Zoom in | Select a region, then click "sel" |
| Zoom out | Click "all" to see everything |
| Play selection | Select a region, press Tab |
| Play visible | Press Tab with nothing selected |
| Play cursor | Click anywhere, press Tab |

### Spectrogram Settings

Go to **Spectrogram → Spectrogram settings...**

The defaults work well for speech, but know what you're looking at:
- **View range:** 0–5000 Hz covers the critical speech frequencies (formants, most fricative energy)
- **Window length:** 0.005 seconds (5 ms) is standard for speech—balances time and frequency resolution

You can widen the view range to 8000 Hz if you want to see more fricative detail. Experiment.

### What You're Seeing

Scroll through your recording slowly. Notice:

- **Vowels** appear as dark horizontal bands (formants)—these are resonant frequencies of your vocal tract
- **Fricatives** (/s/, /ʃ/) show as high-frequency noise, a fuzzy cloud in the upper frequencies
- **/s/ vs. /ʃ/** — the "s" sound has energy concentrated higher than the "sh" sound. Can you spot this?
- **Silence/pauses** appear as blank or nearly blank vertical strips

> Listen to all consonants using this [chart](https://www.ipachart.com/) to familiarize yourself with their sounds.

### Discovery Questions

Answer these by exploring your spectrogram. You'll need to zoom in, make selections, and read values from the editor.

**Q1:** Select just the /s/ in "sells." Look at the spectrogram—where does most of the energy sit? Now select the /ʃ/ in "she." What's the approximate frequency range for each? (Hover over the spectrogram or check the selection info.)

> /s/ energy range: __________ Hz  
> /ʃ/ energy range: __________ Hz

**Q2:** Find the vowel in "sea" and the vowel in "shore." Which one shows formants (dark bands) that are closer together vertically? Which shows them more spread apart?

> Closer formants: __________  
> More spread: __________

**Q3:** Zoom in on a boundary between a fricative and a vowel (like the /ʃ/ to vowel transition in "she"). How long is the transition—instantaneous or gradual? Estimate in milliseconds.

> Transition duration: __________ ms

**Q4:** Look at the waveform for a vowel versus a fricative. How does the amplitude (height of the waveform) compare? What about the regularity of the pattern?

> Vowel amplitude/pattern: __________  
> Fricative amplitude/pattern: __________

These observations preview forensic applications: fricative characteristics and formant patterns vary between speakers, making them useful for comparison work.

---

## Part 4: Creating a TextGrid (15 minutes)

A TextGrid is Praat's annotation system—a separate object that aligns labels to time points in your audio. This is how researchers mark up speech for analysis.

### Create the TextGrid

1. Select your sound in the Objects window
2. Go to **Annotate → To TextGrid...**
3. You'll be prompted for tier names. Enter: `words phones`
4. Leave "Point tiers" blank
5. Click OK

A new TextGrid object appears in your list. Now you have two objects: your Sound and your TextGrid.

### Open Both Together

1. **Select both objects** (click the Sound, then Ctrl/Cmd-click the TextGrid)
2. Click **View & Edit**

The editor now shows your spectrogram with annotation tiers below it.

### Annotation Workflow

You'll see two empty tiers labeled "words" and "phones." Here's how to annotate:

**For interval annotation (which we're using):**
1. Click in a tier at a boundary point—where a word or sound begins/ends
2. A vertical line appears
3. Click again at the next boundary
4. Click between the boundaries and type your label

**Your task:** Label the first word "She" at both the word and phone level.

On the **words** tier:
- Mark the start and end of "She"
- Click in the interval, type: `She`

On the **phones** tier:
- Mark the start of the /ʃ/ sound (you'll see the fricative noise)
- Mark the boundary between /ʃ/ and the vowel
- Mark the end of the vowel
- Label them: `SH` and `IY` (using simple labels—formal IPA isn't required today)

**Continue through the full phrase.** Get as detailed as you have time for. At minimum, label all the words on the words tier and attempt phone-level segmentation for the first three words.

### Tips for Finding Boundaries

- Use the spectrogram: formant changes signal vowel-to-vowel transitions
- Fricatives show clear noise patterns
- Zoom in for precision—you can get boundaries accurate to a few milliseconds
- Play selections repeatedly to verify your boundary placement

---

## Part 5: Formant Measurements (10 minutes)

Now we'll extract actual acoustic data. Formant frequencies—especially F1 and F2—are key measurements in forensic speaker comparison. Different speakers produce the "same" vowel with different formant values based on their vocal tract dimensions.

### Measuring Formants

1. In the editor window, click at the **midpoint** of a vowel (the stable middle portion, away from transitions)
2. Click **Formants → Show formants** in the menu
3. Go to **Formant → Get first formant** — note the value
4. Go to **Formant → Get second formant** — note the value

### Your Measurement Task

Measure F1 and F2 for each vowel below. Click at the vowel midpoint for each measurement.

| Word | Vowel | F1 (Hz) | F2 (Hz) |
|------|-------|---------|---------|
| she | /i/ | | |
| sells | /ɛ/ | | |
| sea | /i/ | | |
| shells | /ɛ/ | | |
| shore | /ɔ/ | | |

### What to Notice

**Q5:** You measured the same vowel twice: /i/ in "she" and "sea," and /ɛ/ in "sells" and "shells." How close are your repeated measurements? Are they identical?

> Difference in "she" vs "sea" F1: __________ Hz  
> Difference in "sells" vs "shells" F1: __________ Hz

**Q6:** Compare your /i/ vowels (she, sea) to your /ɔ/ vowel (shore). Which has the lower F1? Which has the higher F2?

> Lower F1: __________  
> Higher F2: __________

This natural variation within a single speaker is something forensic examiners must account for—when comparing two recordings, they look for patterns across multiple vowels, not single measurements.

---

## Part 6: Save Your Work (5 minutes)

### What You're Submitting

Download and fill out the answer sheet, then submit it:

[📄 Praat Introduction — Answer Sheet](praat-intro-answer-sheet.docx)

The answer sheet contains:
- Discovery questions Q1–Q4
- Formant measurement table
- Reflection questions Q5–Q6

---

## Looking Ahead

Today was about getting comfortable with Praat's interface and workflow. You now know how to:

- Record and manage sound files
- Read spectrograms with speech-relevant interpretation
- Create time-aligned annotations
- Extract basic formant measurements

In upcoming sessions, we'll build on these skills for forensic applications:

- **Formant analysis in depth** — long-term distributions, vowel space plots, and speaker-characterizing patterns
- **Spectrogram analysis for authentication** — detecting edits, splices, and compression artifacts  
- **Pitch and intensity tracking** — prosodic analysis and voice stress considerations
- **Measurement protocols** — standardized approaches for forensic casework

The annotation and measurement skills you practiced today are exactly what forensic examiners use when preparing case materials and documenting their analyses.

---

## Resources

- [Praat official site and documentation](https://www.praat.org)
- [Praat User Guide](https://www.fon.hum.uva.nl/praat/manual/Intro.html) — comprehensive built-in manual (Help menu)
- Will Styler's [Praat Tutorial](http://wstyler.ucsd.edu/praat/) — excellent walkthrough aimed at linguistics students

---

*Questions? Trouble with installation or boundaries? Flag me down during lab time.*
