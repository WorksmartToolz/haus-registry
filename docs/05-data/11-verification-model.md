# Document 11: Verification Model
**Haus Registry | Foundation Documentation**
*Phase: Data Architecture | Status: Complete*

---

## Scope

Document 04 established the Trust Framework: the S1–S6 source hierarchy, the VL-1 through VL-6 verification levels, and the Registry Confidence Score model composed of Coverage, Verification Depth, and Recency. Document 10 established that every Registry Event carries a source tier, a verification status, and a Registry Confidence value as required fields.

This document specifies how those constructs operate at the data layer — how source tiers are assigned to events, how verification levels are applied and updated, how the Registry Confidence Score is calculated for individual events and for the property as a whole, and how verification activity is recorded without altering the events it describes.

This document does not redefine the Trust Framework. It implements it.

---

## Source Tier Assignment

Every Registry Event carries a source tier drawn from the S1–S6 hierarchy established in Doc 04. Source tier is assigned at the time of event ingestion based on the origin of the assertion, not the quality of its content.

Source tier is a property of the event's provenance. It reflects who or what produced the underlying assertion:

- **S1** — Government and regulatory records: permits, tax records, deeds, zoning filings, code enforcement records
- **S2** — Licensed professional records: inspection reports, appraisals, engineering assessments, contractor documentation with license verification
- **S3** — Institutional records: insurance filings, warranty registrations, manufacturer records, lender documentation
- **S4** — Verified participant records: licensed professional submissions verified through Registry Pro, identity-verified homeowner submissions with supporting documentation
- **S5** — Participant records: homeowner submissions, unverified contractor submissions, agent-contributed records
- **S6** — Unverified or anonymous assertions: unverified third-party submissions, historical approximations, inferred data

Source tier is immutable after assignment. If the source of an event is found to have been misclassified, a Correction Event is created. The original event retains its original source tier. The Correction Event carries the updated attribution.

Source tier is one input into verification level but does not determine it. A S1 record is not automatically VL-6 verified. Verification level reflects the degree to which an event's claim has been validated — source tier reflects the credibility of its origin.

---

## Verification Level Assignment

Every Registry Event carries a verification level drawn from the VL-1 through VL-6 scale established in Doc 04. Verification level reflects how thoroughly the event's assertion has been validated at the time of assessment.

Verification levels operate on a cumulative scale:

- **VL-1** — Unverified assertion: recorded as submitted, no validation performed
- **VL-2** — Format and consistency validated: the event passes structural checks and is internally consistent with existing record data
- **VL-3** — Source corroborated: the assertion is supported by at least one additional independent source
- **VL-4** — Professionally reviewed: the assertion has been reviewed or confirmed by a licensed professional with relevant domain authority
- **VL-5** — Institutionally validated: the assertion is supported by an institutional record (S1–S3) or has been formally verified through a Registry verification process
- **VL-6** — Fully verified: the assertion is supported by primary institutional records and has been independently confirmed through the Registry's highest verification standard

Verification level is assigned at the time of ingestion based on available evidence and may be updated as additional verification is obtained. Verification level updates are applied through Status Events — the original event record is not modified.

A newly ingested event with no additional validation receives VL-1 by default. Verification is not a prerequisite for admission to the Institutional Record. It is a quality dimension that accumulates over time.

---

## Verification Activity as Status Events

All verification activity — level assignments, level updates, challenges, resolutions — is recorded as Status Events in the Institutional Record. This preserves the immutability of the original event while maintaining a complete audit trail of how the event's verification status has evolved.

A verification Status Event carries:

- Reference to the event being verified
- Prior verification level
- New verification level
- Verification method and source
- Date of verification activity
- Contributor or system responsible for the verification update

This means that for any Registry Event, the full verification history is recoverable from the Institutional Record without inspecting or altering the original event.

---

## Registry Confidence Score — Event Level

Every Registry Event carries an event-level Registry Confidence value. This value is a derived score calculated from three inputs established in Doc 04:

**Coverage** reflects the breadth of the event's documentation. An event supported by a permit, an invoice, a photo set, and a professional report has higher coverage than an event supported by a single homeowner note.

**Verification Depth** reflects the verification level of the event. VL-6 events contribute more confidence than VL-1 events. Verification depth is weighted by source tier — a VL-4 assessment from a licensed structural engineer carries more depth than a VL-4 assessment from an unverified contributor.

**Recency** reflects how current the event and its verification are. An event recorded and verified recently carries higher recency weight than an event from twenty years ago with no subsequent verification activity. Recency degrades over time for event types where conditions are expected to change.

