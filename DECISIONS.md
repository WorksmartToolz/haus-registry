
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
