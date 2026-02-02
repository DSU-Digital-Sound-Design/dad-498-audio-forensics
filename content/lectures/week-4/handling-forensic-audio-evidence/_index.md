+++
title = "Handling Forensic Audio Evidence"
outputs = ["Reveal"]
[reveal_hugo]
theme = "solarized"
margin = 0.2
separator = "##"
+++

## Handling Forensic Audio Evidence

Chapter 4: Principles of Forensic Audio Analysis

{{% note %}}
- This lecture covers the fundamental practices and procedures for handling forensic audio evidence.
- We'll explore the essential tools used in audio forensic examination, proper evidence handling protocols, and the systematic approach to analyzing audio recordings.
- This material is based on Chapter 4 from Robert C. Maher's "Principles of Forensic Audio Analysis" and represents industry-standard practices used in professional forensic laboratories.
{{% /note %}}

---

## Forms of Audio Evidence

- Digital files (CD, USB, email attachments)
- Proprietary device formats (surveillance systems)
- Analog tape recordings
- Need standard practices for all formats

{{% note %}}
- Audio forensic evidence comes in many forms today.
- Most commonly, you'll encounter digital files transferred via compact disc, USB memory stick, or even email attachments.
- However, some evidence may be stored in proprietary formats within devices or surveillance systems, requiring special knowledge to extract.
- Even in modern times, some audio forensic evidence still arrives as analog tape recordings.
- Regardless of format, official forensics labs must have standard practices and procedures for processing audio evidence.
- If an organization doesn't have its own guidelines, they should follow best practices from groups like the Scientific Working Group on Digital Evidence (SWGDE).
{{% /note %}}

---

## Basic Tools of Audio Forensics

1. High-quality audio playback system
2. Waveform display program
3. Spectrographic display program

All typically performed on desktop or laptop computer

{{% note %}}
- The fundamental tools of contemporary audio forensic examination are straightforward but essential.
- First, you need a good-quality audio playback system that exceeds the frequency content and dynamic range of your forensic material—any quality limitations should be attributable to the recording, not your playback system.
- Second, you need a waveform display program to visualize the audio in the time domain.
- Third, you need a spectrographic display program to analyze the audio in the frequency domain.
- These three functions are typically performed using a conventional desktop or laptop computer with appropriate software.
{{% /note %}}

---

## Audio Playback Requirements

- Frequency response: 50 Hz to 20 kHz
- Professional studio monitor speakers
- Professional-quality sealed headphones
- Separate volume control
- Moderate listening levels to prevent ear fatigue

{{% note %}}
- Your audio playback system must be of sufficient quality and flexibility.
- The computer's audio interface must support appropriate sampling rates and formats, plus various audio format decoding modules.
- For speakers, use professional general-purpose recording studio monitors with stated frequency response of 50 Hz to 20 kHz.
- Headphones are actually recommended for many audio forensic tasks because they reduce effects of room reverberation, computer fan noise, and other audible distractions.
- Look for professional-quality headphones with comfortable earpieces that completely seal around the ears.
- Importantly, arrange the playback system so that headphones have a separate volume control knob.
- Keep listening levels moderate—avoid making the level so loud that it causes the ear to adapt with reduced sensitivity (the acoustic reflex) or causes hearing damage from unexpected loud sounds.
{{% /note %}}

---

## Waveform View

**[IMAGE PLACEHOLDER: Fig 4.1 - Individual samples with connect-the-dots]**

Time on horizontal axis, amplitude on vertical axis

{{% note %}}
- Interpretation of aural information requires the ears, but the eyes can also be helpful in audio forensic analysis.
- The fundamental visual task is graphical waveform display, which depicts the audio recording as a graph with time on the horizontal axis (abscissa) and amplitude on the vertical axis (ordinate).
- Waveform display programs generally allow viewing a specific time range, with controls to zoom in or zoom out on both the time axis and amplitude axis.
- The graphical display usually shows individual waveform samples as dots if the time interval is very short.
- Some display programs have a "connect-the-dots" display that draws lines between individual sample points.
- If the time interval is made longer, there may be more samples to display than horizontal pixels on the screen, and most programs will show the maximum and minimum sample amplitudes in a short time span, creating the envelope of the audio signal.
{{% /note %}}

