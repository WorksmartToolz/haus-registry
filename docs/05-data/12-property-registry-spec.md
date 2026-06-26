# Document 12: Property Registry Specification
**Haus Registry | Foundation Documentation**
*Phase: Data Architecture | Status: Complete*

---

## Scope

This document is the formal specification of the Property Registry — the permanent, Registry ID-anchored record for a single property. It defines what the Property Registry contains, how it is structured, what fields are required versus optional, the enumerated vocabularies that govern event classification and date confidence, the domain registry, the confidence weighting formula, and how the Property Registry evolves across ownership transitions.

This document draws on and implements decisions established in Docs 04, 09, 10, 11, and 13. It does not reopen those decisions. Where prior documents established principles, this document specifies their implementation.

---

## The Property Registry

The Property Registry is the complete, Registry ID-anchored record for a single property within The Registry. It is the persistent container that holds everything the Institutional Record knows about a property: its identity, its event history, its verification state, its confidence score, and its associated identifiers.

Every property that enters The Registry has exactly one Property Registry. The Property Registry is created at the moment the Registry ID is assigned and persists indefinitely. It does not reset at ownership transition. It does not expire. It accumulates.

The Property Registry has two layers:

**The Identity Layer** — fixed fields that establish and anchor the property's canonical identity. These fields are set at creation and do not change.

**The Record Layer** — the accumulating body of Registry Events, verification states, confidence scores, and associated identifiers that constitute the Institutional Record.

---

## Identity Layer

The Identity Layer contains the fields that permanently define and anchor the Property Registry. These fields are immutable after creation.

**Registry ID**
The permanent canonical identifier of this property. Assigned at the moment the Property Registry is created. Globally unique, opaque, and immutable. Specified in Doc 13.

**Registry Created Date**
The date and timestamp at which this Property Registry was created and the Registry ID was assigned. System-assigned. Immutable.

**Registry Created By**
The participant or system responsible for initiating the creation of this Property Registry. Recorded for provenance. Immutable.

**Property Type**
The classification of the property at the time of registration. Drawn from the Property Type enumeration defined in this document. May be updated through a Status Event if the property's classification changes (e.g., conversion from residential to mixed-use). The original value is preserved in the event record.

**Geographic Anchor**
The spatial reference that locates this property in the physical world. Recorded as a coordinate pair (latitude/longitude) at the time of registration. The geographic anchor is the Registry's internal spatial reference and is distinct from the property's address, which may change. Immutable after creation.

---

## Record Layer

The Record Layer is the living body of the Property Registry. It accumulates over time as Registry Events are added, verification levels are updated, and confidence scores are recalculated.

### Event Log

The complete, append-only sequence of all Registry Events anchored to this Registry ID. Events are ordered by recorded date. The event log is never edited, truncated, or reordered. New events are appended. The event log is the Institutional Record.

### Active Event Index

A derived index of all Registry Events with a current status of active, organized by event domain and event class. The active event index provides efficient access to the current state of the Institutional Record without requiring traversal of the full event log. The active event index is a view, not a separate record — it is always derivable from the event log.

### Associated Identifiers

The set of external identifiers associated with this property, each recorded with its type, value, issuing authority, and the date on which the association was recorded. Associated identifiers are not part of the Identity Layer — they may change over time and are recorded as Document or Status Events when they are added, updated, or retired.

Standard identifier types include:

- Street address (current and historical)
- Assessor's Parcel Number (APN)
- FIPS code
- MLS number (transaction-scoped; may have multiple)
- Deed reference
- Permit reference numbers
- Tax parcel identifier

Additional identifier types may be added without altering the Property Registry structure.

### Ownership and Stewardship Record

The sequence of ownership and stewardship transitions recorded for this property, derived from the event log. Each transition is an Occurrence Event in the Ownership and Stewardship Transitions domain. The stewardship record is a view over the event log, not a separate data structure.

### Registry Confidence Score

The current property-level Registry Confidence Score, composed of the Coverage Score, Verification Depth Score, and Recency Score as specified in this document. Recalculated automatically on every triggering event. Presented as a composite value with component breakdown available.

### Registry Verified Status

