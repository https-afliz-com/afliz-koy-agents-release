# The `koy-agents` command line

KOY Agents from a terminal. It works through the running app (its local API — turn it on in **Settings › Permissions ›
Let other tools use KOY Agents on this computer**), so everything you do shows in the app live and the same rules apply.

## Install

Each release has the CLI as one file for Node.js 20+: `koy-agents-<version>.cjs` on the
[release page](https://github.com/https-afliz-com/afliz-koy-agents-release/releases/latest). Download it, then:

```bash
node koy-agents-1.2.0.cjs status
```

To call it `koy-agents`, make it executable and put it on your PATH (macOS / Linux):

```bash
chmod +x koy-agents-1.2.0.cjs && mv koy-agents-1.2.0.cjs ~/.local/bin/koy-agents
```

Use the CLI of the same version as the app (`koy-agents version`, `koy-agents health`).

**From the source repository:** `npm run build:cli`, then `node packages/cli/dist/cli.js status` (or
`npm run koy-agents -- status`).

## Examples

```bash
koy-agents agents                                   # every agent: status, schedule, how closely you check it
koy-agents run "Summarizer" --test --wait           # a test run in the sandbox, then the result and its checks
koy-agents pass "Summarizer" --note "Never mention prices"
koy-agents redo "Post Writer" --note "Shorter, no hashtags"
koy-agents trust "Summarizer" on-fail               # review only when a check fails
koy-agents learn "Summarizer" "Keep it to 3 points"
koy-agents create monitor --name "Price Watch"
koy-agents chat "Make Web Monitor run every hour"
koy-agents chat "Post the result to Slack" --agent "Publisher"
koy-agents plan                                     # your daily plan from the Assistant
koy-agents reminders
koy-agents watch                                    # follow runs and messages live
koy-agents log --agent "Site Watch" --limit 20      # recent activity: runs, reviews, approvals
koy-agents agents --json                            # machine-readable
```

Run `koy-agents help` for every command. `--dev` talks to a development build; `--url` / `--token` (or
`KOY_AGENTS_URL` / `KOY_AGENTS_TOKEN`) connect to a specific API.

Exit codes: 0 done, 1 refused or failed (the app's message is printed), 2 wrong usage.

## koy-ops: the loop with KOY IDE 2

`koy-ops` (in the same package) connects this CLI with KOY IDE 2's `afliz`: results you pass become KOY IDE 2 tasks,
and finished work gets a Release Writer draft in the sandbox. See [KOY-OPS.md](https://github.com/https-afliz-com/afliz-koy-agents-release).
