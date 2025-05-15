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

#### `/Presence Labeling Evaluation`

Contains notebooks and data showing LLM-based concept labeling:

- **Scoring Presence Accuracy.ipynb**: Analysis of concept presence in transcripts and notes
- **LLM-Labeled LLM Note.csv**: LLM-generated note with concept presence labels (automatically labeled by the LLM)
- **LLM-Labeled Patient Transcript.csv**: Patient consultation transcript with concept presence labels (automatically labeled by the LLM)

This directory displays the automated LLM labeling process for one synthetic patient case as a reference example.

#### `/Post-processing Rubric Scoring`

Includes notebooks and manually labeled data for evaluating and scoring clinical notes:

- **Patient2_Scoring.ipynb**: Analysis and scoring of patient notes across key categories:
  - Completeness/Sensitivity: Measures inclusion of relevant information from transcripts
  - Curation/Specificity: Evaluates exclusion of irrelevant information
  - Correctness (Hallucination): Detects invented content not present in source
  - Correctness (Knowledge Gap): Identifies inconsistencies between note and source
- **Manual-Labeled Transcript.csv**: Manually labeled patient transcript
- **Manual-Labeled LLM Note.csv**: Manually labeled LLM-generated note

The scoring process is demonstrated using manually labeled synthetic data from one patient case for reference.

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

### Note on Data

This repository includes labeling and synthetic data for one patient as a reference example. All patient data is synthetic and created for demonstration purposes only. No real patient information is included.

### Note on Notebooks

The Jupyter notebooks in this repository are provided primarily for visualization of the code and methodology. They are not set up to run directly in Colab or other environments as they require specific dependencies and data paths. The notebooks serve as reference implementations to understand our approach.

### Contributors

- Davin Jeong (Harvard)
- Bolanle Oladeji (MIT)
- Dat Tran (MIT)
- Waris Tuchinda (MIT)
