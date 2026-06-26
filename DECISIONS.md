# Decision Log — Haus Registry

Every significant architectural, product, or strategic decision is recorded here.
Format: Decision ID | Decision | Rationale | Source | Date

---

## D-001 | Working Name (Superseded)
**Decision:** Property Passport (working title only)
**Status:** SUPERSEDED by D-002
**Date:** 2026-06-24

---

## D-002 | Company Name and Full Product Naming System
**Decision:** Haus Registry (company) with Registry-prefixed product namespace
**Alternatives Considered:** Property Passport, HomeRecord, DwellOS, HouseChain
**Rationale:** "Haus" signals permanence, heritage, and European registry tradition. "Registry" as a shared prefix creates a scalable brand language where every product surface is instantly recognizable as part of the same ecosystem.
**Full Naming System:**

| Level | Name | Purpose |
|---|---|---|
| Company | Haus Registry | The company |
| Platform | The Registry | The ecosystem |
| Homeowner Workspace | My Registry | The homeowner dashboard |
| Property Record | Property Registry | The permanent digital record for a property |
| Primary Deliverable | Registry Report | The shareable report generated from the Property Registry |
| Property Timeline | Registry Timeline | Chronological history of the property |
| Verification Badge | Registry Verified | Indicates verified information |
| Trust Metric | Registry Confidence Score | Measures completeness and trustworthiness |
| Property Identifier | Registry ID | Permanent identifier for every property |
| Document Storage | Registry Vault | Secure storage for warranties, invoices, permits, manuals, etc. |
| Document AI | Registry AI | AI extraction, classification, and analysis |
| Developer Platform | Registry API | API for third-party integrations |
| Professional Portal | Registry Pro | Contractors, inspectors, appraisers, lenders, insurers |
| Verification Service | Registry Verify | Workflow for validating documents and claims |
| Insights | Registry Insights | Analytics and predictive maintenance |
| Notifications | Registry Alerts | Maintenance reminders, warranty expirations, recalls |
| Network | Registry Network | Manufacturers, contractors, lenders, insurers, municipalities |

**Date:** 2026-06-24

---

## D-003 | Founder's Insight as Separate Document
**Decision:** Doc 00 — Founder's Insight is a standalone document preceding the Founding Thesis.
**Rationale:** Serves a different role — the emotional and philosophical origin before the business argument. The insight precedes the thesis and should not be collapsed into it.
**Source:** Session 002
**Date:** 2026-06-24

---

## D-004 | Constitutional Sequence
**Decision:** The constitutional sequence is four governing documents plus one companion: 00 Founder's Insight, 01 Founding Thesis (companion), 02 Missing Memory Layer, 03 Haus Registry Doctrine, 04 Trust Framework.
**Rationale:** The Founding Thesis is a permanent declaration but not a governing constitutional document. The four governing documents answer: Why did this need to exist? What is broken? What do we believe? How is trust created?
**Source:** Doc 02 — Missing Memory Layer
**Date:** 2026-06-24

---

## D-005 | Constitutional Documents Written Before All Others
**Decision:** All four constitutional documents are completed before any market, product, or technical documents.
**Rationale:** Every downstream document must trace to a constitutional document. Writing market analysis, personas, or architecture before the governing beliefs are locked creates drift risk.
**Source:** Session 002
**Date:** 2026-06-24

---

## D-006 | Six-Level Source Hierarchy and Six Verification Levels
**Decision:** Trust Framework defines S1 through S6 source tiers and VL-1 through VL-6 verification levels.
**Alternatives Considered:** Binary verified/unverified model; three-tier model.
**Rationale:** Binary models are too coarse to reflect actual evidentiary differences between sources. Six levels capture the meaningful distinctions between government authority, licensed professional, verified business, document-supported submission, AI extraction, and unknown sources.
**Source:** Doc 04 — Trust Framework
**Date:** 2026-06-24

---

## D-007 | Registry Confidence Score Composition
**Decision:** Registry Confidence Score is a weighted composite of three dimensions: Coverage, Verification Depth, and Recency.
**Rationale:** A single-dimension score fails to capture the full picture of documentation quality. All three dimensions must be visible to participants — the score is never presented as a naked number.
**Source:** Doc 04 — Trust Framework
**Date:** 2026-06-24

---

## D-008 | Nothing Deleted — Revocation Model
**Decision:** No records are deleted from The Registry under any circumstances. Revoked records are retained with revocation status noted.
**Rationale:** Deletion destroys the auditability that makes a registry trustworthy. A record that was once verified and later found inaccurate is itself historically significant.
**Source:** Doc 04 — Trust Framework
**Date:** 2026-06-24

