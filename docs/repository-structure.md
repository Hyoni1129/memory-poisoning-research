# Repository Structure

## Root Directories
- `configs/`: YAML or JSON configs for experiments and pipelines
- `data/`: staged data (`raw/`, `processed/`, `final/`)
- `src/`: source code modules by function
- `experiments/`: experiment definitions and template folder
- `results/`: generated outputs (`tables/`, `figures/`, `logs/`)
- `analysis/`: interpretation documents and analysis templates
- `paper/`: outline, manuscript draft, references
- `scripts/`: simple command entry points and utilities
- `docs/`: repository operating guides

## Design Logic
- Keep artifacts clean and reproducible.
- Keep process-heavy reasoning in companion lab notes repo.
- Keep experiment IDs stable across code, results, and notes.

## Artifact Traceability Rule
Each major result should be traceable to:
1. experiment ID
2. config reference
3. output location
4. interpretation note
