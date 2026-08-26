# GibNat Satflow Assets

Public assets and native gallery-inscription source for the `dmt-gibnat`
collection.

## Files

- `gallery/` contains the current native `ord` gallery source, inscription
  instructions, snapshot counts, and integrity hashes.
- `icon.jpg` is the collection icon and gallery inscription body.
- `images/` contains the current lossless WebP renders named by inscription ID,
  plus the earlier PNG snapshot retained for compatibility.
- `satflow-gibnats.json`, `image-manifest.json`, `mints.raw.json`,
  `mints.success.json`, and `summary.json` are the current Satflow JSON-ingestion
  snapshot.

Satflow no longer accepts new JSON uploads. Use the files and instructions in
[`gallery/`](gallery/) to create the gallery inscription.

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
