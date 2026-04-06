---
title: "Lab: Case Study — The Trump Rally Assassination Attempt"
date: 2026-04-09
draft: false
---

## Overview

**Session Date**: Thursday, April 9, 2026  
**Duration**: ~60 minutes

**Objective**: Work through Maher's 2025 forensic analysis of the July 13, 2024, shooting at the Trump rally in Butler, PA. You will trace his methodology, apply the crack-pop distance formula yourself, interpret figures from the paper, and practice writing cautious forensic conclusions.

**Primary source**: Robert C. Maher, "Audio Forensic Interpretation of the Trump Rally Assassination Attempt," *Journal of the Audio Engineering Society*, 2025. ([PDF](https://www.montana.edu/rmaher/publications/maher_jaes_1125_782-790.pdf))

**What to submit**: One Word document (`.docx`) with short answers organized by exercise number, submitted to the D2L assignment.

> **Forensic caution**: Use cautious language throughout — "consistent with," "suggests," or "cannot determine from acoustic evidence alone." Do not overclaim.

---

## Part 1: Guided Reading (~15 minutes)

Read the paper before answering the questions below. Pay particular attention to Sections 2–4, which describe the recordings used, the methods, and the key measurements.

### Exercise 1: Sources and Methodology

> **Turn in — Word doc questions:**
> 1. Maher analyzed two categories of audio recordings. Name both categories and explain why each has different forensic value. What are the advantages and limitations of each?
> 2. What is the "crack-pop" sequence? Under what conditions does a microphone near the target hear the crack before the pop, and why? Would a microphone placed behind the shooter hear the same sequence in the same order?
> 3. The 13 user-generated recordings shared no common clock. What technique did Maher use to align them, and why is it important to use a single shared acoustic event as the reference point rather than each recording's internal timestamp?
> 4. Why is it significant that shots A through H showed consistent relative timing across all 13 recording locations, while shots I and J did not?

---

## Part 2: Distance Calculation (~15 minutes)

Maher used the time lag between the ballistic shock wave ("crack") and the muzzle blast ("pop") to estimate the shooter's distance from the podium. The formula he applied is:

$$d = \frac{t_\text{diff}}{\frac{1}{c} - \frac{1}{V}}$$

Where:
- $d$ = distance from shooter to microphone (meters)
- $t_\text{diff}}$ = measured time lag between crack and pop (seconds)
- $c$ = speed of sound in air (m/s)
- $V$ = average speed of the bullet (m/s)

For the Butler rally analysis, Maher used these values:
- $t_\text{diff}$ ≈ **0.217 seconds** (217 ms, measured at the podium microphone for shots A–C)
- $c$ = **350 m/s** (adjusted upward from 343 m/s because the temperature was above 30°C)
- $V$ = **800 m/s** (assumed typical rifle speed; later confirmed at ~795 m/s for the perpetrator's .223 Remington ammunition)

### Exercise 2: Apply the Formula

> **Turn in — Word doc questions:**
> 1. Using the values above, solve for $d$. Show your work. How close is your result to the ~135-meter distance later confirmed by physical evidence?
> 2. Now recalculate using $c$ = 343 m/s (the standard speed of sound at 20°C) instead of 350 m/s. How much does your estimated distance change? What does this tell you about why environmental adjustments matter in forensic acoustics?
> 3. Suppose the time lag had been measured as 200 ms instead of 217 ms (using $c$ = 350 m/s and $V$ = 800 m/s). What distance would that produce? By how many meters does the estimate shift?
> 4. In his initial analysis, Maher assumed $V$ = 800 m/s. The actual confirmed bullet speed was 795 m/s. Does this difference change your distance estimate by more than a few meters? Calculate it and explain your reasoning.

---

## Part 3: Figure Analysis (~15 minutes)

Refer to the figures in the paper as you answer the questions below.

### Exercise 3: Reading the Waveforms

> **Turn in — Word doc questions:**
> 1. **Figures 4 and 5** show the waveform and spectrogram of the lectern microphone for the first three shots (A, B, C), with the crack and pop impulses labeled. Describe what you see for a single shot event: how many distinct impulses are visible, and what physical event does each correspond to?
> 2. The muzzle blast is often described as a very brief impulse — typically 1 to 3 milliseconds — yet in the waveforms it appears to last much longer. What acoustic phenomenon explains this, and why does it matter for forensic analysis?
> 3. **Figure 10** shows five user-generated recordings stacked vertically, time-aligned to Shot A. Shots A through H appear at consistent relative positions across all five tracks. Shots I and J do not. Based on the paper's explanation, what does this inconsistency tell you about the origin of shots I and J?
> 4. **Figure 11** plots the time-of-arrival for all ten shots across all 13 recordings. Shot I arrives approximately 200 ms earlier than expected at one location, and Shot J arrives approximately 400 ms earlier than expected at another. What does "arriving earlier than expected" mean in this context, and why would a shot from a different position produce an offset arrival time?

---

## Part 4: Forensic Interpretation (~10 minutes)

### Exercise 4: Case-Style Conclusion

Write a short forensic summary paragraph — suitable for an expert report — that addresses the following:

- How many distinct shooters did the acoustic evidence support, and from roughly what positions?
- What was the strongest piece of acoustic evidence for the shooter's distance?
- What were the limits of the acoustic analysis? What did physical evidence ultimately need to confirm?

Your paragraph should use cautious forensic language throughout. Do not simply restate the paper's conclusions in different words — explain the reasoning behind those conclusions as if writing to a non-specialist reader.

> **Turn in — Word doc question:**
> 1. Write one paragraph (5–8 sentences) presenting your forensic interpretation of the acoustic evidence, using language appropriate for an expert report.

---

## Submission Checklist

Before you submit, confirm you have:

- [ ] One Word document (`.docx`) with answers to all exercises, labeled by number
- [ ] Calculations shown for Exercise 2 (not just final answers)
- [ ] Forensic caution applied throughout — no overclaiming

Submit to the D2L assignment for Week 13.
