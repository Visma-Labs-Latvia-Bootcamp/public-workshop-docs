# Initiation meeting — Payroll UI Refresh (*Project Aurora*)

> **Workshop material** for the *Claude Cowork Workshop* — sample project material to load into a Cowork project.
> **Fictional & non-sensitive.** The company, people, figures, and quotes are made-up demo data. Safe to paste into AI tools during the workshop.
> **What it is:** the ~25-minute **project-initiation meeting** where Visma's payroll product team reviews mounting customer feedback about the dated interface and **decides to launch a UI-refurbishment programme** (codename *Project Aurora*). The **Transaction list redesign** (see [`../transaction-list-requirements.md`](../transaction-list-requirements.md)) becomes the **first workstream** under this programme.
> **How it's used:** part of the sample "project" you populate in Cowork — pair it with [`customer-feedback.xlsx`](customer-feedback.xlsx) and [`project-brief.docx`](project-brief.docx). Good raw material for asking Claude to draft the brief, extract decisions, or summarise the feedback.

---

**Meeting:** Payroll product — UI refresh · project initiation
**Date:** 2026-03-10
**Participants:**
- **Sofia** — Head of Product, Visma *(sponsor / decision-maker)*
- **Marta** — Business Analyst, Visma
- **Jonas** — Product Designer / Design Lead, Visma
- **Erik** — Engineering Lead, Visma
- **Lena** — Customer Success Lead, Visma

---

[00:00:03] **Sofia:** Okay, I think that's everyone. Erik, you're a touch echoey — can you hear us alright?

[00:00:09] **Erik:** Better now? I moved into one of the small rooms.

[00:00:12] **Sofia:** Much better. Good. So — thanks all for shuffling things to make this work. I'll keep us to about half an hour. The reason I pulled *this* group together specifically: I want us to leave today with an actual decision about the state of the payroll UI. Not another "we should look at that sometime" — a real go or no-go.

[00:00:33] **Marta:** That'd be a nice change. [laughs]

[00:00:36] **Sofia:** [laughs] Right? So the shape of it — Lena's pulled all the customer feedback into one place, Jonas has the design view, Erik's going to keep us honest on what's actually buildable, and Marta's going to take whatever we land on and turn it into a proper brief we can send round. That work for everyone?

[00:00:52] **Jonas:** Works.

[00:00:53] **Erik:** Yep.

[00:00:54] **Sofia:** Lena, you've been sitting on a mountain of this. Set the scene — how bad is it, honestly?

[00:01:01] **Lena:** So, I went back through everything from roughly the last nine months. Support tickets, the NPS verbatims, the user interviews we ran in the autumn, and — this is the part that got my attention — a few sales calls where we actually lost the deal. I put it all into one spreadsheet, deduplicated it, and it's about fifty-odd distinct pieces of feedback. I'll share the file straight after this.

[00:01:24] **Sofia:** And the headline?

[00:01:26] **Lena:** The headline is that it's not really about features anymore. People mostly say the product *does* what they need. What they complain about is how it *looks* and how it *feels* to use. The word "dated" or "old" comes up over and over. One NPS comment literally said — let me find it — "it looks like software from ten years ago." That was a seven-out-of-ten, so not even a detractor.

[00:01:48] **Jonas:** That tracks, sadly.

[00:01:50] **Lena:** And then there's the workflow stuff on top. The Transaction list is the worst offender — people can't tell which lines have errors because everything's grey text, they can't filter properly, the export ignores their filters. But it's across the board: the menus are buried too deep, reports are slow with no loading indicator so people think it's frozen and click again, the login screen looks nothing like the rest of our tools —

[00:02:13] **Erik:** The login one's true, that's a completely different stack, it predates the rest.

[00:02:18] **Lena:** — and on mobile it's basically unusable. Someone left an app-store review saying they tried to approve a run on their phone and the buttons were tiny and half the screen was cut off.

[00:02:28] **Sofia:** Okay. And the lost deals — say more about those, because that's the bit that'll matter upstairs.

