# KOY Agents changelog

What changed in each release of KOY Agents, its `koy-agents` command line and its SDK. Download a version from its
[release page](https://github.com/https-afliz-com/afliz-koy-agents-release/releases).

## [0.5.0] - 2026-10-14

### Added

- **Language setting** — Settings › General › Language: Automatic follows your Mac's languages and region, or pick one
- **Calendar (macOS)** — connect your Mac's own Calendar in Settings › Apps — every calendar the Calendar app shows (iCloud, Google, Exchange…)

### Added

- **Your Assistant on the desktop** — the KOY Agents logo floats on top of your other apps (with a badge for reminders); drag it anywhere, click it to open today's reminders, your next events…
- **Drag files onto the chat** — or pick them with the paperclip
- **Google Drive, Docs, Sheets and Slides** — in Settings › Apps — one Google sign-in for all four, read-only
- **Search in Settings › Apps** — find an app by name or what it does; once Google Drive is connected, the same box finds your Drive files, with *Copy link* to paste one into a skill
- **Share usage data (optional)** — KOY Agents asks once whether to share usage data — the app opening, agents and workflows being created (with the template's name) and runs

### Changed

- **Signing in, upgrading and connecting happen on afliz.com** — (afliz.com/account/) instead of koyide-6137b.web.app, which is now only for development builds
- **One KOY Pro for KOY Agents and KOY IDE 2** — Pro is the same $10-a-month KOY Pro subscription as KOY IDE 2's, so paying once unlocks both apps
- **Messages appear on the map's toolbar** — on the same line as ＋ New, instead of over the top of the map (above a dialog while one is open)

## [0.4.0] - 2026-10-13

### Added

- **Agents run on OpenAI, Google Gemini and Ollama** — not only Claude: the keys in Settings › AI providers now work
- **Alert agents** — an agent whose result starts with P1, P2 or Quiet (card › More settings › Alert agent)
- **Workflow steps work from the steps before them** — in a workflow run, each agent gets the results the earlier steps sent on (what you approved, or your edited version), so the last step can bring them all…
- **The Browser reads news feeds and public data** — an RSS or Atom feed named in a skill becomes a list of dated headlines with their links and a short summary, and data from a public API (JSON, CSV) is read…
- **Schedules at clock times run** — *Every morning at 8:00*, *Weekdays at 8:00*, *Every Monday at 9:00*, *Every evening at 18:00* and the new *Twice a day at 8:00 and 20:00* now start the…
- **Departments** — a tab with its agents and workflows, written down in `departments/*.json` and built by KOY IDE 2's pipelines
- SDK: `tabs()`, `tab()`, `createTab()`, `switchTab()`, `updateTab()` (name, description, colour), `updateWorkflow()`, and `updateAgent()` takes `apps`,…

### Changed

- **On a Mac, the top bar is the title bar** — The window buttons sit in it and you move the window by dragging it (anywhere outside its buttons and the search box; a double click zooms), instead of by a…

### Removed

- **Apps KOY didn't really connect to** — Gmail, Slack, Notion, Calendar, Google Drive, WhatsApp, Zalo, Facebook, Instagram, Threads and Files were placeholders — *Connect* only flipped a switch,…

### Fixed

- **The Apple silicon (arm64) Mac app opens again** — Without a Developer ID it shipped with only the compiler's signature, which macOS rejects on Apple silicon as "damaged", so the Intel build was the one that…

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

[0.5.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.5.0
[0.4.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.4.0
[0.3.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.3.0
[0.2.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.2.0
[0.1.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.1.0