---

## Waveform Display Features

**[IMAGE PLACEHOLDER: Fig 4.2 - Waveform envelope display]**

- Zoom controls for time and amplitude
- Playback with cursor positioning
- Prevents inadvertent edits during viewing

{{% note %}}
- The most useful graphical waveform display programs provide simultaneous audio playback: a pair of cursors or select-and-drag highlighting identifies the chosen playback start and stop positions in the waveform.
- This allows an iterative procedure of listening and watching as the waveform details change aurally and visually.
- Display programs often include waveform editing features, storage format conversion, audio effects processing, and many other useful features.
- However, it is critically important to guard and maintain the original reference copy of the audio, and in particular, prevent inadvertent edits during the viewing and initial assessment procedures.
- This is why proper evidence handling protocols require working with verified copies, never the original.
{{% /note %}}

---

## Warning: Lossy Encoding

MP3 and similar formats are **lossy**

- Viewing requires decoding to PCM
- Re-saving creates second generation encoding
- Each cycle adds audible distortion
- **Never** decode, alter, and re-save in encoded format

{{% note %}}
- One particular concern occurs when working with encoded audio files, such as MP3.
- In order to view and listen to the file, the display program decodes the MP3 file into regular pulse-code modulation (PCM) samples.
- If the file is edited in any way and then saved again as MP3, the PCM samples are re-encoded as MP3, creating a second generation of encoding.
- Because MP3 and other similar perceptual coders are lossy, the decode/re-encode/decode cycle tends to create a build-up of audible distortion with each lossy encoding step.
- This is why it is critical not to decode, alter, and then re-save the edited file in encoded format.
- Always preserve the original and work with appropriate uncompressed formats for any processing.
{{% /note %}}

---

## Spectrographic View

**[IMAGE PLACEHOLDER: Fig 4.3 - Short-time Fourier transform concept]**

- Horizontal axis: time
- Vertical axis: frequency (Hz)
- Color/brightness: signal energy
- Shows signal in frequency domain

{{% note %}}
- A very useful method for visual display of audio forensic recordings is the spectrogram.
- The spectrogram is produced by calculating the short-time Fourier transform magnitude (the spectrum) of successive brief time intervals of the input signal and displaying them sequentially across the screen.
- Like the waveform display, the spectrogram presents a graph of audio signal energy with the horizontal axis being the time scale.
- Unlike the waveform display, the vertical axis of the spectrogram is the signal frequency scale in hertz.
- The relative amount of audio signal energy at a particular time and frequency is given by the color or brightness of the spectrogram at the corresponding coordinates in the graph.
- For this reason, the spectrogram is sometimes referred to as showing the signal in the frequency domain, while the waveform display shows the signal in the time domain.
{{% /note %}}

---

## Reading Spectrograms

**[IMAGE PLACEHOLDER: Fig 4.5 - Click and tone spectrogram]**

- Impulsive sounds (clicks): vertical lines
- Continuous tones (whistles): horizontal lines
- Reveals frequency content over time

{{% note %}}
- In the spectrographic view, an impulsive sound such as a click or gunshot appears as a vertical line, indicating that there is energy across frequency (broad along the vertical axis) but that it lasts for a brief instant (short along the horizontal axis).
- Conversely, a whistle or continuous hum tone appears as a horizontal line, indicating that the sound energy is relatively discrete in its frequency extent but continuous in duration.
- With practice, you can pick out important signal characteristics and changes from the spectrogram and then go back and listen to the audio signal corresponding to the spectral feature.
- This combination of visual and aural analysis is powerful for forensic examination.
{{% /note %}}

