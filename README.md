# Tools for Steam Plugin Database

This repository is the official community plugin catalog for Tools for Steam.

Tools for Steam downloads this file by default:

```text
https://raw.githubusercontent.com/toonymak1993/tfs-plugin-database/main/catalog.json
```

The app caches the catalog locally, displays plugin cards in the TFS Store, verifies package SHA-256 hashes, and installs selected packages into the local Tools for Steam data directory.

## Repository Layout

- `catalog.json`: official store catalog.
- `packages/`: official hosted plugin zip packages.
- `images/`: required plugin preview images.
- `schemas/tfs-catalog.schema.json`: catalog validation schema.

## Current Plugins

- `home-assistant`: first official SDK v1 community plugin. It controls Home Assistant light entities through the Tools for Steam SDK.

## Catalog Rules

Every plugin entry must include:

- Stable `id`.
- Human-readable `title` and `description`.
- `version` matching the package manifest.
- `packageUrl` or `packagePath`.
- `packageSha256`.
- At least one image URL in `images`.

Entries without images are intentionally not listed by Tools for Steam.

## Submit A Plugin

Start from the template repository:

https://github.com/toonymak1993/tfs-plugin-template

Then open a pull request against this repository with:

- Updated `catalog.json`.
- Preview image in `images/` or a stable remote image URL.
- Package zip in `packages/` or a stable remote package URL.
- A short explanation of required SDK permissions.
