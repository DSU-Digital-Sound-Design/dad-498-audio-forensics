+++
title = "Cockpit Voice Recorders"
outputs = ["Reveal"]
[reveal_hugo]
theme = "moon"
+++

# Cockpit Voice Recorders

DAD 498: Audio Forensics — Week 14

{{% note %}}
This lecture focuses on one of the most consequential applications of audio forensics: the analysis of cockpit voice recorder data in aviation accident investigations. CVRs capture the final moments of flight — crew communication, mechanical sounds, warning alarms — and forensic audio specialists are often the ones who decode what happened and why. We will move from the history and technical design of these devices to the strict legal protocols for their handling, and then examine three real accident investigations where CVR analysis was decisive.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Chapter 10: "Application Example 2: Cockpit Voice Recorders." Springer, 2018.
{{% /note %}}

---

## Today's Topics

- History of flight recording
- How CVRs work
- Recovery and legal protocols
- Three case studies
- Future directions

{{% note %}}
We have five sections today. We start with the history of how CVRs came to exist — it took several catastrophic crashes to make them mandatory. Then we look at how they actually work technically. We will spend significant time on the recovery and legal protocols, because the rules around CVR handling are strict and unusual. The heart of the lecture is three case studies from Maher's chapter: Germanwings 9525, USAir 427, and Execuflight 1526. We close with a look at what may replace physical recorders in the future.
{{% /note %}}

---

{{% section %}}

# I. History of Flight Recording

From railroad ledgers to solid-state memory

{{% note %}}
Before there were cockpit voice recorders, there were no systematic records of what happened inside an aircraft during a crash. Investigators could examine wreckage and interview survivors, but the cockpit itself was a black hole. The history of flight recording is a slow accumulation of tragedy and response — each major disaster pushing the industry one step closer to mandatory recording.

- Citation: Epperson, B. "A History of Cockpit Recording in Transport Safety."
{{% /note %}}

---

## The Problem: Crashes Without Answers

- Early accidents left investigators guessing
- No record of crew actions or voice
- Wreckage alone couldn't explain everything
- Systematic recording seemed impossible

{{% note %}}
Before flight recorders, accident investigators had to reconstruct events from physical wreckage, survivor testimony, and ground witnesses. For accidents over water or remote terrain, there was often almost nothing. The idea that aircraft could continuously document their own performance and crew behavior was radical — and it met fierce resistance from pilots who worried about surveillance.
{{% /note %}}

---

## Early Milestones

- **1839** — Babbage proposes railroad crash recorder
- **1939** — Hussenot & Beaudouin: optical film recorder (France)
- **1942** — Finnish "Mata Hari": metal foil styli recorder
- **1953–54** — Ryan patent; David Warren proposes CVR (Australia)
- **1965** — Recorders moved to the tail (empennage)

{{% note %}}
The concept of recording transport accidents actually predates aviation. Charles Babbage proposed a railroad version in 1839. In aviation, the first serious attempts came from France and Finland in the early 1940s. David Warren, an Australian scientist, made the breakthrough proposal in 1953–54 — inspired by witnessing the aftermath of the DeHavilland Comet crashes — that aircraft should record pilot voice alongside flight parameters. His idea was initially dismissed before being adopted internationally.

- Citation: Epperson, B. "A History of Cockpit Recording in Transport Safety."
{{% /note %}}

---

<!-- IMAGE: Timeline of CVR development milestones, or photo of early orange "black box" unit -->
<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2950338825000270-gr1_lrg.jpg" alt="Timeline of CVR development milestones"/>


{{% note %}}
An image here showing the evolution of CVR hardware — from early film-based units to the distinctive bright orange solid-state boxes used today — helps students visualize the century-long development of this technology.
{{% /note %}}

---

## Modern Solid-State CVRs

- **1972** — Regulations prohibit pilot erasure of CVR
- **Early 1990s** — Tape replaced by solid-state memory
- **Today** — 2-hour buffer, four channels, crash-survivable
- Painted bright orange (not black) for recovery visibility

