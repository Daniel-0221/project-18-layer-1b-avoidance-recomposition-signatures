# Layer 1.B Study 2 External Data Package

Clean confirmation-ready package generated on 2026-06-25.

## Purpose

This folder is intended to replace the previous working `03_s2` folder for the Layer 1.B paper.
It preserves the main source structure while removing raw scrape files, temporary files, `.venv`, failed runs, and non-paper intermediate artifacts.

## Current package status

This is a **confirmation-ready** package, not the final locked publication package.

- Total candidate external recovery cases: 212
- RC-1: 55
- RC-2: 38
- RC-3: 26
- RC-4: 48
- RC-5: 45
- Duplicate `case_pair_sha1` values found: 0

## Core files

Start here:

`cand/06_Merged_Final/Layer1B_Study2_ALL_SOURCES_MERGED_FOR_CONFIRMATION_v1_20260625.xlsx`

After Daniel confirms rows, use the edited file to produce the final locked external-data file for the manuscript.

## Source folders

- `cand/01_LMSYS`: Source A, LMSYS-Chat-1M candidates.
- `cand/02_WildChat`: Source B, WildChat candidates.
- `cand/03_OASST1`: Source C, OASST1 candidates.
- `cand/04_HH-RLHF`: Source D, HH-RLHF candidates.
- `cand/05_ShareGPT`: Source E, ShareGPT prompt-only + GPT-5.5 regenerated responses.
- `cand/06_Merged_Final`: canonical merged confirmation dataset and summary files.

## Methodological note

Source E follows a prompt-only construction: ShareGPT-derived user prompts were used, but original ShareGPT assistant turns were not used for coding. Responses were regenerated with `gpt-5.5-2026-04-23`.

## Excluded from this clean package

The following were intentionally removed from the previous working archive:

- `.venv`
- raw search/download files
- failed response logs
- one-off runner scripts
- synthetic QA files
- old LMSYS templates and exploratory raw candidate files
- nested duplicate source package folders

Keep the original full archive separately if forensic reconstruction is needed.
