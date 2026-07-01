# Contributing Plugins

Thanks for helping grow the Tools for Steam plugin ecosystem.

## Pull Request Checklist

- The plugin zip contains `tfs-plugin.json` at the package root.
- The manifest `id` and `version` match the catalog entry.
- The catalog entry includes at least one image.
- The package SHA-256 hash is correct.
- The plugin declares only the permissions it needs.
- Network and secrets permissions are explained in the pull request.

## Permission Guidance

- `frontend`: required for a visible Quick Access plugin.
- `storage`: public per-plugin JSON settings.
- `secrets`: write-only tokens or passwords stored by the Tools for Steam core.
- `network`: HTTP/HTTPS requests through the Tools for Steam core proxy.

Plugins should not ask for `secrets` or `network` unless the feature genuinely needs them.