[00:02:34] **Lena:** Two I'd flag. One mid-size logistics prospect went with a competitor and the feedback that came back was, the interface "looked dated in the demo" next to the other vendor. We had the functionality. We lost on, on first impression. The other was an accounting firm — a partner, manages payroll for a lot of small clients — and they said onboarding new staff onto our UI takes too long because it's not, not intuitive, so it costs them.

[00:02:59] **Sofia:** That's the one that stings. Okay. Jonas — from the design side, what are we actually dealing with?

[00:03:06] **Jonas:** So the honest answer is there isn't *one* UI. It's grown over, what, a decade, in layers, and every layer used whatever the convention was at the time. So you've got three different button styles, two date pickers, tables that all behave slightly differently. Even the spacing and the typography drift from screen to screen. To a user that reads as "cheap" and "confusing" even if they can't name why.

[00:03:30] **Sofia:** So it's not just "make it prettier."

[00:03:33] **Jonas:** No. I mean it'll *look* better, but the real win is consistency — if every table filters the same way, every status looks the same everywhere, people stop having to relearn each screen. The good news is we don't have to invent that from scratch. There's the **GAIA design system** — it's our component library, the Angular one — and if we standardise the payroll product on it, we get the accessibility, the consistency, the modern look basically for free, and we stop hand-rolling components.

[00:03:59] **Sofia:** GAIA's the one the other teams have been moving to?

[00:04:02] **Jonas:** Yeah. It's Angular components, it's maintained, it's already got the accessibility baked in — which, by the way, solves a real complaint. We've got customers whose colour-blind staff can't tell statuses apart because we only use colour. GAIA's patterns handle that properly.

[00:04:18] **Lena:** That exact complaint is in the spreadsheet, more than once.

[00:04:21] **Sofia:** Good — so design-system-led, not a one-off reskin. Erik, reality check. We're on Angular, yes? What does adopting GAIA across the payroll product actually cost us?

[00:04:32] **Erik:** Right, so. Front end's Angular, that part lines up, GAIA's the natural fit. But I want to be clear-eyed: we cannot big-bang this. There are hundreds of screens. If we try to rewrite the whole UI in one go we'll be heads-down for a year, ship nothing, and the business will lose patience halfway through.

[00:04:50] **Sofia:** Agreed, I don't want a year of silence.

[00:04:53] **Erik:** So my strong recommendation is we do it **screen by screen**, highest-pain first. We pick one screen, rebuild it properly on GAIA, prove the approach end to end — the pattern, the tooling, the migration path — and then we roll that out. Each screen ships as it's done, so customers feel progress continuously.

[00:05:12] **Jonas:** And whatever the first screen is, it sets the patterns everything else copies. So it matters which one we pick.

[00:05:18] **Sofia:** So what's the first screen?

[00:05:21] **Lena:** If we're going by pain, it's the Transaction list. Hands down. It's the single most-complained-about screen and it's the one people are in all day.

[00:05:29] **Marta:** And conveniently we're already partway there. We've got draft requirements for a new Transaction list and a customer review booked — Nordvik. So that work can just *become* the pilot for Aurora rather than being a separate thing.

[00:05:42] **Sofia:** I like that a lot. It means the pilot's already moving and it's grounded in a real customer. Erik, does using the Transaction list as the proving ground work technically?

[00:05:52] **Erik:** It's a good test case, honestly — it's a heavy screen, lots of data, tables, filtering, status, the lot. If we can do the Transaction list well on GAIA, the rest is easier, not harder. So yes.

[00:06:05] **Sofia:** Okay. I'm hearing enough to make the call. Let me say it back and you tell me if I've got it wrong. We launch a **UI-refurbishment programme** for the payroll product — let's keep the codename Aurora — *design-system-led*, standardising on **GAIA**. We do it **screen by screen, worst-first**, shipping as we go, not a big-bang rewrite. And the **Transaction list is the pilot**, building on the work Marta and Jonas already have in flight. Anyone want to argue with any of that?

[00:06:32] **Erik:** No argument. As long as "phased" is written down in blood, I'm happy.

