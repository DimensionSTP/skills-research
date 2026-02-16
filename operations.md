# Operations

This folder defines a fully autonomous research planning + paper drafting system.

## Phase 1: Planning (One-Shot)

- Use `AUTONOMOUS_RESEARCH_SYSTEM.md` as the controller prompt.
- Provide only: the idea paragraph (and optionally constraints).
- The agent must emit the 6 artifacts defined in `OUTPUT_CONTRACT.md`.

## Phase 2: Execution (Human)

- Implement experiments exactly as specified by `experiment_design.md` and `result_schema.json`.
- Save results in `experiment_results.json` (validate against `experiment_results.schema.json`).
- Package outputs per `result_pack_guide.md`.

## Phase 3: Writing (One-Shot)

- Use `RESULT_TO_PAPER_ENGINE.md` as the writing prompt.
- Provide `research_blueprint.json` and `experiment_results.json` (and `paper_seed.md` if available).
- The agent outputs `paper_draft.md` and companion files.