---

## Time-Frequency Trade-off

**[IMAGE PLACEHOLDER: Fig 4.6 - Two spectrograms showing trade-off]**

- Longer blocks = better frequency resolution, worse time resolution
- Shorter blocks = better time resolution, worse frequency resolution
- Fundamental mathematical limitation

{{% note %}}
- It is crucial to understand that there is a fundamental mathematical trade-off between signal resolution in time and in frequency.
- Zooming in on a very short-time duration of a signal inherently prevents simultaneously fine frequency resolution, while zooming out for a longer time duration allows finer resolution of frequency detail, but the longer time observation "window" prevents knowing details about when in time a particular signal occurred.
- In other words, the spectrogram has a trade-off between how selective the display can be in separating signal components of similar frequency and how detailed the timing can be.
- Recognizing this inherent trade-off, the examiner may choose to switch among several different settings for frequency and time resolution during analysis.
{{% /note %}}

---

## Avoiding Bias in Examination

- Bias often comes from extraneous non-audio information
- Suspect histories, crime scene details, desired conclusions
- Examiner is **not an advocate** for either side
- Role: educate the court about the audio evidence from scientific standpoint

{{% note %}}
- Among the challenges of forensic examination is avoiding bias in the interpretation process.
- In the context of audio forensic examination, bias often comes from the use of extraneous non-audio information about a case, the suspects, the circumstances, and the investigator's suspicions.
- The individual requesting the audio forensic examination may want to talk about the arrest history of a suspect,
- describe the physical evidence collected at the crime scene,
- suggest the desired conclusion that would "help" build the case,
- or divulge potentially incriminating comments by various individuals.
- While these details may be interesting and ultimately useful to the court or to a jury,
- the statements can also be prejudicial to the audio forensic examination process.
- The role of the forensic examiner is to educate the court about nature and reliability of the audio evidence from a scientific standpoint.
- The examiner is not an advocate for a particular side in the adversarial legal process,
- but an expert who testifies solely regarding the audio evidence presented.
{{% /note %}}

---

## Initial Inquiry Checklist

- Is the original recording available?
- What were the recording circumstances?
- Quality assessment: good, marginal, or poor?
- Any authenticity disputes?
- Prior examinations conducted?
- Specific forensic questions to address?

{{% note %}}
- Audio forensic examinations typically start with an inquiry from a law enforcement organization or an attorney.
- The requester may or may not be familiar with audio forensics procedures, so it is helpful to have a checklist.
- Key questions include: Is the original audio recording available?
- If not, what is the nature of the best-available duplicate recording?
- Under what circumstances was the recording made?
- Is the recording of good quality, marginal quality, or poor quality?
- Is there a dispute about any aspect of the recording, such as its authenticity?
- Has any prior audio forensic examination been conducted?
- If so, what is the reason for the additional requested analysis?
- What are the specific audio forensic questions to be addressed?
- Most audio forensic analysis requests require specific training and experience.
- It is imperative that the examiner declines engagements that go beyond his or her knowledge level.
{{% /note %}}

---

## Documentation Requirements

Detailed notes must include:

- Original recording or exact digital duplicate
- Equipment details (models, serial numbers, manuals)
- Maintenance/repair records
- Recording circumstances and location
- All recording process details
- Prior reports and transcripts

{{% note %}}
- It is vital to keep complete notes and documentation of all forensic engagements.
- Notes should be sufficiently detailed that the requests and processes can be recalled months or even years later.
- It is good practice to prepare notes and documentation in such a way that another examiner could read the description and have a very good idea of the audio forensic processes and conclusions.
- The standard procedure for audio forensic examination in formal laboratory protocols requires specific information to accompany the investigation.
- This includes the original recording or exact digital duplicate,
- complete equipment information,
- all maintenance records,
- detailed recording circumstances including location and background sound level,
- all recording process details like start/stop times and level changes,
- and any available prior reports or transcripts.
{{% /note %}}

