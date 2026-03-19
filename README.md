# Skills Research

`skills-research` is a prompt-and-contract repository for an autonomous research workflow:

1. `ARS` (planning): generate a full research plan from one idea.
2. Human execution: run experiments and collect results in a strict JSON format.
3. `R2P` (writing): draft a paper from the plan + results.

The repository provides controller prompts, output contracts, schemas, sample payloads, and starter templates so the pipeline is reproducible and machine-readable.

## Documentation Hub

- Korean overview: `README_ko.md`
- Detailed usage (EN): `USAGE_GUIDE.md`
- Detailed usage (KO): `USAGE_GUIDE_ko.md`
- Workflow cheatsheet: `research-workflow-cheatsheet.md`
- Contribution rules: `CONTRIBUTING.md`
- Change history: `CHANGELOG.md`

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

- `AUTONOMOUS_RESEARCH_SYSTEM.md`: ARS controller prompt.
- `OUTPUT_CONTRACT.md`: required artifact list and formatting contract.
- `operations.md`: 3-phase workflow overview.
- `RESULT_TO_PAPER_ENGINE.md`: R2P controller prompt.
- `RUN_PLANNING.txt`: one-shot planning trigger.
- `RUN_WRITING.txt`: one-shot drafting trigger.
- `CHATGPT_ONE_SHOT_TRIGGERS.md`: compact trigger prompt.
- `NOTEBOOKLM_SINGLE_TRIGGER.md`: optional literature-ingestion prompt.
- `research_blueprint_schema.json`: schema for `research_blueprint.json`.
- `research_blueprint_sample.json`: sample blueprint payload.
- `experiment_results_schema.json`: schema for `experiment_results.json`.
- `experiment_results_sample.json`: sample results payload.
- `result_pack_guide.md`: result packaging guide.
- Starter templates:
  - `experiment_design.md`
  - `result_schema.json`
  - `research_blueprint.json`
  - `experiment_results.json`
  - `paper_seed.md`
  - `appendix_next_runs.md`

## Quick Start

1. Put your idea paragraph into `RUN_PLANNING.txt` and run ARS with `AUTONOMOUS_RESEARCH_SYSTEM.md`.
2. Generate and keep the ARS artifacts defined in `OUTPUT_CONTRACT.md`.
3. Execute experiments and write `experiment_results.json` matching `experiment_results_schema.json`.
4. Run R2P using `RUN_WRITING.txt` and `RESULT_TO_PAPER_ENGINE.md`.
5. Review generated drafts and evidence gaps (`appendix_next_runs.md`).

## Notes

- Sample JSON files are illustrative and include `SAMPLE` placeholders.
- The prompts are designed with a no-questions policy: missing details should be handled via explicit assumptions in outputs.
- `LICENSE` is MIT.

## Compatibility and Migration

- Keep artifact naming aligned with `OUTPUT_CONTRACT.md`.
- If artifact filenames/contracts change, update `README.md`, guides, and contract docs together.
