# Skills Research

`skills-research` is a prompt-and-contract repository for an autonomous research workflow:

1. `ARS` (planning): generate a full research plan from one idea.
2. Human execution: run experiments and collect results in a strict JSON format.
3. `R2P` (writing): draft a paper from the plan + results.

The repository provides controller prompts, output contracts, schemas, and sample files so the pipeline is reproducible and machine-readable.

## Pipeline Overview

1. Planning (`ARS`)
- Use `AUTONOMOUS_RESEARCH_SYSTEM.md`.
- Output files are defined by `OUTPUT_CONTRACT.md`.
- Quick trigger template: `RUN_PLANNING.txt` or `CHATGPT_ONE_SHOT_TRIGGERS.md`.

2. Execution (human)
- Run experiments according to `experiment_design.md` and `result_schema.json`.
- Save outputs as `experiment_results.json` following `experiment_results_schema.json`.
- Package outputs with `result_pack_guide.md`.

3. Drafting (`R2P`)
- Use `RESULT_TO_PAPER_ENGINE.md`.
- Inputs: `research_blueprint.json`, `experiment_results.json`, and optional `paper_seed.md`.
- Output templates are listed in `RUN_WRITING.txt`.

## Repository Contents

- `AUTONOMOUS_RESEARCH_SYSTEM.md`: ARS controller prompt (end-to-end planning driver).
- `OUTPUT_CONTRACT.md`: required artifact list and formatting contract for ARS outputs.
- `operations.md`: high-level 3-phase workflow (planning -> execution -> writing).
- `RESULT_TO_PAPER_ENGINE.md`: R2P controller prompt for autonomous paper drafting.
- `RUN_PLANNING.txt`: one-shot planning trigger text.
- `RUN_WRITING.txt`: one-shot drafting trigger text.
- `CHATGPT_ONE_SHOT_TRIGGERS.md`: compact ChatGPT trigger prompt.
- `NOTEBOOKLM_SINGLE_TRIGGER.md`: optional literature-ingestion prompt.
- `research_blueprint_schema.json`: schema for `research_blueprint.json`.
- `research_blueprint_sample.json`: sample blueprint payload.
- `experiment_results_schema.json`: schema for `experiment_results.json`.
- `experiment_results_sample.json`: sample results payload.
- `result_pack_guide.md`: packaging guide for result bundles.

## Quick Start

1. Put your idea paragraph into `RUN_PLANNING.txt` and run ARS with `AUTONOMOUS_RESEARCH_SYSTEM.md`.
2. Generate and keep the ARS artifacts defined in `OUTPUT_CONTRACT.md`.
3. Execute experiments and write `experiment_results.json` matching `experiment_results_schema.json`.
4. Run R2P using `RUN_WRITING.txt` and `RESULT_TO_PAPER_ENGINE.md`.
5. Review generated drafts and evidence gaps (`appendix_next_runs.md`, if produced).

## Notes

- Sample JSON files are illustrative and include `SAMPLE` placeholders.
- The prompts are designed with a no-questions policy: missing details should be handled via explicit assumptions in outputs.
- `LICENSE` is MIT.
