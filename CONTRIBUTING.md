# Contributing Plugins

Thanks for helping grow the Tools for Steam plugin ecosystem.

## Pull Request Checklist

- The plugin zip contains `tfs-plugin.json` at the package root.
- The manifest `id`, `version`, `sdkVersion`, `permissions`, and `networkHosts` match the catalog entry.
- The entry validates against `schemas/tfs-catalog.schema.json`.
- The catalog entry includes preview artwork when available.
- The package SHA-256 hash is correct.
- The plugin declares only the permissions it needs.
- Network, secrets, native, and full-trust permissions are explained in the pull request.

## Permission Guidance

- `frontend`: required for a visible Quick Access plugin.
- `storage`: public per-plugin JSON settings.
- `secrets`: write-only tokens or passwords stored by the Tools for Steam core.
- `network`: HTTP/HTTPS requests through the Tools for Steam core proxy.
- `files`, `notifications`, and `logging`: sandboxed file operations and TFS platform services.
- `native.*`: selected gaming and system bridges exposed by Tools for Steam.
- `native.full-trust`: a bundled backend with unrestricted desktop-level capabilities.

Plugins should request only what their feature genuinely needs. `native.full-trust` is intentionally powerful and must be clearly justified because its backend runs with the user's desktop privileges.

Use the official validation and packaging commands before submitting:

```powershell
.\scripts\tfs-plugin.ps1 validate .\path\to\plugin
.\scripts\tfs-plugin.ps1 pack .\path\to\plugin -OutputPath .\plugin.zip
```

The commands are provided by the [Tools for Steam repository](https://github.com/toonymak1993/tools-for-steam).
