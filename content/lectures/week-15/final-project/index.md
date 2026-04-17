---
title: "Final Project: Operation Deep Cut"
date: 2026-04-16T00:00:00.000Z
draft: false
---
<!--
========
INSTRUCTOR NOTES — Not visible to students
========

## Overview

Two teams of 4. Each team picks a scenario type (shooting or CVR) and builds
an evidence package over two class days, then swaps and analyzes the other
team's case independently over the next two class days. Final exam day is
presentations.

The scenario types are intentionally different — if Team A builds a shooting
case, they receive and analyze Team B's CVR case, and vice versa.

## Week 15 Logistics

TUESDAY (4/21) — Day 1: Research + Planning:
- 5 min: Assign teams, explain scenario choice, answer questions
- 10 min: Teams choose scenario type (shooting or CVR), confirm no overlap
  (if both pick the same, negotiate or assign)
- 55 min: Research real cases in their scenario type; begin scenario planning
- 5 min: Check-in — each team states real case(s) they found useful and
  one sentence on their scenario plan

THURSDAY (4/23) — Day 2: Build + Submit:
- 5 min: Recap requirements, answer questions
- 60 min: Record/assemble audio, apply manipulations (shooting) or
  degradation (CVR), complete case brief
- 10 min: Package assembly + answer key submission to instructor
  - Evidence folder goes to D2L
  - Answer key goes to you separately — do NOT share with opposing team

Do NOT let teams see each other's work or case briefs before the swap.
Answer keys go to you only until after analysis reports are submitted.

## Week 16 Logistics

TUESDAY (4/28) — Case Exchange + Analysis Day 1:
- 5 min: Distribute opposing team's evidence package
- 65 min: Independent analysis work time
  - Emphasize: NO consulting teammates yet
  - Each student works alone on their own copy of the file(s)
- 5 min: Check-in — each student states one finding so far (no collaboration)

THURSDAY (4/30) — Analysis Day 2 + Comparison:
- 55 min: Finish independent analysis; each student submits individual report
  to D2L before team discussion begins
- 15 min: Team comparison meeting — compare findings, draft Examiner
  Comparison Memo
- 5 min: Submit Examiner Comparison Memo to D2L

## Grading Summary

FABRICATION — SHOOTING TEAM (25 pts — team grade):
  - Required edit technique applied and documentable:           8 pts
  - Required authentication element included:                   7 pts
  - Multi-source recordings + authentic/fabricated distinction: 5 pts
  - Case brief plausible, complete, follows LSU principles:     3 pts
  - Answer key submitted, accurate, detailed:                   2 pts

FABRICATION — CVR TEAM (25 pts — team grade):
  - Cockpit dialogue is realistic and scenario is plausible:    8 pts
  - Degradation is sufficient to require enhancement but
    solvable through standard techniques:                       7 pts
  - Duration, recording quality, and incident plausibility:     5 pts
  - Case brief plausible, complete, follows LSU principles:     3 pts
  - Answer key submitted, accurate, detailed:                   2 pts

INDIVIDUAL ANALYSIS REPORT (40 pts — individual grade):
  - Aural evaluation documented:                                3 pts
  - Waveform analysis with screenshots:                         5 pts
  - Spectrogram analysis with screenshots:                      5 pts
  - Edit detection findings (or documented negative finding):   8 pts
  - Metadata examination:                                       5 pts
  - ENF analysis or reasoned explanation:                       4 pts
  - Domain-specific analysis:                                   7 pts
  - Executive summary with supported determination:             3 pts

PRESENTATION (35 pts — team grade):
  - Case building walkthrough:                                 10 pts
  - Analysis findings:                                         10 pts
  - Inter-examiner comparison:                                 10 pts
  - Clarity and organization:                                   5 pts

## Optional: Difficulty Incentive

Shooting teams only — tell them that part of their fabrication grade depends
on how convincing their forgery is. If the opposing team misses all edits,
full marks on concealment.

========
END INSTRUCTOR NOTES
========
-->

## Overview

The final project is a full-semester capstone simulation. You will work in two teams: each team builds an audio evidence package over two class days, then receives and analyzes the opposing team's package over the following two days. On final exam day, both teams present — walking through what they built, what they found, and how your individual examiners compared.

You play both roles: case builder and forensic analyst.

---

## Grading

| Component | Weight | Grade Type |
|---|---|---|
| Case Building | 25 pts | Team |
| Individual Analysis Report | 40 pts | Individual |
| Presentation | 35 pts | Team |

