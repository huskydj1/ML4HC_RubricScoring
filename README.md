# ML4HC_RubricScoring

## Evaluation Framework for AI-Generated Clinical Notes in Obstetric Anesthesia

This repository contains the implementation of a novel evaluation framework for assessing AI-generated clinical notes derived from obstetric anesthesia consultations, as described in our research paper "Evaluation of Automated Clinical Notes for Anesthesia Consultations".

### Overview

Our framework addresses the labor-intensive process where anesthesiologists manually convert patient consultations into structured reports. The system combines automated concept labeling, sentence-by-sentence mapping, and retrieval-augmented generation to detect hallucinations, knowledge gaps, and other documentation issues in AI-generated clinical notes.

### Repository Structure

#### `/prompts`

Contains the prompts used in our framework:

- **RAG_PROMPT.txt**: Used for retrieval-augmented generation evaluation
- **PRESENCE_LABELING_PROMPT.txt**: Used for automatic labeling of medical concepts in transcripts and notes

#### `/Presence Labelling`

Contains notebooks and data for examining the automatic labeling process:

- **Scoring Presence Accuracy.ipynb**: Analysis of concept presence in transcripts and notes
- **Patient 2 [label YES, NO, MISSING] - GPT-Labeled-LLM_Note (Bolanle).csv**: Labeled LLM-generated note
- **Patient 2 [label YES, NO, MISSING] - GPT-Labled-Transcript (Waris).csv**: Labeled transcript
- **data/**: Directory containing source transcripts and notes

#### `/Rubric Scoring`

Includes notebooks for evaluating and scoring the clinical notes:

- **Patient2_Scoring.ipynb**: Analysis and scoring of patient notes across key categories:
  - Completeness/Sensitivity: Measures inclusion of relevant information from transcripts
  - Curation/Specificity: Evaluates exclusion of irrelevant information
  - Correctness (Hallucination): Detects invented content not present in source
  - Correctness (Knowledge Gap): Identifies inconsistencies between note and source

#### `/documents`

Contains source data and processed results for the evaluation framework.

### Evaluation Metrics

Our framework assesses notes using a comprehensive rubric including:

- Readability: Professional medical language appropriate for anesthesia consultation
- Completeness: Inclusion of key information from the patient encounter
- Curation: Exclusion of irrelevant information
- Correctness dimensions:
  - Hallucination: Invented content with no basis in the source
  - Knowledge Gap: Content inconsistent with source
  - Faulty Logic: Logically incorrect inferences
  - Bias: Expression of bias toward the patient
- Patient Safety Risk: Absence of errors that could impact patient care
- Clinical Usefulness: Minimal corrections needed before signing

### Contributors

- Davin Jeong (Harvard)
- Bolanle Oladeji (MIT)
- Dat Tran (MIT)
- Waris Tuchinda (MIT)
