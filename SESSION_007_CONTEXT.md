HAUS REGISTRY | Session 007 Brief
Repo: https://github.com/WorksmartToolz/haus-registry
Branch: main (only branch)
Phase: System Architecture
Documents Complete: 15 of 28 (Doc 14 committed this session)

---

OPERATING MODE (maintain throughout):
- Architecture partner, not brainstorming assistant
- Decision Enforcement Protocol: check Constitution → Authoring Standard → DECISIONS.md → upstream dependencies before raising any question
- Inheritance Report required before drafting each major document
- DECISIONS.md is an executable architectural specification — not historical documentation

GOVERNANCE (load first):
  DECISIONS.md (root) — D-001 through D-044
  SESSION_LOG.md (root) — Sessions 001-006
  docs/01-governance/00-repository-authoring-standard.md
  docs/01-governance/04-living-repository-standard.md
  docs/01-governance/02-glossary.md

KEY DECISIONS FOR THIS SESSION:
  D-040: PRD defines capabilities; downstream documents implement them
  D-041: Product Principles in Doc 14 are the inheritance point for System Architecture
  D-043: Technical Stack (Doc 26) is a synthesis document — inherits from system docs
  D-044: Product element taxonomy — two surfaces, four platform services, four artifacts,
          two trust components, three network/intelligence elements

PRODUCT PRINCIPLES FROM DOC 14 (Doc 15 inherits all seven):
  1. Property is always the anchor — nothing attaches primarily to a person
  2. Record accumulates — no system action may reset or truncate it
  3. System assembles, does not adjudicate — no fact assertion without source attribution
  4. Source visibility is non-negotiable — every record carries source tier and verification level
  5. Confidence is multidimensional — always displayed with all three dimensions
  6. Infrastructure, not engagement — accuracy over activity metrics
  7. Every capability passes the governing test (D-016)

SETTLED DATA ARCHITECTURE (Doc 15 must implement, not redefine):
  - Registry ID: opaque, permanent, unconditionally assigned (D-018 through D-021)
  - Four independent architectural layers: Registry ID, Institutional Record,
    Verification, Confidence (D-022)
  - Five Registry Event classes: Occurrence, Observation, Document, Status, Correction (D-024)
  - Append-only: corrections reference and append, never overwrite (D-025)
  - Confidence weighting: Coverage 35%, Verification Depth 40%, Recency 25% (D-036)
  - Ownership transition: Occurrence Event in OWN domain — no reset (D-037)
  - Spatial & Site Documentation: first-class domain (D-042)

---

NEXT ACTION:
  Doc 15 — System Architecture
  File: docs/07-system/15-system-architecture.md
  
  Doc 15 inherits from Doc 14's Product Principles and capability definitions.
  It defines how the system is structured to implement those capabilities.
  It does not redefine what capabilities exist.
  
  Expected scope: system components, service boundaries, data flow architecture,
  integration points, scalability principles, and the technical expression of
  the four independent architectural layers (D-022).
  
  Doc 15 is a prerequisite for:
    Doc 16 (Database Design)
    Doc 17 (Registry API Specification)
    Doc 18 (UX Design System)
    Doc 19 (AI Architecture)
    Doc 20 (Security & Privacy)

---

REPOSITORY STRUCTURE (canonical):
  docs/01-constitutional/   Constitutional docs (Docs 00-04) — COMPLETE
  docs/01-governance/       Authoring Standard, Glossary, Living Standard — COMPLETE
  docs/02-market/           Market docs (Docs 05-06) — COMPLETE
  docs/03-users/            User/stakeholder docs (Docs 07-08) — COMPLETE
  docs/05-data/             Data architecture (Docs 09-13) — COMPLETE
  docs/06-product/          Doc 14 COMPLETE | Doc 27 pending
  docs/07-system/           Docs 15-21, 26 — NEXT PHASE
  docs/08-go-to-market/     Doc 22 — pending
  docs/09-business/         Docs 23-24 — pending
  docs/10-roadmap/          Docs 25, 28 — pending
  DECISIONS.md              Root level — D-001 through D-044
  SESSION_LOG.md            Root level — Sessions 001-006
