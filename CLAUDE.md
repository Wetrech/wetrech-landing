# CLAUDE.md — Website (wetrech-landing)

Guidance for agents working on the Wetrech public landing page
(github.com/wetrechtech/wetrech-landing, deployed at www.wetrech.com).

## Purpose

Public-facing marketing site for Wetrech Technologies. Three languages
(TR/EN/AR). This is the company's front door for municipalities,
distribution utilities, investors, and grant evaluators — every claim on
it may be read by a technical buyer or a due-diligence reviewer.

## Rule 0 — claim discipline (read this first)

Only verified, model-consistent claims go on the site. Canonical claims:

- Energy savings: **"35%'e varan EK tasarruf" / "up to 35% additional
  energy savings"** — always "additional/ek" (on top of LED conversion),
  never a bare percentage, never 40%.
- Pilot commitment threshold (if ever mentioned): 25%.
- Audience: **"belediyeler ve dagitim sirketleri" / "municipalities and
  distribution utilities"** — never municipalities alone.
- NO mesh / self-healing-mesh claims (the architecture is not a mesh).
  Approved wording: "guvenilir kablosuz ag / reliable wireless network";
  failure behavior: device failure -> luminaire falls back to standard
  photocell behavior (lighting service is never interrupted).
- NO audio/speaker claims (hardware has no speaker). Visual signals and
  notifications only.
- NO technical architecture, radio, or protocol detail of any kind
  (topology, frequency, module names, frame/security internals) — same
  IP discipline as wetrech-docs Rule 0. "Kablosuz, uctan uca sifreli"
  is the ceiling of technical specificity.
- Security wording ceiling: "uctan uca sifreli haberlesme, kamera ve
  mikrofon yoktur, kisisel veri islenmez."

If new marketing copy needs a claim not listed here, ask Furkan before
writing it — do not extrapolate from the product's actual capabilities,
because what is TRUE and what is APPROVED FOR PUBLIC are different sets.

## Language rules

- **Rendered site text** (what visitors read): proper Turkish WITH
  diacritics for TR; natural English for EN; Arabic for AR. When unsure
  about an AR translation, translate literally from EN and flag it.
- **Code, comments, commit messages, file names**: Turkish ASCII-only,
  no diacritics — same as every other Wetrech repo.
- Keep TR/EN/AR content synchronized: a claim change in one language
  must be applied to all three in the same commit.

## Git workflow

- Same branch protection as other Wetrech repos if .githooks/ exists
  (develop/main fast-forward only). Plain descriptive commit messages;
  no version-numbered subjects.
- No secrets in the repo (API keys, analytics tokens in plain text).

## Claude Code config in this repo

- `.claude/rules/content-claims.md` — the claim table above in
  checkable form, loads when editing content files.
- `.claude/agents/claim-checker.md` — read-only subagent that reviews
  changed content against the claim rules before publishing.

## NEVER delete

- `CLAUDE.md` (this file).
- Brand assets (logo files) without explicit instruction.

`arsiv/` = eski taslaklar, canli site `public/index.html`'dir, icerik duzenlemeleri SADECE oraya yapilir.
