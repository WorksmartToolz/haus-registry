# Document 10: Event Data Model
**Haus Registry | Foundation Documentation**
*Phase: Data Architecture | Status: Complete*

---

## Scope

Document 09 established that the Institutional Record is represented as an append-only sequence of property events. This document defines that sequence — the structure, classification, and governing rules of the Registry Event, which is the atomic unit of the Institutional Record.

This document defines what a Registry Event is, how events are classified, what fields every Registry Event must carry, and how events relate to one another. It does not define verification levels or confidence scoring (Doc 11), schema enumerations and validation rules (Doc 12), or the Registry ID specification (Doc 13).

---

## The Registry Event

The atomic unit of the Institutional Record is the **Registry Event**.

A Registry Event is a recorded assertion about a property, anchored to the property's Registry ID, supported by provenance, and preserved append-only.

This definition is precise and intentional. The Registry does not store facts as static truth. It stores sourced assertions that can be verified, challenged, supplemented, connected, and strengthened over time. An assertion becomes more or less reliable based on the verification it accumulates — but the event record itself is never altered. What was recorded is always preserved exactly as it was recorded.

A Registry Event may represent:

- Something that happened — a repair, installation, inspection, or ownership transfer
- Something that was observed — a condition, defect, material, or site characteristic
- Something that was issued — a permit, warranty, report, certificate, or disclosure
- Something that changed status — a warranty expiration, permit closure, claim resolution, or recall
- Something that was corrected, challenged, clarified, or superseded

Every one of these is a legitimate contribution to the Institutional Record. The event model accommodates all of them through a defined classification system.

---

## Event Classification

Every Registry Event belongs to one of five event classes. The class determines the event's structural role within the Institutional Record and governs how it relates to other events.

### Occurrence Event

An Occurrence Event records a discrete action, change, or condition that took place at or to the property. The defining characteristic is that something happened.

Examples: roof replacement, HVAC installation, foundation repair, pest treatment, interior renovation, fire damage, flood event, ownership transfer, utility connection.

Occurrence Events are the most common class. They carry the strongest expectation of a known event date.

### Observation Event

An Observation Event records a condition, characteristic, or finding that was observed about the property — without necessarily corresponding to a discrete dated occurrence. The defining characteristic is that something was noted.

Examples: estimated equipment age, visible water staining, cracked masonry, apparent material type, site condition noted during walkthrough, undocumented prior modification.

Observation Events are particularly important for properties entering the Registry with incomplete histories. They capture institutional knowledge that would otherwise be lost, even when that knowledge cannot be precisely dated or sourced.

### Document Event

A Document Event records the existence, issuance, receipt, or attachment of a document associated with the property. The defining characteristic is that a record was created or received.

Examples: permit issued, inspection report uploaded, warranty certificate attached, invoice submitted, photo set recorded, disclosure statement filed, title report received.

Document Events link the Institutional Record to supporting evidence. They are distinct from Occurrence Events because the significance of a Document Event is the document itself — not only the underlying activity it describes.

### Status Event

A Status Event records a change in the state of an existing record, condition, or relationship. The defining characteristic is that something transitioned from one state to another.

Examples: warranty expired, permit closed, insurance claim approved, recall issued, lien released, ownership stewardship transferred, Registry Verified designation applied or removed.

Status Events are system-generated as well as contributor-submitted. They maintain the currency of the Institutional Record without altering the events that preceded them.

### Correction Event

A Correction Event records an amendment, challenge, clarification, or supersession of a prior Registry Event. The defining characteristic is that a prior assertion is being addressed.

Examples: date correction, source attribution update, duplicate identification, conflicting claim, disputed finding, superseding document, verified override of an earlier observation.

Correction Events are the implementation of the architectural principle established in Doc 09: history is accumulated, never rewritten. A correction does not alter the prior event. It creates a new event that references the prior event and records the nature of the correction. The original assertion is preserved. The correction is appended. Both remain part of the Institutional Record.

A Correction Event must carry a reference to the event or events it addresses. The relationship type — amendment, challenge, clarification, supersession — is a required field.

---

## Required Fields

Every Registry Event, regardless of class, carries the following fields. These fields are not optional. An event without complete provenance and classification cannot be admitted to the Institutional Record.

**Registry ID**
The permanent canonical identifier of the property to which this event belongs. Inherited from Doc 13. Every event is anchored to exactly one Registry ID.

**Event ID**
A globally unique identifier assigned to this event at the time of recording. Immutable after assignment. The Event ID is the permanent reference for this event within the Institutional Record and across all systems that interact with it.

**Event Class**
One of the five defined classes: Occurrence, Observation, Document, Status, Correction. Required. Governs structural role and relationship rules.

**Event Domain**
The domain within which this event falls, drawn from the recognized domain list established in Doc 09: construction and commissioning, maintenance and repairs, improvements and renovations, inspections and assessments, ownership and stewardship transitions, regulatory and permitting activity, warranty and manufacturer events, insurance and loss events, environmental and site observations, or future extensible domains. The domain list is non-exhaustive; new domains may be added without altering the event model.

**Event Date**
The date on which the event occurred or was observed. For events where the exact date is unknown, a date confidence qualifier is required in place of or alongside the event date. The vocabulary of date confidence levels is defined in Doc 12.

**Recorded Date**
The date and timestamp on which this event was recorded in the Registry. System-assigned at the moment of ingestion. Immutable. The gap between Event Date and Recorded Date is meaningful provenance information — a repair recorded twenty years after it occurred carries different weight than one recorded the same week.

**Source**
The source tier of this event, drawn from the S1–S6 source hierarchy established in Doc 04. Source tier is assigned based on the origin of the assertion, not the quality of the content.

