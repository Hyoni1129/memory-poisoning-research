# Setup Summary

This repository was scaffolded as the formal artifact repository for the memory poisoning research project.

## Repository Purpose
- Keep reproducible, publication-oriented assets in one clean location.
- Separate formal artifacts from process-heavy notes in the companion repository.

## What Was Scaffolded
- Root documentation and onboarding:
  - `README.md`
  - `SETUP_SUMMARY.md`
  - `GITHUB_CREATION_INSTRUCTIONS.md`
  - `COMMIT_HELPER.md`
- Documentation system under `docs/`:
  - structure, scope, workflow, naming, commit style, cross-repo relationship
- Core research folders:
  - `configs/`, `data/`, `src/`, `experiments/`, `results/`, `analysis/`, `paper/`, `scripts/`
- Experiment template and metadata starter in `experiments/exp_template/`
- Analysis templates for interpretation and failure review in `analysis/templates/`

## Established Conventions
- Experiment IDs: `exp_###_<short_slug>`
- Shared IDs between this repo and `memory-poisoning-lab-notes`
- Date format in filenames: `YYYY-MM-DD`
- Commit prefixes and linking rules documented in `docs/commit-message-guide.md`

## What To Do First
1. Review `docs/research-scope.md` and adapt objectives.
2. Copy `experiments/exp_template/` for your first planned run.
3. Create matching process notes in `memory-poisoning-lab-notes`.
4. Make your first commit using the commit helper.
