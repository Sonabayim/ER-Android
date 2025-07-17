
# Emotional responsiveness in socially assistive robots for older adults 


This repository contains anonymized transcripts from a human–robot interaction (HRI) study conducted as part of the e-VITA project at Tohoku University. The study focused on post-interaction reflections by older adult participants after conversing with a humanoid android capable of emotion-adaptive dialogue. Transcripts include discussions about daily life, emotions, and perceptions of the robot’s responsiveness.

All transcripts are formatted in Markdown and structured for qualitative research, readability, and academic reuse.

---
## Overview

This dataset contains a structured interaction between eight older adult participants and AL-G109ST-F. It includes:

- Multilingual dialogue (Japanese and English)
    
- Emotion annotations based on a 5 category set
    
- Robot gesture tags associated with each response
    
- Contextual notes and metadata
    

The structure reflects the real-world constraints of a gesture-capable robot with limited expressive capabilities. Participants were allowed to exit the interaction at any point, and conversation durations varied from 15 to 20 minutes depending on participant preference.

---

## 📄 Table of Interview Transcripts


- [Participant 1 Post-Interview](participant1_post_interview.md)
- [Participant 2 Post-Interview](participant2_post_interview.md)
- [Participant 3 Post-Interview](participant3_post_interview.md)
- [Participant 4 Post-Interview](participant4_post_interview.md)
- [Participant 5 Post-Interview](participant5_post_interview.md)
- [Participant 6 Post-Interview](participant6_post_interview.md)
- [Participant 7 Post-Interview](participant7_post_interview.md)
- [Participant 8 Post-Interview](participant8_post_interview.md)


> 📝 Each file contains one full interview transcript with a unique participant ID.

---

## 📄 Table of Interaction reports

> Each file contains one full interaction report with a unique participant ID.

- [P001 Report](interaction-data/P001-report.md)
- [P002 Report](interaction-data/P002-report.md)
- [P003 Report](interaction-data/P003-report.md)
- [P004 Report](interaction-data/P004-report.md)
- [P005 Report](interaction-data/P005-report.md)
- [P006 Report](interaction-data/P006-report.md)
- [P007 Report](interaction-data/P007-report.md)
- [P008 Report](interaction-data/P008-report.md)



---

## Purpose of Emotion Labels

Emotion tags in this dataset are not intended to represent nuanced psychological states. Instead, they are used for mapping the robot's verbal responses to its available gestures. This design supports real-time interaction and gesture coordination within a constrained robotic system.

---

## Emotion-Gesture Mapping Table

| Emotion Label | Description                    | Intended Robot Gesture |
| ------------- | ------------------------------ | ---------------------- |
| `Happy`       | Cheerful and supportive tone   | `Smiling`              |
| `Sad`         | Empathetic, slow-paced concern | `Sad`                  |
| `Neutral`     | Informative or factual tone    | `Still`                |
| `Curious`     | Engaged, follow-up questioning | `Nodding`              |
| `Confused`    | Requesting clarification       | `Tilted head right`    |

All robot responses are annotated with both emotion and gesture fields, reflecting the alignment between spoken output and physical expression.

---

## Dialogue Structure

Each turn in the interaction includes:

- `turn_id`: Sequential turn identifier
    
- `user_utterance`: Japanese (`jp`) and machine-translated English (`en`) versions
    
- `robot_response`: Japanese and English versions, `emotion` label, `gesture`, and optional `emotion_label_type`
    
- Optional `interaction_note`: Explanation of any misunderstanding or unique behavior, technical issues such as, ASR, mic dropout, or system overload
    

Example:

```json
{
  "turn_id": 5,
  "user_utterance": {
    "jp": "習活",
    "en": "Job hunting.",
    "emotion": "Confused"
  },
  "robot_response": {
    "jp": "就職活動ですか？",
    "en": "Job hunting?",
    "emotion": "Confused",
    "gesture": "Tilted head",
    "emotion_label_type": "gesture_control"
  },
  "interaction_note": "Misunderstood homophone: 習活 (lesson activity) was misrecognized as 就活 (job hunting)."
}
```

---

## Translation Notes

- English translations are primarily machine generated, with minimal manual correction.
    
- Translations are intended for accessibility and annotation purposes, not for linguistic precision.
    
- Ambiguities or shifts in meaning are documented using the `interaction_note` field or in respective participant's report file
    

---

## Participant Metadata

Participant demographic data (e.g., age, gender, language background) is provided in a separate file: `P00X_metadata.json`. This design supports cleaner data formatting and easier demographic analysis while maintaining participant privacy.

---

## Timing Information

- Interaction duration range from 15 to 20 minutes per participant
    
- Individual turn duration are not timestamped
    
- Average turn length is estimated at 25–30 seconds
    

---

## Ethical Considerations

All participants provided informed consent prior to participation in the study. Participants were informed that they could stop the conversation at any time without consequence. No identifying personal information is included in the dataset. All metadata is anonymized and stored separately. This research adhered to ethical standards established by the affiliated institution and was approved by the Ethics Committee of Tohoku University under protocol number **2023-HR-014**. The project was designed to ensure participant safety, comfort, and confidentiality throughout the process.

---

## Limitations

|Limitation|Rationale|
|---|---|
|Emotion labels are limited to 5 classes|Matches robot's gesture system and does not aim for high-resolution affect modeling|
|Only one participant is shown per segment|Each file is a case study used for in-depth interaction analysis|
|Translations are machine-generated|Translation prioritizes accessibility over linguistic accuracy|
|No detailed timestamps|Reflects constraints in the original capture process; timing was estimated post-hoc|
|Some robot responses lack sensitivity|These are included to document current limitations in empathetic response modeling|

---

## Citation and Reuse

If you use this dataset in your research, please cite the original thesis or dataset publication (DOI to be provided). Suggested acknowledgement:

> "This dataset was created using gesture-mapped emotion tags to support embodied dialogue systems. Emotion labels reflect gesture control constraints rather than psychological classification."

---

## Additional Notes

For questions or clarification, please feel free to reach out via designated email. This documentation is designed to ensure clarity regarding the purpose and structure of the dataset.

---

**Maintained by:** Sonabayim Huseynzade  
**Contact:** sonabayim.huseynzade@tu-dortmund.de

