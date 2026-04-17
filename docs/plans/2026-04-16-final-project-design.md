# Final Project Design: Operation Deep Cut

**Date:** 2026-04-16  
**Course:** DAD 498 — Audio Forensics  
**Status:** Validated

---

## Overview

Two teams of 4. Each team selects a scenario type — **shooting incident** or **CVR incident** — then spends two class days building a fabricated evidence package. On the third and fourth days, teams swap packages and each student analyzes the opposing team's case *independently*, without consulting teammates. After individual analysis is complete, the team compares results and documents where they agreed and disagreed. On final exam day, both teams present — covering their fabrication choices and their analysis findings, including the inter-examiner comparison.

The scenario types are intentionally different. If Team A builds a shooting case, they analyze Team B's CVR case, and vice versa. This tests breadth across the full semester, not just the domain each team chose to build.

**Timeline:**
- Week 15 Tue/Thu: Fabrication (both days)
- Week 16 Tue/Thu: Independent analysis, then team comparison
- Final Exam: Presentations + case reveal + debrief

---

## Fabrication Requirements

Each team must build an evidence package appropriate to their chosen scenario type.

### Shared requirements (both types)
- At least one **edit** (butt splice, crossfade, reverb mismatch, or noise floor inconsistency)
- At least one **authentication element** (metadata manipulation or ENF-based temporal/location claim)
- A **case brief** following LSU principles — context without priming
- A **chain of custody form**
- An **answer key** submitted to instructor only

### Shooting incident requirements
- Multi-channel or multi-source audio (at least 2 recordings from different positions) to enable TDOA analysis
- At least one gunshot-like acoustic event with identifiable muzzle blast and/or shockwave components
- A scenario claim about shooter location, distance, or number of shots that the analysis team must evaluate

### CVR incident requirements
- At least 3–5 minutes of cockpit-style dialogue (can use public domain speech sources)
- Audio degraded enough to require enhancement before interpretation (noise, clipping, or reverb)
- A scenario claim about what was said or when — something the analysis team must verify or refute

### Enhancement rule (both types)
Teams may degrade their audio intentionally. If the analysis team determines enhancement is necessary for interpretability, they must apply and document it before proceeding to other analysis.

---

## Analysis Requirements

Each student analyzes independently first, then the team compares.

### Independent analysis (each student, all scenario types)
- Aural evaluation (full listen, documented impressions)
- Waveform analysis with screenshots
- Spectrogram analysis with screenshots
- Edit detection (timestamp, method, confidence, type)
- Metadata examination (ImHex)
- ENF analysis or reasoned conceptual explanation

### Shooting-specific analysis
- Identify and classify acoustic events (muzzle blast, shockwave, reflections)
- TDOA analysis across available recordings to estimate shooter position
- Distance and shot count estimation with likelihood ratio framing
- Evaluate the scenario's claims about location/distance/shot count

### CVR-specific analysis
- Enhancement if needed (document before/after, justify the approach)
- Transcription of key passages with `[Inaudible]` markers
- Evaluate the scenario's claims about what was said or when

### Inter-examiner comparison (team, after individual work)
- Each team member submits their individual report first (no collaboration before this)
- Team then meets to compare findings — where did they agree? Where did they diverge?
- One team member writes a short **Examiner Comparison Memo** documenting the agreements, disagreements, and how (or whether) they resolved them
- The Examiner Comparison Memo is submitted as a team document, separate from individual reports

---

## Grading

### Fabrication — 25 pts (team grade)

| Criterion | Points |
|---|---|
| Required edit technique applied and documentable | 8 |
| Required authentication element included | 7 |
| Domain-specific requirements met (shooting: multi-source + TDOA-able; CVR: degraded + interpretable) | 5 |
| Case brief is plausible, complete, follows LSU principles | 3 |
| Answer key submitted, accurate, detailed enough to grade analysis | 2 |

### Individual Analysis Report — 40 pts (individual grade)

| Criterion | Points |
|---|---|
| Aural evaluation documented | 3 |
| Waveform analysis with screenshots | 5 |
| Spectrogram analysis with screenshots | 5 |
| Edit detection findings | 8 |
| Metadata examination | 5 |
| ENF analysis or reasoned explanation | 4 |
| Domain-specific analysis (TDOA/shooting or enhancement+transcription/CVR) | 7 |
| Executive summary with supported determination | 3 |

### Presentation — 35 pts (team grade)

| Criterion | Points |
|---|---|
| Fabrication walkthrough — what you built and how you tried to conceal it | 10 |
| Analysis findings — what you found in the opposing team's case | 10 |
| Inter-examiner comparison — agreements, disagreements, resolution | 10 |
| Clarity and organization | 5 |

---

## Presentation Format

Each team presents on final exam day (~15–20 minutes per team).

**Part 1 — What We Built (5 min)**
- Scenario overview and case brief summary
- Edits applied: what, where, how they tried to conceal them
- Authentication elements embedded
- Reveal the answer key live

**Part 2 — What We Found (8 min)**
- Walk through analysis of the opposing team's case
- Key findings by method: waveform, spectrogram, edit detection, metadata, ENF, domain-specific
- Final determination and confidence level
- Opposing team responds briefly

**Part 3 — Inter-Examiner Comparison (5 min)**
- Where did the four individual examiners agree?
- Where did they diverge, and why?
- What does that tell them about the difficulty or ambiguity of the evidence?

**Format requirements:** Slides required. Screenshots from analysis must be included. Each team member must speak.
