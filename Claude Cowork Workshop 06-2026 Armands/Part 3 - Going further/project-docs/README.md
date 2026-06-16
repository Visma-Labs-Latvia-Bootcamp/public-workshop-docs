# Project Aurora — sample project material (Cowork demo)

> **Fictional & non-sensitive** demo material for the *Claude Cowork Workshop*.

This folder is a **sample "project" you load into Claude Cowork** — the kind of real-world material a payroll product team accumulates when kicking off a UI-refurbishment project (codename **Project Aurora**). It exists to make the workshop's key theme concrete — *the project is the one home; everything you set up lives in it* — by giving the room a believable body of material to work in.

It belongs to the **same fictional product** as the Transaction-list requirements demo (Visma's payroll product). Project Aurora is the broader programme; the **Transaction-list redesign is its first workstream** — so the `transaction-list-requirements.md` and `requirement-review-meeting-transcript.md` files in **Part 2's `materials/` folder** are the pilot slice of *this* project.

## Files in this project

- **[`initiation-meeting-transcript.md`](initiation-meeting-transcript.md)** — the kickoff meeting where the team reviews the feedback and decides to refurbish the UI (the *why* and the decision).
- **`customer-feedback.xlsx`** — ~55 rows of (fake) customer feedback about the dated interface and UX problems; the **evidence** behind the decision.
- **`project-brief.docx`** — the stakeholder **brief**: goals, reasoning, scope, phased plan, metrics, risks.
- **`user-personas.docx`** — the **people** we're designing for: Hanne (Payroll Manager), Ola (Payroll Administrator), Sara (new joiner at a partner firm), plus an accessibility lens (Per).
- **`current-ui-audit.xlsx`** — the design team's internal **heuristic / UX audit** of the *current* screens (issue · heuristic · severity · linked feedback · recommendation) — the expert-review counterpart to the customer feedback.
- **`aurora-kickoff-deck.pptx`** — the stakeholder **kickoff deck** summarising the brief for the town-hall.
- **`performance-logs/`** — five days of (fake) web **performance logs** (`payroll-web-perf-2026-02-23 … -27.txt`, Mon–Fri). Page-load timings showing load climbs sharply for customers with **more than ~100 employees** (and reaches 20–40s for the largest, e.g. Nordvik/Vestland) — the data behind the performance concern. Same pattern each day with moderate day-to-day variation.

## Also add to the project

Add these as **references / skill links** alongside the three files, so Claude can help build the refurbished UI with the right building blocks:

- **ngx-gaia-for-angular** — <https://mcpmarket.com/tools/skills/ngx-gaia-for-angular>
  *(A skill for Visma's **GAIA** design system in Angular — the component library the refurbishment standardises on, per the initiation meeting and the brief. Adding it to the project means Claude reaches for the correct GAIA Angular components when helping with UI work.)*
- **Visma UX / design guidelines** — <https://ux.visma.com/>
  *(The **main source of truth** for the look and feel — colours, typography, spacing, and design tokens. Point Claude here so the refurbished UI uses the official Visma palette and styles, consistent with GAIA.)*

---
*All names, companies, quotes, and figures in this folder are fictional demo data.*