---

## Evidence Handling Protocol

- Maintain chain of custody
- Document and photograph all materials
- Initial/label nondestructively
- Use write protection on devices
- Handle volatile memory carefully
- **Work with verified digital copy, never the original**

{{% note %}}
- Once audio forensic evidence is received, the examiner must follow laboratory standard practices.
- These include: maintaining the chain of custody by recording the date and circumstances under which evidence was received and ensuring security;
- observation of the data carrier, metadata, and other details using photographs and written notes to document all materials submitted including model numbers, serial numbers, formats, and any damage;
- initial or label nondestructively following laboratory policy for unique marking;
- protecting evidence with write-protection tabs and mechanical overwrite prevention settings;
- being careful with devices that have volatile memory that could be lost if power fails;
- and most importantly, working with a verified digital copy, never the original, unless absolutely necessary.
- Many digital forensics laboratories use a hardware write blocker device between the storage device and the control computer to prevent any modifications.
{{% /note %}}

---

## Initial Aural Evaluation

1. Listen to verified work copy
2. Quiet environment, moderate level
3. Make preliminary notes
4. Note quality, defects, audible events
5. View spectrograms for additional insights

{{% note %}}
- The first step in an audio forensic evaluation is to listen to the verified work copy of the audio material.
- Use a quiet environment with the sound playback level at a comfortable setting for this initial listening.
- Initial listening with loudspeakers is satisfactory if the playback area is free of distractions.
- It is standard practice to make preliminary notes about the audio material during this initial overall aural review and include any initial impressions about the quality and any noticeable defects or audible events in the recording.
- Many forensic examiners will also choose to view successive spectrograms of the recording, using suitable time and frequency ranges.
- The spectrogram can often help identify subtle aspects of the signal and any background sounds in the recording for additional evaluation.
{{% /note %}}

---

## Critical Listening Process

- Very quiet surroundings, high-quality headphones
- Moderate playback level (avoid acoustic reflex)
- Iterative: listen multiple times
- Focus on foreground, then background sounds
- Avoid creating false percepts from looping

{{% note %}}
- Critical listening is careful, focused audition of the forensic recording.
- Critical listening sessions must be in very quiet surroundings, free of distractions and interruptions, and generally require listening with comfortable high-quality headphones.
- The playback level is kept moderate to prevent aural fatigue and to avoid triggering the acoustic reflex, which causes lowered sensitivity.
- The critical listening process should be iterative, meaning that after listening to the entire recording, the examiner rewinds to re-listen to important sections several times in succession.
- An important aspect is to focus attention deliberately on the foreground sounds, such as speech dialog, and then during subsequent replays, focus deliberately upon the background sounds, such as ambient environmental noise, distant conversations, and subtle rattles.
- Background sounds may help identify the place and time of the recording, and irregularities in background sounds may be a clue to an edited or altered recording.
- However, repetitively listening to a short loop segment can create mental impressions based on the looping rhythm rather than the audio evidence itself, so be careful.
{{% /note %}}

---

## Waveform Analysis Approach

**[IMAGE PLACEHOLDER: Fig 4.2 or 4.4 - Waveform display]**

- Start with broad time range overview
- Zoom in successively on intervals of interest
- Look for discontinuities, dropouts, clicks
- Alternate between visual and aural assessment

{{% note %}}
- The ears can be extremely adept at detecting and identifying sounds, but not so adept at measuring precise time instants and amplitudes.
- The waveform display program provides a visual depiction of the audio signal that can help identify audible events, time intervals, signal changes, and other attributes.
- It is common for a forensic examiner to use the waveform display initially with a broad time range, perhaps as much as a few minutes, to get an overall impression of the signal waveform.
- Then the strategy is to zoom in successively on time intervals of interest, taking notes and making preliminary observations.
- Any signal contents of interest to the investigation, such as the time of a particular utterance or a distinctive background sound, get special scrutiny at this point.
- A good approach is to use an alternating combination of identifying signal features visually and listening to the signal aurally.
- In the zoom-in mode, look carefully for discontinuities, dropouts, abrupt clicks, and similar waveform irregularities that could indicate a problem with the recording system or the possibility of deliberate deletion or alteration.
{{% /note %}}