[00:06:36] **Sofia:** [laughs] It'll be in the brief in blood. Jonas?

[00:06:40] **Jonas:** All for it.

[00:06:41] **Lena:** Yes. And can I ask that we keep collecting feedback through it? So we can show the numbers moving, before and after.

[00:06:48] **Sofia:** Definitely — that's how I'll justify the next phase. Which brings me to — Marta, next steps. I want a brief I can send to stakeholders. The why, the goals, the scope, the phasing, who's involved. Short enough that a director will actually read it.

[00:07:03] **Marta:** Got it. I'll draft the project brief — background and the problem, the goals and the reasoning, scope in and out, the phased approach with the Transaction list as pilot, success metrics, stakeholders, timeline, risks. I'll pull the evidence straight from Lena's feedback file so it's grounded. I can have a draft round to this group by end of week and then we send it out.

[00:07:24] **Sofia:** Perfect. Lena — share the feedback spreadsheet with Marta today, and keep it as a living thing, keep logging.

[00:07:31] **Lena:** Will do.

[00:07:32] **Sofia:** Jonas — start sketching the Transaction list on GAIA patterns so we've got something real to react to at the customer review, not just a text doc.

[00:07:40] **Jonas:** Already itching to. I'll have the status treatment and a couple of the table patterns ready.

[00:07:45] **Sofia:** Erik — I want a rough sizing of what the pilot takes, and what the per-screen migration looks like once the pattern's set. Doesn't need to be exact, just enough to plan phase two.

[00:07:55] **Erik:** I'll put a rough estimate together. Pilot first, then an order-of-magnitude for the rollout.

[00:08:01] **Sofia:** Good. Then we're decided. To be clear for the brief — this is a *go*. Project Aurora is happening, pilot is the Transaction list, and we standardise on GAIA. Marta drafts the brief, Lena owns the feedback evidence, Jonas the design, Erik the technical sizing. Anything I've missed before I let you all get your half hour back?

[00:08:20] **Marta:** Just — who's the audience for the brief? Internal stakeholders only, or does it go wider?

[00:08:25] **Sofia:** Internal for now — the leadership group, the payroll teams, and loop in the GAIA design-system folks since we'll be leaning on them. Mark it as for review, not final.

[00:08:35] **Marta:** Clear. I'll get it drafted.

[00:08:37] **Sofia:** Brilliant. Thank you all — genuinely, this is the most decisive half hour I've had this quarter. Let's go make it look less like 2010.

[00:08:45] **Lena:** [laughs] That's the tagline right there.

[00:08:48] **Sofia:** Don't tempt me. Okay — thanks everyone, I'll let you go.

[00:08:51] **Jonas:** Thanks, bye.

[00:08:52] **Erik:** Bye.

[00:08:53] **Lena:** Bye all.

[recording ends 00:08:55]

> *(With the natural pauses and the time spent looking at Lena's spreadsheet on screen, this ran about 25 minutes; the transcript captures the substance.)*

---

## Decisions & next steps (in-meeting recap)

**Decision:** Launch **Project Aurora** — a phased, design-system-led refurbishment of the payroll product UI, standardising on the **GAIA** Angular design system. Done **screen by screen, worst-first**, shipping continuously (no big-bang rewrite). The **Transaction list** is the **pilot**, building on the in-flight draft requirements and the upcoming Nordvik review.

| Owner | Action |
|-------|--------|
| **Marta** | Draft the **project brief** (why, goals, scope, phasing, metrics, stakeholders, timeline, risks); draft to the group by end of week, then circulate. |
| **Lena** | Share the **customer-feedback spreadsheet** with Marta; keep it as a living record and keep logging. |
| **Jonas** | Sketch the Transaction list on **GAIA** patterns (status treatment + table patterns) ahead of the customer review. |
| **Erik** | Rough-size the **pilot** and an order-of-magnitude estimate for the **per-screen rollout**. |
| **Sofia** | Sponsor; brief goes to leadership, the payroll teams, and the GAIA design-system team — **for review**, not final. |
