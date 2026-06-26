# Document 13: Registry ID
**Haus Registry | Foundation Documentation**
*Phase: Data Architecture | Status: Complete*

---

## Scope

Document 09 established that the Institutional Record has one canonical identity. This document specifies that identity.

The Registry ID is the permanent canonical identifier assigned to every property that enters The Registry. It is the foundational key of the entire data architecture — the anchor to which the Institutional Record, all property events, all verification levels, and all associated identifiers are attached.

This document defines what the Registry ID is, the properties it must possess, the principle of opacity that governs its design, its relationship to existing property identifiers, and the rule governing its assignment. Implementation mechanics — how Registry IDs are generated, stored, and resolved — are deferred to the Property Registry Specification (Doc 12).

---

## The Architectural Necessity

Existing property identifier systems serve their respective domains well. Each is authoritative within its intended scope:

- **Addresses** identify locations for navigation, delivery, and correspondence.
- **Assessor's Parcel Numbers (APNs)** identify parcels within a taxing jurisdiction.
- **MLS numbers** identify listings within a transaction.
- **FIPS codes** identify geographic regions within a federal statistical framework.
- **Deed references** identify legal instruments within a recording system.

None of these identifiers was designed to serve as the permanent canonical identity of a persistent Institutional Record. They were created to solve different problems, and they solve those problems well. The Registry ID does not replace them.

What none of them provides — and what the Institutional Record requires — is a permanent, platform-independent, ownership-independent identifier whose sole purpose is to say: *this is which property this is*, across every ownership transition, every jurisdictional change, every platform, and every decade.

The Registry ID exists to fill that role.

---

## The Principle of Non-Replacement

The Registry ID does not replace existing property identifiers. It provides a permanent canonical identity to which all existing identifiers may be associated over time.

An APN, an address, an MLS number, a deed reference — each may be recorded as an attribute of the Institutional Record, associated with the property's Registry ID. As those external identifiers change — addresses are reassigned, APNs are modified during subdivision, listings expire — the Registry ID remains. The associations are updated. The identity is not.

The Registry ID is the anchor. Existing identifiers are associations.

---

## Required Properties

The Registry ID must possess the following properties. These are not design preferences. They are architectural requirements that follow directly from the purpose the Registry ID must serve.

**Permanent.** Once assigned, a Registry ID is never reassigned, recycled, or retired. It persists for the life of the property and beyond — as a historical reference even if the physical property no longer exists.

**Globally unique.** No two properties may share a Registry ID. Uniqueness is guaranteed at the system level, not dependent on jurisdiction, geography, or any external authority.

**Platform-independent.** The Registry ID belongs to the property, not to any platform, database, or technology implementation. It must remain valid and resolvable regardless of how the underlying system evolves.

**Property-centric.** The Registry ID identifies the property as a physical and legal entity. It does not identify an owner, a transaction, a listing, or a jurisdiction. The property is the primary entity.

**Ownership-independent.** The Registry ID does not change when ownership transfers. It is assigned once and survives every stewardship transition for the life of the property.

**Immutable.** The Registry ID cannot be modified after assignment. It is not a field that can be updated, corrected, or replaced. If a Registry ID is ever found to have been assigned in error, the resolution is recorded as an event in the Institutional Record — the identifier itself is not altered.

**Canonical.** The Registry ID is the authoritative identity of the property within The Registry. All other identifiers — addresses, APNs, MLS numbers, deed references — are associations, not identities.

**Extensible.** The Registry ID must remain valid as the property's Institutional Record grows, as new event domains are added, and as the platform evolves. The identifier must not constrain future architectural decisions.

---

## The Opacity Principle

The Registry ID is opaque.

It does not encode, embed, or imply any descriptive attribute of the property it identifies. It does not encode:

- Address or street name
- City, county, state, or jurisdiction
- Property type or classification
- Creation date or year of registration
- Ownership or stewardship information
- Geographic coordinates or region
- Any characteristic of the property's current or historical condition

Its only responsibility is identity.

All descriptive information about the property belongs in the Institutional Record. The Registry ID points to that record. It does not summarize it.

This principle is borrowed from well-designed identity systems across many domains. Identifiers that encode descriptive attributes become unreliable the moment those attributes change. A Registry ID that embeds a county code is a Registry ID that eventually misrepresents a property that has been redistricted. A Registry ID that encodes a property type is a Registry ID that lies about a property that has been converted. Opacity is not a technical choice. It is an architectural commitment to long-term stability.

