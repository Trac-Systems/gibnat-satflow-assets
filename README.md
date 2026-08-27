# GibNat Satflow Assets

Public images and metadata for the `dmt-gibnat` collection on Satflow.

## Files

- `icon.jpg` is the collection icon.
- `GIBNAT-RARITY-CATALOGUE.pdf` documents the theoretical 8,064-piece
  full-supply rarity distribution.
- `images/` contains the current lossless WebP renders named by inscription ID,
  plus the earlier PNG snapshot retained for compatibility.
- `satflow-gibnats.json`, `image-manifest.json`, `mints.raw.json`,
  `mints.success.json`, and `summary.json` are the current Satflow metadata
  snapshot.
- `gallery/` is the frozen source and record of the separately confirmed
  4,460-item native `ord` gallery. It is not used to update Satflow and does not
  track later mints.

Satflow collection updates are made through Satflow's interface. This repository
hosts the corresponding images and maintains the complete metadata snapshot; a
new gallery inscription is not part of a Satflow update.

The Satflow ingestion JSON intentionally omits `DMT Block` and
`Inscription Block` attributes because those fields are derived elsewhere and
can destabilize Satflow collection ingestion.

## GitHub Pages URLs

The JSON uses image URLs with this base:

```text
https://trac-systems.github.io/gibnat-satflow-assets/images
```

Collection icon URL:

```text
https://trac-systems.github.io/gibnat-satflow-assets/icon.jpg
```

GitHub Pages is deployed from `main` by the repository workflow so the image
URLs resolve publicly.

The Pages workflow publishes only the image assets, icon, Satflow JSON, and
summary. The complete source snapshots and rarity catalogue remain available
through the repository without inflating the marketplace-serving artifact.
