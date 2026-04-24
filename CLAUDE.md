# CLAUDE.md — NRPG Onboarding Framework

> Governance anchor for the NRPG contractor onboarding / training
> content repository. Closes the DR-655 governance gap.
>
> **NOT LEGAL ADVICE — interim scaffold pending counsel validation.**

*Last updated: 2026-04-24 (Foundation Sprint Day 10).*

---

## 1. Purpose of this repo

Authoring surface for contractor training + onboarding content for the
National Restoration Professionals Group (NRPG) / Disaster Recovery
Australia network.

**Current state:** markdown-only. There is no build, no runtime, no
dependency install. Content lives under `contractor-onboarding/`.

**Planned state (DR-682):** a Next.js app will stand up around this
content to serve it as a gated training portal. Until that ticket
ships, DO NOT install dependencies or scaffold a framework here.

## 2. Relationship to the other repos

- **`Disaster-Recovery`** (sibling) — production monolith. The live
  contractor onboarding flow (`/contractor/apply`) lives there and
  will eventually pull content from this repo once DR-682 is live.
  See that repo's `CLAUDE.md` for live business + compliance rules.
- **`DR-Sandbox-starter`** (sibling) — proposals + research scratchpad.
  The DR-655 audit findings that flagged this repo's governance gap
  live there at
  `../DR-Sandbox-starter/proposals/DR-655-nrpg-onboarding-audit/findings.md`.
- **This repo** — content authoring only (for now). Treated as a CMS
  working tree.

## 3. What agents CAN do here (today)

- Read any existing markdown.
- Fix Australian English spelling / grammar in existing markdown.
- Add images under an `images/` folder next to the markdown that
  references them.
- Add new markdown modules under `contractor-onboarding/` following
  the existing folder structure.
- Correct factual errors flagged by subject-matter experts with a
  clear trace in the commit message.

## 4. What agents CANNOT do here (today)

- Do NOT install dependencies (`npm install`, `pip install`, etc.).
- Do NOT add a `package.json`, `next.config.js`, `tsconfig.json`, or
  any build scaffold. DR-682 owns that decision.
- Do NOT pre-empt the planned DR-682 framework — no scaffolding, no
  routing, no component work, no boilerplate.
- Do NOT deploy anything from this repo.
- Do NOT add CI workflows without explicit instruction.
- Do NOT push to `master` — PRs only.
- Do NOT skip git hooks (`--no-verify`) — if none are configured yet,
  that's fine; if configured later, honour them.

## 5. Australian English (mandatory)

All content in this repo is in Australian English. Full rule set
lives in the Disaster-Recovery repo at
`../Disaster-Recovery/.claude/rules/australian-english.md`.

Quick reference:

- `organise` not `organize`.
- `colour` not `color`.
- `centre` not `center`.
- `licence` (noun) / `license` (verb); `practice` (noun) / `practise`
  (verb).
- Dates: `DD/MM/YYYY` or ISO `2026-04-24`.
- Currency: `$1,200` for AUD, `NZ$1,200` for NZD.
- GST-inclusive unless explicitly stated.

US spellings in training content are BUGS — fix on sight.

## 6. Compliance boundary

Content here may be read by contractors during onboarding and therefore
must match the compliance posture of the Disaster-Recovery network.
Key constraints (mirrored from
`../Disaster-Recovery/.claude/rules/compliance.md`):

- **Do NOT** use the phrases "insurance approved", "bill your insurer",
  "guaranteed approval", "every insurer", "fastest response", or any
  other ACL s29-risk puffery.
- **Do** use "IICRC-certified" for credential language.
- **Do NOT** give legal advice, financial advice, or insurance advice
  in training content. Link to the Disaster-Recovery guide pages for
  client-facing compliance.
- **Do NOT** include contractor commission data, Equipped finance
  terms, or any internal economics. That data class is CONFIDENTIAL
  / INTERNAL and does not belong in training content.

## 7. Content conventions

- **One module per folder** under `contractor-onboarding/`. Folder name
  in kebab-case.
- **`README.md`** at the root of each module describing scope, intended
  audience, estimated completion time.
- **Images** in a co-located `images/` folder. Reference with relative
  paths.
- **Links** to the live `disasterrecovery.com.au` site for anything
  that belongs on the public guides — do not duplicate guide content
  here.

## 8. DR-655 governance gap — what this file closes

Before this file landed, the repo had no CLAUDE.md and no
contribution guide. Agents arriving cold had no way to know:

- That the repo is markdown-only by design (today).
- That DR-682 is the paired ticket for standing up the framework.
- That Australian English is mandatory.
- That compliance rules from Disaster-Recovery apply here too.

This file fixes that. See the DR-655 findings file in
DR-Sandbox-starter for the audit trail.

## 9. When in doubt

1. Read this file.
2. Read `../Disaster-Recovery/CLAUDE.md` + the
   `../Disaster-Recovery/.claude/rules/` directory.
3. Read the DR-655 findings.
4. Ask before installing, deploying, or scaffolding.

---

## References

- `../Disaster-Recovery/CLAUDE.md` — live rules for the production monolith.
- `../Disaster-Recovery/.claude/rules/` — topic-specific rule files.
- `../DR-Sandbox-starter/proposals/DR-655-nrpg-onboarding-audit/findings.md` — audit that prompted this file.
- DR-682 — paired ticket for framework stand-up.
