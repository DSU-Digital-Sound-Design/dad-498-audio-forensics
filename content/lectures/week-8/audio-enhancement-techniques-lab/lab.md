---
title: "Workshop: Audio Enhancement with STI Validation"
date: 2026-03-05
draft: false
---

<!--
================================================================
INSTRUCTOR PREPARATION NOTES — Not visible to students
================================================================

Goal: Provide three unknown clips that students must classify as
high/mid/low baseline STI, then improve with EQ + compression/expansion.

Use one clean speech source (10-30 seconds) and create three files:
- clip_1_unknown.wav
- clip_2_unknown.wav
- clip_3_unknown.wav

All files should be mono WAV, 44.1 kHz (or 48 kHz), 16-bit or 24-bit.
Keep all clips similar loudness before exporting so students focus on
intelligibility, not obvious level differences.

Important: Only introduce issues that are realistically addressable with
highpass/lowpass/notch/EQ and compression/expansion/gating. Avoid heavy
reverb, clipping distortion, or nonlinear artifacts requiring AI denoise.

### Recommended Build Recipe

Start with a clean baseline clip from OpenSLR 12:
https://www.openslr.org/12/

1) High-STI clip (minimal processing needed)
- Keep mostly clean.
- Optional: add very light low-frequency rumble around -40 to -45 dB
  (below ~80 Hz) so a gentle highpass can improve slightly.
- Target: already clearly intelligible; likely needs little/no work.

2) Mid-STI clip (moderate processing needed)
- Add low-frequency hum + harmonics:
  - 60 Hz at about -34 to -38 dB
  - 120 Hz at about -38 to -42 dB
  - 180 Hz at about -42 to -46 dB
- Add mild broadband hiss around -42 to -46 dB.
- Add small level swings (about +/-4 dB over phrases) so moderate
  compression helps stabilize audibility.
- Target: intelligible but distracted by hum/hiss and uneven level.

3) Low-STI clip (careful iterative processing needed)
- Add stronger hum + harmonics:
  - 60 Hz at about -28 to -34 dB
  - 120 Hz at about -32 to -38 dB
  - 180 Hz at about -36 to -42 dB
  - optional 240 Hz very light
- Add stronger hiss around -36 to -40 dB.
- Apply a broad low-mid masking bump around 250-500 Hz (+3 to +6 dB)
  to muddy consonant contrast.
- Increase dynamic range problem:
  - quiet sections too quiet and loud words too loud
  - then fixable with moderate compression + gentle expansion/gating.
- Target: clearly degraded but still recoverable with EQ + dynamics.

### Randomization and Student Prompt Design

- Randomize which file is high/mid/low before class.
- Do not reveal which unknown file maps to which condition.
- Ask students to classify by baseline STI + listening before processing.

### Suggested Answer Key (for instructor use only)

Maintain a private mapping table, e.g.:
- clip_1_unknown.wav -> [High or Mid or Low]
- clip_2_unknown.wav -> [High or Mid or Low]
- clip_3_unknown.wav -> [High or Mid or Low]

================================================================
END INSTRUCTOR NOTES
================================================================
-->

## Overview

**Session Date**: Thursday, March 5, 2026  
**Duration**: ~75 minutes

**Objective**: Classify three instructor-provided unknown speech clips by baseline intelligibility level, then use forensic EQ/filtering and dynamics processing in Adobe Audition with FSTIC STI validation. Students will practice the lecture rule: enhancement decisions must be based on intelligibility metrics, not just perceived quality.