**Contributor**
The participant who submitted this event to the Registry. May be a homeowner, licensed professional, institution, system integration, or Registry staff. Contributor identity is distinct from source tier — a homeowner (contributor) may submit a document that originated from a licensed inspector (source).

**Provenance**
A structured record of how this event came to be in the Registry: who submitted it, through what channel, on what date, and with what supporting evidence. Provenance is immutable after recording.

**Supporting Documents**
References to any documents, images, reports, or files associated with this event. May be empty at the time of recording and supplemented by subsequent Document Events.

**Verification Status**
The current verification level of this event, drawn from the VL-1 through VL-6 verification levels established in Doc 04. Verification status may be updated over time as additional verification is obtained. Updates to verification status are themselves recorded as Status Events — the original event record is not modified.

**Registry Confidence**
The confidence score associated with this event at the time of last verification update. Calculated per the Coverage, Verification Depth, and Recency model established in Doc 04. The confidence score is a derived value, not an editable field.

**Event Relationships**
References to other Registry Events with which this event has a defined relationship. Relationship types include: supersedes, supplements, challenges, clarifies, corrects, duplicates, and supports. Required for Correction Events. Optional for all other classes.

**Status**
The current status of this event within the Institutional Record: active, superseded, merged, or under challenge. Default is active at the time of recording. Status transitions are recorded as Status Events.

---

## Governing Rules

**Append-only.** Events are added to the Institutional Record. They are never deleted, overwritten, or modified after recording. This rule has no exceptions.

**Immutable provenance.** The provenance fields of a Registry Event — source, contributor, recorded date, and submission channel — are set at the time of recording and cannot be changed. If provenance information is found to be incorrect, a Correction Event is created.

**Verification is external to the event.** The verification status and Registry Confidence of an event may change as verification is obtained. These changes are applied through Status Events and do not alter the original event record.

**Every event is anchored.** A Registry Event without a valid Registry ID cannot exist in the Institutional Record. The Registry ID is a required field with no default and no null state.

**Corrections reference, not replace.** A Correction Event must carry a reference to the event it addresses. It does not replace that event. Both the original and the correction are active members of the Institutional Record, related through their event relationship fields.

**Date uncertainty is recorded, not suppressed.** When an event date is unknown or approximate, the event is still admitted to the Institutional Record. The date confidence qualifier records the level of certainty. Suppressing events because their dates are uncertain would degrade the Institutional Record — the Registry preserves what is known, including the limits of what is known.

---

## The Accumulation Model

The Institutional Record for any property is the complete, ordered set of all Registry Events anchored to that property's Registry ID.

Events accumulate over time. They do not replace one another. An Occurrence Event recording a roof replacement in 2019 does not remove or diminish the value of an Observation Event recording the prior roof's condition in 2015. Both are part of the lifecycle. Both inform the understanding of the property.

The depth and richness of the Institutional Record is a direct function of how many events have been recorded, how well those events are sourced, and how thoroughly they have been verified. This is what the Registry Confidence Score measures — not the quality of any single event, but the cumulative institutional weight of all events together.

---

## Decisions Established

The following architectural decisions are established by this document and logged in DECISIONS.md:

**D-023:** The atomic unit of the Institutional Record is the Registry Event — a recorded assertion about a property, anchored to the Registry ID, supported by provenance, and preserved append-only.

**D-024:** Registry Events are classified into five classes: Occurrence, Observation, Document, Status, and Correction. Class is a required field and governs structural role and relationship rules.

**D-025:** Correction Events reference prior events and are appended to the record. They do not alter, remove, or replace the events they address.

**D-026:** Date uncertainty is recorded through a date confidence qualifier, not suppressed. Events with uncertain dates are admitted to the Institutional Record. The vocabulary of date confidence levels is deferred to Doc 12.

**D-027:** Verification status and Registry Confidence are external to the event record. Changes to these values are applied through Status Events and do not modify the original event.

---

## Constitutional Traceability

| Principle | Source |
|-----------|--------|
| Records accumulate, do not reset | Doc 03 — Haus Registry Doctrine (Belief 2) |
| We assemble, not create | Doc 03 — Haus Registry Doctrine (Belief 3) |
| Source visibility | Doc 03 — Haus Registry Doctrine (Belief 4) |
| Verification increases value | Doc 03 — Haus Registry Doctrine (Belief 5) |
| History is accumulated, never rewritten | Doc 09 — Data Architecture (Principle 2) |
| The Institutional Record is domain-agnostic | Doc 09 — Data Architecture (Principle 3) |
| S1–S6 source hierarchy | Doc 04 — Trust Framework |
| VL-1 through VL-6 verification levels | Doc 04 — Trust Framework |
| Registry Confidence Score model | Doc 04 — Trust Framework |

---

## Related Documents

- **Doc 04 — Trust Framework:** Establishes the source hierarchy, verification levels, and Registry Confidence model that govern event fields.
- **Doc 09 — Data Architecture:** Establishes the append-only lifecycle model and the four architectural principles this document implements.
- **Doc 11 — Verification Model:** Defines how Registry Events gain verification status and how that status affects Registry Confidence.
- **Doc 12 — Property Registry Specification:** Defines schema enumerations, date confidence vocabulary, validation rules, and domain registry.
- **Doc 13 — Registry ID:** Defines the canonical identifier that anchors every Registry Event.

---

## Downstream Dependencies

- Doc 11 — Verification Model
- Doc 12 — Property Registry Specification
- Registry API — event ingestion, retrieval, and relationship endpoints
- Registry Report — event timeline and domain summaries
- My Registry — homeowner event contribution and history view
- Registry Pro — professional event submission and verification workflows
- Registry AI — event pattern recognition and gap identification
- All data ingestion and deduplication systems
