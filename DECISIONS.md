
## D-014
**Decision:** The Institutional Record is defined as the persistent institutional representation of a property's lifecycle.
**Rationale:** This definition is the organizing principle of the data architecture. All downstream data decisions trace to it.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-015
**Decision:** Four architectural principles govern the Institutional Record: canonical identity, accumulated history, domain-agnosticism, and extensibility.
**Rationale:** These are constraints, not guidelines. All downstream technical documents must honor them.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-016
**Decision:** The governing test for event inclusion is: Does this event materially inform the understanding, condition, provenance, risk, or stewardship of the property?
**Rationale:** Implementation-independent and domain-independent. Designed to hold for any event category, present or future.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-017
**Decision:** Event domains are classifications within one Institutional Record, not separate records. The recognized domain list is illustrative and explicitly non-exhaustive.
**Rationale:** Prevents the architecture from being constrained by today's understanding of property event categories.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-014
**Decision:** The Institutional Record is defined as the persistent institutional representation of a property's lifecycle.
**Rationale:** This definition is the organizing principle of the data architecture. All downstream data decisions trace to it.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-015
**Decision:** Four architectural principles govern the Institutional Record: canonical identity, accumulated history, domain-agnosticism, and extensibility.
**Rationale:** These are constraints, not guidelines. All downstream technical documents must honor them.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-016
**Decision:** The governing test for event inclusion is: Does this event materially inform the understanding, condition, provenance, risk, or stewardship of the property?
**Rationale:** Implementation-independent and domain-independent. Designed to hold for any event category, present or future.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-017
**Decision:** Event domains are classifications within one Institutional Record, not separate records. The recognized domain list is illustrative and explicitly non-exhaustive.
**Rationale:** Prevents the architecture from being constrained by today's understanding of property event categories.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-014
**Decision:** The Institutional Record is defined as the persistent institutional representation of a property's lifecycle.
**Rationale:** This definition is the organizing principle of the data architecture. All downstream data decisions trace to it.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-015
**Decision:** Four architectural principles govern the Institutional Record: canonical identity, accumulated history, domain-agnosticism, and extensibility.
**Rationale:** These are constraints, not guidelines. All downstream technical documents must honor them.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-016
**Decision:** The governing test for event inclusion is: Does this event materially inform the understanding, condition, provenance, risk, or stewardship of the property?
**Rationale:** Implementation-independent and domain-independent. Designed to hold for any event category, present or future.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-017
**Decision:** Event domains are classifications within one Institutional Record, not separate records. The recognized domain list is illustrative and explicitly non-exhaustive.
**Rationale:** Prevents the architecture from being constrained by today's understanding of property event categories.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-014
**Decision:** The Institutional Record is defined as the persistent institutional representation of a property's lifecycle.
**Rationale:** This definition is the organizing principle of the data architecture. All downstream data decisions trace to it.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-015
**Decision:** Four architectural principles govern the Institutional Record: canonical identity, accumulated history, domain-agnosticism, and extensibility.
**Rationale:** These are constraints, not guidelines. All downstream technical documents must honor them.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-016
**Decision:** The governing test for event inclusion is: Does this event materially inform the understanding, condition, provenance, risk, or stewardship of the property?
**Rationale:** Implementation-independent and domain-independent. Designed to hold for any event category, present or future.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-017
**Decision:** Event domains are classifications within one Institutional Record, not separate records. The recognized domain list is illustrative and explicitly non-exhaustive.
**Rationale:** Prevents the architecture from being constrained by today's understanding of property event categories.
**Source:** Doc 09 — Data Architecture
**Date:** 2026-06-26

## D-018
**Decision:** The Registry ID is the permanent canonical identifier assigned to every property that enters The Registry. It is the foundational key of the entire data architecture.
**Rationale:** The Institutional Record requires a permanent, platform-independent, ownership-independent anchor. No existing identifier was designed for this purpose.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

## D-019
**Decision:** The Registry ID is opaque. It encodes no descriptive attributes. Its only responsibility is identity.
**Rationale:** Identifiers that encode descriptive attributes become unreliable when those attributes change. Opacity ensures long-term stability.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

## D-020
**Decision:** A Registry ID is assigned to every property at the moment it first enters The Registry. Assignment is unconditional and requires no evidence threshold, verification, or minimum data.
**Rationale:** Identity is the precondition for everything else in the architecture. It must never be conditional.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

## D-021
**Decision:** The Registry ID does not replace existing property identifiers. It provides the permanent canonical anchor to which all existing identifiers are associated.
**Rationale:** Existing identifiers serve their domains well. The Registry ID anchors them, not competes with them.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

## D-022
**Decision:** The four architectural layers — Registry ID, Institutional Record, Verification, and Registry Confidence — are independent. No layer depends on the state of another to fulfill its function.
**Rationale:** Clean separation ensures each layer can evolve without breaking the others.
**Source:** Doc 13 — Registry ID
**Date:** 2026-06-26

## D-023
**Decision:** The atomic unit of the Institutional Record is the Registry Event — a recorded assertion about a property, anchored to the Registry ID, supported by provenance, and preserved append-only.
**Rationale:** "Sourced assertion" is more precise than "occurrence" or "observation" and accommodates all contribution types without special-casing any of them.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

## D-024
**Decision:** Registry Events are classified into five classes: Occurrence, Observation, Document, Status, and Correction. Class is a required field.
**Rationale:** Classification governs structural role and relationship rules without constraining the domain-agnostic nature of the event model.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

## D-025
**Decision:** Correction Events reference prior events and are appended to the record. They do not alter, remove, or replace the events they address.
**Rationale:** Direct implementation of the architectural principle: history is accumulated, never rewritten.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

## D-026
**Decision:** Date uncertainty is recorded through a date confidence qualifier, not suppressed. Vocabulary of date confidence levels deferred to Doc 12.
**Rationale:** Suppressing events with uncertain dates degrades the Institutional Record. The Registry preserves what is known, including the limits of what is known.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26

## D-027
**Decision:** Verification status and Registry Confidence are external to the event record. Changes are applied through Status Events and do not modify the original event.
**Rationale:** Keeps the event record immutable while allowing confidence to evolve as verification is obtained.
**Source:** Doc 10 — Event Data Model
**Date:** 2026-06-26
