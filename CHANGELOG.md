# KOY Agents changelog

What changed in each release of KOY Agents, its `koy-agents` command line and its SDK. Download a version from its
[release page](https://github.com/https-afliz-com/afliz-koy-agents-release/releases).

## [0.3.0] - 2026-10-13

### Added

- **Sign in, and KOY Agents Pro** — sign in with the same KOY account as KOY IDE 2 (Google, GitHub or a link by email, on KOY's account page in your browser)
- **`koy-ops`: the loop with KOY IDE 2, from the command line** — `koy-ops handoff` turns each result you passed from your build-source agents (Feedback Triage and Site Watch unless you name others) into one KOY IDE 2…
- **`koy-agents log`** — recent activity — runs, reviews, approvals — newest first (`--agent`, `--limit`, `--json`)

### Changed

- **Two plans, Free and Pro** — the Team plan is gone from Billing & plan; "run when a file arrives" needs KOY Agents Pro

### Fixed

- **KOY Agents for Windows updates itself** — like the Mac app: it checks 15 seconds after launch and every 4 hours, downloads a new version in the background and offers **Restart now** or **Later**…

## [0.2.0] - 2026-10-13

### Added

- **Your Assistant answers on your Claude plan while Claude Code is ready** — what its built-in commands don't understand (questions, drafts, advice) is answered by Claude through Claude Code instead of “I'm not sure what to do with…
- **MCP servers** — Settings › MCP servers: give agents extra tools from any Model Context Protocol server — one KOY starts on this computer (a command such as `npx …`) or an…
- **Use your Claude plan through Claude Code** — Settings › AI providers: agents can run on Claude Pro, Max, Team or Enterprise through the `claude` app, with no API key — pick a `claude-code:` model

## [0.1.0] - 2026-10-12

### Added

- **KOY Agents for macOS, Windows and Linux** — build your own agents, workflows and automations on one map — tabs, cards, workflow frames, schedules and apps, with plan limits for guests and signed-in users
- **Runs you approve** — an agent's result waits in the sandbox until you review it; your reviews teach it learned preferences and named checks, and the trust ladder lets it do more…
- **Real runs** — agents read the web pages their skill names with the read-only Browser app (GET only: pages, sitemaps, robots.txt and link checks) and write their result…
- **Your Assistant** — reminders, a daily plan, culture tips and a screen-time view in the dock, and a chat that answers in plain words and takes requirements for each agent
- **The `koy-agents` command line and the SDK** — `@koy/agents-sdk`: run agents, review their results, teach preferences, run workflows and talk to the Assistant from a terminal or from code, through the…
- **Automatic updates** — the app checks for a new version shortly after launch and every 4 hours, downloads it in the background and offers **Restart now** or **Later** (it installs…

[0.3.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.3.0
[0.2.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.2.0
[0.1.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.1.0