{{% note %}}
The shift from magnetic tape to solid-state memory in the early 1990s was transformative. Solid-state units have no moving parts, survive higher crash forces, and are far more resistant to fire and water damage. The "black box" nickname is a misnomer — they are bright orange specifically so recovery crews can spot them in wreckage, mud, or water.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
- Citation: Epperson, B. "A History of Cockpit Recording in Transport Safety."
{{% /note %}}

---

## Discussion

- Why did pilots resist CVR mandates early on?
- How do disasters shape aviation safety rules?
- Should CVR recordings ever be made public?

{{% note %}}
"Why did pilots resist?" — Unions worried about privacy and disciplinary use of recordings. The nondisclosure laws and strict CVR Group protocols were partly a response to this concern, designed to ensure CVR data is used for safety investigation only, not punitive action.

"How disasters shape rules?" — Regulatory change in aviation is nearly always reactive. The DeHavilland Comet crashes drove Warren's proposal; later crashes drove mandatory installation. This pattern — tragedy → investigation → new rule — is consistent throughout aviation safety history.

"Should CVRs be made public?" — Federal law prohibits release of CVR audio, though transcripts can be released. The argument against release is that public dissemination could chill candid cockpit communication. A counterargument is accountability and public interest.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# II. How CVRs Work

Four channels, two hours, crash-survivable

{{% note %}}
Now that we have the historical context, let's look at the technical design of modern CVRs. Understanding what they record — and what they don't — is essential for interpreting their forensic value. The recording architecture, survivability engineering, and activation behavior all shape what audio is actually available to investigators.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## Four Recording Channels

- **Channel 1** — Pilot's headset microphone
- **Channel 2** — Copilot's headset microphone
- **Channel 3** — Cockpit area microphone (ceiling-mounted)
- **Channel 4** — Intercom / passenger address system

{{% note %}}
Each channel captures a different source of audio information. The headset microphones capture what the pilot and copilot say directly — including radio communications. The cockpit area microphone (CAM) is mounted in the ceiling panel and picks up ambient sound in the cockpit: engine noise transmitted through the airframe, warning alarms, switches being toggled, and any crew speech not captured on headsets. The intercom channel can include communications with cabin crew and public address announcements.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## The Memory Buffer Loop

- Records continuously, overwrites oldest data
- Minimum 2 hours of audio retained
- Older units: 30-minute loop only
- Starts recording when aircraft is powered up

{{% note %}}
The CVR operates as a circular buffer — it is always recording, but only the most recent two hours are retained. This means that in a short flight that ends in a crash, the entire flight may be captured. On longer flights, only the final two hours are available. A critical operational implication: if a CVR is left powered after an accident, it may overwrite the accident data. This is why NTSB protocol requires immediate deactivation on arrival at the scene.

The fact that it activates when the aircraft powers up — before the flight data recorder begins recording during takeoff — means it often captures pre-flight checklists, crew discussions, and cockpit preparation. This can be significant in investigations of maintenance-related accidents.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## Survivability Engineering

- Mounted in the tail (empennage) since 1965
- Bright orange for recovery visibility
- Withstands: extreme G-forces, fire, deep water
- The **microphone** doesn't survive — the **data** does
- Underwater locator beacon: 30-day battery

{{% note %}}
CVRs are engineered to survive what the aircraft cannot. They are placed in the tail because crash physics tend to be less severe there than at the nose. The casing must withstand 3,400 G of impact force, fire at 1,100°C for 30 minutes, and water pressure equivalent to a depth of 6,000 meters.

A common misconception worth addressing: the microphone itself is almost certainly destroyed in a crash. What survives is the solid-state memory module — the audio was already digitized and written to it during the flight. The cutaway diagram shows the layers protecting those chips: steel housing, thermal insulation, a thermal block, and the crash-survivable memory unit at the center. By the time the aircraft hits the ground, the microphone has done its job. The chips just need to stay intact and readable.

The underwater locator beacon (ULB) emits a 37.5 kHz acoustic pulse to help recovery crews find the device in water — but its 30-day battery life was challenged dramatically by the MH370 disappearance, where the search lasted over two years.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

