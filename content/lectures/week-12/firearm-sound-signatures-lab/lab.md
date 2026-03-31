---
title: "Lab: Firearm Sound Signature Analysis"
date: 2026-03-31
draft: false
---

<!--
================================================================
INSTRUCTOR PREPARATION NOTES — Not visible to students
================================================================

## Lab Goal

Build a mixed comparison set that supports the Week 12 lecture topics
from Sections I-III:
- firearm/ammunition basics
- muzzle blast behavior
- ballistic shock waves

Adobe Audition is the only required tool. The lab is designed for
analysis and classification, not for enhancement or restoration.

# Clip Mapping — Mixed Comparison Set

| Clip | Source File | Firearm | Category | Notes |
|------|-------------|---------|----------|-------|
| clip_01.wav | `glock/glock_007_SA_214B_S03.wav` | Glock (9mm semi-auto pistol) | **Handgun** | Clean close-range shot; classic semi-auto muzzle blast signature |
| clip_02.wav | `sw-10-8-38spl-revolver/sw-10-8-38spl-revolver_009_SA_206A_S02.wav` | S&W Model 10-8 (.38 Spl revolver) | **Revolver-like** | Single-action revolver; audible cylinder gap contribution to blast character |
| clip_03.wav | `pump-action-shotgun/pump-action-shotgun_005_pump_0m_center_1907.wav` | Pump-action shotgun (12 ga) | **Long gun** | Close-range center mic; large bore, low-frequency content; pump rack audible |
| clip_04.wav | `remington-700/remington-700_003_SA_020B_S01.wav` | Remington 700 (bolt-action rifle) | **Long gun** | Clean close-range reference shot; supersonic crack present; no distance artifacts |
| clip_05.wav | `m24-sws/m24-sws_001_m24_200m_front_0095.wav` | M24 SWS (7.62×51 sniper rifle) | **Shockwave** | Recorded 200 m directly in front of muzzle; bullet shockwave arrives before muzzle blast — shockwave/muzzle timing separation is clearly audible |
| clip_06.wav | `m24-sws/m24-sws_009_m24_100m_back_0031.wav` | M24 SWS (7.62×51 sniper rifle) | **Angle/distance** | Recorded 100 m behind the shooter; muzzle blast is attenuated and arrives late; only the supersonic crack precedes; easily misread as a closer, smaller-caliber weapon |

## Criteria Coverage

- **Handgun:** clip_01 (Glock)
- **Long gun:** clip_03 (shotgun), clip_04 (Remington 700)
- **Revolver-like:** clip_02 (S&W .38 revolver)
- **Shockwave reasoning relevant:** clip_05 (M24 at 200 m front — shockwave/muzzle separation)
- **Recording angle/distance complicates interpretation:** clip_06 (M24 at 100 m rear — suppressed muzzle, crack-only presentation)


## Suggested Design Targets

The clips do not need to support exact model identification. They only
need to support careful, defensible comparisons such as:
- handgun versus long gun
- revolver-like versus semiautomatic-pistol-like behavior
- shock wave plus muzzle blast versus muzzle blast alone
- cleaner direct arrival versus strong reflections/reverberation

## Answer-Key Guidance

Students should be rewarded for cautious reasoning. Strong answers use
phrasing such as:
- "consistent with"
- "suggests"
- "cannot determine from this recording alone"

Avoid rewarding overclaims about exact caliber, exact firearm model, or
exact shooter position unless the audio genuinely supports it.

================================================================
END INSTRUCTOR NOTES
================================================================
-->

## Overview

**Session Date**: Thursday, April 2, 2026  
**Duration**: ~60 minutes

**Objective**: Use Adobe Audition to analyze a mixed set of firearm recordings and identify acoustic features that are consistent with firearm class, muzzle-blast behavior, and ballistic shock waves. You will practice distinguishing broad firearm categories, recognizing when a waveform suggests a shock wave plus muzzle blast versus muzzle blast alone, and explaining what cannot be determined confidently from the recording by itself.

**Primary tool**:
- Adobe Audition

**What to submit:** Each exercise ends with a **Turn in** block. Submit one Word document (`.docx`) with short answers organized by exercise number, plus the required screenshots from Adobe Audition, to the D2L assignment.

> **Screenshot tip:** Capture the full Adobe Audition window so the file name, current view, playhead position, and zoom level are visible. Label each file with the exercise number (for example, `Ex2_clip_sort.png` or `Ex3_dual_impulse.png`).

> **Forensic caution:** Do not overclaim. Unless the recording clearly supports a stronger conclusion, use cautious language such as "consistent with," "suggests," or "cannot determine from this recording alone."

---

## Part 1: Download Lab Materials (~5 minutes)

Download the Week 12 lab folder from D2L or the course share link provided in class. Save it to your desktop as `Week12_Firearm_Lab`.

Your folder should contain these files:

- `clip_01.wav`
- `clip_02.wav`
- `clip_03.wav`
- `clip_04.wav`
- `clip_05.wav`
- `clip_06.wav`

These filenames are intentionally neutral. Your job is to infer what the recordings suggest from the audio itself.

Before you begin:

1. Launch **Adobe Audition**
2. Open all six clips
3. Listen once through each clip without making any edits
4. Keep a notebook or a blank Word document open so you can record first impressions

No screenshots are required for this part.

---

## Part 2: Initial Listening and Sorting (~10-12 minutes)

### Exercise 1: First-Pass Classification

Listen to each clip one full time before zooming in on the waveform.

