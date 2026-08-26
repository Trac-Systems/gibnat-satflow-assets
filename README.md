# GibNat Satflow Assets

Public images and metadata for the `dmt-gibnat` collection on Satflow.

## Files

- `icon.jpg` is the collection icon.
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
