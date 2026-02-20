---
title: "Midterm: Operation Blind Spot"
date: 2026-02-20
draft: true
---

<!--
================================================================
INSTRUCTOR NOTES — Not visible to students
================================================================

## Overview

Two teams of 4. Each team both creates evidence AND analyzes
the other team's evidence:

- TUESDAY: Both teams fabricate a fake audio case
- THURSDAY: Teams swap; each analyzes the other's package
- After reports are submitted on Thursday, reveal answer keys
  and run the class debrief.

## Tuesday Logistics

Reserve ~75 minutes:
- 5 min: Team assignments, overview, questions
- 60 min: Fabrication work time
- 10 min: Package assembly + answer key submission to instructor

Teams should NOT share what they're doing with the other team.
If the classroom allows it, seat teams on opposite sides.

Answer keys go to you only (e-mail, D2L dropbox, or paper).
Do not show them to the opposing team until after Thursday's
report is submitted.

## Thursday Logistics

Reserve ~75 minutes:
- 5 min: Distribute packages, answer questions
- 55 min: Analysis work time
- 10 min: Save screenshots, finalize and submit report
- (Debrief in remaining time, or beginning of following class
  if time runs short)

## Grading Summary

Each team receives two grades:

FABRICATION (30 pts):
  - Required edit technique applied correctly:     10 pts
  - Required authentication element included:      10 pts
  - Case Brief is plausible + not priming:          5 pts
  - Answer key submitted, accurate, detailed:       5 pts

ANALYSIS REPORT (70 pts):
  - Aural evaluation documented:                   5 pts
  - Waveform analysis + screenshots:              10 pts
  - Spectrogram analysis + screenshots:           10 pts
  - Edit detection findings:                      15 pts
  - Metadata examination:                         10 pts
  - ENF analysis or reasoned alternative:         10 pts
  - Executive summary with determination:         10 pts

## openENF Contingency

Students who could not get openENF working may satisfy the
ENF component by writing a detailed explanation of:
  - What ENF analysis would involve for this file
  - What result they would expect and why
  - What evidence (if any) in the scenario supports or
    contradicts the stated recording conditions

This tests conceptual understanding without penalizing
installation failures.

## Optional: Difficulty Incentive

Tell teams that part of their fabrication grade depends on
how convincing their forgery is — if the opposing team misses
all of their edits, they score full marks on concealment.
This encourages more sophisticated forgeries and more careful
analysis. Use your judgment based on class skill level.

## Optional: Authentic Recording Red Herring

If one team is confident, allow them to submit a genuinely
authentic recording with a misleading (but plausible) scenario.
The analysis team must correctly conclude "authentic" — this
tests methodological restraint and avoidance of confirmation bias.
This team should note in their answer key: "No manipulations —
authentic recording."

================================================================
END INSTRUCTOR NOTES
================================================================
-->

## Overview

The midterm for this course is an adversarial simulation. You will work in two teams: each team builds a fake audio evidence package on Tuesday and analyzes the other team's package on Thursday.

By the end of Thursday you will have played both roles that define real forensic audio work — attacker and defender. The goal is not just to detect forgeries, but to understand how and why they are made.

**Teams are assigned by the instructor and posted before Tuesday's class.**

---

## What You Are Being Graded On

You receive **two separate grades** for this midterm:

| Role | Weight | When |
|---|---|---|
| Fabrication (building the fake case) | 30 pts | Assessed after Thursday via your Answer Key |
| Analysis (forensic report on the other team's case) | 70 pts | Assessed from your submitted report |

---

## Tuesday: Building the Fake Case (75 min)

Your team fabricates a realistic-sounding fake audio evidence package. The other team will try to detect your forgeries on Thursday — your job is to make it as convincing as possible.

### Step 1 — Record or Assemble Source Audio

You need a base audio recording of at least **2–3 minutes** of continuous speech or ambient sound. You have three options:

- **Record it now** in or near the classroom (hallway, bathroom, stairwell for reverb; treated closet or carpeted space for dry audio)
- **Use a public-domain recording** from [LibriVox](https://librivox.org) or [Open Speech Repository](https://openslr.org) (download as WAV)

Save your source material as a **44.1 kHz, 16-bit, mono WAV** file before doing anything else.

### Step 2 — Apply Required Manipulations

You must apply at least one technique from each category below.

**Edit Technique (choose ≥ 1):**

| Technique | What to Do | Key Artifact |
|---|---|---|
| Butt splice | Cut and rejoin two segments with zero crossfade | Click + waveform discontinuity |
| Crossfade edit | Delete a segment with a 5–100 ms crossfade | Subtle spectral smearing |
| Reverb mismatch | Insert a dry segment into a reverberant recording | Missing reverb tails in spectrogram |
| Noise floor inconsistency | Insert a segment with different background noise (missing 60 Hz hum, different noise level) | Broken horizontal lines in low-frequency spectrogram |

**Authentication Element (choose ≥ 1):**

| Technique | What to Do |
|---|---|
| Metadata manipulation | After saving, open the file in ImHex and alter the timestamp, device info, or sample rate field in the file header. Alternatively, re-encode the file to a different format and back to create inconsistent codec history. |
| ENF-based claim | Write a scenario that makes a specific claim about *when or where* the recording was made (e.g., "recorded indoors in the evening on Feb 24"). The analysis team will attempt ENF extraction or metadata inspection to verify the claim. |

> **Aim to conceal your edits.** The more convincing your forgery, the better your fabrication grade.

### Step 3 — Write the Case Brief

Write a **one-page Case Brief** that the opposing team will receive on Thursday. The brief must:

- State **who** allegedly made the recording and **who** is named in it
- State **when** the recording was allegedly made (specific date and approximate time)
- State **where** the recording was allegedly made (indoor/outdoor, general location)
- State **what** the recording allegedly proves — the legal or factual claim it supports (e.g., an alibi, a threat, a confession, a timestamped presence at a location)

> **Bias warning:** The Case Brief must *not* tell the analysis team what to listen for, describe the audio contents in detail, or suggest what conclusions they should reach. Give them context without priming. Follow the same principles discussed in Week 3 (LSU — Linear Sequential Unmasking). If your brief would make an unprimed analyst more likely to reach a particular conclusion before doing any technical analysis, revise it.

**Good example:**
> *"This 3-minute WAV file was submitted as alibi evidence in a civil dispute. The recording was allegedly made indoors at the subject's home on the evening of February 24, 2026. The submitting party claims the recording demonstrates continuous presence at that location."*

**Bad example (biased — do not do this):**
> *"This recording sounds a little funny around the 1:20 mark. We think it was spliced to remove something. There's also something weird in the metadata."*

### Step 4 — Assemble the Evidence Package

Create a folder called `Team_[A or B]_Evidence` containing:

- [ ] `recording.wav` — your manipulated audio file
- [ ] `case_brief.pdf` or `case_brief.docx` — your one-page Case Brief
- [ ] `chain_of_custody.docx` — filled out (template below)

Submit this folder to the instructor. **Do not share it with the other team yet** — they receive it Thursday morning.

### Step 5 — Submit Your Answer Key (to instructor only)

In a **separate document** (not shared with the other team), record:

- Every manipulation you applied, with exact timestamps
- How you attempted to conceal each manipulation
- Whether the correct authenticity determination is "authentic," "not authentic," or "could be either" (if you used the red herring approach)

Submit the Answer Key directly to the instructor via D2L or e-mail before leaving Tuesday's class.

---

## Thursday: Forensic Analysis (75 min)

You receive the opposing team's evidence package at the start of class. Your task is to conduct a systematic forensic examination and submit a formal report by the end of class.

### Your Job

Analyze the package as a **neutral forensic examiner** — not as an advocate for any position. Follow the methods from Weeks 4–6. Your report must be grounded in technical evidence, not intuition.

### Required Analysis Methods

You must demonstrate at least one method from each of the following categories. If a method produces no findings, document that as well — a negative finding is a valid forensic result.

**1. Aural Evaluation**

- Listen to the full recording once in quiet conditions at moderate level
- Note preliminary impressions (foreground sounds, background environment, overall quality)
- Avoid looping sections before completing the full listen — this can create false percepts

**2. Waveform Analysis (Adobe Audition)**

- View the full waveform and look for visible discontinuities, amplitude jumps, or level inconsistencies
- Zoom in on any suspicious areas to the sample level

**3. Spectrogram Analysis (Adobe Audition)**

- Switch to Spectral Frequency Display (`Shift+D`)
- Look for: vertical broadband artifacts (edit points), missing reverb tails, broken horizontal lines in the low-frequency range, noise floor changes
- Use FFT Size 4096 or 8192 for better frequency detail on subtle artifacts

**4. Edit Detection**

- Based on your waveform and spectrogram findings, identify any candidate edit locations
- Document each with a timestamp, the method that revealed it, and your confidence level (high / medium / low)
- Note the type of edit (butt splice, crossfade, reverb mismatch, noise inconsistency) if determinable

**5. Metadata Examination (ImHex)**

- Open the WAV file in ImHex
- Inspect the file header: sample rate, bit depth, format tag, any embedded timestamp or device info
- Note anything that is inconsistent with the stated recording conditions in the Case Brief

**6. ENF Analysis (openENF)**

Run the ENF analysis or write a reasoned explanation:

*If openENF is working:*
- Run: `enf recording.wav --grids GB DE --start 2025-01-01 --end 2026-12-31`
- Report the match score, estimated timestamp, and grid identified (or "no match found")
- Compare to the scenario's claimed date and location

*If openENF is not working on your machine:*
- Write a paragraph explaining: (a) what ENF analysis would involve for this file, (b) what result you would expect based on the scenario's claims, and (c) what recording conditions would need to be true for ENF to be detectable

### Forensic Report Format

Submit a single Word document (`.docx`) structured as follows:

---

**FORENSIC AUDIO EXAMINATION REPORT**

**Case Reference:** [receiving team name] — Midterm Examination
**Examiner(s):** [your team names]
**Date of Examination:** February 26, 2026
**Evidence Received:** [file name, format, duration, chain of custody notes]

---

**1. Executive Summary**

One paragraph. State your authenticity determination (authentic / not authentic / inconclusive), your confidence level, and the primary technical basis for your conclusion. Write this section *last* — after completing all analysis.

---

**2. Evidence Received**

- File name and format
- Duration
- Sample rate and bit depth (from ImHex header examination)
- Chain of custody: how the file was received, any handling notes

---

**3. Methods Used**

Brief list of tools and techniques applied (e.g., "Adobe Audition waveform/spectrogram analysis, ImHex metadata examination, openENF analysis").

---

**4. Findings**

Organized by analysis type. Include screenshots annotated with timestamps or arrows where relevant.

**4a. Aural Evaluation**
What you heard. Note any preliminary indicators, foreground/background sounds, quality assessments.

**4b. Waveform Analysis**
Document any findings. Screenshot waveform at relevant points.

**4c. Spectrogram Analysis**
Document any findings. Screenshot spectrogram at relevant points.

**4d. Edit Detection**
List each candidate edit location with timestamp, detection method, type, and confidence.

**4e. Metadata Examination**
Report header values and note any inconsistencies with the Case Brief.

**4f. ENF Analysis**
Report openENF results, or write the conceptual analysis paragraph.

---

**5. Opinion**

A supported statement of your authenticity determination. Cite the specific findings from Section 4 that support your conclusion. Do not introduce new evidence here.

---

**Appendix: Screenshots**

Number all screenshots and reference them from the Findings section (e.g., "Fig. 1").

---

> **Bias reminder:** Do not write conclusions before completing the technical analysis. Do not let the scenario's claims substitute for evidence. Mark any content you cannot understand as `[Inaudible]` rather than guessing. You are educating the court, not advocating for a position.

---

## Post-Class Debrief

After reports are submitted, the instructor will reveal each team's Answer Key. Each fabrication team will walk the class through what they embedded and how they tried to conceal it. Then the analysis teams share what they found versus what was actually there.

This is worth paying attention to — understanding the attacker's perspective is one of the fastest ways to improve as a forensic examiner.

---

## Submission Checklist

**Tuesday (before leaving class):**

- [ ] `Team_[A or B]_Evidence` folder submitted to instructor
  - [ ] `recording.wav`
  - [ ] `case_brief.pdf` or `case_brief.docx`
  - [ ] `chain_of_custody.docx`
- [ ] Answer Key submitted to instructor separately (not in the evidence folder)

**Thursday (before leaving class):**

- [ ] Forensic report `.docx` submitted to D2L

---

## Chain of Custody Template

Copy and fill out for your evidence package:

---

**CHAIN OF CUSTODY FORM**

| Field | Value |
|---|---|
| File name | |
| File format | |
| File size | |
| MD5 or SHA-256 hash (if generated) | |
| Date and time of creation | |
| Created by (team name) | |
| Storage location (e.g., USB drive, OneDrive folder) | |
| Transferred to instructor on | |
| Transferred to analysis team on | |
| Notes | |

*Signature (fabrication team lead):* __________________________ *Date:* __________

*Received by (instructor):* __________________________ *Date:* __________

---

## Grading Rubric

### Fabrication (30 pts)

| Criterion | Points |
|---|---|
| At least one required edit technique applied and documentable | 10 |
| At least one required authentication element included | 10 |
| Case Brief is plausible, complete, and follows LSU principles (no priming) | 5 |
| Answer Key submitted, accurate, and detailed enough to grade analysis | 5 |

### Forensic Report (70 pts)

| Criterion | Points |
|---|---|
| Aural evaluation documented | 5 |
| Waveform analysis with screenshots | 10 |
| Spectrogram analysis with screenshots | 10 |
| Edit detection findings (correct identification or correctly-stated negative) | 15 |
| Metadata examination | 10 |
| ENF analysis or reasoned conceptual explanation | 10 |
| Executive summary with supported authenticity determination | 10 |

---

## Resources

- [Adobe Audition User Guide](https://helpx.adobe.com/audition/user-guide.html)
- Week 3 slides — Ethics and bias avoidance, LSU protocol
- Week 5 slides + lab — Edit detection techniques
- Week 6 slides + lab — ENF analysis and metadata

**Questions about the midterm format?** Ask before Tuesday's class.
