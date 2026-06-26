# Document 09: Data Architecture
**Haus Registry | Foundation Documentation**
*Phase: Data Architecture | Status: Complete*

---

## Scope

This document defines the nature and organizing principles of the Institutional Record — what it is, what governs it, and what architectural principles all downstream data decisions must honor.

This document does not specify implementation. The event model, verification model, Property Registry specification, and Registry ID are each addressed in their own documents (Docs 10–13). Those documents are architectural consequences of what is established here. This document is their foundation.

---

## The Institutional Record

The Institutional Record is the persistent institutional representation of a property's lifecycle.

This definition contains three claims that must be understood together.

**Persistent.** The Institutional Record does not reset at ownership transfer, does not expire with a subscription, and is not abandoned when a platform shuts down. It is designed to outlast any single owner, any single steward, and any single technology cycle. Persistence is not a feature. It is the purpose.

**Institutional.** The Institutional Record is not a personal file, a homeowner's collection, or a vendor's database. It is a structured, verifiable, and governed record that carries the credibility of its sources and the transparency of its provenance. It is designed to function as infrastructure — trusted by parties who did not create it and relied upon by parties who will never meet.

**Lifecycle.** A property's lifecycle is the accumulation of significant, verifiable events and relationships that shape the property across time. This includes, but is not limited to, construction and commissioning, maintenance and repairs, improvements and renovations, inspections and assessments, ownership and stewardship transitions, regulatory and permitting activity, warranty and manufacturer events, insurance and loss events, and environmental and site observations. These are not separate histories. They are different dimensions of the same Institutional Record.

---

## Architectural Principles

Four principles govern the Institutional Record. They are not implementation guidelines. They are architectural constraints from which all downstream decisions follow.

### 1. The Institutional Record Has One Canonical Identity

Each property has exactly one Institutional Record. That record has one persistent identity — the Registry ID — that it carries from the moment it is created. There are no duplicate records, no parallel histories, and no version forks. Events from multiple sources, submitted by multiple parties, across multiple ownership periods, are all aggregated into this single canonical record.

This principle is the justification for the Registry ID, for continuity across ownership transitions, for duplicate prevention, and for the integrity of event aggregation. A record that can be duplicated, forked, or reset is not an institutional record. It is a file.

### 2. History Is Accumulated, Never Rewritten

Events are added to the Institutional Record. They are never deleted, overwritten, or revised. A correction to a prior event is itself a new event, with its own timestamp, provenance, and verification status. The original event remains.

This principle is what makes the Institutional Record trustworthy. A record that can be altered retroactively carries no institutional weight. The integrity of the Registry depends on the permanence of what has been recorded. Disputes, corrections, and reinterpretations do not change history — they add to it.

### 3. The Institutional Record Is Domain-Agnostic

The Institutional Record does not distinguish between physical events, ownership events, regulatory events, or any other category of property event by kind. Its purpose is to represent any significant property event that can be associated with the property, described through a defined schema, and supported by appropriate provenance and verification.

The governing test for inclusion is:

> Does this event materially inform the understanding, condition, provenance, risk, or stewardship of the property?

If the answer is yes, the architecture is capable of representing it. An inspection that confirms no defects is as institutionally valuable as one that identifies them. A warranty registration, a permit correction, a manufacturer recall — each materially informs the property's record without necessarily changing its condition. The governing test holds for all of them.

Event domains are classifications within the Institutional Record, not separate records. Current recognized domains include:

- Construction and commissioning
- Maintenance and repairs
- Improvements and renovations
- Inspections and assessments
- Ownership and stewardship transitions
- Regulatory and permitting activity
- Warranty and manufacturer events
- Insurance and loss events
- Environmental and site observations
- Future extensible event domains

This list is illustrative, not exhaustive. It represents current recognized domains, not a closed taxonomy. The architecture does not depend on the completeness of this list.

### 4. The Architecture Is Extensible

