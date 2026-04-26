# GibNat Satflow Assets

Static Satflow marketplace export for the currently minted `dmt-gibnat`
collection.

## Files

- `satflow-gibnats.json` — Satflow ingestion JSON.
- `icon.jpg` — collection icon image.
- `images/` — rendered PNGs named by inscription id.
- `image-manifest.json` — inscription id to local image path and DMT block.
- `mints.raw.json` — raw ord-tap mint records fetched for the export.
- `mints.success.json` — successful `fail:false` records used in the export.
- `summary.json` — export counts and generation settings.

## GitHub Pages URLs

The JSON uses image URLs with this base:

```text
https://trac-systems.github.io/gibnat-satflow-assets/images
```

Collection icon URL:

```text
https://trac-systems.github.io/gibnat-satflow-assets/icon.jpg
```

Enable GitHub Pages for this repository from the `main` branch root so the image
URLs resolve publicly.

## Refresh

Regenerate from the local GibNat workspace:

```sh
node satflow/export-satflow.js \
  --out gibnat-satflow-assets \
  --image-base-url https://trac-systems.github.io/gibnat-satflow-assets/images
```