The event-level Registry Confidence value is a weighted composite of these three inputs. The specific weighting formula is an implementation detail deferred to Doc 12. The principle established here is that confidence is multidimensional — no single input determines it.

Event-level confidence is recalculated whenever a relevant Status Event is recorded: a new verification update, an additional supporting document, a correction, or a challenge resolution.

---

## Registry Confidence Score — Property Level

The property-level Registry Confidence Score is a composite of event-level confidence values across the full Institutional Record, weighted by event domain and recency.

The property-level score reflects the overall institutional weight of everything the Registry knows about a property. It is not a simple average. Events in high-stakes domains — structural, regulatory, ownership — carry more weight than events in lower-stakes domains. Recent events carry more weight than older events in domains where conditions change over time.

The property-level score has three components, inherited from Doc 04:

**Coverage Score** — The proportion of significant property domains for which at least one verified event exists. A property with verified events across many domains scores higher than a property with deep verification in one domain and nothing in others.

**Verification Depth Score** — The weighted average verification level across all active events in the Institutional Record, adjusted by source tier.

**Recency Score** — The degree to which the Institutional Record reflects the property's current condition. Domains with time-sensitive events — systems, structure, regulatory status — apply a recency decay that degrades confidence as time passes without updated verification.

The property-level Registry Confidence Score is recalculated whenever a new event is admitted, a verification level is updated, or a recency decay threshold is crossed.

The score is presented to Registry participants as a composite value. Its components are available for inspection in Registry Pro and Registry Report, providing the transparency required by the source visibility principle established in Doc 03.

---

## Confidence and Trust

Registry Confidence is a measurement, not a judgment. A low confidence score does not mean a property is defective or a seller is dishonest. It means the Institutional Record does not yet have sufficient verified history to support high confidence. A high confidence score does not guarantee that a property is in good condition. It means the Registry has accumulated substantial, well-sourced, well-verified evidence about the property's history.

This distinction must be preserved in all downstream implementations. The Registry Confidence Score informs participants. It does not adjudicate properties or their owners.

---

## Decisions Established

The following architectural decisions are established by this document and logged in DECISIONS.md:

**D-028:** Source tier is assigned at ingestion based on the origin of the assertion and is immutable after assignment. Misclassification is resolved through Correction Events.

**D-029:** Verification level is assigned at ingestion and may be updated over time. All verification level updates are recorded as Status Events. The original event record is not modified.

**D-030:** Event-level Registry Confidence is a weighted composite of Coverage, Verification Depth, and Recency. Specific weighting formula deferred to Doc 12.

**D-031:** Property-level Registry Confidence Score is a domain-weighted composite of event-level confidence values, recalculated on every new event, verification update, or recency decay threshold crossing.

**D-032:** Registry Confidence is a measurement, not a judgment. It informs participants and does not adjudicate properties or owners.

---

## Constitutional Traceability

| Principle | Source |
|-----------|--------|
| S1–S6 source hierarchy | Doc 04 — Trust Framework |
| VL-1 through VL-6 verification levels | Doc 04 — Trust Framework |
| Registry Confidence Score: Coverage + Verification Depth + Recency | Doc 04 — Trust Framework |
| Source visibility | Doc 03 — Haus Registry Doctrine (Belief 4) |
| Verification increases value | Doc 03 — Haus Registry Doctrine (Belief 5) |
| Confidence reduces uncertainty | Doc 03 — Haus Registry Doctrine (Belief 6) |
| Trust is a market outcome | Doc 03 — Haus Registry Doctrine (Belief 7) |
| History is accumulated, never rewritten | Doc 09 — Data Architecture (Principle 2) |
| Verification status is external to the event record | Doc 10 — Event Data Model (D-027) |

---

## Related Documents

- **Doc 04 — Trust Framework:** Establishes the source hierarchy, verification levels, and confidence score model that this document implements.
- **Doc 09 — Data Architecture:** Establishes the architectural principles governing immutability and accumulation.
- **Doc 10 — Event Data Model:** Defines the Registry Event fields — source tier, verification status, Registry Confidence — that this document specifies.
- **Doc 12 — Property Registry Specification:** Defines the confidence weighting formula, domain weight table, and recency decay parameters.

---

## Downstream Dependencies

- Doc 12 — Property Registry Specification
- Registry API — confidence score retrieval and verification status endpoints
- Registry Report — confidence score presentation and component breakdown
- Registry Pro — verification workflow, professional submission, and confidence audit tools
- Registry Verified — designation criteria tied to verification level thresholds
- Registry AI — confidence gap identification and verification recommendation
- My Registry — homeowner-facing confidence display and contribution guidance