---

## D-009 | Buyer and Seller Framed as Stewardship Roles
**Decision:** The buyer and seller are not treated as transactional participants. The seller is the Primary Steward at the moment stewardship transfers. The buyer is the Incoming Steward beginning a new stewardship period.
**Rationale:** Consistent with the constitutional principle that the property is the primary entity. Prevents the participant framework from defaulting to real estate transaction logic.
**Source:** Doc 07 — Registry Participants
**Date:** 2026-06-24

---

## D-010 | Stakeholder Analysis Organized by Institutional Relationship
**Decision:** Doc 08 organizes stakeholders into four institutional relationship categories: Foundational Institutions, Record Ecosystem Partners, Decision-Making Institutions, Market Infrastructure Partners.
**Rationale:** Stakeholders are defined by how they relate to the Institutional Record, not by market segment or commercial relationship.
**Source:** Doc 08 — Stakeholder Analysis
**Date:** 2026-06-24

---

## D-011 | Participant Analysis and Stakeholder Analysis Are Distinct Layers
**Decision:** Doc 07 (Registry Participants) and Doc 08 (Stakeholder Analysis) are distinct analytical layers. Participants are analyzed by their relationship to the property and its record. Stakeholders are analyzed by their institutional relationship to The Registry as infrastructure.
**Rationale:** Collapsing them would force a single document to serve two different analytical purposes and two different inheritance chains.
**Source:** Doc 08 — Stakeholder Analysis
**Date:** 2026-06-24

---

## D-012 | Strategic Importance Classifications Are Property-Centric
**Decision:** Strategic Importance classifications in the Stakeholder Analysis are based on each stakeholder's relationship to the Institutional Record — not on their revenue potential or commercial priority.
**Rationale:** Consistent with infrastructure-first positioning. Revenue potential is a downstream consideration, not a governing one.
**Source:** Doc 08 — Stakeholder Analysis
**Date:** 2026-06-24

---

## D-013 | Constitutional Traceability, Related Documents, and Downstream Dependencies Are Repository Standards
**Decision:** Every major document closes with three required sections: Constitutional Traceability, Related Documents, and Downstream Dependencies.
**Rationale:** Ensures every document explicitly maps to the constitutional layer and makes its dependency relationships visible. Prevents drift across the document sequence.
**Source:** Doc 08 — Stakeholder Analysis
**Date:** 2026-06-24

---

## D-014 | Institutional Record Definition
**Decision:** The Institutional Record is defined as the persistent institutional representation of a property's lifecycle.
**Rationale:** "Institutional" signals authority. "Persistent" signals continuity. "Lifecycle" signals scope. Distinguishes the Registry's record from owner-held records, title records, or listing data.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

---

## D-015 | Four Architectural Principles of the Data Model
**Decision:** The data model is governed by four architectural principles: canonical identity, accumulated history, domain-agnosticism, and extensibility.
**Rationale:** These principles ensure the data model can serve the 50-year horizon without requiring structural replacement.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

---

## D-016 | Governing Test for Registry Events
**Decision:** The governing test for whether something belongs in the Institutional Record is: does this event materially inform understanding, condition, provenance, risk, or stewardship of the property?
**Rationale:** Provides a principled inclusion criterion that does not require enumeration of every possible event type.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

---

## D-017 | Event Domains Are Classifications Within One Record
**Decision:** Event domains are classification labels within one Institutional Record. They do not create separate records or sub-records.
**Rationale:** The property is one entity. Its record is one record. Domain classification aids retrieval and weighting — it does not fragment the record.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

---

## D-018 | Registry ID as Permanent Canonical Identifier
**Decision:** The Registry ID is the permanent canonical identifier for every property in The Registry. It is assigned at entry and is the foundational key of the entire data architecture.
**Rationale:** Every other identifier (address, APN, MLS number) is mutable. The Registry ID is the stable anchor.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

---

## D-019 | Registry ID Is Opaque
**Decision:** The Registry ID encodes no descriptive attributes. It does not encode address, geography, sequence, or any other property characteristic.
**Rationale:** Opaque identifiers survive changes that would invalidate descriptive identifiers (address changes, parcel splits, rezoning).
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

---

