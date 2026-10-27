# KOY Agents changelog

What changed in each release of KOY Agents, its `koy-agents` command line and its SDK. Download a version from its
[release page](https://github.com/https-afliz-com/afliz-koy-agents-release/releases).

## [1.2.0] - 2026-10-27

### Added

- **Zalo "Listen only"** — Settings › Apps › Zalo: KOY never replies in Zalo
- **Your Assistant can summarize your agents' work** — when it runs, it reads every agent — its tab, schedule and status, any error, and the result it made since the Assistant's previous report — so a skill like…
- **Give your Assistant your own skill and it runs on its AI model** — like any agent; with its built-in skill it still makes your daily plan on this computer, with no model
- **Microsoft Teams** — Settings › Apps: connect your work or school Microsoft account and agents read the Teams discussions their skill links to — read-only, KOY never posts in Teams

### Fixed

- **Microsoft Teams: a chat's new messages are no longer missed** — An agent summarizing a chat read nothing new after its first report, so it kept repeating the old summary
- **Microsoft Teams: a pasted link finds its discussion** — Pasting a Teams link (Copy link in Teams) in **Find a Teams discussion…** now shows that chat or channel by name, or says why you can't read it, instead of…

## [1.1.1] - 2026-10-23

### Changed

- **Two-step verification is your choice for your KOY ID, and needed only to share with people (P2P)** — Signing in (Settings › Account) and staying signed in no longer require it: a password-only KOY ID sign-in works for your account, KOY Pro and your…

### Security

- **Sharing with people still requires two-step verification** — Settings › People & devices › Turn on now signs in to KOY ID with two-step verification (if you're signed in already, KOY ID usually asks only for your…

## [1.1.0] - 2026-10-22

### Added

- **Binance app — market data and paper trading** — Settings › Apps › Binance: name the symbols to watch (e.g. BTCUSDT, ETHUSDT) and a paper account's starting cash
- **Connect by hand on the map** — drag an agent's dot onto another agent to pass it its result, or onto an app (or an app's dot onto an agent) to give the agent that app
- **The map shows how data moves** — lines end in arrows — into the agent for apps it reads, out of it for apps it writes to, both ways for the rest — and animate while an agent runs
- **Focus mode for an agent** — the expand button in the agent panel opens the whole agent in a large view — its full skill, settings, schedule and next run, apps, recent runs and latest…
- **Invoices into ERPNext, from another of your devices** — docs/ui/erpnext-handoff-mockup.html: - **ERPNext app** (Settings › Apps › ERPNext): the site's address and an API key and secret, which stay in that…
- **People & devices works in this version** — KOY's credential issuer (issuer.afliz.com) and its key are built in, so devices can enrol and find each other on the same network
- **Your Afliz account, one click away** — Settings › Account has **Open your account**, which opens the Afliz account portal (KOY ID signs you in there), and **Manage billing** now goes to your…
- **People & devices: work with other people's agents, peer to peer** — Turn it on in Settings › People & devices by signing in to your **KOY ID**, with two-step verification
- **OpenAI-compatible model servers** — agents can run on any server with the OpenAI Chat Completions API — set the agent's model to `compatible:<model id>`
- **Afliz's shared models (Afliz employees only)** — signed in with an @afliz.com account, KOY Agents picks up the model server Afliz switches on in the account portal (for example GLM 4.7 Flash on Afliz's own…

### Changed

- **The agent panel** — the AI questions card folds away (KOY remembers it), the skill box opens tall enough for the skill and drags taller, and **Skill: collect invoices** appears…
- **Clearer wording** — in several languages for the new connect and map texts (Brazilian Portuguese throughout, the formal "Sie" in German, each language's usual words for…
- **Sign in with KOY ID** — Settings › Account signs you in with KOY ID (id.afliz.com, with a second factor) in your browser — the same account as before (your plan, trial and devices…
- **Signing out says what it signs out of** — Sign out (Settings › Account, the account menu) and *Sign out of KOY ID* (People & devices) ask first, and say that it signs you out of KOY ID everywhere in…

### Security

- **KOY ID sign-ins must include the second step** — KOY Agents now refuses a KOY ID ID token that doesn't say two-step verification was done (`acr` = `mfa`), on sign-in and when it refreshes the sign-in, and…
- **Signing out ends your KOY ID session, not just the sign-in on this computer** — KOY Agents now revokes its KOY ID sign-in at KOY ID when you sign out, so a copy of it stops working too

## [1.0.0] - 2026-10-16

### Added

- **KOY Pro is on sale** — Settings › Billing & plan: $10 a month or $100 a year, one subscription for KOY Agents and KOY IDE 2, paid on KOY's account page (Paddle)
- **Mail (Apple Mail)** — every account Mail has, no sign-in
- **Collect invoices** — Settings › Apps › Mail: the e-invoices (XML) of the last N days become rows of the sheet "Invoices" in your Excel book — seller, tax codes, series, number,…
- **Notes (Apple Notes)** — **Word** (each run's report as a .docx in Documents › KOY Agents › Reports) and **Weather** (MET Norway forecast for your place) apps
- **Excel tables** — besides the run log, agents can add rows to a sheet of their own, keyed so nothing is added twice
- **Chat with KOY on Telegram and Zalo** — /status, /agents, /run <agent>, /help — anything else goes to your Assistant and its answer comes back (Settings › Apps › "Chat with KOY here"; only your…
- **Run when a file arrives** — KOY Pro: pick "When a file arrives" for an agent or a workflow and the folder to watch (Documents › Inbox, ~/Downloads or a full path)
- **Screen time** — with your OK, KOY notes which app is in front (names only) so the Assistant can suggest breaks
- **Privacy** — personal details (emails, phone numbers, card and account numbers, codes) are masked before any model reads them; Sensitive sources (senders and apps) are…
- Each app's card has **How it works**, and Afliz can switch an app off for everyone (the card says so)
- **Mail, Calendar and Notes on Windows** — Settings › Apps: Mail and Calendar work with classic Outlook (in Microsoft 365 or Office) — every account's Inbox and calendar, no sign-in — and Notes with…
- **19 languages** — Settings › General › Language: English, Tiếng Việt, 日本語, 한국어, 简体中文, ไทย, Bahasa Indonesia, Bahasa Melayu, Français, Deutsch, Español, Português, Italiano,…
- **Move to tab** — an agent's card (More settings › Tab) or a workflow's panel moves it to another tab
- **Open at login** — Settings › General: KOY Agents opens when you log in to the computer, so scheduled agents and alerts start without opening it by hand
- **Skills** — an agent can have a built-in skill KOY runs before its model
- **Invoice totals** — in Excel: after every scan, the sheet "Invoice totals" adds up all the invoices collected so far — by month and by seller (number of invoices, before tax,…
- **Amounts worked out and checked** — when an e-invoice leaves out its total, VAT or amount before tax, KOY works it out from the other two, the VAT rate or the invoice's lines

### Changed

- **App icons** — Settings › Apps and the map: on a Mac, Mail, Calendar, Notes, Weather, Excel, Word, Zalo and Telegram show their real icon when the app is installed — macOS…
- The Weather card always credits its data: "Weather data from MET Norway (CC BY 4.0) · place search © OpenStreetMap contributors"
- **No more beta plan** — signed-in testers' "Beta (unlimited)" ends — your licence decides Free, trial or Pro
- The map fits in agents added from outside the app, and Fit to screen always fits
- **"Share usage events"** — the question when KOY Agents first opens and the switch in Settings › Permissions now say exactly what is shared — usage events (the app opening, agents and…
- **The Assistant does it when you say OK** — in KOY, on Telegram and on Zalo: instead of telling you what to type, it says what it will do — e.g. make an agent that moves GitHub mail to Junk, then run…
- **"update <agent>: …"** — in the chat (KOY, Telegram, Zalo) adds to that agent's skill — e.g. *update Inbox Watch: move GitHub notifications to Junk* — the same as saying it in the…

### Fixed

- **Zalo** — connecting the bot never found your chat, because Zalo only hands over a message that arrives while KOY is listening
- Mail: Connect no longer fails when the inbox's first message has moved

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

[1.2.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v1.2.0
[1.1.1]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v1.1.1
[1.1.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v1.1.0
[1.0.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v1.0.0
[0.5.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.5.0
[0.4.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.4.0
[0.3.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.3.0
[0.2.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.2.0
[0.1.0]: https://github.com/https-afliz-com/afliz-koy-agents-release/releases/tag/v0.1.0