The current Registry Verified designation for this property, if applicable. Registry Verified is awarded when the Institutional Record meets the threshold criteria established in Doc 04. The designation is a Status Event in the record — it is awarded, maintained, and revoked through the event model.

---

## Enumerated Vocabularies

### Property Type Enumeration

| Code | Description |
|------|-------------|
| SFR | Single-family residential |
| MFR-2 | Two-unit residential (duplex) |
| MFR-3-4 | Three- to four-unit residential |
| MFR-5+ | Five or more units residential |
| CONDO | Condominium unit |
| COOP | Cooperative unit |
| MOBILE | Mobile or manufactured home |
| MIXED | Mixed-use residential/commercial |
| LAND | Vacant land |
| OTHER | Other; description required |

### Event Class Enumeration

Established in Doc 10. Reproduced here for specification reference.

| Code | Class |
|------|-------|
| OCC | Occurrence Event |
| OBS | Observation Event |
| DOC | Document Event |
| STA | Status Event |
| COR | Correction Event |

### Event Domain Enumeration

Established in Doc 09. Reproduced here with domain codes for schema implementation.

| Code | Domain |
|------|--------|
| CON | Construction and commissioning |
| MNT | Maintenance and repairs |
| IMP | Improvements and renovations |
| INS | Inspections and assessments |
| OWN | Ownership and stewardship transitions |
| REG | Regulatory and permitting activity |
| WRN | Warranty and manufacturer events |
| INR | Insurance and loss events |
| ENV | Environmental and site observations |
| EXT | Future extensible event domains |

### Source Tier Enumeration

Established in Doc 04 and Doc 11. Reproduced here for schema reference.

| Code | Tier | Description |
|------|------|-------------|
| S1 | Government and regulatory | Permits, tax records, deeds, zoning, code enforcement |
| S2 | Licensed professional | Inspection reports, appraisals, engineering assessments |
| S3 | Institutional | Insurance filings, warranty registrations, manufacturer records |
| S4 | Verified participant | Identity-verified submissions with supporting documentation |
| S5 | Participant | Homeowner submissions, unverified contractor records |
| S6 | Unverified | Unverified third-party submissions, inferred data |

### Verification Level Enumeration

Established in Doc 04 and Doc 11. Reproduced here for schema reference.

| Code | Level | Description |
|------|-------|-------------|
| VL-1 | Unverified | Recorded as submitted, no validation performed |
| VL-2 | Format validated | Passes structural checks, internally consistent |
| VL-3 | Source corroborated | Supported by at least one independent source |
| VL-4 | Professionally reviewed | Confirmed by a licensed professional |
| VL-5 | Institutionally validated | Supported by institutional record or formal Registry process |
| VL-6 | Fully verified | Primary institutional records, independently confirmed |

### Event Status Enumeration

| Code | Status | Description |
|------|--------|-------------|
| ACT | Active | Current, uncontested event in the Institutional Record |
| SUP | Superseded | Addressed by a subsequent Correction or Status Event |
| MRG | Merged | Identified as a duplicate and merged with a canonical event |
| CHL | Under challenge | Subject to an open Correction Event challenge |

### Correction Relationship Type Enumeration

| Code | Type | Description |
|------|------|-------------|
| AMD | Amendment | Supplementary information added to a prior event |
| CHL | Challenge | Prior event's accuracy is disputed |
| CLR | Clarification | Prior event's meaning or scope is clarified |
| SUP | Supersession | Prior event is replaced by a more authoritative assertion |
| DUP | Duplicate | Prior event is identified as a duplicate of another event |

### Date Confidence Enumeration

Established as a requirement in Doc 10 (D-026). Specified here.

| Code | Level | Description |
|------|-------|-------------|
| DC-1 | Exact | Full date known to day precision |
| DC-2 | Month/Year | Known to month and year, day uncertain |
| DC-3 | Year only | Known to year, month and day uncertain |
| DC-4 | Approximate range | Known within a span of years (e.g., 2010–2015) |
| DC-5 | Decade | Known to decade only |
| DC-6 | Unknown | No date information available |

When date confidence is DC-2 through DC-6, the event date field records the earliest plausible date in the known range, and the date confidence field specifies the precision level. This approach preserves sortability while accurately representing uncertainty.

