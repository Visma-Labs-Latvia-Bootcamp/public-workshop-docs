# Payroll Transaction list — Requirements

> **Status:** Draft **v0.1** — prototype baseline · prepared **ahead of** the customer review. **Customer feedback not yet incorporated.**
> **What this is:** the Transaction list screen as currently designed/built in the prototype — the starting point we'll put in front of the customer. It will be **updated from the review meeting** (see [`requirement-review-meeting-transcript.md`](requirement-review-meeting-transcript.md)).
> **Captured:** 2026-06-11 · **Author:** Visma payroll product team
>
> *Demo / non-sensitive. All names and figures are fictional.*

---

## 1. Overview & context

The Transaction list is the screen a user lands on when they open a payroll run and click into its transactions. It is intended to **replace the legacy grid** — the large flat table used today. Every line represents one payroll transaction: a salary line, an overtime line, a deduction, a reimbursement.

**Intended users:**

- **Payroll Manager** — reviews a run and signs it off.
- **Payroll Administrator** — works the detail of a run day to day.

**Scale:** a real payroll run can be several thousand transactions.

This document describes the **current prototype scope** — what we have built or planned so far. It is deliberately the *baseline*: our starting design, written before we've heard how customers actually work. The customer review is where we expect it to change.

---

## 2. Functional requirements (current prototype scope)

### FR-1 — Transaction list & columns

- Show one row per payroll transaction.
- Display a default set of columns: **employee number, name, transaction type, period, amount, cost center, project code, account, status**.

### FR-2 — Filtering

- Provide a filter control (funnel icon) on the list.
- Filter by **transaction type** and by **period**.

### FR-3 — Totals

- Show a total row at the bottom of the list with the **grand total of all transactions**.

### FR-4 — Status

- Each transaction carries a status: **Approved**, **Pending**, or **Error**.
- The status is shown as text in the transaction row.

### FR-5 — Transaction detail *(planned)*

- Clicking a transaction opens a **detail panel** showing the full detail of that transaction.
- Not yet built in the prototype; included here as planned scope.

### FR-6 — Bulk actions

- Select multiple transactions (checkboxes); a contextual toolbar appears.
- **Approve** or **edit** the selected transactions together.

### FR-7 — Search

- Search the list by **employee name** and **employee number**.

---

## 3. Cross-cutting / non-functional

| # | Concern | Current position |
|---|---------|------------------|
| NFR-1 | **Localization** | Prototype is currently in **English**. Full localization (Norwegian and others) is **planned** — details TBD. |
| NFR-2 | **Performance** | Must handle large payroll runs (several thousand lines). Targets and limits **TBD**. |

---

## 4. Open questions — to validate in the customer review

These are the things we want to learn from the review. *(Answers are not yet known — the review is where we expect to capture them.)*

- Is the default column set (FR-1) the right one for how customers actually work?
- Which filters (FR-2) matter most in day-to-day review, and how are they used together?
- What do reviewers need to see and do in the transaction detail panel (FR-5)?
- How do customers currently check a run and sign it off?
- What do customers do with the data outside this screen (e.g. other tools, reconciliation)?

---

## 5. Change log

| Version | Date | Summary |
|---------|------|---------|
| **v0.1** | 2026-06-11 | Initial **prototype baseline**, prepared ahead of the customer review. Customer feedback not yet incorporated. |

> **Next iteration:** update this document from the review transcript ([`requirement-review-meeting-transcript.md`](requirement-review-meeting-transcript.md)). The review is expected to refine several of the requirements above and add new ones — record those changes here as the next version.
