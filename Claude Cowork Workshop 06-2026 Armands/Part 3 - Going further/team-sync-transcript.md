# Weekly team sync — raw transcript

> **Demo / non-sensitive.** A short, rough meeting transcript for the *Claude Cowork Workshop* — used in §13 to test the live-created "structure meeting notes" skill. All names, products, and figures are fictional. Deliberately raw: spoken-style, with small talk and tangents to filter out.
>
> *Project "Atlas" — internal web team weekly sync. ~15 min. Recorded 2026-06-15.*

---

**Maria (PM):** Okay, I think we're all here. Jonas, you're a bit frozen — there you are. Right, let's get going, I've got a hard stop at half past.

**Tom (BA):** Before we start — did anyone fix the coffee machine on the third floor? It ate my coin again.

**Priya (QA):** Facilities said Thursday. Don't hold your breath.

**Maria:** Ha. Okay, status first. Jonas, where are we on the release?

**Jonas (dev lead):** So the build's green as of this morning. The export-to-CSV feature is done and merged. The only thing still open is the date-range picker — it's behaving weird on Safari, the dropdown closes when you click into the month field.

**Priya:** Yeah I logged that yesterday, it's reproducible on Safari 17 but not Chrome or Firefox. I marked it high because it's on the main flow.

**Maria:** Is that a blocker for Friday?

**Jonas:** Honestly, yes. If we ship with that, half the support tickets will be Safari users who can't pick a range. I'd rather hold the picker than ship it broken.

**Maria:** Okay. Decision then — we pull the date-range picker out of Friday's release and ship the rest. Jonas, you'll feature-flag it off?

**Jonas:** Yep, I'll wrap it in the flag today so the CSV export still goes out clean.

**Maria:** Good. Priya, keep the Safari bug open and we'll target it for the next sprint.

**Priya:** Will do. I'll also add a Safari case to the regression suite — we clearly don't have enough browser coverage there.

**Tom:** Quick one — the analytics team pinged me. They want to know how many people actually use the CSV export once it's live. Do we have event tracking on that button?

**Jonas:** Not yet. We'd have to add an event. It's small but it's not in this build.

**Tom:** Can we get it in before Friday or is that next sprint too?

**Jonas:** Let's not rush it into Friday. I don't want to touch the build again once it's green.

**Maria:** Agreed. Tom, can you write up exactly what the analytics folks want to measure — which events, what properties — and we'll scope it next planning? I don't want to guess and build the wrong thing.

**Tom:** Sure, I'll get the requirements from them and drop a one-pager in the channel by tomorrow.

**Maria:** Perfect. What else... oh, the new customer — Berg & Co — they start their trial Monday. Anyone touching onboarding?

**Priya:** I did a dry run of the signup flow this morning. It works, but the welcome email still has the old logo on it. Cosmetic, but it's the first thing they see.

**Maria:** Let's fix that, it's a five-minute thing. Who owns the email templates?

**Jonas:** That's me, technically. I'll swap the logo today.

**Tom:** While we're on it — do we have a doc for what Berg & Co actually need? Last time we onboarded someone blind and it was painful.

**Maria:** Fair. That's an open question — I'm not sure anyone's captured their requirements yet. I'll check with sales and find out who owns that account.

**Priya:** Did everyone see the photos from the team dinner? Tom's dance moves are... a lot.

**Tom:** We agreed those would never be discussed in a meeting.

**Maria:** [laughs] Moving on. Anything else for the good of the group? No? Okay — so to recap: CSV export ships Friday, date-range picker is flagged off and moves to next sprint, Tom gets the analytics requirements, Jonas fixes the email logo, and I'll chase the Berg & Co requirements. Thanks everyone.

**Jonas:** Thanks all.

**Priya:** Bye!
