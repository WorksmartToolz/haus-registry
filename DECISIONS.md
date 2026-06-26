
# Decision Log – Haus Registry

Every significant architectural, product, or strategic decision is recorded here.
Format: Decision → Alternatives Considered → Rationale → Date

---

## D-001 | Working Name (Superseded)
**Decision:** Property Passport (working title only)
**Status:** SUPERSEDED by D-002
**Date:** 2026-06-24

---

## D-002 | Company Name & Full Product Naming System
**Decision:** Haus Registry (company) with Registry-prefixed product namespace
**Alternatives Considered:** Property Passport, HomeRecord, DwellOS, HouseChain
**Rationale:** "Haus" signals permanence, heritage, and European registry tradition.
"Registry" as a shared prefix creates a scalable brand language where every product
surface is instantly recognizable as part of the same ecosystem. The naming system
was designed to be modular — each product name communicates its function while
reinforcing the registry metaphor that is central to the company's identity.

**Full Naming System:**

| Level                   | Name                    | Purpose                                                         |
|-------------------------|-------------------------|-----------------------------------------------------------------|
| Company                 | Haus Registry           | The company                                                     |
| Platform                | The Registry            | The ecosystem                                                   |
| Homeowner Workspace     | My Registry             | The homeowner dashboard                                         |
| Property Record         | Property Registry       | The permanent digital record for a property                     |
| Primary Deliverable     | Registry Report         | The shareable report generated from the Property Registry       |
| Property Timeline       | Registry Timeline       | Chronological history of the property                           |
| Verification Badge      | Registry Verified       | Indicates verified information                                  |
| Trust Metric            | Registry Confidence Score | Measures completeness and trustworthiness                     |
| Property Identifier     | Registry ID             | Permanent identifier for every property                         |
| Document Storage        | Registry Vault          | Secure storage for warranties, invoices, permits, manuals, etc. |
| Document AI             | Registry AI             | AI extraction, classification, and analysis                     |
| Developer Platform      | Registry API            | API for third-party integrations                                |
| Professional Portal     | Registry Pro            | Contractors, inspectors, appraisers, lenders, insurers          |
| Verification Service    | Registry Verify         | Workflow for validating documents and claims                    |
| Insights                | Registry Insights       | Analytics and predictive maintenance                            |
| Notifications           | Registry Alerts         | Maintenance reminders, warranty expirations, recalls            |
| Network                 | Registry Network        | Manufacturers, contractors, lenders, insurers, municipalities   |

**Date:** 2026-06-24

---

## D-005 | Constitutional Document Completion Order
**Decision:** Write all four constitutional documents before any market, product,
or technical documents
**Rationale:** Every downstream document must trace to a constitutional document.
Writing market analysis, personas, or architecture before the governing beliefs
are locked creates drift risk — downstream documents would be written without
a stable anchor and would need to be revised when beliefs were later clarified.
**Date:** 2026-06-24

---

## D-006 | Trust Framework Structure
**Decision:** Six-level source hierarchy (S1-S6) and six verification levels
(VL-1 through VL-6) as the operating model for trust
**Alternatives Considered:** Binary verified/unverified model; three-tier model
(government/professional/self-reported)
**Rationale:** Binary models are too coarse to reflect actual evidentiary
differences between sources. A six-level model captures the meaningful
distinctions between government authority, licensed professional, verified
business, document-supported homeowner submission, AI extraction, and unknown
sources — distinctions that matter to lenders, insurers, and appraisers.
**Date:** 2026-06-24

---

## D-007 | Registry Confidence Score Components
**Decision:** Three dimensions — Coverage, Verification Depth, Recency —
weighted composite
**Rationale:** A single-dimension score (e.g. record count, or average
verification level alone) fails to capture the full picture of documentation
quality. Coverage gaps matter as much as verification depth. Recency matters
because an outdated Registry may not reflect current property state.
All three dimensions must be visible to participants — the score is never
presented as a naked number.
**Date:** 2026-06-24

---

## D-008 | Nothing Is Deleted — Revocation Model
**Decision:** Revoked records are retained with revocation status noted.
No records are deleted from The Registry under any circumstances.
**Rationale:** Deletion destroys the auditability that makes a registry
trustworthy. A record that was once verified and later found to be inaccurate
is itself historically significant — it documents what was believed at a given
time and what was later corrected. Deletion would make the Registry less
trustworthy, not more.
**Date:** 2026-06-24

---
## D-009 — Buyer and seller framed as stewardship roles, not transaction participants

**Date:** 2026-06-25
**Status:** Decided

**Decision:**
The buyer and seller are not treated as transactional participants in the Registry
participant framework. The seller is the Primary Steward at the moment stewardship
transfers. The buyer is the Incoming Steward beginning a new stewardship. Neither
is a separate persona category.

**Rationale:**
Consistent with the constitutional principle that the property is the primary entity.
Framing buyer and seller as stewardship roles rather than transaction participants
keeps the document philosophically aligned with the Doctrine and prevents the
participant framework from defaulting to real estate transaction logic.

**Implications:**
This framing propagates into the PRD, UX design, onboarding flows, and GTM language.
Every downstream document that references buyers or sellers should inherit this framing.

---
## D-010 — Stakeholder analysis organized by institutional relationship, not commercial priority
**Date:** 2026-06-25
**Status:** Decided
Full rationale in Doc 08 — Stakeholder Analysis.

---
## D-011 — Participant analysis and stakeholder analysis are distinct analytical layers
**Date:** 2026-06-25
**Status:** Decided
Full rationale in Doc 08 — Stakeholder Analysis.

---
## D-012 — Strategic Importance classifications are property-centric, not revenue-centric
**Date:** 2026-06-25
**Status:** Decided
Full rationale in Doc 08 — Stakeholder Analysis.

---
## D-013 — Constitutional Traceability, Related Documents, and Downstream Dependencies are repository standards
**Date:** 2026-06-25
**Status:** Decided
Full rationale in Doc 08 — Stakeholder Analysis.
