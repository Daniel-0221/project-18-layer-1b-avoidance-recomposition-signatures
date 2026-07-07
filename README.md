# Layer 1.B Study 2 External-Source Validation Data

This folder contains public-facing materials for the Study 2 external-source validation component of the Layer 1.B manuscript.

## Purpose

Study 2 examines whether the response-stabilization signatures reported in the controlled Study 1 dataset are also observable in externally sourced public human-LLM interaction or alignment materials.

This package is intended for transparency, auditability, and reproducibility while avoiding unnecessary redistribution of raw public-user text from external datasets.

## Core Files

- `Layer1B_Study2_public_source_confirmation_20260708.xlsx`  
  Public source-confirmation workbook containing source identifiers, adjudication fields, RC labels, inclusion decisions, and derived coding information.

- `Layer1B_Study2_DATA_DICTIONARY_v1_20260625.md`  
  Data dictionary describing the Study 2 external-validation fields.

- `Layer1B_Study2_SOURCE_SUMMARY_FOR_CONFIRMATION_v1_20260625.csv`  
  Source-level summary of candidate counts by dataset component and response-stabilization signature.

## Public Source Components

Study 2 uses material derived from the following public source components:

- LMSYS-Chat-1M
- WildChat
- OpenAssistant/oasst1
- Anthropic/hh-rlhf
- A ShareGPT-derived prompt-only component

For the ShareGPT-derived component, user prompts were used as prompts only; original ShareGPT assistant turns were not used for coding.

## Redistribution Note

External-source raw text may be subject to the terms of the original dataset providers. This public package therefore emphasizes source identifiers, inclusion decisions, derived coding fields, and documentation rather than redistributing unnecessary raw public-user text.
