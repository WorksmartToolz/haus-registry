HAUS REGISTRY | Session 006 Brief
Repo: https://github.com/WorksmartToolz/haus-registry
Branch: main (only branch — master deleted)
Phase: Product Definition
Documents Complete: 14 of 28

---

GOVERNANCE (load first — these are authoritative):
  DECISIONS.md (root) — D-001 through D-041
  SESSION_LOG.md (root) — Sessions 001-005
  docs/01-governance/00-repository-authoring-standard.md
  docs/01-governance/04-living-repository-standard.md
  docs/01-governance/02-glossary.md

CONSTITUTIONAL (settled — do not reopen):
  docs/01-constitutional/00-founders-insight.md
  docs/01-constitutional/01-founding-thesis.md
  docs/01-constitutional/02-missing-memory-layer.md
  docs/01-constitutional/03-haus-registry-doctrine.md
  docs/01-constitutional/04-trust-framework.md

DATA ARCHITECTURE (settled — do not reopen):
  Institutional Record: persistent institutional representation of lifecycle
  Registry Event: sourced assertion, five classes, append-only
  Registry ID: opaque, permanent, unconditionally assigned at entry
  Confidence: Coverage 35% + Verification Depth 40% + Recency 25%
  Property Registry: Identity Layer + Record Layer

KEY DECISIONS FOR THIS SESSION:
  D-040: PRD defines capabilities; Business Model defines value capture — separate concerns
  D-041: Product Principles belong in PRD opening section, not a standalone document

---

OPEN SEQUENCE DECISIONS (resolve before Doc 14):
Three questions from the Session 005 architectural review remain open.
Do not skip these — they affect document numbering and inheritance.

  1. Technical Stack (Doc 26)
     Currently in docs/07-system/ but numbered 26, after business documents.
     Technical Stack is a dependency for System Architecture (15), Database
     Design (16), API Spec (17), AI Architecture (19) — not something that
     follows monetization decisions.
     Decision needed: renumber it earlier in the system phase, or keep 26
     as a late-stage consolidation document with a different scope?

  2. Regulatory Considerations (Doc 21)
     Currently positioned after six system architecture documents.
     Regulatory constraints (FCRA, CCPA, RESPA, state data laws) are
     architectural constraints that affect the PRD, API design, security
     model, and data access model.
     Decision needed: does a regulatory framing belong earlier, or is
     Doc 21 in its current position sufficient?

  3. Document count: is 28 the right number?
     The 28-document count was inherited from the Session 001 scaffold,
     not derived from the actual work. Now that the repository has depth,
     the sequence deserves a deliberate answer.
     Decision needed: validate 28 as correct, or revise the sequence?

---

NEXT ACTION (after sequence decisions):
  Doc 14 — Product Requirements Document
  File: docs/06-product/14-product-requirements.md
  Organize around product surfaces: My Registry, Registry Pro, Registry
  Report, Registry Vault, Registry AI, Registry API, Registry Verified,
  Registry Confidence Score.
  Open with a Product Principles section translating constitutional
  philosophy into product-layer design constraints (D-041).
  Full product vision — no MVP scoping here.
  MVP Definition is Doc 27 and inherits from this document.

---

REPOSITORY STRUCTURE (canonical):
  docs/01-constitutional/   Constitutional docs (Docs 00-04) — COMPLETE
  docs/01-governance/       Authoring Standard, Glossary, Living Standard
  docs/02-market/           Market docs (Docs 05-06) — COMPLETE
  docs/03-users/            User/stakeholder docs (Docs 07-08) — COMPLETE
  docs/05-data/             Data architecture (Docs 09-13) — COMPLETE
  docs/06-product/          Product docs (Docs 14, 27) — NEXT
  docs/07-system/           System docs (Docs 15-21, 26) — PENDING
  docs/08-go-to-market/     GTM (Doc 22) — PENDING
  docs/09-business/         Business (Docs 23-24) — PENDING
  docs/10-roadmap/          Roadmap (Docs 25, 28) — PENDING
  DECISIONS.md              Root level
  SESSION_LOG.md            Root level

PRODUCT NAMING (reference):
  Company: Haus Registry | Platform: The Registry
  Homeowner dashboard: My Registry | Record: Property Registry
  Report: Registry Report | ID: Registry ID | AI: Registry AI
  Storage: Registry Vault | Pro portal: Registry Pro | API: Registry API
  Score: Registry Confidence Score | Badge: Registry Verified
  Network: Registry Network | Insights: Registry Insights
  Alerts: Registry Alerts | Verify: Registry Verify