---

## The Four Layers

The Registry ID is one of four distinct layers in the data architecture, each answering a different question:

```
Registry ID            →  Which property is this?
Institutional Record   →  What do we know about this property?
Verification           →  How reliable is what we know?
Registry Confidence    →  How much confidence should participants place in that knowledge?
```

These layers are independent. No layer depends on the state of another to fulfill its function. A property with a Registry ID may have an Institutional Record of any size, any verification level, and any Registry Confidence Score. A property with very little known about it is still a property. It still has an identity. That identity does not depend on what the record contains.

---

## Assignment

A Registry ID is assigned to every property when it first enters The Registry.

The assignment of a Registry ID establishes a property's permanent canonical identity within Haus Registry. It does not imply completeness, verification, ownership validation, or a particular Registry Confidence. Those characteristics belong to the Institutional Record and evolve over time. Identity does not.

Assignment is unconditional. There is no evidence threshold, no minimum data requirement, and no verification prerequisite. The moment a property enters The Registry, it receives a Registry ID. The record that accumulates beneath that identity may begin with a single event or with thousands. The identity itself is established at the moment of entry and never revisited.

---

## What the Registry ID Anchors

The Registry ID is the key to which all other data in the architecture is attached:

- The Institutional Record — the full accumulation of property events
- All event records — each timestamped, sourced, and verified independently
- All verification levels and Registry Confidence calculations
- All associated external identifiers — addresses, APNs, MLS numbers, deed references
- All ownership and stewardship transitions
- All Registry Reports generated for the property
- All Registry Verified designations applied to specific events or claims

Nothing in the data architecture exists independently of the Registry ID. It is the root node of everything the Registry knows about a property.

---

## Decisions Established

The following architectural decisions are established by this document and logged in DECISIONS.md:

**D-018:** The Registry ID is the permanent canonical identifier assigned to every property that enters The Registry. It is the foundational key of the entire data architecture.

**D-019:** The Registry ID is opaque. It encodes no descriptive attributes. Its only responsibility is identity.

**D-020:** A Registry ID is assigned to every property at the moment it first enters The Registry. Assignment is unconditional and requires no evidence threshold, verification, or minimum data.

**D-021:** The Registry ID does not replace existing property identifiers. It provides the permanent canonical anchor to which all existing identifiers are associated.

**D-022:** The four architectural layers — Registry ID, Institutional Record, Verification, and Registry Confidence — are independent. No layer depends on the state of another to fulfill its function.

---

## Constitutional Traceability

| Principle | Source |
|-----------|--------|
| Property as primary entity | Doc 03 — Haus Registry Doctrine (Belief 1) |
| Records accumulate, do not reset | Doc 03 — Haus Registry Doctrine (Belief 2) |
| The Institutional Record has one canonical identity | Doc 09 — Data Architecture (Principle 1) |
| History is accumulated, never rewritten | Doc 09 — Data Architecture (Principle 2) |
| Build for decades | Doc 03 — Haus Registry Doctrine (Belief 8) |
| Infrastructure, not product | Doc 03 — Haus Registry Doctrine (Belief 9) |
| Every decision is a precedent | Doc 03 — Haus Registry Doctrine (Belief 10) |

---

## Related Documents

- **Doc 09 — Data Architecture:** Establishes the principle that the Institutional Record has one canonical identity. This document fulfills that commitment.
- **Doc 10 — Event Data Model:** All events are anchored to a Registry ID.
- **Doc 11 — Verification Model:** All verification levels are calculated against the Institutional Record anchored to a Registry ID.
- **Doc 12 — Property Registry Specification:** Specifies the implementation of the Registry ID — generation, storage, and resolution mechanics.

---

## Downstream Dependencies

Documents and systems that depend on the Registry ID specification:

- Doc 10 — Event Data Model
- Doc 11 — Verification Model
- Doc 12 — Property Registry Specification
- Registry API — all endpoints reference Registry ID as the primary key
- Registry Report — generated per Registry ID
- My Registry — homeowner view anchored to Registry ID
- Registry Pro — professional access organized by Registry ID
- All data ingestion, deduplication, and conflict resolution systems
