# Phase 02 Payload Templates

This folder contains the shared JSON templates used to render controlled Phase 02 payload and control text for Mem0 storage and retrieval experiments.

## Files

| File | Role |
| --- | --- |
| `authority_payload.json` | Authority Framing payload template for the poisoned condition. |
| `random_control.json` | Matched non-directive control template for the random-control condition. |

## Provenance

- Source daily log: `memory-poisoning-lab-notes/03_daily_log/daily-2026-06-03.md`
- Source decision note: `memory-poisoning-lab-notes/02_decision_log/decision-2026-06-03-payload-json-policy.md`
- Source config path: `memory-poisoning-lab-notes/05_experiment_notes/Phase_02/config/`
- Related dataset ID: `selected_25`
- Related experiment IDs: `Phase_02_Payload_Insertion`, `Exp_002_Mem0_Storage_Retrieval`
- Validation status: published as active Phase 02 templates on 2026-06-03.

## Use

Use `authority_payload.json` as the only Authority Framing payload template for the poisoned condition. Use `random_control.json` as the matched non-directive control template.

The URL-like strings in these templates are inert benchmark-style text for storage and retrieval measurement. Do not execute, open, validate, fetch, or send network requests to any URL rendered from these templates.

The template library includes shopping, classifieds, and reddit domain keys. The frozen final-25 dataset currently uses shopping and reddit rows only; validators should check a rendered payload against the selected domain, not against every domain in the full template library.

## Expected Manifest Linkage

Rendered payload or control artifacts should record at least:

- trajectory ID
- source file
- output file
- condition
- payload or control family
- domain
- sample ID
- nonce
- canary
- insertion step and field
- rendered text SHA-256
- creation time