---

## Domain Registry

The domain registry is the authoritative list of recognized event domains within The Registry. It is maintained as part of the Property Registry Specification and is extensible without requiring changes to the event model or any other document.

Each domain entry specifies:

- Domain code
- Domain name
- Description
- Default recency decay period (the interval after which events in this domain begin to lose recency weight in the confidence calculation)
- Domain weight in the property-level Coverage Score

### Domain Registry — Initial Entries

| Code | Domain | Recency Decay | Coverage Weight |
|------|--------|---------------|-----------------|
| CON | Construction and commissioning | None | High |
| MNT | Maintenance and repairs | 5 years | Medium |
| IMP | Improvements and renovations | None | Medium |
| INS | Inspections and assessments | 3 years | High |
| OWN | Ownership and stewardship transitions | None | High |
| REG | Regulatory and permitting activity | None | High |
| WRN | Warranty and manufacturer events | Per warranty term | Medium |
| INR | Insurance and loss events | None | Medium |
| ENV | Environmental and site observations | 7 years | Medium |
| EXT | Future extensible domains | TBD at domain creation | TBD |

Recency decay periods represent the interval after which events in a domain begin to lose recency weight. "None" indicates that events in this domain do not decay — historical events retain their full recency weight because they represent permanent facts about the property's history. Construction records from 1952 are as permanently relevant as construction records from last year.

---

## Registry Confidence Score — Calculation Specification

The Registry Confidence Score is a composite of three component scores, each calculated independently and combined into a single property-level score.

### Coverage Score

The Coverage Score measures the proportion of high-weight domains for which at least one verified event (VL-3 or above) exists in the Institutional Record.

```
Coverage Score = (Sum of coverage weights for domains with at least one VL-3+ event)
                 / (Sum of all high and medium weight domain coverage weights)
```

A property with verified events in all high-weight domains and most medium-weight domains approaches a Coverage Score of 1.0. A property with verified events in only one or two domains scores proportionally lower.

### Verification Depth Score

The Verification Depth Score measures the weighted average verification level across all active events, adjusted by source tier.

```
For each active event:
  Adjusted VL = Verification Level × Source Tier Multiplier

Source Tier Multipliers:
  S1: 1.00
  S2: 0.90
  S3: 0.85
  S4: 0.75
  S5: 0.60
  S6: 0.40

Verification Depth Score = (Sum of Adjusted VL for all active events)
                           / (VL-6 × 1.00 × Total active events)
```

This produces a score between 0 and 1, where 1.0 represents a record in which every active event is fully verified from a government or regulatory source.

### Recency Score

The Recency Score measures the degree to which the Institutional Record reflects the property's current condition, accounting for domain-specific decay.

```
For each active event in a domain with recency decay:
  Event Recency Weight = max(0, 1 - (Years since event / Decay period))

Recency Score = (Sum of Event Recency Weights across all decay-eligible domains)
                / (Total active events in decay-eligible domains)
```

Events in domains with no recency decay (CON, IMP, OWN, REG, INR) are excluded from the recency calculation — they contribute to coverage and verification depth but do not affect recency.

### Composite Score

```
Registry Confidence Score = (Coverage Score × 0.35)
                           + (Verification Depth Score × 0.40)
                           + (Recency Score × 0.25)
```

The composite score is presented on a scale of 0 to 100 (multiply by 100 for display). Component scores are available for inspection in Registry Pro and Registry Report.

These weights represent the initial specification. They may be recalibrated through a formal architectural revision process as empirical data on score distribution becomes available. Any recalibration is logged as a Decision.

---

## Ownership Transition Behavior

When a property changes ownership, the Property Registry does not reset. The following occurs:

1. An Occurrence Event in the OWN domain is recorded, documenting the transition: prior owner, new owner, transfer date, transfer type, and supporting documentation (deed reference, transfer instrument).
2. A Status Event updates the stewardship record to reflect the new owner.
3. All prior events remain active and unchanged in the Institutional Record.
4. The Registry Confidence Score is recalculated to reflect the updated event log — it does not reset.
5. The new owner gains access to the full Institutional Record through My Registry upon verified identity confirmation.

