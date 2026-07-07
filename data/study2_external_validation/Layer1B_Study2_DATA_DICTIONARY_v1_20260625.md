# Layer 1.B Study 2 Data Dictionary

This folder contains a clean, repository-ready Study 2 external-data confirmation package.

## Core merged file

`Layer1B_Study2_ALL_SOURCES_MERGED_FOR_CONFIRMATION_v1_20260625.csv`

Each row is one candidate public/naturalistic external recovery case for Layer 1.B.

## Key columns

- `study2_case_id`: canonical row ID assigned in this clean package.
- `source_id`: source group. A=LMSYS, B=WildChat, C=OASST1, D=HH-RLHF, E1=ShareGPT prompt-only GPT-5.5 v1, E2=ShareGPT prompt-only GPT-5.5 extra.
- `primary_rc_current`: current RC label before final audit confirmation.
- `candidate_strength`: `LOCK_READY_DRAFT`, `REVIEW_STRICT`, or `PENDING_USER_CONFIRMATION`.
- `confirmation_status`: `QUICK_CONFIRM` or `CONFIRM_REQUIRED`.
- `paper_eligible_current`: current paper-use flag before final confirmation.
- `redaction_required_later`: whether this row should be considered for later masking/redaction before public release.
- `source_assistant_text_used_for_coding`: whether the original source assistant answer was used as behavioral evidence.
- `target_model_used_for_coding`: model/source of the response used for coding.
- `user_text_raw`: raw user-side text retained for analysis.
- `assistant_text_raw`: raw assistant-side text used for coding.
- `previous_context_excerpt`: optional context excerpt when available.
- `screening_note`: reason for inclusion or screening judgment.
- `user_confirmed_inclusion`: blank column for user confirmation. Suggested values: `INCLUDE`, `EXCLUDE`, `NEEDS_REVIEW`.
- `user_final_rc`: blank column for corrected final RC if the final audit changes the label.
- `user_final_notes`: blank column for final notes.

## Important methodological note

Source E uses ShareGPT-derived user prompts only. Source assistant turns were not used for coding.
All analyzed Source E responses were regenerated with `gpt-5.5-2026-04-23`.

## Current pre-confirmation count

- Total candidate cases: 212
- RC-1: 55
- RC-2: 38
- RC-3: 26
- RC-4: 48
- RC-5: 45

These should be described as a curated external recovery set until final confirmation is completed.
