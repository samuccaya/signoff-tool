# Signoff Studio — downloads and version checks

Public catalog for **Signoff Studio** installers and in-app update checks.

Source code stays in a private repository. This repo holds:

- GitHub **Releases** with `SignOff-studio-<version>-Setup.exe` and `latest.yml` (what the app checks)
- A **version folder index** under `versions/` so each build is easy to inspect

## Current version

- Semver (installer / updater): **26.8.1**
- In-app label: **26_08_01**

Download the latest installer: [Releases · latest](https://github.com/samuccaya/signoff-tool/releases/latest)

## Version folders

| Path | Purpose |
|------|---------|
| [`versions/latest.json`](versions/latest.json) | Pointer to the current latest version |
| [`versions/26.8.1/version.json`](versions/26.8.1/version.json) | Details for this release |

Add `versions/<YY.M.counter>/` for each new build and update `latest.json`. Matching git branches (for example `26.8.1`) are optional and mirror that folder.

## How the desktop app checks for updates

Packaged Signoff Studio uses `electron-updater` against this repo’s **GitHub Releases**:

1. https://github.com/samuccaya/signoff-tool/releases.atom
2. `latest.yml` attached to the latest Release
3. `SignOff-studio-<version>-Setup.exe` from that Release

Do **not** commit `.exe` files to git. Attach them to a Release.