The incoming owner receives the Institutional Record as accumulated. They inherit what is known, including events they did not contribute. This is the foundational value proposition of the Registry: knowledge that survives the transaction.

---

## Required vs. Optional Fields — Summary

### Identity Layer Fields

| Field | Required | Mutable |
|-------|----------|---------|
| Registry ID | Required | No |
| Registry Created Date | Required | No |
| Registry Created By | Required | No |
| Property Type | Required | Via Status Event |
| Geographic Anchor | Required | No |

### Registry Event Fields (all event classes)

| Field | Required | Mutable |
|-------|----------|---------|
| Registry ID | Required | No |
| Event ID | Required | No |
| Event Class | Required | No |
| Event Domain | Required | No |
| Event Date | Required if known | No |
| Date Confidence | Required | No |
| Recorded Date | Required | No |
| Source Tier | Required | No |
| Contributor | Required | No |
| Provenance | Required | No |
| Supporting Documents | Optional | Via append |
| Verification Status | Required | Via Status Event |
| Registry Confidence | Required | Derived |
| Event Relationships | Required for COR | Via append |
| Event Status | Required | Via Status Event |

---

## Decisions Established

The following architectural decisions are established by this document and logged in DECISIONS.md:

**D-033:** The Property Registry has two layers: the Identity Layer (immutable, set at creation) and the Record Layer (accumulating, event-driven).

**D-034:** The date confidence enumeration defines six levels (DC-1 through DC-6). Events with uncertain dates record the earliest plausible date and the applicable confidence level. Sortability is preserved.

**D-035:** The domain registry specifies recency decay periods and coverage weights for each event domain. Domains with no recency decay retain permanent recency weight. The domain registry is extensible.

**D-036:** The Registry Confidence Score composite weighting is Coverage (35%), Verification Depth (40%), Recency (25%). Weights may be recalibrated through formal architectural revision with Decision logging.

**D-037:** At ownership transition, the Property Registry does not reset. The transition is recorded as an Occurrence Event in the OWN domain. All prior events remain active.

---

## Constitutional Traceability

| Principle | Source |
|-----------|--------|
| Property as primary entity | Doc 03 — Haus Registry Doctrine (Belief 1) |
| Records accumulate, do not reset | Doc 03 — Haus Registry Doctrine (Belief 2) |
| Confidence reduces uncertainty | Doc 03 — Haus Registry Doctrine (Belief 6) |
| Build for decades | Doc 03 — Haus Registry Doctrine (Belief 8) |
| S1–S6 source hierarchy | Doc 04 — Trust Framework |
| VL-1 through VL-6 verification levels | Doc 04 — Trust Framework |
| Registry Confidence Score model | Doc 04 — Trust Framework |
| The Institutional Record has one canonical identity | Doc 09 — Data Architecture (Principle 1) |
| History is accumulated, never rewritten | Doc 09 — Data Architecture (Principle 2) |
| Registry Event as atomic unit | Doc 10 — Event Data Model (D-023) |
| Date confidence as required field | Doc 10 — Event Data Model (D-026) |
| Confidence weighting formula | Doc 11 — Verification Model (D-030, D-031) |
| Registry ID specification | Doc 13 — Registry ID |

---

## Related Documents

- **Doc 04 — Trust Framework:** Source hierarchy, verification levels, and confidence score model.
- **Doc 09 — Data Architecture:** Architectural principles and event domain list.
- **Doc 10 — Event Data Model:** Registry Event definition, classification, and required fields.
- **Doc 11 — Verification Model:** Source tier assignment, verification level assignment, and confidence score components.
- **Doc 13 — Registry ID:** Registry ID specification and assignment rule.

---

## Downstream Dependencies

- Registry API — schema validation, event ingestion contracts, identifier association endpoints
- Registry Report — confidence score presentation, event timeline, domain coverage summary
- Registry Pro — full record access, verification workflows, confidence component breakdown
- My Registry — homeowner record view, event contribution, stewardship transition
- Registry Verified — designation threshold evaluation
- Registry AI — schema-aware gap identification, event classification assistance
- Database Design (Doc 16) — physical schema derived from this specification
- System Architecture (Doc 15) — confidence recalculation triggers and event ingestion pipeline