The Institutional Record must be capable of incorporating new event domains without redefining what it is. No architectural decision made today should require the Registry to be rebuilt because a new category of property event becomes relevant in ten, twenty, or fifty years.

Extensibility is achieved not by anticipating every future domain, but by designing around principles rather than categories. Domain-agnosticism, canonical identity, and accumulated history are all durable because they operate at the level of what the record is, not what it currently contains.

---

## Implementation Consequence

Because the Institutional Record represents a lifecycle rather than a moment in time, it cannot be modeled as a collection of static property states or disconnected documents.

The lifecycle is therefore represented as an append-only sequence of property events, anchored to the Registry ID. Each event carries its own timestamp, provenance, verification status, and Registry Confidence. These attributes belong to the event itself and may be updated over time — a previously unverified event may be subsequently verified — without altering the historical event record.

The implementation of this model is the subject of the documents that follow.

---

## Explicit Deferrals

This document establishes what the Institutional Record is and the principles that govern it. The following documents address implementation:

- **Doc 10 — Event Data Model:** How the Institutional Record is built from discrete, timestamped events. The structure, schema, and lifecycle of a property event.
- **Doc 11 — Verification Model:** How source tiers (S1–S6) and verification levels (VL-1 through VL-6) from the Trust Framework translate into the data layer. How Registry Confidence is calculated.
- **Doc 12 — Property Registry Specification:** The formal specification of the Property Registry — the permanent, Registry ID-anchored record for a single property.
- **Doc 13 — Registry ID:** The permanent property identifier. How it is assigned, what it anchors, and how it survives ownership transitions.

---

## Decisions Established

The following architectural decisions are established by this document and logged in DECISIONS.md:

**D-014:** The Institutional Record is defined as the persistent institutional representation of a property's lifecycle. This definition is the organizing principle of the data architecture and governs all downstream data decisions.

**D-015:** Four architectural principles govern the Institutional Record: canonical identity, accumulated history, domain-agnosticism, and extensibility. These are constraints, not guidelines.

**D-016:** The governing test for event inclusion is: Does this event materially inform the understanding, condition, provenance, risk, or stewardship of the property? This test is implementation-independent and domain-independent.

**D-017:** Event domains are classifications within one Institutional Record, not separate records. The list of recognized domains is illustrative and explicitly non-exhaustive.

---

## Constitutional Traceability

| Principle | Source |
|-----------|--------|
| Persistent institutional record | Doc 00 — Founder's Insight; Doc 02 — Missing Memory Layer |
| Property as primary entity | Doc 03 — Haus Registry Doctrine (Belief 1) |
| Records accumulate, do not reset | Doc 03 — Haus Registry Doctrine (Belief 2) |
| We assemble, not create | Doc 03 — Haus Registry Doctrine (Belief 3) |
| Verification increases value | Doc 03 — Haus Registry Doctrine (Belief 5) |
| Source hierarchy and verification levels | Doc 04 — Trust Framework |
| Build for decades | Doc 03 — Haus Registry Doctrine (Belief 8) |
| Infrastructure, not product | Doc 03 — Haus Registry Doctrine (Belief 9) |

---

## Related Documents

- **Doc 04 — Trust Framework:** Establishes the source hierarchy (S1–S6) and verification levels (VL-1 through VL-6) that the data architecture implements.
- **Doc 10 — Event Data Model:** Direct downstream implementation of the event-based architecture established here.
- **Doc 11 — Verification Model:** Direct downstream implementation of the verification and confidence principles established here.
- **Doc 12 — Property Registry Specification:** The formal specification of the record this document defines.
- **Doc 13 — Registry ID:** The canonical identity mechanism this document requires.

---

## Downstream Dependencies

Documents that depend on the principles established here:

- Doc 10 — Event Data Model
- Doc 11 — Verification Model
- Doc 12 — Property Registry Specification
- Doc 13 — Registry ID
- All product and technical documents that interact with property data
EOF