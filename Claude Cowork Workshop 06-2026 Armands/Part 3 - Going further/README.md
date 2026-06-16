# Part 3 — Going further: skills, plugins & autonomy

## What you'll leave with
By the end of this part you'll have Claude **turn any raw meeting transcript into clean, structured notes automatically** — and tomorrow's **day-brief waiting for you**. You'll make a reusable skill, see a live result, put Claude on a schedule, and build one real flow end-to-end yourself.

> **See it first:** your facilitator will show the finished, structured meeting-notes output up front — before we even explain what a "skill" is.

## Short theory (plain language)

**Skills — your saved playbooks.** A skill is a **packaged set of instructions** that teaches Claude *how* to do one kind of task — and Claude reaches for it automatically when your request matches. The difference from the notes in Part 2: `CLAUDE.md` and `about-me.md` are *who you are / what the folder is*; a **skill is a how-to** — a repeatable procedure you save once and reuse.

**Plugins — the "app store".** If a skill is one playbook, a **plugin is a whole kit** — a ready-made bundle of skills and connectors you install in one click from a marketplace. Because a plugin can reach your live accounts and act on your work, installing one is a bigger "allow" than a single skill — install from trusted sources only.

**Live, interactive results.** Beyond writing files, Claude can produce a **live result that renders right in the app** — something you click around in, not a document you open elsewhere. The clearest example: a brief of your day pulled live from your calendar. *See it, don't just read it.*

**Scheduling — Claude on a cadence.** Until now Claude worked *when you asked*. Scheduling makes it run a task **automatically on a schedule**, so the work is waiting for you. It runs inside your project, so it already has your context, connectors and skills. **One honest limit:** a scheduled task only runs while your computer is awake and the Claude app is open — it's not a cloud service. And because it runs *unattended* (no one's there to approve anything), lean toward read-only / produce-output tasks — this is where being deliberate about what you allow matters most.

**The reveal.** Put it all together — a project, an outcome, a skill or a connector, your control, maybe a schedule — and you're no longer just *chatting* with an AI. You're **directing** one. That's the whole arc of the series.

## What you'll do (practical)

1. **Find your skills** — open **Customize → Skills**, see the built-in ones, and notice the on/off toggles (you decide what Claude is allowed to reach for).

2. **Create a skill together** — build a *"Structure meeting notes"* skill with the built-in skill-creator. It asks what the skill should do; you answer in plain language. Then **make it yours**: type one refinement in your own words, e.g.
   > "Also capture who raised each open question."
   Test it by pasting a transcript and asking for notes.
   - ✅ Done when the skill appears under **Customize → Skills**, a pasted transcript comes back in the structured format, **and** you made one change in your own words.

3. *(If time)* **Browse the plugins marketplace** — see how a bundle packages several capabilities at once.

4. **Get a live result** — with a calendar connected, ask:
   > "Give me a brief of my day — all my meetings today, laid out so I can see what's coming."
   - ✅ Done when you get an interactive day view you can click into (not a flat text list).
   - **No calendar connector?** Use the optional [`project-docs/`](./project-docs/) sample project instead and ask for an *interactive chart* of real data — e.g. *"chart page-load time against employee count from the performance logs"* — so you still see a live, interactive result.

5. **Schedule it** — set the brief to run each morning:
   > "Every weekday at 8am, prepare a brief of my day's meetings and have it ready for me."
   Then trigger it once on demand so you see a real result land now.
   - ✅ Done when you've created the scheduled task and can find where to edit or cancel it.

6. **Capstone — build one real flow yourself.** In your own project, pick **one** and assemble it end-to-end:
   - run your new meeting-notes skill on a real (non-sensitive) transcript of your own; **or**
   - connect something you actually track and ask for a live brief; **or**
   - do a plan → review → apply on a real note and save a versioned output.
   - ✅ Done when you produced one real, useful result that used **two or more** things you learned today — and *you* assembled the flow.

## What you need
- [`team-sync-transcript.md`](./team-sync-transcript.md) — a short sample transcript to test your new skill.
- A calendar — a **sample** one on the shared screen — for the live-result and scheduling steps. *(Connectors and scheduling may be admin-gated; if they're not enabled for you, you'll follow along.)*
- *(Optional)* [`project-docs/`](./project-docs/) — **Project Aurora**, a richer sample project (a payroll UI-refresh with a stakeholder brief, ~55 rows of customer feedback, a UX audit, user personas, a kickoff deck, and five days of performance logs). Use it as the data behind an interactive chart in step 4 if you don't have a calendar connector — or explore it as a fuller example of a *furnished* project Claude can reason across.

> **Heads-up:** steps 4 and 5 depend on a connector being available to you. The capstone (step 6) always has a connector-free option — your meeting-notes skill on your own transcript — so everyone builds something real.