---

## Choosing Your Scenario Type

At the start of Week 15, each team chooses one scenario type. The two teams must choose **different types**.

| Type | What You Build |
|---|---|
| **Shooting Incident** | Multi-source recordings of a shooting event — some authentic, some fabricated — plus a scenario claim about location, distance, or shot count |
| **CVR Incident** | Degraded cockpit-style dialogue recording and a scenario claim about what was said or when — no fabricated edits required |

You will **not** analyze the same type you built — you receive the opposing team's case on Week 16 Tuesday.

---

## Week 15: Case Building (Two Days)

### Day 1: Research Your Scenario (Before You Build Anything)

Before recording or editing anything, spend the first part of Tuesday researching real cases in your scenario type. Your case brief and choices must be grounded in how these incidents actually unfold — not invented from scratch.

**Shooting teams** should research real shooting incident investigations, paying attention to:
- How multi-source recordings are collected (smartphones, body cameras, security cameras)
- What acoustic signatures are actually present and how they vary with distance and environment
- How investigators establish shot count, location, and sequence
- Example: the [Maher investigation of the Trump rally assassination attempt](../../week-13/trump-rally-case-study-lab/lab) from Week 13

**CVR teams** should research real CVR investigations, paying attention to:
- What kinds of audio degradation are present in real CVR recordings
- How transcription disputes arise and what makes them difficult to resolve
- What specific claims (about timing, wording, crew state) are typically contested
- Example: the [Southern Airways Flight 932 CVR investigation](../../week-14/southern-airways-cvr-lab/lab) from Week 14

> Your goal is plausibility. A case brief or scenario that couldn't happen in the real world will be easy to dismiss. Research first, build second.

**Check-in at end of Day 1:** each team gives a one-sentence summary of the real case(s) they found most useful and how it shaped their scenario plan.

---

### Shooting Incident Requirements

Shooting teams must include:

- **At least two recordings** from different positions (e.g., `mic_A.wav`, `mic_B.wav`)
  - At least one recording must be **authentic** (unmanipulated)
  - At least one recording must be **fabricated** — manipulated using an edit technique and authentication element below
- At least one **gunshot-like acoustic event** with identifiable components (muzzle blast, shockwave, or reflections)
- A case brief with a **specific claim** about shooter location, distance, or number of shots
- An **answer key** submitted to the instructor only — identifying which recordings are authentic and which are fabricated

> The analysis team's job is to identify which recordings have been tampered with, exclude them as tainted evidence, and base their forensic conclusions only on the authentic recordings. This mirrors real casework, where fabricated evidence is inadmissible.

**Edit Techniques (choose ≥ 1, apply to fabricated recording only):**

| Technique | What to Do | Key Artifact |
|---|---|---|
| Butt splice | Cut and rejoin two segments with zero crossfade | Click + waveform discontinuity |
| Crossfade edit | Delete a segment with a 5–100 ms crossfade | Subtle spectral smearing |
| Reverb mismatch | Insert a dry segment into a reverberant recording | Missing reverb tails in spectrogram |
| Noise floor inconsistency | Insert a segment with different background noise | Broken horizontal lines in low-frequency spectrogram |

**Authentication Elements (choose ≥ 1, apply to fabricated recording only):**

| Technique | What to Do |
|---|---|
| Metadata manipulation | Open the file in ImHex and alter the timestamp, device info, or sample rate field. Or re-encode to a different format and back to create inconsistent codec history. |
| ENF-based claim | Write a scenario that makes a specific claim about *when or where* the recording was made. The analysis team will attempt to verify or refute it. |

> **Source material:** You may record impulsive sounds (claps, slams, balloons) in different spaces to simulate muzzle blast and environment interactions. Label your recordings by position (e.g., `mic_A.wav`, `mic_B.wav`).

---

### CVR Incident Requirements

CVR recordings are official flight records — not something a party would realistically fabricate. CVR teams build a realistic degraded recording and a contested scenario claim. No fabricated edits required. Include:

