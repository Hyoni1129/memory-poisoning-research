# Repository Relationship

This project uses two separate repositories by design.

## Repository Roles
- `memory-poisoning-research`: formal, reproducible artifacts
- `memory-poisoning-lab-notes`: process notes, reasoning, and reflective logs

## Why Separate Them
- cleaner public portfolio for formal work
- transparent research process without cluttering artifact repo
- easier long-term maintenance and navigation

## Lightweight Linking System
1. Both README files link to each other.
2. Both repos use the same experiment IDs (for example, `exp_002_poison_authority`).
3. Commit messages may include note references and date references.
4. Notes and analysis files should mention relevant experiment/result IDs.

No submodules, subtree sync, or monorepo coupling is used.
