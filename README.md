# KOY Agents — downloads

KOY Agents is a desktop app for building and running your own agents, workflows and automations on one map — for
people who aren't developers. Agents learn what "good" means from your reviews, every result waits for your approval
until an agent has earned your trust, and your Assistant looks after your day. Made by Anh Luu Services Co. Ltd..

This repository holds the **installers, the command line and the SDK** only — the source code is private.

## Download

Get the [latest release](https://github.com/https-afliz-com/afliz-koy-agents-release/releases/latest):

| OS | File |
|---|---|
| macOS (Apple silicon) | `KOY-Agents-<version>-arm64.dmg` |
| macOS (Intel) | `KOY-Agents-<version>-x64.dmg` |
| Windows | `KOY-Agents-<version>-x64-setup.exe` (or `.msi`) |
| Linux | `KOY-Agents-<version>-x64.AppImage`, `.deb` or `.rpm` |

Install on macOS by dragging KOY Agents into **Applications**. On Linux, keep the AppImage in a folder you can write
to, e.g. `~/Applications`.

Release notes for each version are on its release page and in [CHANGELOG.md](CHANGELOG.md).

## Command line and SDK

Each release also has:

| File | What it is |
|---|---|
| `koy-agents-<version>.cjs` | **koy-agents**, KOY Agents on the command line — one file for Node.js 20+: run agents, review and approve their results, teach preferences, run workflows, talk to your Assistant. Guide: [CLI.md](CLI.md) |
| `koy-agents-sdk-<version>.tgz` | **The SDK** (`@koy/agents-sdk`) — `npm install <its URL>`: a typed client for KOY Agents (ESM + CommonJS + TypeScript). Guide: [SDK.md](SDK.md) |

Both work through the running app's local API: turn it on in **Settings › Permissions › Let other tools use
KOY Agents on this computer**. It listens on this computer only, needs a token that changes every time the app starts,
and can never read your AI keys. The same approvals, sandbox and plan limits apply as in the app.

## License

KOY Agents is © 2026 Anh Luu Services Co. Ltd., licensed under the **Business Source License 1.1** — see [LICENSE](LICENSE).
It is not an Open Source license; the Change License is GPL-2.0-or-later. For commercial licensing contact
legal@afliz.com or visit https://afliz.com/legal/commercial.

## Files in each release

`latest.json`, the `latest-<platform>.json` files, the `.app.tar.gz` and the `.sig` files are the update feed —
you don't need to download them. GitHub also attaches “Source code (zip / tar.gz)” to every release; those archives
only contain this repository (README, LICENSE, CHANGELOG and the guides), not KOY Agents' source code.
