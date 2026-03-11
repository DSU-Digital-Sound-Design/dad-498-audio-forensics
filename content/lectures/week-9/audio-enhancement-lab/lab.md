---
title: "Lab: Audio Enhancement in Adobe Audition"
date: 2026-03-10
draft: false
---

<!--
================================================================
INSTRUCTOR PREPARATION NOTES — Not visible to students
================================================================

## Lab Goal

Build 4 short case files that match the Tuesday, March 10, 2026 lecture:
- stationary broadband noise / spectral subtraction
- clicks and pops / waveform restoration
- reverberation / dereverb
- a mixed-problem file where order of operations matters

Adobe Audition should be the primary tool. Keep all files short
(10-25 seconds) so students spend time analyzing, not waiting on exports.

## Actual File Set

You built the following package for students:

- `De-reverb/verb 1.wav`
- `De-reverb/verb 2.wav`
- `De-reverb/verb 3.wav`
- `Noise print/clip_1_noise.wav`
- `Noise print/clip_2_noise.wav`
- `Noise print/clip_3_noise.wav`
- `enhancement_combo.wav`
- `forensic_with_clicks_pops.wav`

All files should be mono WAV, 44.1 kHz or 48 kHz, 16-bit or 24-bit.

The set now has:
- 3 de-reverb files
- 3 noise-print files
- 1 click/pop restoration file
- 1 mixed-problem combo file

## Measurement Tool

Use DNSMOSPro as the required before/after scoring tool:
- repo: https://github.com/tatecarson/DNSMOSPro
- class release artifacts:
  https://github.com/tatecarson/DNSMOSPro/actions/runs/22923550404

Use it as a relative quality comparison, not as a claim that a file is
"forensically validated." Students should compare original vs processed
versions and explain when the metric agrees or disagrees with listening.

## Suggested Answer-Key Expectations

- `clip_1_noise.wav`, `clip_2_noise.wav`, `clip_3_noise.wav`: use Capture
  Noise Print, then conservative Noise Reduction (Process), then compare
  DNSMOSPro before/after
- `forensic_with_clicks_pops.wav`: Automatic Click Remover or spot healing
  first; students should justify why denoise is not the first tool
- `verb 1.wav`, `verb 2.wav`, `verb 3.wav`: mild DeReverb only, with
  explanation of limits
- `enhancement_combo.wav`: a defensible order of operations matters more
  than finding one perfect setting

================================================================
END INSTRUCTOR NOTES
================================================================
-->

## Overview

**Session Date**: Thursday, March 12, 2026  
**Duration**: ~60-75 minutes

**Objective**: Practice the advanced enhancement techniques from the Tuesday, March 10 lecture in Adobe Audition. You will repair clicks and pops, reduce steady background noise, test dereverberation, and defend your order of operations on a mixed-problem recording. You will use DNSMOSPro to compare the original and processed versions after each major step.

**Primary tools**:
- Adobe Audition
- DNSMOSPro

**What to submit:** Each exercise ends with a **Turn in** block. Submit one Word document (`.docx`) with short answers organized by exercise number, plus your processed WAV files, to the D2L assignment.

---

## Part 1: Setup and Baseline (~10 minutes)

### Exercise 1: Install DNSMOSPro and Inspect the Files

Create a folder on your desktop named `Week9_Enhancement_Lab` and copy these files into it:

- `Noise print/clip_1_noise.wav`
- `Noise print/clip_2_noise.wav`
- `Noise print/clip_3_noise.wav`
- `De-reverb/verb 1.wav`
- `De-reverb/verb 2.wav`
- `De-reverb/verb 3.wav`
- `enhancement_combo.wav`
- `forensic_with_clicks_pops.wav`

Download the DNSMOSPro release artifact that matches your operating system:

