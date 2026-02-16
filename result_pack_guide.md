# Result Pack Guide

Goal: package experiment outputs so **Result-to-Paper Engine (R2P)** can draft without manual copy/paste.

## Directory Layout (Recommended)

```text
result_pack/
  research_blueprint.json
  result_schema.json
  experiment_results.json
  artifacts/
    tables/
    figures/
    logs/
    checkpoints/   (optional)
```

## Minimal Required Files

- `research_blueprint.json`
- `result_schema.json`
- `experiment_results.json`

## Naming Conventions

- `experiment_results.json` must validate against `experiment_results.schema.json`.
- `experiment_id` must match `research_blueprint.json.experiment_matrix[*].id`.
- `variant` and `baseline` strings must match those declared in the blueprint.

## Required Content in `experiment_results.json`

- `runs`: per-seed results, including timing (`wall_ms`, `tokens_generated`, `tokens_per_sec`).
- `aggregates`: mean and dispersion for each `(experiment_id, dataset, variant, baseline)`.
- `artifacts`: relative paths to generated tables/figures/logs.

## Aggregation Rules (Default)

- `summary`: mean of metrics across seeds
- `dispersion`: std across seeds

If you compute confidence intervals, store them under `dispersion` with explicit key names.

## Example Snippet (One Aggregate Item)

```json
{
  "experiment_id": "E1",
  "dataset": "GSM8K",
  "variant": "retrieved_skeleton",
  "baseline": "vanilla_slm",
  "summary": {
    "accuracy": 0.62,
    "avg_output_tokens": 210.4,
    "avg_latency_ms": 95.2
  },
  "dispersion": {
    "accuracy_std": 0.01,
    "avg_output_tokens_std": 8.1,
    "avg_latency_ms_std": 3.4
  }
}
```

## Adding New Ablations Safely

- Add a new experiment entry to `blueprint.experiment_matrix` with a new id (e.g., `E_new`).
- Add matching `runs` and `aggregates` for `E_new` in `experiment_results.json`.
- Do NOT rename existing ids (breaks linkage).