## D-020 | Registry ID Assignment Is Unconditional
**Decision:** Registry ID assignment requires no evidence threshold. A property receives a Registry ID upon entry regardless of how much information is available at the time of entry.
**Rationale:** The Registry accumulates — it does not gatekeep. Requiring evidence to assign an ID would exclude properties with sparse records.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

---

## D-021 | Registry ID Does Not Replace Existing Identifiers
**Decision:** The Registry ID anchors existing identifiers (APN, address, MLS number). It does not replace them. The Registry maps between Registry ID and all known identifiers for a property.
**Rationale:** The Registry operates within the existing ecosystem. Replacement would require industry adoption that cannot be assumed.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

---

## D-022 | Four Architectural Layers Are Independent
**Decision:** The four architectural layers — Registry ID, Institutional Record, Verification, and Confidence — are independent. Each layer can evolve without requiring changes to the others.
**Rationale:** Independence is a prerequisite for the 50-year horizon. Coupling layers would make the architecture brittle.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

---

## D-023 | Registry Event Definition
**Decision:** A Registry Event is a recorded assertion about a property, anchored to a Registry ID, timestamped, attributed to a source, and preserved append-only.
**Rationale:** Events are assertions, not facts. Recording them as assertions with source attribution preserves provenance and enables the verification layer to operate independently.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

---

## D-024 | Five Registry Event Classes
**Decision:** Registry Events are classified into five classes: Occurrence, Observation, Document, Status, and Correction. Class is a required field on every event.
**Rationale:** Classification enables domain-specific retrieval, weighting, and confidence calculation without requiring separate record structures.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

---

## D-025 | Correction Events Reference and Append
**Decision:** Correction Events reference the event being corrected and append the correction. They do not alter or delete the original event.
**Rationale:** Implements D-008 at the event level. The original assertion is preserved as part of the historical record.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

---

## D-026 | Date Uncertainty Recorded, Not Suppressed
**Decision:** Date uncertainty is recorded through a date confidence qualifier. Events with uncertain dates are not suppressed. The vocabulary of date confidence levels is defined in Doc 12.
**Rationale:** Suppressing events with uncertain dates degrades the Institutional Record. The Registry preserves what is known, including the limits of what is known.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

---

## D-027 | Verification and Confidence Are External to the Event Record
**Decision:** Verification status and Registry Confidence are external to the event record. Changes are applied through Status Events and do not modify the original event.
**Rationale:** Keeps the event record immutable while allowing confidence to evolve as verification is obtained.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

---

## D-028 | Source Tier Immutable After Assignment
**Decision:** Source tier is assigned at ingestion and is immutable after assignment. Misclassification is resolved through Correction Events.
**Rationale:** Provenance must be preserved exactly as recorded. Corrections are events, not edits.
**Source:** Doc 11 — Verification Model
**Date:** 2026-06-26

---

## D-029 | Verification Level Updates Recorded as Status Events
**Decision:** Verification level is assigned at ingestion and may be updated over time. All updates are recorded as Status Events. The original event record is not modified.
**Rationale:** Implements immutability while allowing confidence to evolve as verification is obtained.
**Source:** Doc 11 — Verification Model
**Date:** 2026-06-26

---

## D-030 | Event-Level Confidence Is a Weighted Composite
**Decision:** Event-level Registry Confidence is a weighted composite of Coverage, Verification Depth, and Recency. The weighting formula is defined in Doc 12.
**Rationale:** Confidence is multidimensional. No single input determines it.
**Source:** Doc 11 — Verification Model
**Date:** 2026-06-26

---

## D-031 | Property-Level Confidence Score
**Decision:** Property-level Registry Confidence Score is a domain-weighted composite of event-level confidence values. It is recalculated on every new event, verification update, or recency decay threshold crossing.
**Rationale:** Property-level confidence must reflect the full Institutional Record, not any single event or domain.
**Source:** Doc 11 — Verification Model
**Date:** 2026-06-26

---

## D-032 | Registry Confidence Is a Measurement, Not a Judgment
**Decision:** Registry Confidence is a measurement. It informs participants and does not adjudicate properties or owners.
**Rationale:** Prevents misuse of the confidence score as a pass/fail determination. Preserves participant trust in the Registry as neutral infrastructure.
**Source:** Doc 11 — Verification Model
**Date:** 2026-06-26

---

## D-033 | Property Registry Has Two Layers
**Decision:** The Property Registry has two layers: the Identity Layer (immutable, set at creation) and the Record Layer (accumulating, event-driven).
**Rationale:** Separates what never changes from what continuously accumulates. Prevents confusion between identity fields and record fields.
**Source:** Doc 12 — Property Registry Specification
**Date:** 2026-06-26

