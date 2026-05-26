# Day 2 — Alpha Vantage MCP Spec

> Day 2 vibe-coding spec. You'll **prompt Claude Code to build this for you** — not follow a step-by-step recipe.

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

## Starter prompt

Open Claude Code in an empty folder (e.g. `mkdir alpha-vantage-mcp && cd alpha-vantage-mcp`) and paste this:

> "Build me an MCP server in TypeScript that wraps the Alpha Vantage API. It should expose three tools:
>
> - `get-stock-price(symbol)` — calls `https://www.alphavantage.co/query?function=GLOBAL_QUOTE&symbol=<SYMBOL>&apikey=<KEY>` and returns the latest price, daily change in dollars, and change percent.
> - `get-fx-rate(from_currency, to_currency)` — calls `function=CURRENCY_EXCHANGE_RATE&from_currency=<FROM>&to_currency=<TO>` and returns the current exchange rate and last refresh time.
> - `get-company-overview(symbol)` — calls `function=OVERVIEW&symbol=<SYMBOL>` and returns company name, sector, industry, market cap, and a short description.
>
> Read the API key from `process.env.ALPHAVANTAGE_API_KEY` — never hardcode it. If the env variable is missing, fail at startup with a clear error message telling me how to set it.
>
> Use `@modelcontextprotocol/sdk`, stdio transport, `zod@3` for input schemas. Set up `package.json` with `"type": "module"` and a `build` script using `tsc`. Create a minimal `tsconfig.json` that compiles `src/` to `build/`. Don't run the build yet — just write the files."

## Likely follow-up prompts (in order)

1. *"Now run `npm install` and `npm run build`. Fix any errors."*
2. *"Alpha Vantage's `GLOBAL_QUOTE` response nests data under a top-level `'Global Quote'` key with numbered fields like `'05. price'`. Clean up the parser so the returned fields are `price`, `change`, `changePercent`."*
3. *"Add error handling for `{"Note": "..."}` (rate-limit) and `{"Error Message": "..."}` (bad symbol). Surface those as clear MCP errors."*
4. *"The tool descriptions feel generic. Rewrite each in 1–2 sentences so the model knows exactly when to call them — when the user asks for a price vs an FX rate vs company info."*

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
