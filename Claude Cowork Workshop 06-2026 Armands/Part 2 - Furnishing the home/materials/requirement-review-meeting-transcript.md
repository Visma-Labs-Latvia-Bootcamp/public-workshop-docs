# Sample transcript — Customer review of the draft *Transaction list* requirements

> **Workshop material** for the *Claude Cowork Workshop* (the "draft a requirements doc from a transcript" segment).
> **Fictional & non-sensitive.** All names, the customer company, and all amounts/IDs are made-up demo data. Safe to paste into AI tools during the workshop.
> **What it is:** a ~30-minute **requirements-review call**. A Visma team walks a customer through the **draft requirements** for a new *Transaction list* screen in a payroll system; the customer reacts to what's written — and what's missing — and gives **10 insights**. The raw transcript is deliberately messy (filler, crosstalk, a screen-share hiccup, anecdotes, off-topic moments) so attendees can practice turning it into clean document updates.
> **How it's used:** pair this with the draft [`transaction-list-requirements.md`](transaction-list-requirements.md) (the **v0.1 baseline**) and have the AI **update the requirements document** with the needs raised here.
> A **facilitator key** at the bottom lists the 10 insights so you can sanity-check what the AI extracts. (Don't show the key to attendees first.)

---

**Meeting:** Nordvik Logistics AS — Payroll Transaction list draft-requirements review
**Date:** (demo)
**Participants:**
- **Marta** — Business Analyst, Visma (host)
- **Jonas** — Product Designer, Visma
- **Hanne** — Payroll Manager, Nordvik Logistics
- **Ola** — Payroll Administrator, Nordvik Logistics

---

[00:00:04] **Marta:** Hi Hanne, hi Ola — can you hear me okay?

[00:00:07] **Hanne:** Yes, loud and clear. Good morning.

[00:00:09] **Marta:** Morning. Jonas is joining as well, he's the designer who's been working on this. Jonas, you there?

[00:00:15] **Jonas:** Yep, hi everyone. Hi Hanne, hi Ola.

[00:00:18] **Ola:** Hi. Sorry, my camera's not working today, it's just me as a circle with initials.

[00:00:23] **Marta:** No worries, that's totally fine. Um, how was the long weekend, did you get any sun?

[00:00:29] **Hanne:** A little. It rained Saturday but Sunday was nice. We were up at the cabin.

[00:00:34] **Marta:** Nice, nice. Whereabouts is the cabin?

[00:00:37] **Hanne:** Up near Geilo. It's, it's my parents' place really, but we, we use it more than they do these days. [laughs]

[00:00:44] **Marta:** [laughs] That's how it goes. Ola, you do anything?

[00:00:48] **Ola:** Not really, I, I moved apartment two weeks ago so I'm still, there's boxes everywhere. So I spent the weekend with, with a flat-pack wardrobe and my, my will to live.

[00:00:58] **Marta:** [laughs] Oh no. The instructions with the little, the little screws —

[00:01:02] **Ola:** Twelve of one kind, fourteen of another, and you find out at step nineteen you used the wrong ones. Yeah.

[00:01:08] **Marta:** [laughs] Okay, well, hopefully this is, this is less painful than that. So — thanks both for making the time. The plan for today, I've got about thirty minutes, is to walk you through the **draft requirements** we've written up for the new Transaction list. Important thing — this is just a draft, nothing here is built yet, it's a document of what we're *planning*. So the more critical you are the better. We'd much rather hear "that's wrong" now than after we've built it.

[00:01:30] **Hanne:** Okay, good, because I have opinions. [laughs]

[00:01:33] **Marta:** Perfect, that's exactly what we want. And just so you know how I'm, how I'm running it — I'll share the document on screen, I'll read out what we've got written for each part, and please just, just interrupt me whenever. Don't, don't wait politely, if something's missing or wrong say it in the moment, that's, that's the gold for us.

[00:01:49] **Hanne:** Noted.

[00:01:50] **Marta:** So let me share the doc. Jonas will jump in on the design questions. Can you, uh — can you see my screen now?

[00:01:58] **Ola:** I see your desktop, the, the wallpaper. Nice mountains.

[00:02:02] **Marta:** Ah. That's, thank you, that's, that's the wrong window though. One second. Sorry. How about now?

[00:02:09] **Hanne:** Now it's, it's the document, but it's, it's tiny. Can you bump the zoom?

[00:02:14] **Marta:** Yeah, sorry, let me, there we go. Is that better?

[00:02:18] **Hanne:** That's better, yeah.

[00:02:20] **Marta:** Okay. So this is the draft requirements document for the new Transaction list. The idea is this is what you'd land on when you open a payroll run and click into the transactions. And it's written here at the top — it replaces the old grid you have today.

[00:02:34] **Hanne:** Okay. So this, this replaces the giant table we've got now.

[00:02:38] **Marta:** Exactly, yeah. So the doc says every line is one payroll transaction — a salary line, an overtime line, a deduction, a reimbursement, all of it. And I've dropped a rough mock-up into the document so you can picture it — those are dummy names, by the way, "Test Testesen", "Demo Demosen", not real people.

[00:02:54] **Hanne:** Yeah I can see. [laughs] Okay. Good, because I was going to ask.

[00:02:58] **Marta:** No, no, we'd never put a real run in a, in a draft. So — first impressions, just from what we've written down and that mock-up?

[00:03:06] **Ola:** It's a lot of columns.

[00:03:08] **Marta:** Say more about that?

[00:03:10] **Ola:** I mean — okay, so in the mock-up I'm counting, the doc lists employee number, name, transaction type, the period, amount, then there's a cost center, a project code, a, what's that one, "account"? And then status. That's, that's nine, ten columns, and the way it's written they're, they're a fixed set, and status — the one I care about most — is way over on the right.

[00:03:32] **Hanne:** Yeah, that's a real thing. We don't use project code at all, Nordvik doesn't, that's not relevant for us, but the cost center we use constantly. Every line has to have a, a cost center for us.

[00:03:44] **Marta:** Okay so that's, that's really useful. The columns listed here are kind of a default we picked, but —

[00:03:50] **Ola:** Can I choose which columns I see? Like hide the project one and move status to the front? Because the doc doesn't, it doesn't say anything about that, it just lists the one set.

[00:03:59] **Jonas:** That's the direction we want to go, yeah. The thinking is you'd be able to pick which columns are visible and drag them to reorder, and it'd remember your choice. It's just, it's not written into the requirements yet — but that's, that's exactly the kind of thing we need to add.

[00:04:14] **Ola:** Okay good, because otherwise that sideways scrolling is going to drive me crazy. On my laptop I can see maybe six columns at once and then it's, it's scroll, scroll, scroll.

[00:04:24] **Hanne:** Mm. And ideally that's per-person, right? Because Ola looks at different things than I do. I care about status and totals, he's more in the, the detail.

[00:04:34] **Jonas:** Yeah, saved per user. So your layout is yours and Ola's is his. Noted, we'll write that in.

[00:04:40] **Hanne:** And does it, sorry, would it stick? Like if I set it up today and log in next month is it still how I left it, or do I redo it every run?

[00:04:49] **Jonas:** It should persist, yeah. Set it once, it stays. That's the intent.

[00:04:53] **Hanne:** Okay. Because if I have to redo it every time that's, that's worse than now. Make sure the doc says it sticks.

[00:04:59] **Marta:** Will do — persistent, per user. Okay, let me scroll down to the next part. So while we're here — how big is a real run for you, roughly?

[00:05:08] **Hanne:** For a normal month we're around, hmm, twenty-six hundred employees, so with all the lines it's, it can be six, seven thousand transactions. December it's worse with the bonuses, that one's, that's our nightmare month.

[00:05:21] **Marta:** Right. So nobody's scrolling through seven thousand lines —

[00:05:25] **Hanne:** No. No, nobody does that. That's the thing with the old system, you have to know what you're looking for. Which brings me to — this filtering section. So the doc says I can filter, let me read it... by transaction type and by period. That's, that's it?

[00:05:41] **Marta:** That's what's in the draft right now, yeah — type and period.

[00:05:45] **Hanne:** Okay, that's a start, but — can I filter by status too? Like show me only the ones with errors? Because that's not in here.

[00:05:53] **Marta:** It's not, no. But that's, that's a good one.

[00:05:56] **Hanne:** That would be huge for us. Honestly the filtering is, that's maybe the most important thing on this whole screen. By type, by period, by status, and — can you combine them? Overtime AND errors AND this period?

[00:06:09] **Jonas:** Yeah, the intent is filters should stack. So you'd narrow it down with as many as you want at once. We should make the requirement say that explicitly.

[00:06:18] **Hanne:** Good. And is it, is it easy to clear them? Because in the old one you set a filter and then you forget it's on and you panic because half your data's "missing". [laughs]

[00:06:28] **Marta:** [laughs] Yes — so we'd want a, a clear-all, and we want the active filters shown as little, little chips so you can see at a glance what's applied. That, that exact panic is what we're trying to kill. None of that's written down yet though, so — good, noting it.

[00:06:43] **Hanne:** Good. Okay. Sorry, I'm jumping ahead.

[00:06:46] **Marta:** No, no, this is exactly the conversation we want. Keep going.

[00:06:50] **Ola:** Can I ask about, um — the amounts. So the doc mentions a total somewhere?

[00:06:56] **Marta:** Let me find it — yeah, here. It says there's a total row at the bottom showing the grand total of all transactions.

[00:07:04] **Ola:** "All transactions." But that's the total of everything. If I filter to overtime I want the overtime total, and honestly I'd want it per employee too. Like, group the transactions by employee and show me each person's subtotal, then the big total at the bottom. The doc doesn't mention any grouping.

[00:07:20] **Hanne:** Yes. Grouping by employee. Because the way we check a run is employee by employee — does this person's total look right for this month. So if it's just a flat list of seven thousand lines I can't, I can't do that sanity check.

[00:07:34] **Marta:** So grouping with subtotals per employee, and — what you said, Ola — the total should reflect whatever filter is active, not "all transactions". Got it.

[00:07:43] **Ola:** Yeah. And the total following the filter, that's important, the way it's written here it's just the grand total, and the old one's the same, and we've, we've made mistakes because of it.

[00:07:53] **Marta:** Can you, can you tell me about one of those? It, it really helps to hear the actual, the actual story.

[00:07:59] **Ola:** Sure, so — this was, gosh, maybe a year ago. We filtered to a, a department to check their overtime, and the total at the bottom still showed the whole company's number, but we, we read it as the department's. So we thought the department had way more overtime than they did, and there was a whole, a whole back-and-forth with their manager, emails, a meeting, and it turned out we'd just, we'd misread a total that wasn't, wasn't filtered. Embarrassing. Couple of hours wasted, easily.

[00:08:27] **Hanne:** And it, it dents trust, right, when we go to a manager with a number and it's wrong. So that filter-aware total is not a, a nice-to-have for us, it's, it's kind of a, a trust thing. Whatever the doc ends up saying, that total has to follow the filter.

[00:08:40] **Marta:** That's, yeah, that's really valuable, thank you. Jonas, you getting all this?

[00:08:44] **Jonas:** Writing it down. Custom columns, status filter, stacking, chips and clear-all, grouping, subtotals, filter-aware total, and the, the story about the department. Got it.

[00:08:54] **Marta:** Okay. Let me scroll to the status part, because I want your honest reaction to this one. So the draft says — let me read it — each transaction has a status, and it's one of "Approved", "Pending", or "Error", and it's shown as text in the row.

[00:09:10] **Hanne:** As text. So in the mock-up here they're all just, they're grey, right? They all kind of look the same. I'm squinting.

[00:09:17] **Ola:** Yeah it's grey text on white, all of them. If it's built like the doc says, plain text, I genuinely can't tell at a glance which is which.

[00:09:25] **Marta:** Okay. That's, that's fair feedback. The draft really does just say "text".

[00:09:30] **Hanne:** Can the errors be red? Or have a, an icon, a little warning triangle or something. Something I can see when I'm scrolling fast. Because if it's plain text an error looks exactly like an approved one and I'll miss it.

[00:09:42] **Jonas:** Yeah. So colour and an icon for status, especially making errors jump out. That's — yeah, the requirement as written is too thin, it just says text. We'll change it.

[00:09:52] **Hanne:** And green for approved maybe, so I can see the run is, is mostly fine. Like if I open it and it's a, a sea of green with three red ones, I know immediately, okay, three things to fix.

[00:10:03] **Ola:** That'd be, that'd actually be calming. [laughs]

[00:10:06] **Jonas:** [laughs] Calming payroll, that's the, that's the dream.

[00:10:10] **Hanne:** And — sorry, is there a colour-blind thing to think about? My, my colleague Per is red-green colour-blind, so if it's only colour he, he won't see it.

[00:10:19] **Jonas:** Yeah, that's, that's exactly why I'd want an icon as well as the colour, not colour alone. Good that you, you raise it though, I'll make sure the requirement says that, that explicitly.

[00:10:29] **Marta:** Okay, so that's the status. Now — the next section is the detail panel. What the draft says is fairly thin, honestly: it just says clicking a transaction opens a panel that shows the full detail of that transaction, and it's marked as planned, not built. So I want to hear — what would you actually need in there?

[00:10:48] **Ola:** That's, that's actually my first question. When there's an error, why is it an error? The doc says the status can be "Error" but nothing about telling me what's *wrong*. Today I have to go dig in three other screens to figure out it's, oh, the employee's tax card is missing or whatever.

[00:11:04] **Marta:** Right. So the detail panel — Jonas, jump in — for an error it should tell you what the problem is and ideally what to do about it.

[00:11:12] **Jonas:** Yeah, so the idea would be you click the line, the panel opens, and for an error it explains the reason in plain language — "missing tax card", "amount exceeds the limit", whatever it is — and links you to where you fix it. So you're not hunting. None of that's in the doc yet, it just says "full detail".

[00:11:28] **Hanne:** That, okay, that would save us so much time. The "what do I do about it" part especially. Because Ola knows, but our new person doesn't, and they just get stuck.

[00:11:38] **Ola:** It's true. I get, I get pinged on Teams like, "Ola what does this one mean", five times a day.

[00:11:44] **Hanne:** And those errors aren't, they're not all the same severity either, right? Like a missing tax card, that stops the payment, that's serious. But some of them are more like, like a warning, the line still pays but you should know about it. The doc just says "Error", flat — does it, should it tell those apart?

[00:12:01] **Marta:** That's a, that's a good distinction. Right now in the draft it's just "Error". Jonas, do we want a notion of error versus warning?

[00:12:09] **Jonas:** We should, yeah. A blocking error versus a, a soft warning. Let me, let me note that as something to design — they probably need to look different, and maybe filter differently too. It's not in the requirements at all right now.

[00:12:22] **Hanne:** Yeah, because I'd treat them, treat them differently. The blocking ones I must fix before I, I can't run payroll. The warnings I, I want to review but they don't, they don't stop me.

[00:12:32] **Marta:** Okay, error-versus-warning, noted as a, a design question. And Ola, you mentioned "amount exceeds the limit" —

[00:12:39] **Ola:** Right, and that one I'd, I'd want to see the limit and the amount side by side. Like "the limit is X, this is Y". So I can see how far over it is.

[00:12:48] **Jonas:** Mm, show the rule it broke and the, the actual value. Good.

[00:12:52] **Hanne:** And — while we're in that panel. Does it, does the doc say anything about a history? Who created the transaction, if it was changed, by whom, when?

[00:13:02] **Marta:** It, it doesn't, no. It just says "full detail".

[00:13:05] **Hanne:** Okay, because we'd need that. An audit trail basically. We get audited, internal and, and the external ones, and the question is always "who changed this and when". Right now I, I genuinely sometimes can't answer that, I have to, to ask around. So having it right there on the transaction, that's, that's a big deal for me — and it's, it's not in here at all.

[00:13:25] **Marta:** No, good catch. Audit trail in the detail panel — who created and changed it, and when. Adding it.

[00:13:32] **Ola:** And can I, in that history, can I leave a, a note? Like sometimes I fix something and I want to write "checked with the manager, this overtime is correct" so the next person doesn't, doesn't re-flag it.

[00:13:43] **Marta:** Hmm. A comment or note on the transaction. That's, that's not in the draft and it wasn't something we'd planned, but it, it makes sense. Let me note it as a, a separate idea. Jonas?

[00:13:53] **Jonas:** Yeah, log it. Comments on a transaction, with, presumably, who wrote it and when, like the rest of the history.

[00:13:59] **Hanne:** That would actually cut down a lot of the, the Teams pinging Ola was talking about. [laughs]

[00:14:04] **Ola:** Please. Yes.

[00:14:06] **Marta:** [laughs] Okay, noted, comments as a, a maybe. Now — speaking of the history, Hanne, you mentioned audits — there's a, a related thing I want to make sure we get right, and I don't think it's anywhere in this draft.

[00:14:18] **Hanne:** The back-dated stuff?

[00:14:20] **Marta:** Exactly that, yeah.

[00:14:22] **Hanne:** Okay so this is, this is a thing. So somebody's salary changes back-dated to two months ago, and now there's a correction transaction in this month's run for the two previous months. Today those just appear and it's really confusing, you see an amount and you don't know it's a back-dated thing. And there's nothing in your doc about it.

[00:14:41] **Marta:** Mm. There isn't.

[00:14:43] **Hanne:** So somewhere — in the list, in the history — I'd want it really clear: this transaction is a retroactive correction, it relates to these periods, here's the original. Linked, ideally. Because the auditors ask about exactly these, and because they, they throw off the employee's total for the month so the, the sanity check we do gets confused.

[00:15:02] **Ola:** And they're always the ones that look wrong at first glance, the back-dated ones. So they're the ones I drill into the most. If the screen just, just told me "this is a retro correction for March", I'd, I'd save so much time.

[00:15:13] **Marta:** Okay, so — retroactive transactions clearly flagged, and linked back to the period and the original they're correcting. That's a, a whole requirement we're missing, thank you.

[00:15:23] **Jonas:** Sorry, can I ask — when you see a back-dated correction today, is it a separate line, or is it bundled into the current amount?

[00:15:31] **Hanne:** Separate line, usually, but it's not labelled, so you only know because the period column says a different month. If you've hidden the period column, which, you know, we just said we want to be able to do, then you'd, you'd have no idea.

[00:15:43] **Jonas:** Right. Okay, so the flag can't just be the period column, it needs to be its own, its own marker on the line. Good point.

[00:15:50] **Hanne:** Maybe a little, a little icon again, like a, a clock or a, a "retro" tag.

[00:15:55] **Jonas:** Yeah, something that survives whatever columns you've got showing. I like the clock idea.

[00:16:00] **Marta:** Good catch, both of you. Okay, the next section in the doc is bulk actions, let me read what we've got. It says — you can select multiple transactions with checkboxes, and a toolbar appears, and you can approve them or edit them together.

[00:16:15] **Hanne:** Oh that's good, that one's actually in there. Because approving one at a time is — for a run that's mostly fine, I just want to select everything that's "Pending" and approve it in one go, and only deal with the errors individually.

[00:16:28] **Ola:** Can you select all of a filter? Like filter to "Pending overtime, no errors" and then select all and approve? Because that combined with the filtering we talked about —

[00:16:37] **Hanne:** That, that's the workflow right there. That's how we'd actually use it. Filter, eyeball it, select all, approve, move on to the, the messy ones. The doc should tie those two together.

[00:16:48] **Ola:** Though — careful, right? Select-all and approve is, that's powerful but it's, it's also how you approve seven thousand things you didn't mean to. Is there a, a confirmation? "You're about to approve 2,400 transactions, are you sure"? Because the draft doesn't say.

[00:17:03] **Marta:** Yeah, for a bulk action that big we'd, we'd want a confirm step that tells you how many you're about to hit. Good — I'll add that, because that's, that's exactly the kind of thing that scares people off bulk actions.

[00:17:14] **Hanne:** And can I, can I undo? If I bulk-approve and then go "oh no".

[00:17:19] **Marta:** Undo's a, a harder one, I won't, I won't promise it, but the confirm step is, is definitely going in. Let me, let me note undo as a, a question mark.

[00:17:29] **Hanne:** Fair.

[00:17:30] **Marta:** Okay, and the last thing actually written in the draft is search. It says you can search by employee name and employee number.

[00:17:39] **Ola:** Yeah, the name search I use constantly. Half my day is someone from a department emails and says "what did Kari get paid for the December overtime" and I need to find Kari's lines fast. So as long as that's, that's in there and it's fast, good.

[00:17:53] **Ola:** Can I search by amount, though? Sometimes finance says "there's a transaction for 12,450, what is it" and I need to find it by the number. That's not in the doc.

[00:18:03] **Marta:** Hmm. Search by amount. Jonas, is that feasible?

[00:18:07] **Jonas:** Not sure — it's name and employee number as written, and amount is a different kind of search, you'd be matching the value. Let me, let me look into it.

[00:18:16] **Ola:** It'd be nice. Not a, not a dealbreaker, but nice.

[00:18:20] **Marta:** Okay, I'll note amount-search as a, a maybe, Jonas to check feasibility. And name and number search confirmed as core. Now — Ola, there's one thing I *don't* see anywhere in this draft, and I have a feeling it matters. You export to Excel, right?

[00:18:36] **Ola:** Constantly. Every single run, first thing. And no, I, I didn't see it in the doc.

[00:18:41] **Marta:** Walk me through that, what, what do you actually do with it?

[00:18:45] **Ola:** So I pull the transactions into Excel and I, I cross-check the totals against what finance has in their, their ledger, and against the, the payment file we send the bank. So three numbers that all have to, to agree. And I do it in Excel because I've got, I've got my own sheet with formulas built up over, over years, that flags the differences for me.

[00:19:06] **Marta:** Okay. So we need an export, and it needs to —

[00:19:09] **Ola:** Respect whatever I've filtered and grouped. If I export and it just dumps all seven thousand lines unfiltered that's, that's not helpful, I've got to re-do all the filtering in Excel.

[00:19:19] **Hanne:** And the column choice too, right? Export what I'm seeing.

[00:19:23] **Ola:** Yeah. Export what's on screen, basically. Same columns, same filter, same grouping. If the screen shows me employee subtotals, the Excel should, should have them too, ideally.

[00:19:33] **Marta:** Okay. Export to Excel, matching the current view — that's a whole requirement we're missing. Is CSV ever needed or is it always Excel?

[00:19:42] **Ola:** Excel is fine for me. Honestly Excel. I don't, I don't use CSV.

[00:19:46] **Hanne:** Finance might want CSV for their import but that's, that's their problem, not this screen. [laughs]

[00:19:52] **Marta:** [laughs] Noted, we'll, we'll park CSV for now, Excel's the, the priority. Okay, let me stop sharing the doc and just, let's talk. So based on what you've seen written down — and again it's a rough draft — what's your, what's your gut feeling?

[00:20:08] **Hanne:** Honestly? It's, it's the right direction. The bones are good. If you nail the filtering and the status visibility and the grouping, that's, that's already better than what we have. My, my worry is performance, can it actually handle seven thousand lines without, you know, choking. The old one, when you sort a big run it just, it hangs for like thirty seconds and you don't know if it's, if it's working or dead.

[00:20:32] **Marta:** Yeah, performance is — we're planning to test with large datasets, that's a, a separate workstream but it's on our radar. I can't, I can't promise numbers today. But that, that hang-for-thirty-seconds thing, even, even just a, a clear loading indicator helps, right?

[00:20:48] **Hanne:** Honestly yes. Even just "it's working, wait" versus, versus silence. Half the time I, I click again because I think it didn't register, and then I've made it worse.

[00:20:58] **Marta:** [laughs] Right. Okay, performance noted, and the, the feedback-while-loading thing. Oh — and one I keep meaning to ask. The language. The draft notes it's all in English right now — "Approved", "Pending" — with localization planned. Is that, is that right for you?

[00:21:15] **Hanne:** Yeah I was going to, going to ask that. It needs to be Norwegian.

[00:21:19] **Marta:** It'll be fully localized, Norwegian and the others. The English in the draft is just, just because it's the draft.

[00:21:26] **Hanne:** Good. Because half my team's English is, you know, it varies, and for, for something like payroll they need to, to understand it exactly. "Pending" versus "Approved", if you're not, not sure of the word, that's, that's risky.

[00:21:39] **Marta:** Completely fair, fully localized, that's, that's a commitment. Is there ever a, a need to print? Like a paper or PDF version? I ask because it's not in the doc.

[00:21:50] **Hanne:** Occasionally. When my, my director signs off the run he likes a, a one-page summary, the totals basically, on paper or PDF. He's, he's old school. But that's, that's the summary, not the seven thousand lines.

[00:22:03] **Marta:** Okay, so a, a print or PDF of the summary view, low priority, more of a, a manager sign-off thing. I'll, I'll note it small.

[00:22:11] **Hanne:** Yeah, small. Don't, don't build it for, for one director. [laughs]

[00:22:15] **Marta:** [laughs] Noted. And do you, do you get notified when a run's ready to review, or is that, is that outside this?

[00:22:22] **Hanne:** Today it's, it's outside, someone messages me. But honestly a, a notification, "the run's calculated, there are six errors", that, that would be nice. So I know when to, to come look.

[00:22:33] **Marta:** Okay, that's, that's a bit beyond this screen but I'll, I'll capture it as a, a related idea — notification when a run's ready, with the, the error count.

[00:22:42] **Hanne:** Don't, don't let me scope-creep you. [laughs]

[00:22:45] **Marta:** [laughs] No, it's, it's all useful, we, we decide later what's in. Okay. I think we've, we've covered a huge amount. Let me, let me try to play back what I heard, and you tell me if I got it wrong.

[00:22:57] **Hanne:** Go.

[00:22:58] **Marta:** So, against what the draft currently says. Columns — the doc has a fixed set, too many by default; you want to choose which show, reorder them, saved per user and persistent. Filtering — the draft only does type and period; you need status too, and they have to stack, with chips and a clear-all, and it's the single most important thing. Grouping by employee with subtotals — not in the doc at all. And the total, which the draft says is "all transactions", has to respect the active filter — that's the trust issue, the department mix-up. Status, which the draft says is just text, needs colour and icons, not colour alone, so errors jump out and Per can see them. The detail panel, which the draft barely describes, needs the error reason and how to fix it — and we should look at blocking errors versus soft warnings — plus a history slash audit trail of who changed what when. Retroactive corrections, not in the doc, clearly flagged with their own marker and linked to the original. Bulk actions are in the draft, but they need the filter-then-select-all workflow and a confirm step that says how many. And export to Excel matching the current view — completely missing from the draft. Plus search, which the draft covers for name and number, and you'd like amount as a maybe. Did I, did I miss anything?

[00:24:18] **Ola:** The, the comments on a transaction.

[00:24:20] **Marta:** Ah, right — comments on a transaction, with who and when. Noted as a maybe.

[00:24:25] **Ola:** And that's, that's pretty much it then. That's a good summary.

[00:24:29] **Hanne:** The performance worry, and the, the print thing, and the localization, and the notification — but those you've, you've noted as the side ones.

[00:24:37] **Marta:** Yep — performance is a separate workstream, print/PDF of the summary is low priority for the director sign-off, localization is committed and already noted in the draft, and the ready-to-review notification is a related idea outside this screen. Did I, did I frame those right?

[00:24:52] **Hanne:** That's right. Yeah. You, you got it all.

[00:24:55] **Marta:** Amazing. Okay so, next steps. On our side — I'm going to take all of this and **update the requirements document**, so the next version actually reflects what you need, not just our first guess. I'll send it over so you can check I, I captured it right. I'll get that to you this week.

[00:25:12] **Hanne:** Great.

[00:25:13] **Marta:** And Jonas is going to sketch the trickier bits so next time you're not just reading text — the status colours and icons, a mock of the detail panel for an error case with the reason and the fix link, and the, the error-versus-warning idea. Jonas, realistic?

[00:25:29] **Jonas:** The status treatment and the detail-panel error case, yes. I'll sketch the error-versus-warning idea so we can, we can talk about it. And I'll check the amount-search feasibility before then.

[00:25:40] **Marta:** Perfect. And we should book the, the follow-up to go through the updated requirements. Hanne, are you the right person for scheduling or —

[00:25:48] **Hanne:** Send it to me and I'll, I'll find a slot. Maybe after, we've got month-end the last week so, first week of next month is better. The last week I'm, I'm useless for meetings.

[00:25:58] **Marta:** Got it, I'll, I'll aim for the first week. Should I, should I include Ola again, or —

[00:26:03] **Ola:** Yeah please, this is, this is my screen really, I'm in it all day.

[00:26:07] **Hanne:** Definitely include Ola. And maybe, maybe Per from my side for the next one, the, the colour-blind point, he'd be a good, good test.

[00:26:15] **Marta:** Oh that's a, that's a great idea, yeah, bring Per. And one open thing — the amount search, Jonas is checking, and Ola, if you think of more of those "find it by X" cases, just, just email me, that helps us shape the search requirement.

[00:26:30] **Ola:** Will do. I'll, I'll keep a note this month of every time I, I struggle to find something.

[00:26:35] **Marta:** Oh that'd be, that'd be gold, thank you. Anything else from either of you before we, we wrap?

[00:26:41] **Hanne:** No, this was good. Genuinely. It's, it's nice to be asked before it's built for once. Usually it just, it just appears and we, we live with it. [laughs]

[00:26:50] **Marta:** [laughs] That's, that's the whole idea, that's why we do these before we write the final spec. Ola, anything?

[00:26:56] **Ola:** No, I'm, I'm happy. Just, just looking forward to the, the filtering honestly. That'll, that'll change my week.

[00:27:02] **Marta:** [laughs] We'll, we'll make the filtering good, I promise. Okay. Thank you both so much, really, really helpful. I'll get the updated requirements over this week, I'll find a, a first-week slot and include Ola and Per, and Jonas will have the, the sketches for next time.

[00:27:18] **Hanne:** Sounds perfect. Thank you, Marta. Thanks Jonas.

[00:27:21] **Jonas:** Thank you, this was, this was really useful for me. Bye.

[00:27:24] **Ola:** Thanks, bye everyone.

[00:27:26] **Hanne:** Bye bye.

[00:27:27] **Marta:** Bye, take care.

[recording ends 00:27:32]

> *(With the screen-share waits, the document scrolling, and natural pauses that don't all show as text, this was a ~30-minute session. Treat the transcript as the full meeting.)*

---

## Facilitator key — the 10 customer insights (don't reveal before the exercise)

Use this to check what the AI pulled out, **and** to check that it correctly updated the draft `transaction-list-requirements.md` rather than starting from scratch. The customer raised roughly these ten — each is a change or addition to what the draft (v0.1) says:

1. **Customizable columns** — the draft has a fixed default set; users want to choose, reorder, and save which columns show (per user, persistent across runs). Nordvik doesn't use "project code"; uses cost center on every line.
2. **Filtering by status + stacking** — the draft only filters by type and period; add **status** filtering, make filters **stack/combine**, with visible filter chips and an easy clear-all. Called out as the single most important feature.
3. **Grouping with subtotals** — not in the draft; group by employee, show per-employee subtotals; needed for their employee-by-employee sanity check.
4. **Filter-aware total** — the draft says the total is "all transactions"; the grand total (and subtotals) must reflect the **active filter**. Framed as a *trust* issue, backed by the department-overtime mix-up anecdote.
5. **Status visibility** — the draft says status is shown as plain text; want colour **and** an icon (not colour alone — colour-blind colleague), errors red, approved green, visible while scrolling fast.
6. **Error reason + fix** — the draft's detail panel only says "full detail"; clicking an error should explain *why* in plain language and link to where to fix it. Related design question: **blocking errors vs. soft warnings** should look/filter differently; show the rule broken + actual value (e.g. limit vs amount).
7. **Detail panel history / audit trail** — not in the draft; who created/changed a transaction, when; needed for internal & external audits.
8. **Retroactive corrections flagged & linked** — not in the draft; back-dated corrections need their own marker (e.g. a clock/"retro" icon, not the period column, which may be hidden) and a link to the original period/transaction.
9. **Bulk actions enriched** — the draft has basic select-and-approve; add the "filter → select all → approve" workflow and a **confirm step stating the count**; undo requested (raised as a question mark).
10. **Export to Excel matching the current view** — completely missing from the draft; same columns, filter, and grouping; for reconciliation against finance's ledger and the bank payment file. Excel, not CSV.

**Additional minor requests** (not part of the core 10 — good for testing what the AI keeps vs. drops, and for the "is this a real ask?" discussion):
- **Comments/notes on a transaction** (with who + when) — to reduce repeated questions.
- **Loading feedback / progress indicator** — "it's working, wait" instead of silence on big operations.
- **Ready-to-review notification** with the error count — acknowledged as beyond this screen.
- **Print / PDF of the summary view** — low priority, for a director's sign-off.
- **Amount search** — feasibility unknown.

**Pure "noise"** (off-topic / not actionable — good for showing the AI should drop these): cabin/Geilo small talk, the flat-pack wardrobe story, the wrong-window screen-share glitch, the document being small/slow to share.

**Open / unresolved items** (good for the "mark as [unclear] / [unassigned]" teaching):
- Amount search — feasibility unknown; **Jonas to check**.
- Undo for bulk actions — not promised; **open question**.
- Performance with ~7,000 lines — acknowledged, **separate workstream**, no commitment.
- Localization — committed (already noted in the draft); Norwegian + others.
- Follow-up session — first week of next month, include Ola and Per; **Hanne to find a slot**.
- Updated requirements write-up — **Marta to send this week**.
- Ola to keep a log of "couldn't find it by X" cases and **email Marta**.