For each clip, make an initial judgment about whether it is more consistent with:

- a **handgun** or a **long gun**
- a **revolver-like** signature or a **pistol-like** signature, if the evidence seems to support that comparison
- a **shock wave plus muzzle blast** sequence or **muzzle blast only / unclear**

As you listen, focus on broad clues rather than exact identification:

- Does the recording sound like a single dominant blast, or like a crack followed by a second event?
- Do you hear any subtle mechanical sounds before or after the main blast?
- Does the shot seem tightly focused and brief, or does the recording suggest a longer, more reverberant environment?
- Does anything suggest the recording was made off-axis or at some distance from the source?

At this stage, you are making a first-pass classification only. It is acceptable to mark a clip as **unclear** if the evidence is weak.

> **Turn in:**
> - **Screenshot:**
>   1. One screenshot showing all six clips open in Adobe Audition
> - **Word doc questions:**
>   1. For each clip, state your first-pass classification:
>      - handgun or long gun
>      - revolver-like, pistol-like, or indeterminate
>      - shock wave plus muzzle blast, muzzle blast only, or indeterminate
>   2. For each clip, name one audible clue that led you to that first-pass judgment.
>   3. Which clip were you least confident about, and why?

---

## Part 3: Waveform and Spectral Inspection (~15-18 minutes)

### Exercise 2: Looking for Acoustic Components

Now choose **three** clips that seemed most informative during your first-pass listening.

For each selected clip:

1. Inspect it in **waveform view**
2. Switch to **Spectral Frequency Display** (`Shift+D`)
3. Zoom in until the main transient structure is easy to see
4. Compare the first arrival, any later peak, and the reverberant tail

Look for features that may be consistent with the lecture:

- a very short muzzle-blast transient
- a possible dual-impulse pattern that could be consistent with a revolver cylinder-gap event
- a crack-then-boom sequence that may be consistent with a ballistic shock wave followed by the muzzle blast
- obvious reflections or reverberant energy that should **not** be mistaken for a second source event

As you inspect the clips, keep these cautions in mind:

- A later echo is not the same thing as a separate ballistic component.
- A loud transient alone does not prove a particular firearm class.
- A waveform may be suggestive without being conclusive.

> **Turn in:**
> - **Screenshots:**
>   1. Three screenshots total, one from each selected clip, showing the feature you think is most important
> - **Word doc questions:**
>   1. For each selected clip, describe the most important visible feature in the waveform or spectrogram.
>   2. What physical event do you think that feature is most consistent with?
>   3. Which of the three clips most strongly suggests a dual-impulse or crack-then-boom structure?
>   4. In at least one example, explain why a later feature is more likely a reflection or reverberant tail than a separate ballistic event.

---

## Part 4: Structured Comparison (~15 minutes)

### Exercise 3: Pairwise Reasoning

You will now compare clips in pairs and defend your interpretation.

Use these comparison pairs:

- **Pair A:** `clip_01.wav` and `clip_02.wav`
- **Pair B:** `clip_03.wav` and `clip_04.wav`
- **Pair C:** `clip_05.wav` and `clip_06.wav`

For each pair, listen again and inspect the waveform and spectrogram side by side if possible.

Your goal is not to force a perfect label. Your goal is to explain what the pair comparison makes more visible.

Possible comparison ideas:

- one clip seems more consistent with revolver-like behavior, while the other seems more consistent with pistol-like behavior
- one clip seems more consistent with shock wave plus muzzle blast, while the other seems more consistent with muzzle blast alone
- one clip seems to have a clearer direct arrival, while the other is more affected by reflections, distance, or off-axis recording geometry

For each pair, explain:

- what acoustic components seem to be present
- which interpretation is strongest
- what you still cannot determine confidently from the recording alone

> **Turn in:**
> - **Screenshots:**
>   1. One screenshot for each pair, or one combined screenshot if you arrange the pair visually in Audition
> - **Word doc questions:**
>   1. For Pair A, what is the strongest defensible difference between the two clips?
>   2. For Pair B, what is the strongest defensible difference between the two clips?
>   3. For Pair C, what is the strongest defensible difference between the two clips?
>   4. For at least one pair, explain what evidence would be needed before you would make a stronger claim about exact firearm type or ammunition.

---

## Part 5: Short Forensic Interpretation (~10 minutes)

### Exercise 4: Case-Style Conclusion

Choose the **single clip** from the set that you think is most interpretable.

Listen one more time, then inspect the waveform and spectrogram one final time. Write a short case-style paragraph that answers the following:

- What broad class of recording is this most consistent with?
- Is the clip more consistent with **shock wave plus muzzle blast** or **muzzle blast alone**?
- Does the recording seem more consistent with a **downrange**, **off-axis**, **rear-position**, or **indeterminate** microphone placement?
- What are the strongest limits on your interpretation?

Your answer should read like a cautious forensic note, not like a guess. Focus on what the recording supports and where the uncertainty remains.

> **Turn in:**
> - **Word doc question:**
>   1. Write one short paragraph that states your interpretation of the selected clip using cautious forensic language.

---

## Final Submission Checklist

Before you submit, make sure you have:

- one Word document with answers labeled by exercise number
- one screenshot showing all six clips open in Audition
- three feature screenshots from Exercise 2
- one screenshot per comparison pair, or one combined comparison screenshot set from Exercise 3

This lab is about careful reasoning, not perfect certainty. A cautious, well-supported interpretation is better than an overly specific claim that the recording does not actually justify.
