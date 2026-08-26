# GIBNAT Native Ord Gallery

This directory contains the complete source for one native `ord` gallery
inscription. It is a point-in-time snapshot of successful `dmt-gibnat` mints.
See `summary.json` for the exact count, indexed block, generation time, hashes,
and encoded property sizes.

## Files

- `gallery-input.json` is the marketplace-style JSON accepted by the gallery
  importer at <https://inscribe.dev/>. It contains inscription IDs, titles, and
  traits only. External item image URLs are deliberately not included because
  they are not part of the native gallery standard.
- `ord-batch.yaml` is the equivalent batch file for the reference `ord` client.
  It creates one gallery inscription whose body is the repository-root
  `icon.jpg`.
- `summary.json` records the snapshot and integrity hashes.

Both source files describe the same ordered set of gallery items.

Items issued through the original paid flow include the Boolean trait
`BURNER: true`. The trait is limited to successful on-chain mints that match
both a historical paid assignment and a confirmed GIB burn address. Later free
claims made to the same address are not tagged.

## Inscribe With inscribe.dev

1. Upload the repository-root `icon.jpg` as the inscription file.
2. Set the inscription title to `GIBNAT`.
3. Add gallery-level traits `Protocol: TAP DMT` and `Ticker: dmt-gibnat`.
4. Enable **Attach a Gallery** and import `gallery-input.json`.
5. Confirm that the displayed gallery count matches `summary.json`.
6. Enable **Apply Brotli compression** before signing.

## Inscribe With ord

Run these commands from the repository root with a current `ord` client:

```sh
ord wallet batch --dry-run --compress --fee-rate <RATE> --batch gallery/ord-batch.yaml
ord wallet batch --compress --fee-rate <RATE> --batch gallery/ord-batch.yaml
```

The first command builds and checks the transaction without signing or
broadcasting it. Review the dry-run output before running the second command.

After the reveal confirms, use the resulting gallery inscription ID for the
existing `dmt-gibnat` collection submission on Satflow.

Gallery inscriptions are immutable. Mints confirmed after this snapshot require
a newly generated gallery and a replacement submission.