---

## D-034 | Date Confidence Enumeration DC-1 Through DC-6
**Decision:** Date confidence is enumerated at six levels (DC-1 through DC-6). Events with uncertain dates record the earliest plausible date and the applicable confidence level.
**Rationale:** Preserves sortability while accurately representing temporal uncertainty. Implements D-026.
**Source:** Doc 12 — Property Registry Specification
**Date:** 2026-06-26

---

## D-035 | Domain Registry Specifies Recency Decay Per Domain
**Decision:** The domain registry specifies recency decay periods and coverage weights per domain. Domains with no applicable recency decay retain permanent recency weight. The domain registry is extensible.
**Rationale:** Recency decay must be domain-specific. Construction records do not decay; inspection records do.
**Source:** Doc 12 — Property Registry Specification
**Date:** 2026-06-26

---

## D-036 | Registry Confidence Score Composite Weighting
**Decision:** Registry Confidence Score composite weighting: Coverage 35%, Verification Depth 40%, Recency 25%. Recalibration requires a formal architectural revision and Decision logging.
**Rationale:** Verification Depth is weighted highest as the primary confidence driver. Recalibration pathway preserves long-term adaptability.
**Source:** Doc 12 — Property Registry Specification
**Date:** 2026-06-26

---

## D-037 | Ownership Transition Does Not Reset the Property Registry
**Decision:** At ownership transition, the Property Registry does not reset. The transition is recorded as an Occurrence Event in the OWN domain. All prior events remain active.
**Rationale:** Direct implementation of the constitutional principle: records accumulate, they do not reset.
**Source:** Doc 12 — Property Registry Specification
**Date:** 2026-06-26

---

## D-038 | Canonical Repository Directory Structure
**Decision:** The canonical directory structure is:

```
docs/00-meta/             REMOVED — superseded
docs/01-foundation/       REMOVED — superseded
docs/04-trust/            REMOVED — superseded
docs/01-constitutional/   Constitutional documents (Docs 00-04)
docs/01-governance/       Governance standards
docs/02-market/           Market documents (Docs 05-06)
docs/03-users/            User and stakeholder documents (Docs 07-08)
docs/05-data/             Data architecture documents (Docs 09-13)
docs/06-product/          Product documents (Docs 14, 27)
docs/07-system/           System architecture documents (Docs 15-21, 26)
docs/08-go-to-market/     GTM documents (Doc 22)
docs/09-business/         Business documents (Docs 23-24)
docs/10-roadmap/          Roadmap documents (Docs 25, 28)
DECISIONS.md              Root level
SESSION_LOG.md            Root level
```

**Rationale:** Resolves the structural divergence between the Session 001 scaffold and the work completed in Sessions 002–004. Establishes a canonical layout that accurately reflects the repository's conceptual architecture.
**Source:** Session 005 — Repository Integrity Audit
**Date:** 2026-06-26

---

## D-039 | Repository Map Removed
**Decision:** docs/01-governance/03-repository-map.md is removed from the repository.
**Rationale:** The document was a sparse stub with no unique content beyond what the README, Authoring Standard, and Session Log already provide. Removed by deliberate evaluation, not oversight. May be reintroduced if a concrete need for a centralized dependency graph emerges during the system or product phase.
**Source:** Session 005 — Architectural Review
**Date:** 2026-06-26

---

## D-040 | PRD Defines Capabilities; Business Model Defines Value Capture
**Decision:** The Product Requirements Document (Doc 14) defines what capabilities Haus Registry provides. The Business Model (Doc 23) and Monetization Strategy (Doc 24) define how Haus Registry captures value from those capabilities. These are intentionally separate concerns sequenced as separate documents.
**Rationale:** Product capabilities should not be constrained by monetization decisions at the definition stage. The PRD defines the complete product. Commercial packaging follows from it.
**Source:** Session 005 — Architectural Review
**Date:** 2026-06-26

---

## D-041 | Product Principles Belong in the PRD, Not a Standalone Document
**Decision:** Product-level design principles — the translation of constitutional philosophy into product-layer constraints — are authored as the opening section of Doc 14 (PRD), not as a separate document.
**Rationale:** A standalone Product Principles document would create a dependency layer between the Constitution and the PRD without adding enough unique content to justify its existence. Embedding principles in the PRD makes them immediately actionable for every downstream document that inherits from it.
**Source:** Session 005 — Architectural Review
**Date:** 2026-06-26
