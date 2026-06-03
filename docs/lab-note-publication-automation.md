# Lab Note Publication Automation

This guide defines how a daily Codex Automation may publish reproducible artifacts from the companion lab-notes repository into this public research repository.

## Purpose

The automation should reduce manual transfer work while preserving the separation between private/process notes and public/reproducible research artifacts.

- Source repository: `../memory-poisoning-lab-notes`
- Target repository: `memory-poisoning-research`
- Public language requirement: all human-authored text committed to this repository must be English.
- Publication principle: publish artifacts, provenance, prompts, configs, and formal summaries; do not publish private reflection or unfinalized reasoning.

## Source Inputs

Use the smallest useful set of lab-note files.

Primary inputs:
- `../memory-poisoning-lab-notes/03_daily_log/daily-YYYY-MM-DD.md`
- decision notes in `../memory-poisoning-lab-notes/02_decision_log/` modified on the same local date
- experiment notes, prompts, scripts, and output files explicitly referenced by the daily or decision notes

Fallback inputs:
- the most recent unprocessed daily log from the last seven local calendar days
- lab-note `git status` and `git diff --name-only` to discover newly modified notes

Do not browse unrelated private notes just because they exist. Treat lab notes as evidence, not as text to copy verbatim.

## Publishability Gates

Publish a candidate artifact only when all gates pass.

1. Evidence gate: a daily log, decision note, or experiment note explicitly says the artifact is final, locked in, approved, canonical, completed, ready for the next phase, or otherwise intended as a public research artifact.
2. Artifact gate: the candidate is code, config, prompt, dataset, run output, result table, figure, formal experiment metadata, or an English analysis summary tied to a concrete experiment or dataset.
3. Path gate: the source file path is explicitly named or can be derived directly from a named manifest, CSV, script output, or dataset folder.
4. Safety gate: the artifact does not contain credentials, API keys, private meeting material, restricted data, private user data, or non-public advisor/reviewer comments.
5. Stability gate: the lab note does not mark the candidate as provisional, draft, uncertain, blocked, needs review, or pending human confirmation.
6. Traceability gate: the published artifact includes enough provenance to identify the source lab note, experiment ID or dataset ID, source path, prompt/config used, and validation status.
7. English gate: public README files, metadata prose, analysis notes, experiment descriptions, and prompt documentation are written in English. Raw source artifacts may preserve their original machine-generated content.

If any gate fails, do not publish the artifact. Summarize the hold reason in the automation result instead of guessing.

## Target Mapping

| Lab-note signal | Public target |
| --- | --- |
| final or canonical dataset | `data/final/<dataset_id>/` |
| raw source data approved for release | `data/raw/<dataset_id>/` |
| cleaned or transformed intermediate data | `data/processed/<dataset_id>/` |
| experiment-specific prompt | `experiments/<exp_id>/prompts/` |
| shared pipeline prompt | `configs/prompts/` |
| experiment metadata or setup | `experiments/<exp_id>/` |
| scripts or reusable helpers | `scripts/` or `src/` |
| run logs | `results/logs/<exp_id>/` |
| figures | `results/figures/<exp_id>/` |
| tables | `results/tables/<exp_id>/` |
| stable interpretation | `analysis/<exp_id>_<topic>.md` |
| process-only decision rationale | keep in lab notes; link or summarize only when needed |

When a new experiment folder is created, copy `experiments/exp_template/` and keep the experiment ID consistent with the lab notes.

## Daily Run Procedure

1. Determine the current local date.
2. Inspect both repository states:
   - research repo: `git status --short --branch --untracked-files=all`
   - lab-notes repo: `git status --short --branch --untracked-files=all`
3. In the research repo, stop before editing if there are tracked changes that are not part of this automation run. Preserve pre-existing untracked files and inspect them before staging.
4. Pull the latest research baseline with `git pull --rebase origin main` when the worktree is safe to update.
5. Read the primary source inputs for the current date. If no current-date log exists, inspect only the most recent unprocessed daily log from the last seven days.
6. Extract candidate artifacts and classify each as `publish`, `hold`, or `skip`.
7. For each `publish` candidate:
   - copy or generate the public artifact in the mapped target path
   - translate human-authored documentation to English
   - include provenance and validation notes
   - avoid copying private reflection or Korean lab-note prose verbatim
8. Run validation:
   - `git diff --check -- . ":(exclude)data/**/render_*.html"` so raw WebArena HTML whitespace is preserved
   - verify expected file counts or CSV row counts for datasets
   - search staged human-authored files for Korean text and translate before commit
9. Stage only the intended public artifacts and supporting documentation.
10. Commit with a concise message from `docs/commit-message-guide.md`. Include commit body references such as `source_daily_log: daily-YYYY-MM-DD.md`, `source_decision_log: ...`, `exp_id: ...`, or `dataset_id: ...`.
11. Push to `origin main`.
12. Verify delivery by fetching and confirming local `HEAD`, cached `origin/main`, and live remote `refs/heads/main` match. If push or verification fails, report the exact blocker and leave local commits intact.

## No-Publication Days

It is correct for the automation to publish nothing on days without final, public-ready artifacts. In that case, leave the research repository unchanged and report:
- source notes inspected
- candidate count
- hold or skip reasons
- current git state

## Current Known Candidate Pattern

Phase 01 data preparation may produce a final selected WebArena trajectory dataset. When a lab note states that `final_selected_dataset_v2.csv` is locked in or canonical, the public target should be `data/final/selected_25/` with:
- `metadata.csv`
- exactly 25 selected `render_*.html` files grouped by site
- an English `README.md`
- provenance pointing to the lab-note source paths and validation notes
