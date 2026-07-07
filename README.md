# Response-Stabilization Signatures in Human-LLM Interaction

This repository provides the public project location for materials associated with the manuscript:

**Response-Stabilization Signatures in Human-LLM Interaction: A Black-Box Behavioral Framework for Evaluating Conversational AI Responses**

The manuscript is submitted to the **International Journal of Human-Computer Interaction** as a Research Article.

## Author

Wooram Jeong  
Independent Researcher

## Project Overview

This project studies response-stabilization signatures in human-LLM interaction. The analysis is restricted to observable prompt-response behavior under black-box conditions. It does not claim access to model internals, hidden mechanisms, latent representations, proprietary safety systems, or user mental states.

The controlled study examines five response-stabilization signatures:

- **RC-1: Constrained Neutralization**
- **RC-2: Meaning Recomposition**
- **RC-3: Sharpness Attenuation**
- **RC-4: Anger Absorption and De-escalation**
- **RC-5: Self-Nullification**

The formal controlled dataset contains **477 independent prompt-response trials**. A balanced subset of **96 trials** was used for blind second-pass reannotation and within-researcher reliability analysis.

## Repository Structure

```text
project-18-layer-1b-avoidance-recomposition-signatures/
|
|-- README.md
|-- data/
|   |-- Layer1B_dataset_coding_ready.xlsx
|   |-- Layer1B_pass2_blind_reannotation.xlsx
|   `-- raw_outputs/
|-- analysis/
|   |-- Layer1B_reliability_analysis.xlsx
|   `-- Layer1B_reliability_report.txt
`-- code/
    |-- run_experiment.py
    |-- config.example.json
    `-- requirements.txt
```

## Data and Materials

- `data/Layer1B_dataset_coding_ready.xlsx`  
  Controlled prompt-response dataset and coding workbook for the formal Layer 1.B study.

- `data/Layer1B_pass2_blind_reannotation.xlsx`  
  Blind second-pass reannotation subset used for within-researcher reliability analysis.

- `data/raw_outputs/`  
  Raw API output JSON files from the controlled prompt-response execution.

- `analysis/Layer1B_reliability_analysis.xlsx`  
  Reliability workbook containing pass1/pass2 comparison, agreement summaries, reliability calculations, and disagreement tables.

- `analysis/Layer1B_reliability_report.txt`  
  Text summary of validation and reliability results.

- `code/run_experiment.py`  
  Script used to run independent prompt-response trials through the OpenAI Responses API.

- `code/config.example.json`  
  Example execution configuration. No API key or private configuration is included.

## Controlled Trial Design

The controlled dataset includes:

- 477 independent prompt-response trials
- 159 unique prompt variants
- 3 repeated runs per prompt variant
- 5 response-stabilization signatures
- 3 contrastive conditions:
  - Target condition
  - Minimal-control condition
  - Counterfactual condition

Each trial was executed as an independent API request. No prior prompt, response, browsing, tools, memory, or conversation history was included in later requests.

## Reliability Summary

A balanced subset of 96 trials was blindly reannotated by the same researcher after the first coding pass. These values should be interpreted as within-researcher coding consistency, not inter-rater generalizability.

| Coding variable | Scale type | Reannotated trials | Krippendorff's alpha | Interpretation |
|---|---:|---:|---:|---|
| Primary RC label | Nominal | 96 | 0.801 | High within-researcher stability |
| Transformation intensity | Ordinal | 96 | 0.802 | High within-researcher stability |
| Recomposition signature | Binary | 96 | 0.779 | Substantial within-researcher stability |
| Interpretive stabilization marker | Binary | 96 | 0.779 | Substantial within-researcher stability |

## Data Availability and Redistribution Notes

The materials in this repository are provided for transparency and reproducibility. The controlled raw outputs consist of model-generated responses to researcher-constructed prompts. No human-subject experiment was conducted for the controlled dataset.

Where external public datasets are discussed in the manuscript, redistribution of externally sourced text may be subject to the terms of the original dataset providers. This repository is intended to provide controlled study materials, coding workbooks, reliability materials, code, and documentation sufficient to audit the reported analyses while respecting anonymization and source-dataset redistribution constraints.

## Reuse and Citation

If citing this project, please cite the associated manuscript:

> Jeong, W. Response-Stabilization Signatures in Human-LLM Interaction: A Black-Box Behavioral Framework for Evaluating Conversational AI Responses. Manuscript submitted to the International Journal of Human-Computer Interaction.

## License

Unless a separate license file is later added, this repository is provided for scholarly review, transparency, and reproducibility. Reuse of code, data, and model outputs should cite the associated manuscript and respect any applicable source-dataset redistribution constraints.
