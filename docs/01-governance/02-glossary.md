# Glossary
**Project:** Haus Registry
**Document Type:** Governance Standard
**Status:** Accepted
**Purpose:** Canonical terminology for the Haus Registry repository. All documents must use these terms consistently. Do not introduce synonyms or alternate terms without an explicit architectural revision.

---

## Canonical Terms

**The Registry**
The platform. The full ecosystem of products, data, and participants operated by Haus Registry.

**Haus Registry**
The company.

**Property**
The primary entity. A residential property is the anchor of every record, every event, and every identity in the system. It is not defined by its owner, its transaction history, or its current condition.

**Institutional Record**
The persistent, append-only accumulation of verified events and relationships that represent a property's lifecycle. Not a file. Not a database entry. An institutional record in the fullest sense.

**Property Registry**
The permanent, Registry ID-anchored record for a single property. Contains the Identity Layer and the Record Layer.

**Registry ID**
The permanent, opaque, globally unique canonical identifier assigned to every property when it first enters The Registry. Immutable. Ownership-independent. Platform-independent.

**Registry Event**
The atomic unit of the Institutional Record. A recorded assertion about a property, anchored to the Registry ID, supported by provenance, and preserved append-only.

**Registry Confidence Score**
The weighted composite measurement of the Institutional Record's completeness and trustworthiness. Composed of Coverage, Verification Depth, and Recency. A measurement, not a judgment.

**Registry Verified**
The designation awarded to a property whose Institutional Record meets the threshold criteria established in the Trust Framework.

**Registry Report**
The shareable, participant-facing report generated from the Property Registry. The primary external deliverable of the platform.

**Registry Timeline**
The chronological representation of a property's event history derived from the Institutional Record.

**My Registry**
The homeowner-facing dashboard. The primary interface through which a homeowner stewards their property's Institutional Record.

**Registry Pro**
The professional portal. The interface through which licensed professionals — inspectors, contractors, appraisers, agents, lenders, insurers — interact with and contribute to the Institutional Record.

**Registry Vault**
Secure document storage for warranties, invoices, permits, manuals, and other property-related documents.

**Registry AI**
The AI layer responsible for document extraction, event classification, gap identification, and record analysis.

**Registry API**
The developer platform. The interface through which third-party systems integrate with The Registry.

**Registry Network**
The ecosystem of institutional partners — manufacturers, contractors, lenders, insurers, municipalities — connected to The Registry.

**Registry Alerts**
Participant notifications for maintenance reminders, warranty expirations, recalls, and other time-sensitive events.

**Registry Insights**
Analytics and predictive maintenance recommendations derived from the Institutional Record.

**Registry Verify**
The workflow for validating documents, claims, and contributor identity.

**Stewardship**
The relationship between a property and its current owner. Ownership transfers; stewardship transitions. The Institutional Record outlasts both.

**Primary Steward**
The current homeowner. The participant with the greatest ongoing relationship to the property's Institutional Record.

**Stewardship Transition**
The event that records a change in ownership. Recorded as an Occurrence Event in the OWN domain. Does not reset the Institutional Record.

**Source Tier**
The credibility classification of an event's origin. Six levels: S1 (government/regulatory) through S6 (unverified). Assigned at ingestion. Immutable.

**Verification Level**
The degree to which a Registry Event's assertion has been validated. Six levels: VL-1 (unverified) through VL-6 (fully verified). May be updated over time through Status Events.

**Coverage**
The breadth dimension of Registry Confidence. Measures the proportion of significant property domains for which at least one verified event exists.

**Verification Depth**
The quality dimension of Registry Confidence. Measures the weighted average verification level across all active events.

**Recency**
The currency dimension of Registry Confidence. Measures the degree to which the Institutional Record reflects the property's current condition, accounting for domain-specific decay.

**Lifecycle**
The full accumulation of significant, verifiable events and relationships that shape a property across time. The scope of what the Institutional Record represents.

**Persistent Institutional Record**
The defining characteristic of what Haus Registry builds. Persistent means it does not reset at ownership transfer, does not expire, and is not abandoned when a platform shuts down.

---

*Terminology drift creates conceptual drift. Use these terms consistently across all documents, sessions, and contributors.*
