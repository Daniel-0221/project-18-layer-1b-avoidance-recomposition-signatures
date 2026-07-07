# Layer 1.B Study 2 Data Dictionary

This file documents the public-facing Study 2 external-source validation workbook:

`Layer1B_Study2_public_source_confirmation_20260708.xlsx`

Each row represents one candidate external-source validation case used to assess whether the response-stabilization signatures reported in Study 1 are also observable in externally sourced public human-LLM interaction or alignment materials.

## Key Columns

- `study2_case_id`: Canonical Study 2 case identifier.
- `source_id`: Source group identifier.
- `source_dataset`: Public source component associated with the case.
- `primary_rc`: Primary response-stabilization signature label.
- `candidate_strength`: Strength or status of the candidate case.
- `inclusion_status`: Inclusion or exclusion decision for the public validation set.
- `source_assistant_text_used_for_coding`: Indicates whether the original source assistant response was used as behavioral evidence.
- `target_model_used_for_coding`: Model or source of the response used for coding.
- `screening_note`: Short note describing the basis for inclusion or screening.
- `redaction_or_redistribution_note`: Note on whether source text is omitted, summarized, or restricted for redistribution reasons.

## Source Components

Study 2 uses material derived from the following public source components:

- LMSYS-Chat-1M
- WildChat
- OpenAssistant/oasst1
- Anthropic/hh-rlhf
- A ShareGPT-derived prompt-only component

For the ShareGPT-derived component, user prompts were used as prompts only; original ShareGPT assistant turns were not used for coding. Responses for that component were regenerated for analysis.

## Redistribution Note

External-source raw text may be subject to the terms of the original dataset providers. The public workbook therefore emphasizes source identifiers, inclusion decisions, derived coding fields, and documentation sufficient to audit the reported analysis without unnecessarily redistributing raw public-user text.

## Summary Counts

The public Study 2 source summary is provided in:

`Layer1B_Study2_SOURCE_SUMMARY_FOR_CONFIRMATION_v1_20260625.csv`
