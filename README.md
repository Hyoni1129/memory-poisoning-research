# memory-poisoning-research

Formal research repository for the undergraduate project on memory poisoning in consolidated memory systems.

## Research Goal
Build and evaluate reproducible experiments that test how poisoning-style interventions affect memory consolidation, retrieval reliability, and downstream system behavior.

## Purpose Of This Repository
This repository is for formal, reusable research artifacts:
- source code
- configuration files
- experiment definitions and run metadata
- results (tables, figures, logs)
- analysis summaries tied to concrete runs
- paper drafting assets

Use the companion repository for process notes, reflective logs, and day-to-day research thinking:
- Related repository: `memory-poisoning-lab-notes`
- Planned GitHub URL: `https://github.com/<your-username>/memory-poisoning-lab-notes`
- Local path (sibling repo): `../memory-poisoning-lab-notes`

## What Goes Here vs Lab Notes
Use this repo when content is part of the reproducible research artifact.

Keep in `memory-poisoning-research`:
- code and scripts
- experiment setup and metadata
- curated datasets and references to raw sources
- run outputs and summarized analysis

Keep in `memory-poisoning-lab-notes`:
- daily logs and meeting notes
- decision rationale and alternatives
- deep research reports (including LLM-assisted research)
- reading notes and idea capture
- failure narratives beyond formal result summaries

## Directory Overview
- `configs/`: experiment and pipeline config files
- `data/`: raw, processed, and final data staging
- `src/`: implementation modules
- `experiments/`: experiment folders and templates
- `results/`: generated figures, tables, and logs
- `analysis/`: interpretation notes and analysis templates
- `paper/`: outline, draft, and references for writing
- `scripts/`: lightweight command helpers and runners
- `docs/`: repository conventions and workflow documentation

## Experiment ID Convention
Use shared IDs across both repositories:

`exp_###_<short_snake_case_slug>`

Examples:
- `exp_001_baseline`
- `exp_002_poison_authority`
- `exp_003_random_injection_control`

When an experiment appears in lab notes, include the same `exp_###_...` identifier.

## Initial Workflow
1. Define scope and success criteria in `docs/research-scope.md`.
2. Create an experiment from `experiments/exp_template/`.
3. Record planning and rationale in `memory-poisoning-lab-notes`.
4. Run code/scripts and save outputs to `results/`.
5. Add interpretation notes under `analysis/`.
6. Update paper materials in `paper/` when insights are stable.

Detailed guidance:
- `docs/experiment-workflow.md`
- `docs/naming-conventions.md`
- `docs/commit-message-guide.md`

## Start Here
1. Read `SETUP_SUMMARY.md`.
2. Review `docs/README.md`.
3. Create your first experiment folder using `experiments/exp_template/`.
4. Log your first daily and decision notes in `memory-poisoning-lab-notes`.
