# SoftwareCenter Catalog

Public, cryptographically signed application catalogs for [Software Center](https://github.com/Nevers01/SoftwareCenter).

## Channels

- Stable: `https://raw.githubusercontent.com/Nevers01/SoftwareCenter-Catalog/main/channels/stable/signed-catalog.json`
- Preview: `https://raw.githubusercontent.com/Nevers01/SoftwareCenter-Catalog/main/channels/preview/signed-catalog.json`

The preview endpoint is created when the first preview catalog is published.

## Security model

This repository contains only signed catalog envelopes and audit evidence. It never stores private signing keys or private application source code.

Software Center verifies every downloaded catalog with its embedded RSA public key. Publishing files here is not enough to make a catalog trusted: the envelope signature, approval receipt, candidate hash, and release manifest must all match the private release pipeline.

Each channel update is pushed as one Git commit and includes:

- `signed-catalog.json`
- `signed-catalog.sha256`
- `catalog.next.json`
- `catalog.approval.json`
- `catalog.diff.txt`
- `release-check.txt`
- `release-manifest.json`