![CVR internal components](figures/cvr-cutaway.jpg)

{{% note %}}
cutaway diagram of the crash-survivable casing, reinforces the survivability engineering discussed on the previous slide.
{{% /note %}}

---

## Discussion

- Why is the cockpit area microphone forensically significant?
- What are the limitations of a 2-hour buffer?
- How does recorder placement in the tail affect what gets captured?

{{% note %}}
"CAM significance?" — The area microphone picks up sounds that headset mics miss: airframe vibrations, structure-borne sounds, background noise that can reveal engine state, mechanical failures, and environmental conditions. In the USAir 427 case we will see shortly, the CAM captured the "clunks and rattles" that ultimately identified the rudder defect.

"2-hour buffer limitations?" — Any flight longer than 2 hours will not have the takeoff captured. This is relevant for long-haul flights where the accident may have roots in decisions made at departure. Air France 447 was on an 11-hour overnight flight; only the final 2 hours were available.

"Tail placement?" — The tail is the most survivable location, but it also means the recording is somewhat distant from some engine and wing events. Structure-borne sounds travel through the airframe and may be attenuated or altered by the distance.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# III. Recovery & Legal Protocols

Chain of custody in the cockpit

{{% note %}}
Before a single second of CVR audio can be analyzed, investigators must follow extraordinarily strict protocols. These rules exist because CVR recordings are unlike other forms of forensic evidence — they are simultaneously safety data, potential legal evidence, and deeply private communications protected by federal law. Getting the chain of custody wrong can make recordings inadmissible, damage labor relations, or contaminate the investigation itself.

- Citation: National Transportation Safety Board. *Cockpit Voice Recorder Handbook*. NTSB, Washington, DC.
{{% /note %}}

---

<img src="https://ars.els-cdn.com/content/image/1-s2.0-S2950338825000270-gr2_lrg.jpg" alt="FDR and CVR from Air France Flight 447 recovered from the Atlantic Ocean, 2011"/>

{{% note %}}
This image shows the actual FDR and CVR from Air France Flight 447, recovered from the Atlantic Ocean in 2011 — nearly two years after the crash. When the investigation team first located the recorders on April 26, 2011, only the chassis of the FDR was found; the protected memory module wasn't recovered until May 1. The CVR was located and salvaged the following day, May 2. The team then spent a full year analyzing the data before completing the accident report in 2012.

This is a useful image to hold in mind throughout this section. Despite sitting at 3,800 meters depth for two years, the memory modules survived. The protocols that follow — immediate deactivation, no on-scene playback, packing water-recovered units in fresh water — exist precisely to protect data that has already survived the unsurvivable.
{{% /note %}}

---

## Immediate Steps at the Scene

