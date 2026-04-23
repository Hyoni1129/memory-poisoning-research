# Commit Message Guide

Use concise, consistent commit messages. The goal is traceability, not perfection.

## Prefixes
- `feat`: new research code capability
- `fix`: bug fix
- `exp`: experiment run/setup/change
- `analysis`: interpretation or failure-analysis update
- `data`: dataset staging or curation change
- `docs`: documentation changes
- `chore`: maintenance work

## Message Pattern
`<prefix>: <short summary>`

Examples:
- `feat: add preprocessing pipeline for observation normalization`
- `exp: run exp_002_poison_authority with seed sweep`
- `analysis: add retrieval miss analysis for exp_002_poison_authority`
- `docs: update experiment workflow for result logging`

## Linking Across Repositories
When useful, include lightweight references in commit body:

```text
exp_id: exp_002_poison_authority
lab_note: exp-note-exp_002_poison_authority.md
daily_log: daily-2026-04-24.md
```

This keeps formal artifacts connected to process notes without hard technical coupling.
