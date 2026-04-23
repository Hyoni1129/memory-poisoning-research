# Naming Conventions

## Experiment IDs
Format:

`exp_###_<short_snake_case_slug>`

Examples:
- `exp_001_baseline`
- `exp_002_poison_authority`
- `exp_003_random_injection_control`

Rules:
- Use a zero-padded 3-digit index.
- Keep slugs short and descriptive.
- Do not rename old IDs after publishing results.

## Result IDs
Suggested format:

`res_<exp_id>_<artifact_type>_<version>`

Examples:
- `res_exp_002_poison_authority_table_v1`
- `res_exp_002_poison_authority_figure_v2`

## File And Directory Style
- Use `snake_case` for directories and generated files.
- Use `YYYY-MM-DD` for date-based filenames.
- Prefer concise, descriptive names over abbreviations.

## Cross-Repository Linking
When a note in `memory-poisoning-lab-notes` discusses an experiment, include the exact experiment ID in the note title or header.
