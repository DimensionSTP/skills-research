# Output Contract

ARS MUST output exactly the following files.

If a file is not applicable, it must still be produced with an explanation and assumptions.

## 1) `research_blueprint.json`

Purpose: single source of truth for the entire research plan.

Requirements:

- Must conform to `research_blueprint.schema.json`.
- Must be self-contained (no external references required to parse).

## 2) `experiment_design.md`

Purpose: human-readable plan that matches `research_blueprint.json`.

Must include:

- RQ and summary
- Contributions (measurable)
- Taxonomy and novelty positioning
- Hypotheses (with load-bearing marking)
- Baselines and controls
- Decisive experiments (top 3 + single best)
- Full experiment matrix
- Metrics (accuracy + efficiency)
- Compute plan
- Expected outcomes and interpretation rules
- Confounds and mitigation

## 3) `risk_report.md`

Purpose: reviewer-preemptive attack/defense.

Must include:

- Reviewer #2 Top 5 major concerns
- Minor concerns
- Killer questions list
- Required mitigations with minimal-scope fixes
- Accept-conditions checklist (pass/fail)

## 4) `paper_seed.md`

Purpose: a seed pack for an autonomous writing agent.

Must include:

- Title candidates (10)
- Abstract skeleton
- Paper outline (Intro/Related/Method/Experiments/Discussion/Limitations)
- Claim registry snapshot (claim -> required evidence -> where it appears)
- Figure/table plan
- Writing constraints (no vague claims, etc.)
- Placeholders for results (explicit keys that match `result_schema.json`)

## 5) `result_schema.json`

Purpose: a strict schema for experiment outputs.

Requirements:

- Must conform to `experiment_results.schema.json`.
- Must define:
  - required runs
  - metric names and units
  - aggregation rules
  - artifact paths (logs, checkpoints if needed)
  - reproducibility fields (seed, code commit, config hash)

## 6) `result_pack_guide.md`

Purpose: instructions for packaging results so the paper engine can draft automatically.

Must include:

- Directory structure for the result pack
- Naming conventions
- Minimal required files
- Examples for JSON payloads
- How to add new ablations without breaking schema
