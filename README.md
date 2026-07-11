# Tools for Steam Plugin Database

This repository is the official community plugin catalog for Tools for Steam.

Tools for Steam downloads this file by default:

```text
https://raw.githubusercontent.com/toonymak1993/tfs-plugin-database/main/catalog.json
```

The app caches the catalog locally, displays plugin cards in the TFS Store, shows the declared trust and permission profile before installation, verifies package SHA-256 hashes, and installs selected packages into the local Tools for Steam data directory.

Developer documentation, SDK types, schemas, templates, packaging, and sideloading tools live in the [`sdk` directory of Tools for Steam](https://github.com/toonymak1993/tools-for-steam/tree/main/sdk).

## Repository Layout

- `catalog.json`: official store catalog.
- `packages/`: official hosted plugin zip packages.
- `images/`: required plugin preview images.
- `schemas/tfs-catalog.schema.json`: catalog validation schema.

## Current Plugins

- `home-assistant`: first official SDK v1 community plugin. It controls Home Assistant light entities through the Tools for Steam SDK.

## Catalog Rules

Every SDK 1.0 plugin entry must include:

- Stable `id`.
- Human-readable `title` and `description`.
- `version` matching the package manifest.
- `sdkVersion` matching the package manifest (currently `1.0.0`).
- `permissions` matching the package manifest exactly.
- `networkHosts` when `network` is requested.
- `packageUrl` or `packagePath`.
- `packageSha256`.
- Preview URLs in `images` whenever artwork is available.

Catalog metadata is not a permission grant by itself. Tools for Steam compares it with the packaged `tfs-plugin.json`, blocks mismatches, and presents powerful native or full-trust access to the user before installation.

## Submit A Plugin

Start from the template repository:

https://github.com/toonymak1993/tfs-plugin-template

Then open a pull request against this repository with:

- Updated `catalog.json`.
- Preview image in `images/` or a stable remote image URL.
- Package zip in `packages/` or a stable remote package URL.
- Matching SDK version, permissions, and network host declarations.
- A short explanation of every requested native or full-trust permission.
