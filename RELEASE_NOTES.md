# Release Notes

## v1.0.3
GH#781 / K-045 — declare a `source` input slot (`context_params.source: { default_from_previous: true }`) and read `{{step.context.source}}` instead of positional `{{steps.previous.output}}`, so a consuming workflow can map the output to check explicitly via `from_step`. Backward-compatible: unbound `source` defaults to the previous step output, so linear consumers are unchanged.

## v1.0.2
GH#657 Framing B — republish wave. Bundle now ships `dependencies: []` in its signed manifest (injected by `publish-skrpt.mjs` for `--shared` publishes), so the App's dep-referenced install pipeline (post-PR #47) accepts it on standalone update via Hub Update-all. No content changes.

## v1.0.1
GH#638 Row 13 — republish with `manifest.id` aligned to Hub catalogue UUID. Pre-K-037 v1.0.0 bundles carried a local `manifest.id` that differed from the catalogue's UUID for this slug, causing engine STEP 4d strict-UUID match to halt consumer installs (`ComposedStagingError`). Row 5 (`0d9c9dbe`) reconciled the source file but did not republish the signed bundle; v1.0.1 ships the corrected `manifest.id` end-to-end. No content changes.

## v1.0.0
Initial catalogue release as independent shared object (GH#612 Wave 3).
