# AIM Workbench — public releases (trial builds)

Public update channel for the AIM Workbench desktop app (trial).
This repo contains ONLY compiled artifacts — **no source code, no server
binaries, no secrets, no credentials**:

| File | What it is |
|---|---|
| `AIM.Workbench.Desktop_<version>_x64.msix` | Signed MSIX package of the desktop app (client only — contains no secrets). |
| `AIM.Workbench.Test.cer` | Self-signed test certificate that signed the matching `.msix`. A fresh cert is created per build; the updater installs the new cert BEFORE the new package. |
| `version.json` | Update manifest the app polls: latest version, download URLs, SHA-256 hashes. |

The source lives in the PRIVATE repo `syfazel/aim-workbench-desktop`
and stays private. The TEST reference server is never published here
(it carries DEV-ONLY passwords) — it ships inside the one-click
installer only.

Releases are published automatically by CI on every push to `main` of
the private source repo. This repo can be deleted or made private at
any time — the app then simply reports "no update available" (it never
fails to start because the manifest is unreachable).
