# Part 2 — Furnishing the home: context, knowledge work, memory & reach

## What you'll leave with
By the end of this part you'll **turn a messy 30-minute customer call into the next version of a real requirements document** — the most job-shaped task in the whole series. Along the way you'll teach the project about you, watch it *remember* across chats, and reach beyond your folder.

> **See where we're going first:** your facilitator will show the finished requirements document up front — that's what you'll produce from a transcript by the end of the part.

## Short theory (plain language)

**Where your context lives.** A few places, broad to narrow:
- **Global instructions** — apply to every Cowork session (your "ask first" rule from Part 1).
- **Project instructions** — apply to this one project.
- **`CLAUDE.md`** — a plain-text "read me first" note that lives *in* the folder and travels with it.

You won't hand-write any of these — you ask Claude in plain English and it creates the file. (`#` just marks headings; `.md` just means "plain text note".)

**The three notes you'll build:** `about-me.md` = *who I am* · `CLAUDE.md` = *what this folder is + what to read first* · `memory.md` = *the decisions I want written down*.

**Memory across sessions.** A project **remembers automatically** across chats — you don't have to do anything for it to carry your work forward. You stay in control of what it keeps: you can view and edit memory, use Temporary chats that don't save, and you should keep sensitive data (passwords, customer details) out of it in the first place — it does **not** auto-remove that for you. A `memory.md` is simply an explicit, portable record *you* control, for the decisions worth keeping.

**Connectors.** A connector is a **link to another place your documents live** — Google Drive, SharePoint, Calendar. Once connected, Claude can read from there too. It's a bigger boundary than a local folder, because it reaches a live account in your name — so **read the permission screen, grant only the minimum the task needs, and disconnect any time.**

**Plan → review → apply.** For real knowledge work, don't let Claude silently rewrite a document. Have it produce a **plan of changes** first, **review that plan** (it's the cheapest place to catch a problem), then let it apply the approved plan. The AI proposes; you review; it executes. You stay the editor.

## What you'll do (practical)

1. **Create a `CLAUDE.md`** for your folder:
   > "Create a CLAUDE.md file in this folder that explains this folder is used for learning Claude Cowork and contains material I'm using to learn it."
   - ✅ Done when a `CLAUDE.md` exists describing what the folder is.

2. **Write your own `about-me.md`** (a short who-am-I — name, role, what you care about), then update `CLAUDE.md` to *"always read about-me.md first."*
   - ✅ Done when asking *"what do you know about me?"* reflects your `about-me.md`.

3. *(If time)* **A bigger thinking task** — ask Claude to help you build a short course to teach colleagues Cowork, and answer its questions in plain language. There are no wrong answers — the back-and-forth is how it tailors the result to you.

4. **Capture a `memory.md`** and link it in `CLAUDE.md`:
   > "Summarise what we've set up and decided so far into a memory.md file, and link it in CLAUDE.md."
   Then open a **fresh chat** in the same project and ask about earlier work — see that it already knows.
   - ✅ Done when `memory.md` lists your key decisions and `CLAUDE.md` points at it.

5. **Connect a connector** (e.g. Calendar). Read the permission screen carefully — the access it asks for can range from harmless ("view events") all the way up to "permanently delete all calendars". Grant only what the task needs. *(If connectors aren't enabled for you yet, you'll follow along on the shared screen.)*

6. **The headline task — transcript → requirements (plan → review → implement):**
   - **Plan first (no editing yet):**
     > "Read this transcript against the current requirements document and give me a plan of changes — what to add, change, flag, and ignore. Don't edit the document yet. Scope: only the Transaction list; the document is the source of truth."
   - **Review the plan — this is the BA skill.** Go through Claude's proposed changes critically: did it capture *every* real need raised in the meeting? Did it add anything that **wasn't actually said**? Are the priorities right, and did it correctly ignore the small talk and side-chatter? Adjust, then approve. *(This is the whole point — the human reviews the cheap plan before any document is rewritten.)*
   - **Implement:**
     > "Apply the approved plan and produce v1.0 of the requirements document, with a change-log entry for this meeting."
   - ✅ Done when v1.0 folds in the agreed needs, leaves out the noise, and has a dated change-log entry — *and you reviewed the plan before letting it write anything.*

## What you need
- [`transaction-list-requirements.md`](./transaction-list-requirements.md) — the starting (v0.1) requirements document.
- [`requirement-review-meeting-transcript.md`](./requirement-review-meeting-transcript.md) — the customer review transcript.
- A short **review checklist** for step 6 — your facilitator hands this out *during* the review. It's deliberately not in this repo, so it doesn't give away what to look for ahead of time.

Copy the two files above into your project folder before you start step 6.