- Deactivate CVR immediately (pull circuit breakers)
- Do NOT play back or open at the scene
- If found in water: pack in fresh water, keep submerged
- Ship directly to NTSB headquarters, Washington DC
- Source: [Cockpit Voice Recorder Handbook for Aviation Accident Investigations](https://skybrary.aero/sites/default/files/bookshelf/5945.pdf)

{{% note %}}
The first priority is preventing overwrite. If the CVR is still powered, it continues to record — and will eventually overwrite the accident data. On-scene staff must know to pull the relevant circuit breakers as soon as possible. The prohibition on on-scene playback prevents contamination of the original recording and ensures that any damage assessment happens in a controlled laboratory setting. The instruction to keep water-recovered units submerged in fresh water (not let them dry) is counterintuitive but critical — the memory media is more stable when wet, and drying can cause corrosion or short circuits.

- Citation: NTSB. *Cockpit Voice Recorder Handbook.*
{{% /note %}}

---

## Chain of Custody

- Assigned to a single CVR specialist at NTSB
- Full extraction without filters — no processing yet
- Transcription done by a formal CVR Group
- CVR Group includes: FAA, manufacturer, pilot unions

{{% note %}}
Unlike many forensic investigations where multiple technicians may handle evidence, the CVR is assigned to a specific specialist who controls the extraction process. The initial extraction captures everything — no filtering, no enhancement yet. A formal CVR Group is then convened with representatives from the FAA, aircraft manufacturer, and pilot unions. This multi-party structure is designed to ensure accuracy and to give labor organizations visibility into how their members' communications are being used.

- Citation: NTSB. *Cockpit Voice Recorder Handbook.*
{{% /note %}}

---

## Transcription Rules

- Document facts only: words and sounds
- No interpretation in the official transcript
- All participants sign nondisclosure agreements
- Unauthorized release is a federal offense

{{% note %}}
This is one of the most distinctive aspects of CVR handling: the official transcript is strictly factual. Transcribers document what was said and what sounds were heard — but they are prohibited from adding interpretive commentary. The reasoning is that interpretation should happen in the formal investigation process, not in the transcription room where it might be colored by premature theories. The nondisclosure requirement is enforced by federal statute. Leaking CVR audio or transcripts to the media is a criminal act — and this has created significant tension with journalism and public accountability in high-profile crashes.

- Citation: NTSB. *Cockpit Voice Recorder Handbook.*
{{% /note %}}

---

## Discussion

- Why are pilot union reps included in the CVR Group?
- What conflicts arise between transparency and nondisclosure?
- How does "no interpretation" in the transcript shape the investigation?

{{% note %}}
"Why pilot unions?" — Unions negotiated to be in the room partly to protect members from disciplinary use of recordings, and partly to provide expertise in interpreting aviation jargon and normal cockpit communication patterns. Their presence is both a safeguard and a form of participatory oversight.

"Transparency vs. nondisclosure?" — Families of victims, journalists, and the public often push for release of CVR audio. The NTSB argues that releasing audio would make crews less candid in cockpits. The families of Germanwings 9525 victims were particularly vocal about wanting to hear what happened. This tension has no easy resolution.

"No interpretation in transcript?" — It keeps the document neutral but can frustrate analysts who want to note ambiguities. It also means the same transcript can later support very different interpretive theories.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# IV. Case Studies

Three accidents, three roles for CVR analysis

{{% note %}}
We now turn to three case studies from Maher's chapter. Each one illustrates a different dimension of CVR forensic analysis. Germanwings 9525 demonstrates how speech and physiological sounds can prove intent. USAir 427 shows how non-speech acoustic events — mechanical vibrations — can identify a hardware defect. Execuflight 1526 shows what happens when the CVR is the only recorder available and audio quality is poor.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## Germanwings Flight 9525 (2015)

- Airbus A320 crashed in the French Alps
- 150 people killed — no survivors
- Captain locked out of cockpit mid-flight
- Copilot deliberately crashed the aircraft

{{% note %}}
Germanwings 9525 departed Barcelona for Düsseldorf on March 24, 2015. Approximately 38 minutes into the flight, the captain left the cockpit, likely to use the lavatory. The aircraft then began a controlled descent into the mountains. The captain was unable to re-enter. When investigators recovered the CVR, it provided unambiguous evidence of deliberate action.
{{% /note %}}

---

## Germanwings: What the CVR Captured

- Captain's urgent knocking — then attempts to break the door
- Copilot's slow, steady breathing throughout the descent
- No response to air traffic control
- Passenger screams in the final seconds

{{% note %}}
The CVR recording was decisive. The cockpit area microphone captured everything: the automated altitude warnings, the captain's increasingly frantic attempts to break down the reinforced door, and the copilot's breathing — steady and controlled throughout the entire descent. This physiological evidence was critical. The copilot never spoke again after locking the door. His breathing pattern ruled out incapacitation. The combination of silence, steady respiration, and the automated descent proved conscious, deliberate action. The copilot, Andreas Lubitz, had hidden a history of severe depression and suicidal ideation from his employer.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## USAir Flight 427 (1994)

- Boeing 737 crashed near Pittsburgh
- 132 people killed — no survivors
- CVR captured unusual mechanical sounds
- Led to major Boeing 737 inspection program

{{% note %}}
USAir 427 was on final approach to Pittsburgh when it suddenly rolled left and plunged into the ground. There were no survivors. The crash sparked one of the most extensive and expensive accident investigations in NTSB history, taking over four years to resolve. At the heart of the investigation were 23 seconds of CVR audio from the crash sequence.
{{% /note %}}

---

## USAir 427: "Clunks and Rattles"

- CVR captured unusual structure-borne vibrations
- NTSB reproduced sounds in laboratory experiments
- Matched: rudder power control unit (PCU) failure
- Cause: sudden rudder reversal — "rudder hardover"

{{% note %}}
Forensic acoustic analysis of the CVR revealed specific "clunks and rattles" in the seconds before the crash. NTSB specialists conducted extensive laboratory experiments, moving a Boeing 737 rudder through various positions and failure modes while recording the resulting structure-borne vibrations through the airframe microphone. They eventually reproduced the exact sounds from the accident recording — matching the acoustic signature to a rudder PCU failure mode that caused the rudder to suddenly deflect fully in the direction opposite to pilot input. This "rudder hardover" was the cause of the crash. The investigation also implicated an identical defect in another 737 crash (United 585) that had occurred three years earlier.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

<img src="https://www.faa.gov/sites/faa.gov/files/images/lessons_learned/N513AU/how-valve-works.jpg" alt="Diagram of Boeing 737 rudder PCU showing the valve mechanism"/>

{{% note %}}
A spectrogram showing the acoustic event from the USAir 427 CVR — the "clunks and rattles" captured by the cockpit area microphone — would powerfully illustrate how non-speech audio carries forensic information. Alternatively, a diagram of the 737 rudder PCU showing the defect mechanism connects the audio evidence to the mechanical cause.
{{% /note %}}

---

## Execuflight Flight 1526 (2015)

- Beechcraft King Air crashed near Akron, Ohio
- 9 people killed — no survivors
- No flight data recorder on board
- Old analog CVR in poor condition

{{% note %}}
Execuflight 1526 was a charter flight that crashed on approach to Akron-Canton Airport on November 10, 2015. The aircraft was a Beechcraft King Air twin turboprop. Because it was below the weight threshold requiring a Flight Data Recorder, investigators had only the CVR — and that CVR was an older analog unit producing a lower-quality recording than modern solid-state devices.
{{% /note %}}

---

## Execuflight: Engine Whine as Evidence

- No FDR — CVR was the only recorder
- Engine turbine whine captured on recording
- Whine frequency → turbine speed → throttle setting
- Crew failed checklist; should have aborted the approach

{{% note %}}
With no FDR to provide engine parameters, investigators turned to the CVR audio itself for performance data. The turbine engines of a King Air produce a characteristic high-frequency whine whose pitch correlates with turbine rotational speed. Forensic audio specialists analyzed this whine to extract RPM data, then converted that to throttle settings and engine performance at each phase of the approach. The analysis showed that the crew had not followed proper checklists and had continued an approach that should have been aborted due to an impending aerodynamic stall.

The CVR thus served double duty: as a speech recorder and as an inadvertent flight data recorder. This case also demonstrated an important forensic principle: sounds that seem like background noise often carry significant technical information.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## Discussion

- How does each case use CVR audio differently?
- What would investigators have missed without the CVR?
- What ethical questions does Germanwings raise about pilot privacy?

{{% note %}}
"Different uses?" — Germanwings: speech and physiological sounds proving intent. USAir 427: structure-borne vibrations identifying mechanical defect. Execuflight: background engine sounds serving as substitute flight data. Each shows the CVR as a multi-dimensional forensic tool, not just a voice recorder.

"Without CVR?" — Germanwings: investigators might have assumed catastrophic mechanical failure; the deliberate act could have been obscured. USAir 427: the investigation already took four years with the CVR; without it, the rudder defect might never have been identified. Execuflight: without both recorders, a definitive cause would have been nearly impossible.

"Pilot privacy in Germanwings?" — Lubitz's mental health records were legally protected in Germany. The question of how much airlines and regulators should be able to access pilot medical records, and whether continuous monitoring might prevent such tragedies, has reshaped European aviation regulations since 2015.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# V. Future Directions

When the box can't be found

{{% note %}}
The case studies illustrate both the power and the limitations of CVRs. They require physical recovery — and as the searches for Air France 447 and MH370 demonstrated, that may take years, cost billions, or prove impossible. Researchers and regulators have been working on alternatives that would transmit data in real time or eject recorders automatically before impact.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## The Recovery Problem

- Air France 447: 2 years to recover CVR (deep Atlantic)
- MH370: still missing — CVR never recovered
- Deep water, remote terrain, vast debris fields
- Locator beacon battery lasts only 30 days

{{% note %}}
Air France 447 disappeared in 2009 over the Atlantic Ocean. The wreckage was eventually located, but the CVR was not recovered until 2011 — nearly two years later, from a depth of about 3,800 meters. MH370 disappeared in March 2014 and has never been found; the CVR, if the aircraft is ever located, would hold the only definitive answers. These cases drove urgent discussion about the adequacy of physical recorder recovery in an era when aircraft can disappear over deep ocean.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## Proposed Solutions

- **Automatic ejection** — CVR ejects and floats before impact
- **Satellite streaming** — Real-time transmission to orbit
- **Extended beacons** — Longer battery, stronger signal
- Some aircraft already carry upgraded systems post-MH370

{{% note %}}
Satellite streaming is the most radical proposal: rather than recording to an on-board device, flight data and voice data would be continuously transmitted to satellites and stored remotely. This eliminates the recovery problem entirely. The challenge is cost — continuous satellite data transmission for thousands of commercial flights globally is expensive. Automatic ejection systems, similar to those used on military aircraft, are a more conservative alternative. Following recommendations from the MH370 investigation, some aircraft operating on extended oceanic routes now carry additional beacons with longer battery lives.

- Citation: Maher, R.C. *Principles of Forensic Audio Analysis*, Ch. 10.
{{% /note %}}

---

## Discussion

- Does real-time streaming change the privacy calculus for CVRs?
- Would streaming have solved the MH370 mystery?
- Who should have access to streamed flight data?

{{% note %}}
"Privacy calculus?" — If voice data is streamed to satellites in real time and stored on remote servers, the strict nondisclosure protections that currently apply to CVRs become more complex. Who controls the data? Under what circumstances can it be accessed? The protection currently comes partly from physical custody of a single device.

"Would streaming have solved MH370?" — Almost certainly yes: if the flight's final position data and cockpit audio had been transmitted in real time, the aircraft would have been found within days. This is a powerful argument for the technology.

"Who has access?" — Airline? Government? NTSB? Manufacturer? The governance question is unresolved and would vary by country. This parallels questions about cloud storage of sensitive data in other domains.
{{% /note %}}

{{% /section %}}

---

## Key Takeaways

- CVRs capture 4 channels in a 2-hour crash-survivable loop
- Strict protocols protect both evidence integrity and pilot privacy
- CVR audio can prove intent, identify mechanical faults, and substitute for missing data
- Recovery limitations are driving a shift toward real-time transmission

{{% note %}}
Summarizing the four major threads of today's lecture:
1. The technical design of CVRs — four channels, buffer loop, crash survivability — shapes what forensic analysis is possible.
2. The legal and procedural framework is unusually strict, balancing safety investigation needs against privacy and labor rights.
3. The three case studies show CVR analysis operating very differently — proving deliberate action, identifying a mechanical defect through structure-borne sounds, and substituting for missing flight data through engine acoustic analysis.
4. The physical recovery problem is real and is pushing the industry toward satellite alternatives.
{{% /note %}}

---

## Coming Up Thursday

- **Major case studies in depth**
- Air France 447: cognitive bias in the cockpit
- MH370: satellite pings and the limits of acoustic evidence
- CVR transcripts as a dataset: the Noort study

{{% note %}}
On Thursday we go deeper into two of the landmark aviation disasters mentioned today — Air France 447 and Malaysia Airlines MH370. We will look at how cognitive bias affects decision-making in the cockpit, how acoustic and signal evidence was used in the MH370 investigation, and briefly examine the Noort dataset of 172 CVR transcripts as a tool for studying crew communication patterns.
{{% /note %}}
