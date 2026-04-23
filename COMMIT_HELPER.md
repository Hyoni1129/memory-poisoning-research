# Commit Helper

Quick reference for clean, consistent commits.

## Commit Prefixes
- `feat`: new code capability
- `fix`: bug fix
- `exp`: experiment setup/run/update
- `analysis`: interpretation or failure analysis update
- `data`: data movement, curation, schema changes
- `docs`: documentation updates
- `chore`: maintenance, non-functional housekeeping

## Fast Patterns
- `exp: run exp_002_poison_authority initial prompt variant`
- `analysis: summarize retrieval miss patterns for exp_002_poison_authority`
- `feat: add normalization step for conversation traces`
- `docs: update naming conventions for result IDs`

## Optional Linking Tags In Commit Body
Use one line per reference to connect context across repositories:

```text
exp_id: exp_002_poison_authority
lab_note: daily-2026-04-24.md
decision_note: decision-2026-04-24-baseline-retriever.md
```

Consistency beats perfection. Short and clear is enough.
