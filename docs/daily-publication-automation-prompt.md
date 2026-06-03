# Daily Publication Automation Prompt

Use this prompt for the Codex Automation that publishes public-ready artifacts from `memory-poisoning-lab-notes` into this repository.

## Prompt

Read `README.md`, `docs/repository-relationship.md`, `docs/repository-structure.md`, `docs/experiment-workflow.md`, `docs/naming-conventions.md`, `docs/commit-message-guide.md`, and `docs/lab-note-publication-automation.md`. Then execute the daily lab-note-to-public-research publication task.

Treat this repository as the public, reproducible artifact repository. Treat `../memory-poisoning-lab-notes` as a private/process source repository. Do not modify the lab-notes repository.

Use the current local date. Inspect `../memory-poisoning-lab-notes/03_daily_log/daily-YYYY-MM-DD.md`, same-date decision notes, and explicitly linked experiment notes, prompts, scripts, manifests, or output files. If there is no current-date daily log, inspect only the most recent unprocessed daily log from the last seven days. Do not browse unrelated private notes.

Publish only artifacts that pass every gate in `docs/lab-note-publication-automation.md`: explicit final/approved/canonical evidence, reproducible artifact type, explicit source path, public-data safety, stable/non-provisional status, traceability, and English public documentation. Hold ambiguous candidates instead of guessing.

All human-authored public text must be English. Translate public README files, metadata prose, analysis summaries, experiment descriptions, and prompt documentation into English. Do not copy Korean lab-note prose verbatim into this repository. Raw machine-generated source artifacts may preserve their original content when required for reproducibility.

Use the repository mapping rules:
- final datasets -> `data/final/<dataset_id>/`
- raw public source data -> `data/raw/<dataset_id>/`
- processed data -> `data/processed/<dataset_id>/`
- experiment-specific prompts -> `experiments/<exp_id>/prompts/`
- shared pipeline prompts -> `configs/prompts/`
- experiment metadata -> `experiments/<exp_id>/`
- run logs -> `results/logs/<exp_id>/`
- figures -> `results/figures/<exp_id>/`
- tables -> `results/tables/<exp_id>/`
- stable interpretation -> `analysis/<exp_id>_<topic>.md`

Before editing, inspect git state in both repositories. In the public research repo, pull with rebase only when there are no tracked local changes. Preserve and inspect pre-existing untracked files before staging them. Never overwrite untracked files blindly.

When publishing, add provenance to the public artifact or nearby README: source lab note, source path, experiment or dataset ID, prompt/config reference, validation status, and known caveats. For datasets, verify expected file counts and CSV row counts.

Run `git diff --check -- . ":(exclude)data/**/render_*.html"` so raw WebArena HTML whitespace is preserved. Search staged human-authored files for Korean text and translate before committing. Stage only intended public artifacts and supporting docs. Commit with a message prefix from `docs/commit-message-guide.md`, include source references in the commit body, push to `origin main`, then verify that local `HEAD`, cached `origin/main`, and live remote `refs/heads/main` match. If remote delivery fails, report the exact blocker and leave local commits intact.

If no artifact is public-ready, leave the research repository unchanged and report source notes inspected, candidates considered, hold or skip reasons, and current git state.
