# GIBNAT Native Ord Gallery

This directory contains the complete source for one native `ord` gallery
inscription. It is a point-in-time snapshot of successful `dmt-gibnat` mints.
See `summary.json` for the exact count, indexed block, generation time, hashes,
and encoded property sizes.

## Confirmed Gallery

The gallery was confirmed in Bitcoin block `964178`:

<https://ordinals.com/inscription/08df00511d424001e6874be71712c65a7e5fb62cf7ebf6065d9a845f1f19a16ci0>

It contains all 4,460 source inscription IDs in the original order, with
matching titles and traits. The inscriber encoded the source value `"None"` as
CBOR `null`; all other trait values match, including 377 Boolean `BURNER`
traits.

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

## Reproduce With inscribe.dev

1. Upload the repository-root `icon.jpg` as the inscription file.
2. Set the inscription title to `GIBNAT`.
3. Enable **Attach a Gallery** and import `gallery-input.json`.
4. Confirm that the displayed gallery count matches `summary.json`.
5. Enable **Apply Brotli compression** before signing.

## Inscribe With ord

Run these commands from the repository root with a current `ord` client:

```sh
ord wallet batch --dry-run --compress --fee-rate <RATE> --batch gallery/ord-batch.yaml
ord wallet batch --compress --fee-rate <RATE> --batch gallery/ord-batch.yaml
```

The first command builds and checks the transaction without signing or
broadcasting it. Review the dry-run output before running the second command.

Use the confirmed gallery inscription ID above when submitting `dmt-gibnat` to
collection registries.

Gallery inscriptions are immutable. Mints confirmed after this snapshot require
a newly generated gallery and a replacement submission.
