# Project 18 — Layer 1.B Avoidance-and-Recomposition Signatures

This repository contains the execution materials, dataset, coding materials, and reliability analysis for the Layer 1.B study:

**Avoidance and Recomposition in Large Language Model Interaction:  
A Black-Box Behavioral Analysis of Five Response-Stabilization Signatures**

Layer 1.B analyzes observable avoidance-and-recomposition patterns in large language model interaction under black-box conditions. The study does not claim access to model internals, hidden mechanisms, latent representations, or proprietary safety systems. Instead, it examines recurring input-output regularities in prompt-response behavior.

## Overview

The project investigates five response-stabilization signatures:

- **RC-1: Constrained Neutralization**
- **RC-2: Meaning Recomposition**
- **RC-3: Sharpness Attenuation**
- **RC-4: Anger Absorption and De-escalation**
- **RC-5: Self-Nullification**

The formal dataset contains **477 independent prompt-response trials**. A subset of **96 trials** was used for blind pass2 reannotation and intra-rater reliability analysis.

## Core Principles

- Each trial was executed as an independent API request.
- No previous prompt or response was included in any later request.
- No system prompt, tools, browsing, memory, or conversation history was used.
- Trials were executed according to randomized order.
- The analysis is restricted to observable prompt-response behavior.
- RC labels are behavioral descriptors, not claims about internal model modules.
- Reliability values should be interpreted as within-researcher consistency, not inter-rater generalizability.

## Repository Structure

```text
project-18-layer-1b-avoidance-recomposition-signatures/
│
├─ README.md
├─ paper/
│  └─ Layer1B_manuscript.docx
│
├─ data/
│  ├─ Layer1B_dataset_coding_ready.xlsx
│  ├─ Layer1B_pass2_blind_reannotation.xlsx
│  └─ raw_outputs/
│
├─ analysis/
│  ├─ Layer1B_reliability_analysis.xlsx
│  └─ Layer1B_reliability_report.txt
│
└─ code/
   ├─ run_experiment.py
   ├─ config.example.json
   └─ requirements.txt
```

## Package Contents

### Paper

- `paper/Layer1B_manuscript.docx`  
  Final Layer 1.B manuscript.

### Data

- `data/Layer1B_dataset_coding_ready.xlsx`  
  Final coding-ready dataset containing the formal Layer 1.B trial data.

- `data/Layer1B_pass2_blind_reannotation.xlsx`  
  Blind pass2 reannotation subset used for intra-rater reliability analysis.

- `data/raw_outputs/`  
  Raw API output JSON files from the formal prompt-response execution.

### Analysis

- `analysis/Layer1B_reliability_analysis.xlsx`  
  Workbook containing pass1/pass2 comparison, agreement summaries, reliability calculations, and disagreement tables.

- `analysis/Layer1B_reliability_report.txt`  
  Text summary of validation results, Krippendorff’s alpha values, and table-ready reliability results.

### Code

- `code/run_experiment.py`  
  API execution script used to run the formal prompt-response trials.

- `code/config.example.json`  
  Example configuration file.

- `code/requirements.txt`  
  Required Python packages.

## Dataset Summary

The formal dataset includes:

- **477 independent prompt-response trials**
- **159 unique prompt variants**
- **3 repeated runs per prompt variant**
- **5 RC signatures**
- **3 contrastive conditions**
  - Target condition
  - Minimal control condition
  - Counterfactual condition

The trial structure was designed to test whether specific prompt-pressure dimensions are associated with observable response-stabilization signatures.

## Reliability Summary

A blind pass2 reannotation subset of **96 trials** was used to assess intra-rater reliability.

Summary reliability results:

| Coding variable | Scale type | Reannotated trials | Krippendorff’s alpha | Interpretation |
|---|---:|---:|---:|---|
| Primary RC label | Nominal | 96 | 0.801 | High within-researcher stability |
| Transformation intensity | Ordinal | 96 | 0.802 | High within-researcher stability |
| Recomposition signature | Binary | 96 | 0.779 | Substantial within-researcher stability |
| Interpretive stabilization marker | Binary | 96 | 0.779 | Substantial within-researcher stability |

These values indicate within-researcher coding consistency only. They should not be interpreted as inter-rater generalizability.

## Installation

From the `code/` directory:

### Windows PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

### macOS/Linux

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## API Key Setup

### Windows PowerShell

```powershell
$env:OPENAI_API_KEY="YOUR_API_KEY_HERE"
```

### macOS/Linux

```bash
export OPENAI_API_KEY="YOUR_API_KEY_HERE"
```

## Dry Run

Use this command first to verify that the workbook rows are being read correctly.  
This does not call the API.

```bash
python run_experiment.py --input ../data/Layer1B_dataset_coding_ready.xlsx --output ../data/Layer1B_dataset_coding_ready.xlsx --model PUT_EXACT_MODEL_ID_HERE --limit 3 --dry-run
```

## Recommended Full Execution

This command omits sampling parameters by default. This is recommended when the selected model uses a model-compatible default generation setting rather than user-specified `temperature` and `top_p`.

```bash
python run_experiment.py --input ../data/Layer1B_dataset_coding_ready.xlsx --output ../data/Layer1B_dataset_coding_ready.xlsx --model PUT_EXACT_MODEL_ID_HERE --max-output-tokens 900 --omit-sampling-params --save-raw-json
```

## Partial Execution

Example: execute only trials with `random_order` from 1 to 20.

```bash
python run_experiment.py --input ../data/Layer1B_dataset_coding_ready.xlsx --output ../data/Layer1B_dataset_coding_ready.xlsx --model PUT_EXACT_MODEL_ID_HERE --start-order 1 --end-order 20 --omit-sampling-params --save-raw-json
```

## Optional Sampling Parameters

Use this option only if the selected model supports `temperature` and `top_p`.

If the API rejects these parameters, the script retries once without them and records the model-compatible default setting.

```bash
python run_experiment.py --input ../data/Layer1B_dataset_coding_ready.xlsx --output ../data/Layer1B_dataset_coding_ready.xlsx --model PUT_EXACT_MODEL_ID_HERE --include-sampling-params --temperature 0.3 --top-p 1.0
```

## Completion Check

After execution, verify that the following fields are filled in the trial execution sheet:

- `response_text`
- `model_id`
- `execution_date`
- `response_length_chars`
- `raw_output_saved`
- `temperature`
- `top_p`

After this check, proceed to manual coding and reliability analysis using the coding sheets and analysis files.

## Data Availability

The dataset, raw model outputs, coding-ready workbook, blind pass2 reannotation file, and reliability analysis materials are included in this repository for transparency and reproducibility.

The raw outputs consist of model-generated responses from controlled prompts. No personal user data were collected or analyzed.

## Citation

If citing this project, please cite the associated manuscript:

> Jeong, D. Layer 1.B: Avoidance and Recomposition in Large Language Model Interaction — A Black-Box Behavioral Analysis of Five Response-Stabilization Signatures.

## License

License information should be added before public release.
