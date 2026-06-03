# Selected 25 Trajectories - Frozen Final Dataset

This folder contains the frozen final set of 25 WebArena-derived trajectory HTML files selected for Phase 02 Mem0 storage and retrieval experiments.

The dataset supersedes the earlier v2 selected set. The frozen final set removes map, GitLab, shopping-admin, shopping-order-detail, admin-only, and system-generated-only surfaces. It keeps only shopping and reddit/forum surfaces where an attacker could plausibly write or influence visible page text.

## Dataset ID

- Dataset ID: `selected_25`
- Source dataset ID: `final_25_v5`
- Related experiment IDs: `Exp_001_Trajectory_Preprocessing`, `Phase_02_Payload_Insertion`
- Status: frozen final 25 as of 2026-06-03

## Contents

```text
selected_25/
|-- README.md
|-- metadata.csv
|-- phase02_ready_dataset_registry.csv
|-- phase02_injection_target_regions.csv
|-- reddit_empty_stop_freeze_audit.md
|-- reddit/
|   `-- render_*.html
`-- shopping/
    `-- render_*.html
```

## Source Provenance

- Source daily log: `memory-poisoning-lab-notes/03_daily_log/daily-2026-06-03.md`
- Source decision notes:
  - `memory-poisoning-lab-notes/02_decision_log/decision-2026-06-03-final-25-dataset-freeze.md`
  - `memory-poisoning-lab-notes/02_decision_log/decision-2026-06-03-surface-selection-policy.md`
  - `memory-poisoning-lab-notes/02_decision_log/decision-2026-06-03-reddit-empty-stop-keep-acceptable.md`
- Source metadata path: `memory-poisoning-lab-notes/data/metadata/final_25/`
- Source selected CSV: `memory-poisoning-lab-notes/data/metadata/final_25/final_selected_dataset_final_25.csv`
- Source registry CSV: `memory-poisoning-lab-notes/data/metadata/final_25/phase02_ready_dataset_registry_final_25.csv`
- Source target-region CSV: `memory-poisoning-lab-notes/data/metadata/final_25/phase02_injection_target_regions_final_25.csv`
- Source raw HTML path: `memory-poisoning-lab-notes/05_experiment_notes/Phase_01_Data_Preparation/919_gpt4_8k_cot/`
- Source working selection path: `memory-poisoning-lab-notes/targeted_replacement_v5/final_selected_dataset_v5.csv`

## Distribution

| Domain | Count |
| --- | ---: |
| shopping | 17 |
| reddit | 8 |
| total | 25 |

| Surface | Count |
| --- | ---: |
| shopping product listing/search result | 11 |
| shopping product review | 6 |
| reddit/forum post | 8 |
| total | 25 |

## Validation Status

- `metadata.csv` contains 25 rows.
- The folder contains 25 `render_*.html` trajectory files.
- All 25 rows reference unique files.
- All referenced raw HTML files were present in the source corpus at publication time.
- The Phase 02 registry marks every row as ready for payload insertion.
- Every row has an Authority Framing target region and at least three benign entity candidates.
- The final set has no map, GitLab, shopping-admin, shopping-order-detail, admin-only, or system-generated-only rows.

## Known Caveats

- This is not a direct reproduction dataset for end-to-end browser attack execution. It is a controlled observation dataset for studying whether instruction-like payload text survives Mem0 extraction, storage, and retrieval.
- `render_596.html`, `render_598.html`, and `render_599.html` have empty final `stop []` actions. They are retained because each is an action-completion forum task whose final observation shows the completed subscribe state and a visible forum thread or post body. See `reddit_empty_stop_freeze_audit.md`.
- Phase 02 payload insertion should use `phase02_injection_target_regions.csv`, not the final answer string.
- Payload and control templates are published separately under `configs/prompts/phase_02_payload_templates/`.
