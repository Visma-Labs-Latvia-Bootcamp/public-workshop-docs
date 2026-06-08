# Day 2 — Alpha Vantage MCP Spec

> Day 2 vibe-coding brief. You'll **prompt Claude Code to build this for you** — not follow a step-by-step recipe. We do it with discipline: **Research → Plan → Implement → Review** (a.k.a. spec-driven vibe coding). Yesterday's two MCPs come back today — **DeepWiki** feeds Research, **MCP Inspector** closes Review.

## What you're building

A small MCP server that wraps the [Alpha Vantage](https://www.alphavantage.co/) financial-data API and exposes three tools:

| Tool | Input | Returns |
|---|---|---|
| `get-stock-price` | `symbol: string` (ticker like TSLA, MSFT) | Latest price, daily change ($), change percent |
| `get-fx-rate` | `from_currency: string`, `to_currency: string` (ISO codes) | Current exchange rate + last refresh time |
| `get-company-overview` | `symbol: string` | Company name, sector, industry, market cap, short description |

The server reads the API key from the `ALPHAVANTAGE_API_KEY` environment variable — never hardcoded. That's how you'll meet the **env pattern** in `.mcp.json` for the first time today.

## Before you start

Make sure you've signed up for a **free** Alpha Vantage API key:

1. Open <https://www.alphavantage.co/support/#api-key>
2. Fill the form (name, email, occupation — any answer; nothing is validated)
3. Submit. Key arrives by email within seconds.
4. Copy the key somewhere you can paste from later.

Free tier limits: **25 requests/day** and **5 requests/minute** per key — plenty for the workshop.

## Tech to use

- **Language:** TypeScript
- **SDK:** `@modelcontextprotocol/sdk`
- **Schema:** `zod@3`
- **Transport:** `stdio`
- **Module type:** ESM (`"type": "module"` in `package.json`)
- **Build:** `tsc`, compiling `src/` → `build/`
- **API key:** read from `process.env.ALPHAVANTAGE_API_KEY` (never hardcode)

## Build it: Research → Plan → Implement → Review

Open Claude Code in an empty folder (`mkdir alpha-vantage-mcp && cd alpha-vantage-mcp`). Don't pre-create any files. Then walk these four phases — each one has a paste-ready prompt.

The point of R → P → I → R is that **Research and Plan absorb the things that would otherwise show up as bugs**: wrong field names, generic tool descriptions, missing error handling. By the time you Implement, the spec already tells the model exactly what to write.

### R — Research (~8–10 min) — using DeepWiki + live API calls

Two prompts. Both stay in chat; no files written yet.

**Prompt 1 — SDK shape** (reuses Day 1's DeepWiki MCP):

> "Using deepwiki on `modelcontextprotocol/typescript-sdk`, show me three things I need before designing my own MCP:
> 1. The `server.tool()` signature — what arguments it takes, in order.
> 2. The shape of a minimal handler return value (the `content: [...]` structure).
> 3. How `StdioServerTransport` is wired up at the bottom of `index.ts`.
> Quote the SDK directly where you can."

**Prompt 2 — API shape** (paste your real key):

> "I have an Alpha Vantage API key (`<paste-yours-here>`). Fetch each of these three endpoints and show me the actual JSON shape so I know exactly how to parse them:
> - `https://www.alphavantage.co/query?function=GLOBAL_QUOTE&symbol=MSFT&apikey=<KEY>`
> - `https://www.alphavantage.co/query?function=CURRENCY_EXCHANGE_RATE&from_currency=EUR&to_currency=USD&apikey=<KEY>`
> - `https://www.alphavantage.co/query?function=OVERVIEW&symbol=MSFT&apikey=<KEY>`
> If any of them returns a `{"Note": ...}` rate-limit response or an `{"Error Message": ...}` error response, show me that shape too — I need to handle both."

Read the findings — pay attention to the actual JSON keys (e.g. `'Global Quote'`, `'05. price'`). Those facts go into the spec next.

### P — Plan (~7–10 min) — write `SPEC.md`

> "Based on the research above, write a `SPEC.md` in the project root that describes the MCP we're about to build. Include:
> - **Goal:** a one-paragraph summary of what we're building.
> - **Tools** (three): for each, the exact name, input schema (zod), and what it returns. **Use the actual field names you discovered in research** (e.g. `'05. price'` from `'Global Quote'`). Include a 1–2 sentence description tuned for model selection — make it crystal clear when to call this tool vs the others (price vs FX rate vs company info).
> - **File layout:** `package.json` (ESM, `"type": "module"`, `build` script), `tsconfig.json` (compile `src/` → `build/`), `src/index.ts`.
> - **Runtime contract:** read `ALPHAVANTAGE_API_KEY` from `process.env`; if missing, fail at startup with a clear message telling the user how to set it.
> - **Error handling:** detect `{"Note": ...}` (rate limit) and `{"Error Message": ...}` (bad input) in API responses; surface them as MCP errors that include the original text, not crashes.
> - **Build commands:** the exact `npm` commands to run.
>
> Write the file. Don't write any code yet — just the SPEC."

**Refinement prompt — use it; this is the whole point:**

> "Read `SPEC.md` back to me and tell me where it's still vague. I want a spec another developer could implement without asking questions."

Iterate one or two more times, then explicitly type **"approved"** when the spec looks right. That's your gate.

### I — Implement (~10–12 min) — one prompt

> "Read `SPEC.md` and implement it end-to-end. Create `package.json`, `tsconfig.json`, and `src/index.ts`. Don't run `npm install` or `npm run build` yet — we'll review the diff against the spec first."

### R — Review (~10–15 min) — diff → build → MCP Inspector

**1. Diff vs spec:**

> "Compare the code you just wrote against `SPEC.md`. List every place the code deviates from the spec — names, return shapes, error handling, missing pieces. Be brutal."

Decide which deviations matter; fix with a prompt or two.

**2. Build:**

> "Now run `npm install` and then `npm run build`. Fix any TypeScript or dependency errors that come up. Don't rewrite working code — just fix what fails."

**3. MCP Inspector smoke test** — Day 1's Inspector, used in anger. The Inspector doesn't read `.mcp.json`, so set the env in your shell first:

PowerShell:
```powershell
$env:ALPHAVANTAGE_API_KEY = "<your-key>"
npx @modelcontextprotocol/inspector node build/index.js
```

bash:
```bash
ALPHAVANTAGE_API_KEY=<your-key> npx @modelcontextprotocol/inspector node build/index.js
```

In the Inspector UI:
- Confirm all three tools appear with the descriptions from your spec
- Call `get-stock-price` with `symbol: MSFT` → see live data
- Try a bad symbol (e.g. `NOPENOPENOPE`) → confirm your error envelope surfaces cleanly

**4. Fix-it prompts** for anything Inspector reveals. Pattern:

> "In the MCP Inspector, calling `<tool>` with `<args>` returned `<actual>` but `SPEC.md` says it should return `<expected>`. Fix it."

## Register your server

Once it builds, ask Claude Code:

> *"Help me register this MCP in the `.mcp.json` at my workshop folder root. Use the absolute path to `build/index.js` and add an `env` block with my Alpha Vantage API key."*

The entry should look like:

```json
{
  "mcpServers": {
    "alpha-vantage": {
      "type": "stdio",
      "command": "node",
      "args": ["<absolute-path-to>/alpha-vantage-mcp/build/index.js"],
      "env": { "ALPHAVANTAGE_API_KEY": "your-key-here" }
    }
  }
}
```

Then restart Claude Code (approve the new server when prompted).

### A note about your API key + git

You've just put a credential in `.mcp.json`. If that file's in git, you've committed a secret. In real codebases there are three fixes — pick one **after** the workshop:

1. **User scope** — `claude mcp add --scope user alpha-vantage ...` → the entry moves to `~/.claude.json`, off git. **What most teams do.**
2. **Local scope** — `claude mcp add --scope local ...` → same idea, per-project entry in `~/.claude.json`.
3. **Gitignore `.mcp.json`** — cruder; breaks the team-share intent of the file.

For today, keep the env block in `.mcp.json` so you can see how it works. Migrate after.

## Test it

- *"What's the current price of TSLA?"*
- *"What's the EUR to USD exchange rate right now?"*
- *"Give me an overview of Microsoft."*

## What "done" looks like

- Your project folder has a `SPEC.md` next to `src/`, `build/`, and `package.json` — and the code matches the spec
- Claude Code lists the three `alpha-vantage` tools after restart
- Each test prompt returns real, live data (a price, an FX rate, a company description)
- You can describe in one sentence what each piece of the server does

## If you get stuck

- **`{"Note": "Thank you for using Alpha Vantage..."}`** — the 5/min free-tier limit got hit. Wait a minute and retry; **not** a server bug.
- **No data returned, no error** — check the ticker symbol. Try with `MSFT` or `AAPL` to confirm the path works.
- **Server fails to start with "ALPHAVANTAGE_API_KEY missing"** — check the `env` block in your `.mcp.json` and restart Claude Code after editing.
- **MCP Inspector says the same** — the Inspector doesn't inherit env from `.mcp.json`. Set the variable in your shell first:
  - PowerShell: `$env:ALPHAVANTAGE_API_KEY = "your-key"`
  - bash: `export ALPHAVANTAGE_API_KEY=your-key`
  Then run: `npx @modelcontextprotocol/inspector node build/index.js`
- Ask Claude Code to explain whichever piece is confusing — that's part of the exercise.
- Flag the presenter; there's a reference solution to screen-share.