- GitHub repo: [https://github.com/tatecarson/DNSMOSPro](https://github.com/tatecarson/DNSMOSPro)
- GUI: [https://github.com/tatecarson/DNSMOSPro/actions/runs/22923550404](https://github.com/tatecarson/DNSMOSPro/actions/runs/22923550404)

Try the GUI artifact first. If it does not launch or work correctly on your machine, follow the normal Python installation and usage instructions from the DNSMOSPro GitHub repo instead.

Open DNSMOSPro and score each original file before you process anything.
Record the baseline score for all eight files.

Open each file in Adobe Audition.

For each file:
1. Listen once without making changes.
2. Switch between waveform view and spectral frequency display.
3. Identify the main problem type.
4. Decide what tool you would try first.

Use the Tuesday framework from class:
- waveform restoration first when the waveform itself is damaged
- filtering / noise reduction after obvious defects are repaired
- dynamics and normalization last

> **Turn in:**
> - **Word doc questions:**
>   1. Report the baseline DNSMOSPro score for all eight original files.
>   2. What is the primary problem category for each file or folder set?
>   3. Which file most clearly requires waveform repair before any denoising?
>   4. Which files seem most likely to benefit from a captured noise print?

---

## Part 2: Noise Print Reduction (~15 minutes)

### Exercise 2: Clean the Noise-Print Set

Open these three files:

- `clip_1_noise.wav`
- `clip_2_noise.wav`
- `clip_3_noise.wav`

For each file:
1. Find a short section that contains noise but no speech.
2. Select that region.
3. Use **Effects > Noise Reduction / Restoration > Capture Noise Print**.
4. Select the full file.
5. Open **Noise Reduction (Process)** and start conservatively.
6. Preview your settings before applying them.
7. Avoid metallic or watery artifacts.
8. Export your result as:
   - `clip_1_noise_cleaned.wav`
   - `clip_2_noise_cleaned.wav`
   - `clip_3_noise_cleaned.wav`
9. Run DNSMOSPro on each processed file and compare it with its baseline.

After processing, compare:
- original vs processed by listening
- baseline vs processed DNSMOSPro score

> **Turn in:**
> - **Word doc questions:**
>   1. For each of the three clips, what noise-only region did you use for the noise print?
>   2. What settings did you use for each file?
>   3. Report the original and processed DNSMOSPro scores for all three clips.
>   4. Which of the three files improved the most?
>   5. Did you hear any new artifacts after denoising?

---

## Part 3: Click and Pop Repair (~10 minutes)

### Exercise 3: Restore Short Transients

Open `forensic_with_clicks_pops.wav`.

1. Inspect the file in waveform view for abrupt discontinuities.
2. Switch to spectral view to look for short vertical broadband events.
3. Repair the file using one or both of these approaches:
   - **Automatic Click Remover**
   - manual spot repair / healing on isolated defects
4. Re-listen after each change.
5. Export your best version as `forensic_with_clicks_pops_repaired.wav`.
6. Run DNSMOSPro on the repaired file and compare it with the original.

Do not apply broadband denoise first unless you can justify it.

> **Turn in:**
> - **Word doc questions:**
>   1. How many obvious clicks or pops did you repair?
>   2. Which tool worked better for this file: automatic removal or manual repair?
>   3. What was the original DNSMOSPro score, and what was the repaired score?
>   4. Why is click repair usually performed before heavy noise reduction?

---

## Part 4: Dereverberation with Restraint (~10 minutes)

### Exercise 4: Test DeReverb Carefully

Open these three files:

- `verb 1.wav`
- `verb 2.wav`
- `verb 3.wav`

For each file:
1. Listen for smeared consonants and room tail.
2. Open Audition's dereverb tool and begin with conservative settings.
3. Preview carefully.
4. Apply only enough processing to improve intelligibility.
5. If the result sounds hollow, phasey, or damaged, back off.
6. Export your best version as:
   - `verb 1_dereverb.wav`
   - `verb 2_dereverb.wav`
   - `verb 3_dereverb.wav`
7. Run DNSMOSPro on each processed file and compare it with the original.

Remember: dereverb often has stronger side effects than simple filtering.

> **Turn in:**
> - **Word doc questions:**
>   1. For each verb file, what was the main audible sign of reverberation?
>   2. What settings did you use for each file?
>   3. Report the original and dereverb DNSMOSPro scores for all three files.
>   4. Which file responded best to dereverb, and which one broke down fastest when pushed too far?
>   5. Would you present your processed versions as evidence, or would you keep the originals as primary and use the processed files only as aids? Explain.

---

## Part 5: Mixed-Problem File and Order of Operations (~15 minutes)

### Exercise 5: Defend Your Workflow

Open `enhancement_combo.wav`.

Your task is not just to improve the file. Your task is to choose and defend a sensible sequence of steps.

1. Inspect the waveform and spectrogram.
2. Write down your proposed order of operations before you process anything.
3. Apply your steps one at a time.
4. Save an intermediate version after each major step.
5. Export your final version as `enhancement_combo_final.wav`.
6. Run DNSMOSPro on the original, at least one intermediate version, and the final version.

Recommended naming:
- `enhancement_combo_step1.wav`
- `enhancement_combo_step2.wav`
- `enhancement_combo_step3.wav`
- `enhancement_combo_final.wav`

> **Turn in:**
> - **Word doc questions:**
>   1. What order of operations did you choose, and why?
>   2. Report the DNSMOSPro scores for the original, one intermediate version, and the final version.
>   3. Which step produced the biggest improvement?
>   4. Which step carried the most risk of over-processing?
>   5. If you had to testify about this enhancement, what would you document in your notes?

---

## Part 6: Reflection (~5 minutes)

### Exercise 6: When Not to Process

Choose one file from today's lab and explain a limit of enhancement.

> **Turn in:**
> - **Word doc questions:**
>   1. Which Audition tool felt most reliable today, and why?
>   2. Which tool felt easiest to misuse?
>   3. Did DNSMOSPro always agree with what you heard? If not, describe one mismatch.
>   4. Give one example of a situation where a file should be processed less, not more.