---

## Spectral Analysis Strategy

**[IMAGE PLACEHOLDER: Fig 4.7 - Time-frequency trade-offs]**

- Experiment with different block lengths
- Try various window functions (Hann, Hamming, Kaiser)
- Switch between settings for different purposes
- Combine spectrogram with waveform and playback

{{% note %}}
- In addition to the waveform time domain display, viewing the spectrogram can help identify signal features of interest.
- With practice, one can pick out important signal characteristics and changes from the spectrogram and then go back and listen to the audio signal corresponding to the spectral feature.
- Recognizing the spectrogram's inherent time-frequency trade-off, the examiner may choose to switch among several different settings for frequency and time resolution.
- Reducing the analysis block length gives a better indication of when a sonic event occurred, while increasing the block length gives more resolution in the frequency dimension but reduces the time resolution.
- Along with the basic time-frequency trade-off selection, another common option is the choice of window function.
- Common amplitude window functions include triangular, Bartlett, Hann, Hamming, Kaiser, and Blackman-Harris.
- While the amplitude window mitigates the abrupt boundaries of each block, it also has the side effect of reducing spectral resolution to some extent.
- The precise shape of the window function has subtle effects on frequency resolution, so it may be useful to experiment with different window functions and block lengths to help visualize the spectrographic details of greatest interest in a particular investigation.
{{% /note %}}

---

## Minimum Analysis Suite

Following initial listening and spectrographic observation:

1. **Critical listening** - focused audition
2. **Waveform analysis** - visual time domain
3. **Spectral analysis** - visual frequency domain

Keep comprehensive notes throughout!

{{% note %}}
- Following the initial listening and spectrographic observation, the examiner will then turn to the audio forensic questions posed by the requesting party.
- The minimum suite of analysis procedures includes critical listening, waveform analysis, and spectral analysis.
- These three approaches work together to provide a comprehensive understanding of the audio evidence.
- Critical listening provides the aural assessment, waveform analysis provides precise timing and amplitude measurements, and spectral analysis reveals frequency content and temporal patterns.
- Throughout all of these procedures, it is essential to keep complete and comprehensive work notes during the aural and visual assessment.
- It is very common to have weeks or months between the initial observation of the evidence and subsequent steps, such as report writing and testimony.
- Details that may seem obvious on the first examination need to be written down for future use, not simply committed to memory.
- Your notes should be detailed enough that another examiner could understand your processes and conclusions.
{{% /note %}}

---

## Key References

- Audio Engineering Society (1996): AES27-1996 - Managing recorded audio materials for forensic examination
- Scientific Working Group on Digital Evidence (2008): SWGDE best practices for forensic audio
- Allen & Rabiner (1977): Short-time Fourier analysis and synthesis

{{% note %}}
- The practices covered in this lecture are based on industry standards and best practices.
- The Audio Engineering Society published AES27-1996, which provides recommended practices for forensic purposes when managing recorded audio materials intended for examination.
- The Scientific Working Group on Digital Evidence published best practices for forensic audio in 2008, which provides comprehensive guidance for handling digital audio evidence.
- The foundational work by Allen and Rabiner from 1977 on short-time Fourier analysis and synthesis provides the mathematical basis for spectrographic analysis.
- These references represent the professional standards that guide forensic audio examination and ensure that work is scientifically rigorous and legally defensible.
- As you continue in this field, you should familiarize yourself with these standards and stay current with updates and new best practices as they emerge.
{{% /note %}}