**Primary tools**:
- Adobe Audition
- FSTIC (adapted STI tool): [https://github.com/tatecarson/FSTIC](https://github.com/tatecarson/FSTIC)
<!-- - Source context (instructor prep): [OpenSLR 12 - LibriSpeech dev-clean](https://www.openslr.org/12/) -->

**What to submit:** Each exercise ends with a **Turn in** block. Submit one Word document (`.docx`) with short answers organized by exercise number. No screenshots are required.

---

## Part 1: Setup and Baseline (~15 minutes)

### Exercise 1: Build Your 3-Clip Case Set and Baseline STI

1. Create a folder on your desktop named `Week8_STI_Workshop`.
2. Download the three instructor-provided files and place them in your folder:
   - `clip_1_unknown.wav`
   - `clip_2_unknown.wav`
   - `clip_3_unknown.wav`
3. Run FSTIC (Single File mode) on all three clips and record baseline STI values.
4. Listen to each clip in Audition and note key audible issues.
5. Classify each clip as probable **high**, **mid**, or **low** baseline intelligibility.
6. Assign working labels for your workflow:
   - `clip_A_high.wav`
   - `clip_B_mid.wav`
   - `clip_C_low.wav`

**Target setup for this workshop:**
- Clip A: already intelligible (high STI) -> minimal or no processing justified
- Clip B: somewhat degraded (mid STI) -> moderate processing
- Clip C: clearly degraded (low STI) -> careful iterative processing

> **Turn in:**
> - **Word doc questions:**
>   1. Report baseline STI for A, B, and C.
>   2. Why did you classify A as high, B as mid, and C as low?
>   3. For each clip, list 1-2 audible problems.

---

## Part 2: EQ and Filtering with STI Checks (~25 minutes)

### Exercise 2: Build an Iterative Filter Chain

Create processed versions incrementally for **clips B and C**. After each step, export a new WAV and run FSTIC.

1. **Highpass step**
   - Apply a highpass filter (start around 120-200 Hz).
   - Export as `clip_B_hp.wav` and `clip_C_hp.wav`.
   - Run FSTIC and log STI.
2. **Notch step**
   - Identify any tonal interference (for example, around 60 Hz and harmonics).
   - Apply narrow notch filter(s) with conservative Q.
   - Export as `clip_B_hp_notch.wav` and `clip_C_hp_notch.wav`.
   - Run FSTIC and log STI.
3. **Band-limit / lowpass step**
   - If needed, apply gentle top-end control (avoid removing speech-critical consonant detail).
   - Export as `clip_B_hp_notch_lp.wav` and `clip_C_hp_notch_lp.wav`.
   - Run FSTIC and log STI.
4. **Consonant presence step**
   - Apply a modest presence boost in the speech-critical range (for example 1-4 kHz).
   - Export as `clip_B_eq_final.wav` and `clip_C_eq_final.wav`.
   - Run FSTIC and log STI.

If STI drops after any step, revert that step and note why.

For `clip_A_high.wav`, do a quick verification pass only. If baseline STI is already high, justify minimal/no EQ processing.

> **Turn in:**
> - **Word doc questions:**
>   1. Fill this table for B:
>
>      | File | Processing Step | STI |
>      |------|------------------|-----|
>      | clip_B_mid.wav | Baseline | |
>      | clip_B_hp.wav | Highpass | |
>      | clip_B_hp_notch.wav | + Notch | |
>      | clip_B_hp_notch_lp.wav | + Lowpass/Band-limit | |
>      | clip_B_eq_final.wav | + Presence boost | |
>
>   2. Fill the same table for C (rename with `clip_C_*` files).
>   3. Which step produced the largest STI gain for B and for C?
>   4. Did any step make a clip sound cleaner but reduce STI?
>   5. For A, explain why minimal/no processing was appropriate.

---

## Part 3: Compression and Expansion with STI Checks (~20 minutes)

### Exercise 3: Dynamics Processing Without Over-Processing

Use `clip_B_eq_final.wav` and `clip_C_eq_final.wav` as inputs for this part.

1. **Moderate compression**
   - Start with conservative settings (for example ratio 2:1-4:1).
   - Tune threshold, attack, and release to avoid pumping and transient damage.
   - Export as `clip_B_comp.wav` and `clip_C_comp.wav`.
   - Run FSTIC and log STI.
2. **Expansion or noise gate (optional but recommended)**
   - Apply gentle downward expansion or gate to reduce between-word noise.
   - Verify onsets are not clipped.
   - Export as `clip_B_comp_expand.wav` and `clip_C_comp_expand.wav`.
   - Run FSTIC and log STI.
3. Compare all versions in FSTIC Compare mode:
   - `clip_B_eq_final.wav` vs `clip_B_comp.wav`
   - `clip_B_comp.wav` vs `clip_B_comp_expand.wav`
   - `clip_C_eq_final.wav` vs `clip_C_comp.wav`
   - `clip_C_comp.wav` vs `clip_C_comp_expand.wav`

If pumping, chopped consonants, or STI degradation appears, back off settings.

> **Turn in:**
> - **Word doc questions:**
>   1. Report final dynamics settings (threshold, ratio, attack, release, and gate threshold if used).
>   2. Did dynamics processing improve STI for B and C relative to each `*_eq_final.wav` file?
>   3. What artifact checks did you perform (pumping, onset clipping, noise surges)?

---

## Part 4: Decision and Defensibility (~15 minutes)

### Exercise 4: Pick the Court-Defensible Version

1. Review your STI results across all versions.
2. Choose:
   - one final version for A (likely unchanged or minimally changed),
   - one final version for B,
   - one final version for C.
3. Keep each original clip available as the unenhanced original.
4. Write a short forensic justification for each clip based on:
   - Measured STI trend
   - Processing transparency (what was changed)
   - Any trade-offs observed (quality vs intelligibility)

> **Turn in:**
> - **Word doc questions:**
>   1. Which final file did you select for A, B, and C, and why?
>   2. Provide a 3-4 sentence defensibility statement for each clip using STI evidence.
>   3. For A, did STI evidence support doing little or no processing?
>   4. Would you submit any processed version that lowered STI even if it sounded cleaner? Explain.

---

## Quick Rubric (Instructor)

- Correct use of iterative workflow (stepwise exports + STI after each step)
- Appropriate, documented EQ/filter and dynamics settings
- Evidence of rollback when STI worsens
- Final selection justified with objective intelligibility evidence

---

## FSTIC Student Launch (Reference)

From the FSTIC repo folder:

```bash
./setup_student.command
./launch_student.command
```

Fallback:

```bash
./launch_notebook.command
```

Use FSTIC modes:
- **Single File** for per-step STI logging
- **Compare Two Files** for before/after decisions
