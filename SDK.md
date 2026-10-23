# KOY Agents SDK (`@koy/agents-sdk`)

Drive KOY Agents from code: list and run agents, review their results in the sandbox, teach them preferences, run
workflows, talk to the Assistant. The SDK talks to the running app's **local API**, so every call goes through the same
commands as the app's buttons — plan limits, approvals and the sandbox all apply, and everything shows in the app live.
It can never read or change your AI keys.

## Install

Each release has the SDK as an npm package, `koy-agents-sdk-<version>.tgz`, on the
[release page](https://github.com/https-afliz-com/afliz-koy-agents-release/releases/latest). Install it from its URL
(Node.js 20+; ESM and CommonJS, with TypeScript types):

```bash
npm install https://github.com/https-afliz-com/afliz-koy-agents-release/releases/download/v1.1.0/koy-agents-sdk-1.1.0.tgz
```

Use the SDK of the same version as the app (`(await koy.health()).version`).

## Turn on the local API

In the app: **Settings › Permissions › Let other tools use KOY Agents on this computer** (or start the app with
`KOY_LOCAL_API=1`). The app then listens on `127.0.0.1` and writes its address and a fresh token to `local-api.json` in
its data folder (readable only by you). The token changes every time the app starts.

| OS | Data folder |
|---|---|
| macOS | `~/Library/Application Support/app.koy.agents` |
| Windows | `%APPDATA%\app.koy.agents` |
| Linux | `~/.local/share/app.koy.agents` |

Development builds keep their data in a `dev` sub-folder (`connect({ dev: true })`).

## Connect

```ts
import { KoyAgents } from '@koy/agents-sdk';

const koy = await KoyAgents.connect();                    // finds local-api.json; or KOY_AGENTS_URL + KOY_AGENTS_TOKEN
```

## Run an agent and review its result

```ts
const a = await koy.runAndWait('Summarizer', { test: true }); // test: in the sandbox, nothing is sent
if (a.status === 'review') {
  console.log(a.result!.text, a.result!.checks);
  await koy.pass('Summarizer', { note: 'Keep it to 3 points' }); // the note becomes a learned preference
}
```

## API

| Call | What it does |
|---|---|
| `health()` · `state()` | Version and edition · everything the app shows (tabs, agents, workflows, the Assistant dock, plan limits) |
| `agents()` · `agent(nameOrId)` · `workflows()` · `workflow(nameOrId)` | Look things up (names are case-insensitive; "Assistant" finds yours) |
| `run(agent, { test })` · `waitFor(agent, { until })` · `runAndWait(agent, { test })` | Run, wait for the outcome |
| `review(agent)` · `pass(agent, { note, edited })` · `redo(agent, { note })` · `discard(agent)` | The sandbox review |
| `approve(agent, ok?)` · `pause(agent)` | Answer an approval · stop a run |
| `createAgent(template, { name, workflow })` · `updateAgent(agent, patch)` · `deleteAgent(agent)` | Templates: blank, researcher, summarizer, writer, monitor, analyst |
| `createWorkflow(name)` · `joinWorkflow(agent, workflow)` · `runWorkflow(workflow)` | Workflows |
| `setTrust(agent, 'review-all' \| 'on-fail' \| 'autopilot')` | How closely you check its results |
| `learn(agent, text)` · `forget(agent, text)` · `questions(agent)` · `answer(agent, id, value)` | Preferences and the card's AI questions |
| `chat(text, { agent })` · `suggestions({ agent })` | Your Assistant, or one agent (what you tell it becomes its requirements) |
| `dock()` · `reminderDone(id, { snooze })` | The Assistant's reminders, calendar, screen time, culture |
| `events((event, payload) => …)` | Live `state` and `toast` events; returns a function that stops listening |
| `invoke(command, args)` | Any app command by name (TRD §5) |

Errors are `KoyAgentsError` with the app's message in plain words and an HTTP-like `status` (401 wrong token,
400 refused, 404 not found).

## Security

- The local API listens on 127.0.0.1 only and every request needs the token; turn it off in Settings and it refuses
  everything at once.
- Treat `local-api.json` like a password. AI keys, and turning the API itself on or off, stay in the app.
