# Experiment Workflow

This workflow is intentionally simple and beginner-friendly.

## 1. Plan
1. Copy `experiments/exp_template/` to a new folder named with your experiment ID.
2. Fill out metadata and define expected outcomes.
3. Record planning rationale in the companion lab-notes repository.

## 2. Prepare
1. Add or update configs in `configs/`.
2. Ensure required input data is documented under `data/`.
3. Add or update scripts in `scripts/` if needed.

## 3. Run
1. Execute run commands.
2. Store raw logs in `results/logs/`.
3. Store plots/tables in `results/figures/` and `results/tables/`.

## 4. Interpret
1. Write a short insight note in `analysis/` based on templates.
2. Capture failure modes and edge cases.
3. Link results to matching experiment IDs.

## 5. Reflect In Lab Notes
Document decisions, day-level progress, and reasoning in `memory-poisoning-lab-notes` with references to the same experiment ID.