- **At least 3–5 minutes** of cockpit-style dialogue (you may use public domain speech from [LibriVox](https://librivox.org) or record your own)
- **Degradation** sufficient to require enhancement before interpretation — apply noise, clipping, or heavy reverb
- A case brief with a **specific claim** about what was said at a particular moment, or when a key statement was made
- An **answer key** submitted to the instructor only — including a full transcript and the correct interpretation of the contested claim

---

### Writing the Case Brief

Follow the same LSU principles from the midterm. The brief must state:

- **Who** is speaking or named in the recording
- **When** the recording was made (specific date and approximate time)
- **Where** the recording was made
- **What** the recording allegedly proves or establishes

The brief must **not** tell the analysis team what to listen for, describe the audio contents in detail, or suggest what conclusions to reach.

---

### Assembling the Evidence Package

Create a folder called `Team_[A or B]_Evidence` containing:

- [ ] Your audio file(s) (WAV format)
- [ ] `case_brief.pdf` or `case_brief.docx`

Submit to D2L. **Answer key goes to the instructor separately — not in the evidence folder.**

---

## Week 16: Analysis (Two Days)

You receive the opposing team's evidence package at the start of Week 16 Tuesday.

### Rule: Independent Analysis First

Each team member analyzes the evidence **alone**, without consulting teammates, until their individual report is submitted. The inter-examiner comparison only happens after all individual reports are in.

---

### Required Analysis Methods (All Types)

Apply all six methods to every recording in the package. If a method produces no findings, document that — a negative finding is a valid forensic result.

**1. Aural Evaluation**
- Listen to the full recording once in quiet conditions at a moderate level
- Document preliminary impressions before any technical analysis

**2. Waveform Analysis (Adobe Audition)**
- Look for discontinuities, amplitude jumps, or level inconsistencies
- Zoom in on suspicious areas to the sample level

**3. Spectrogram Analysis (Adobe Audition)**
- Use Spectral Frequency Display (`Shift+D`), FFT Size 4096 or 8192
- Look for: vertical broadband artifacts, missing reverb tails, broken horizontal lines, noise floor changes

**4. Edit Detection**
- Document each candidate edit location with timestamp, detection method, type, and confidence level
- If no edits are found, document that explicitly

**5. Metadata Examination (ImHex)**
- Inspect file header: sample rate, bit depth, format tag, embedded timestamp or device info
- Note anything inconsistent with the case brief

**6. ENF Analysis (openENF)**
- Run openENF and report match score, estimated timestamp, and grid
- Or write a conceptual analysis paragraph if openENF is not working
- If no ENF claim is made in the case brief, note whether ENF analysis is applicable and why

---

### Shooting-Specific Analysis

**Step 1 — Authenticate each recording before using it**

Apply the six required methods to every recording individually. For each recording, reach a determination: authentic or tainted.

- **Tainted recordings must be excluded** from acoustic analysis. Document why and state that the recording cannot be used as evidence.
- **Only authentic recordings** may be used for acoustic event analysis and TDOA.

**Step 2 — Acoustic and TDOA analysis (authentic recordings only)**

- Identify and classify acoustic events (muzzle blast, shockwave, reflections) in each authentic recording
- Measure the arrival time difference of the gunshot event between recordings in Adobe Audition — zoom to the sample level to identify the precise onset in each file, then calculate the time delay between them
- Use the time delay and the speed of sound (adjusted for temperature if known) to estimate the shooter's distance or position
- Express your conclusion using likelihood ratio framing
- Evaluate the scenario's specific claim about location, distance, or shot count

**Executive Summary for shooting cases:** State which recordings you determined to be authentic and which tainted, your basis for each determination, and what the authentic recordings support about the scenario's claim.

---

### CVR-Specific Analysis

- Determine whether enhancement is necessary for interpretability
- If yes: apply enhancement in Adobe Audition, document your before/after settings, and justify the approach
- Transcribe key passages; mark unintelligible content as `[Inaudible]`
- Evaluate the scenario's specific claim about what was said or when

**Executive Summary for CVR cases:** State your interpretation of the contested claim, your confidence level, and the primary technical basis (enhancement decisions, transcription, acoustic analysis).

---

### Individual Report Format

Submit a single Word document (`.docx`) structured as follows:

---

**FORENSIC AUDIO EXAMINATION REPORT**

**Case Reference:** [receiving team name] — Final Project  
**Examiner:** [your name]  
**Date of Examination:** [date]  
**Evidence Received:** [file names, format, duration]

---

**1. Executive Summary**

One paragraph. See scenario-specific guidance above. Write this *last*.

---

**2. Evidence Received**

File name(s), format, duration, sample rate, bit depth.

---

**3. Methods Used**

Brief list of tools and techniques applied.

---

**4. Findings**

Organized by analysis type with annotated screenshots.

- 4a. Aural Evaluation
- 4b. Waveform Analysis
- 4c. Spectrogram Analysis
- 4d. Edit Detection
- 4e. Metadata Examination
- 4f. ENF Analysis
- 4g. Domain-Specific Analysis (TDOA or Enhancement + Transcription)

---

**5. Opinion**

Supported determination. Cite only findings from Section 4.

---

**Appendix: Screenshots**

Number all screenshots and reference them from Section 4.

---

### Inter-Examiner Comparison

After all individual reports are submitted, your team meets to compare findings. One team member writes and submits the **Examiner Comparison Memo** — a short document covering:

- Where all four examiners agreed
- Where they diverged, and on what specific points
- How (or whether) the team resolved disagreements
- What the disagreements reveal about the difficulty or ambiguity of the evidence

---

## Final Exam Day: Presentations

Each team presents for approximately **15–20 minutes**, structured as follows:

**Part 1 — What We Built (5 min)**

*Shooting teams:*
- Scenario overview and case brief summary
- Which recordings were authentic and which fabricated
- Edits applied: what, where, how you tried to conceal them
- Authentication elements embedded
- Reveal your answer key live

*CVR teams:*
- Scenario overview and case brief summary
- What the degradation consisted of and why you chose it
- What the correct interpretation of the contested claim is
- Reveal your answer key live

**Part 2 — What We Found (8 min)**
- Walk through your analysis of the opposing team's case
- Key findings by method
- Final determination and confidence level
- Opposing team responds briefly

**Part 3 — Inter-Examiner Comparison (5 min)**
- Where did your four examiners agree?
- Where did they diverge, and why?
- What does that tell you about the evidence?

**Requirements:** Slides required. Analysis screenshots must be included. Every team member must speak.

---

## Submission Checklist

**Thursday of Week 15 (before leaving class) — one submission per team member:**

- [ ] `Team_[A or B]_Evidence` folder submitted to D2L
  - [ ] Audio file(s) in WAV format
  - [ ] `case_brief.pdf` or `.docx`
- [ ] Answer key submitted to D2L separately

**Thursday of Week 16 (before team comparison begins) — individual:**

- [ ] Individual forensic report `.docx` submitted to D2L

**Thursday of Week 16 (before leaving class) — one submission per team:**

- [ ] Examiner Comparison Memo submitted to D2L

---

## Grading Rubric

### Case Building — Shooting Team (25 pts — team grade)

| Criterion | Points |
|---|---|
| Required edit technique applied and documentable | 8 |
| Required authentication element included | 7 |
| Multi-source recordings provided with clear authentic/fabricated distinction | 5 |
| Case brief plausible, complete, follows LSU principles | 3 |
| Answer key submitted, accurate, and detailed | 2 |

### Case Building — CVR Team (25 pts — team grade)

| Criterion | Points |
|---|---|
| Cockpit dialogue is realistic and scenario is plausible | 8 |
| Degradation is sufficient to require enhancement but solvable | 7 |
| Recording meets duration and plausibility requirements | 5 |
| Case brief plausible, complete, follows LSU principles | 3 |
| Answer key submitted, accurate, and detailed | 2 |

### Individual Analysis Report (40 pts — individual grade)

| Criterion | Points |
|---|---|
| Aural evaluation documented | 3 |
| Waveform analysis with screenshots | 5 |
| Spectrogram analysis with screenshots | 5 |
| Edit detection findings (or documented negative finding) | 8 |
| Metadata examination | 5 |
| ENF analysis or reasoned explanation | 4 |
| Domain-specific analysis | 7 |
| Executive summary with supported determination | 3 |

### Presentation (35 pts — team grade)

| Criterion | Points |
|---|---|
| Case building walkthrough | 10 |
| Analysis findings | 10 |
| Inter-examiner comparison | 10 |
| Clarity and organization | 5 |

---

## Resources

- [Week 5 — Splices and edit detection](../../week-5/splices-and-edit-detection/)
- [Week 6 — ENF analysis and metadata consistency](../../week-6/enf-analysis-and-metadata-consistency/)
- [Week 8 — Audio enhancement techniques](../../week-8/audio-enhancement-techniques/)
- [Week 11 — Acoustic event analysis](../../week-11/acoustic-event-analysis/)
- [Week 12 — Physics of firearm sound signatures](../../week-12/physics-of-firearm-sound-signatures/)
- [Week 14 — Cockpit Voice Recorders](../../week-14/cockpit-voice-recorders/)
