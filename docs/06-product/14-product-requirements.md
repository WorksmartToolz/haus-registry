# 14 – Product Requirements Document
**Status:** COMPLETE
**Owner:** Founder
**Last Updated:** 2026-06-26
**Document Version:** 1.0
**Phase:** Product Architecture

---

## Inherits From

- Doc 00: Founder's Insight — the property loses its story at every ownership transition
- Doc 02: Missing Memory Layer — the market abandons knowledge rather than destroys it
- Doc 03: Haus Registry Doctrine — ten governing beliefs constraining every product decision
- Doc 04: Trust Framework — source hierarchy, verification levels, confidence score composition
- Doc 07: Registry Participants — participant roles and their relationship to the Institutional Record
- Doc 08: Stakeholder Analysis — institutional relationships informing professional and API surfaces
- Docs 09–13: Data Architecture — the complete settled data model this document exposes

## Settled Principles (Do Not Reopen)

- D-014: Institutional Record as the persistent institutional representation of a property's lifecycle
- D-015: Four architectural principles: canonical identity, accumulated history, domain-agnosticism, extensibility
- D-016: Governing test for what belongs in the record
- D-022: Four architectural layers are independent
- D-032: Registry Confidence is a measurement, not a judgment
- D-037: Ownership transition does not reset the Property Registry
- D-040: PRD defines capabilities; Business Model defines value capture
- D-042: Spatial & Site Documentation is a first-class domain
- D-044: Product element taxonomy by architectural role

## This Document Defines

- Product Principles: constitutional philosophy translated into product-layer constraints
- Complete capability definition for all product surfaces, platform services, institutional artifacts, trust framework components, and platform network & intelligence elements
- Acceptance criteria for each capability
- Explicit non-goals for each element

## This Document Does Not Define

- Pricing, packaging, access tiers, or monetization (Doc 23, Doc 24)
- System architecture, database design, or API specification (Docs 15–17)
- UX design or interaction patterns (Doc 18)
- AI model selection or training methodology (Doc 19)
- Security implementation or regulatory compliance (Docs 20–21)
- MVP scope (Doc 27)

---

## Part I — Product Principles

The following principles translate the Haus Registry Doctrine into product-layer constraints. Every product surface, platform service, and institutional artifact inherits these principles. Where a capability appears to conflict with a principle, the principle governs.

### Principle 1: The Property Is Always the Anchor

Every product surface is organized around the property, not around the participant using it. A homeowner using My Registry is interacting with their property's Institutional Record — not with a personal account that happens to contain property information.

This has direct product consequences:
- Participant accounts are stewardship relationships with properties, not containers for property data
- When a participant relationship ends (sale, account closure, subscription lapse), the property's Institutional Record is unaffected
- No product feature may require treating the owner as the primary entity

*Traces to Doctrine I, D-018, D-037*

### Principle 2: The Record Accumulates — The Product Never Resets It

No product action, no participant decision, and no business event may cause the Institutional Record to reset, truncate, or lose previously recorded information.

This has direct product consequences:
- Ownership transition workflows transfer stewardship — they do not clear history
- Account deletion removes the participant relationship — it does not remove property records
- Archive, hide, or suppress functions are not permitted for verified records
- Correction is always append — not overwrite

*Traces to Doctrine II, D-008, D-025*

### Principle 3: The Product Assembles — It Does Not Adjudicate

The product presents what is known about a property, attributed to its source, at its verified level. It does not determine truth. It does not rank competing claims. It does not resolve disputes by choosing a winner.

This has direct product consequences:
- When two records conflict, both are displayed with their sources and verification levels
- The Registry Confidence Score is presented as a measurement with its component dimensions visible — never as a verdict
- Registry AI extracts and classifies — it does not assert facts without source attribution
- Registry Verified is a threshold designation, not a quality ranking

*Traces to Doctrine III, IV, V, D-032*

### Principle 4: Source Visibility Is Non-Negotiable

Every record displayed in any product surface shows its source tier and verification level. There is no design exception to this rule.

This has direct product consequences:
- No aggregated view may suppress source attribution in the name of simplicity
- Registry AI-extracted data is always labeled as AI-extracted with confidence level
- Homeowner-submitted records are always labeled as homeowner-submitted
- Municipal permit records are always labeled as municipal permit records

*Traces to Doctrine IV, D-006, D-028*

### Principle 5: Confidence Is Multidimensional — Always Displayed in Full

The Registry Confidence Score is never presented as a single number without its three component dimensions: Coverage, Verification Depth, and Recency. Compressing confidence to a single score without context converts a measurement into a judgment — which the product explicitly does not do.

*Traces to Doctrine V, VI, D-007, D-032*

### Principle 6: The Product Is Infrastructure — It Does Not Optimize for Engagement

Product features are evaluated against whether they strengthen the Institutional Record, not whether they increase engagement metrics. Features that encourage unverified record submission, inflate confidence scores, or prioritize activity over accuracy are not built.

This has direct product consequences:
- No gamification that incentivizes record volume over record quality
- No notification design that creates urgency around record submission without verified need
- No confidence score presentation that rewards activity rather than accuracy

*Traces to Doctrine IX*

### Principle 7: Every Capability Passes the Governing Test

A product capability earns its place by answering yes to: does this materially inform the understanding, condition, provenance, risk, or stewardship of the property? Features that do not pass this test are not built regardless of their commercial appeal.

*Traces to D-016*

---

## Part II — Product Surfaces

Product Surfaces are participant-facing workspaces through which users interact with the platform. Each surface is a complete experience organized around a participant's relationship to the Institutional Record.

---

### My Registry

**Architectural role:** Product Surface
**Participant served:** Primary Steward (homeowner)
**Core purpose:** The workspace through which a homeowner stewards their property's Institutional Record across their period of ownership — and prepares it for stewardship transition.

#### Capabilities

**Property Registry Dashboard**
The homeowner's primary view of their property's Institutional Record. Displays the Registry Confidence Score in full (Coverage, Verification Depth, Recency), the Registry Timeline, domain coverage summary, and verification status across domains.

Acceptance criteria:
- Confidence Score always displays all three component dimensions, never as a standalone number
- Domain coverage gaps are visible and actionable
- Timeline is chronological and append-only in presentation
- Source tier and verification level are visible for every displayed record

**Record Contribution**
The workflow through which homeowners add events, documents, and records to the Institutional Record. Homeowner-contributed records are automatically assigned Source Tier S4 (homeowner-submitted) and Verification Level VL-1 (unverified) at ingestion.

Acceptance criteria:
- Every submitted record is attributed to the homeowner at S4/VL-1 upon ingestion
- No mechanism exists to submit records without source attribution
- Submission confirmation states the source tier and verification level assigned
- Registry AI extraction is offered for document uploads, clearly labeled as AI-extracted

**Registry Vault Access**
The homeowner's interface to Registry Vault — secure document storage organized by domain. Homeowners can upload, organize, and retrieve documents. Documents in the Vault are source-attributed and linked to Registry Events where applicable.

Acceptance criteria:
- Spatial & Site Documentation domain is a first-class Vault category (D-042)
- Documents are linked to Registry Events when the event-document relationship is established
- All documents carry upload date, contributor, and source tier
- Documents are never deleted — only superseded by newer versions with prior versions retained

**Registry Report Generation**
The workflow for generating and sharing a Registry Report from the current state of the Institutional Record. The homeowner controls sharing — the report is not publicly accessible without homeowner action.

Acceptance criteria:
- Report reflects the Institutional Record at the moment of generation with a generation timestamp
- Homeowner may share via link, PDF export, or direct participant invitation
- Shared reports are read-only — recipients cannot modify the Institutional Record through report access
- Report includes full source attribution and verification levels for all displayed records

**Stewardship Transition Preparation**
The workflow that guides a homeowner preparing to sell. Identifies record gaps, highlights high-value verifiable records, and prepares the Institutional Record for incoming steward review.

Acceptance criteria:
- Gap analysis is based on domain coverage — not on commercial completeness metrics
- No record is marked as mandatory — gaps are informational, not blocking
- Transition does not reset or archive any existing records
- Incoming steward access is granted as a stewardship transfer, not a data migration

**Registry Alerts Management**
The homeowner's interface for managing maintenance reminders, warranty expirations, permit anniversaries, and recall notifications derived from the Institutional Record.

Acceptance criteria:
- All alerts are derived from actual records in the Institutional Record, not generic schedules
- Alert sources are visible — the record that generated the alert is accessible from the alert
- Homeowner may dismiss or defer alerts — dismissal is recorded as a Status Event

**Non-goals for My Registry:**
- My Registry does not set pricing or access tiers (Doc 23)
- My Registry does not define UX patterns or visual design (Doc 18)
- My Registry does not process payments or manage subscriptions

---

### Registry Pro

**Architectural role:** Product Surface
**Participants served:** Licensed professionals — inspectors, contractors, appraisers, agents, lenders, insurers
**Core purpose:** The workspace through which licensed professionals interact with, contribute to, and derive value from the Institutional Record in the course of their professional work.

#### Capabilities

**Property Record Access**
Registry Pro provides professionals with structured access to the Institutional Record for properties relevant to their work, subject to participant consent and access controls defined in Doc 20.

Acceptance criteria:
- Access is property-specific and consent-gated — professionals do not have platform-wide browsing access
- Source tier and verification level are displayed for every record, consistent with Principle 4
- Professional access is logged as a Status Event on the Institutional Record

**Professional Record Contribution**
The workflow through which licensed professionals add verified records to the Institutional Record. Professional contributions are source-tiered based on the contributor's license and institutional affiliation (S2 for government-affiliated, S3 for licensed professional businesses, per Trust Framework).

Acceptance criteria:
- Contributor credential verification is required before professional source tier is assigned
- Records submitted through Registry Pro carry the contributor's professional classification
- Registry Verify integration is available for high-value professional contributions

**Inspection and Assessment Integration**
The workflow for licensed inspectors and appraisers to submit structured inspection and assessment records directly to the Institutional Record. Structured data fields extracted from standard inspection formats are supported.

Acceptance criteria:
- Registry AI extraction is offered for standard inspection report formats, labeled as AI-extracted
- Inspector can review, correct, and approve extracted records before submission
- Submitted inspection records carry the inspector's license tier and firm affiliation
- Spatial & Site Documentation domain is supported for site surveys and structural assessments (D-042)

**Contractor Work Record Submission**
The workflow for licensed contractors to submit completed work records — including invoices, permits, warranties, and as-built documentation — to the Institutional Record.

Acceptance criteria:
- Permit records are cross-referenced with municipal records where available (S1 verification path)
- Warranty documents are linked to the Registry Event and stored in Registry Vault
- As-built drawings and spatial documentation are filed in the Spatial & Site Documentation domain (D-042)
- Contractor submissions carry the contractor's license classification

**Registry Report Access**
Professionals with homeowner-granted access may view Registry Reports for properties in their workflow.

Acceptance criteria:
- Report access requires explicit homeowner authorization
- Professional access to reports is logged
- Report displays are identical in source attribution and verification level display to homeowner views — professionals do not see a "cleaner" version

**Non-goals for Registry Pro:**
- Registry Pro does not define professional licensing standards or credential verification methodology (Doc 20)
- Registry Pro does not set professional pricing or subscription structure (Doc 23)
- Registry Pro does not provide lead generation, client management, or CRM functionality

---

## Part III — Platform Services

Platform Services are cross-cutting capabilities used by multiple product surfaces. They are not participant destinations — they are the infrastructure that product surfaces are built on.

---

### Registry Vault

**Architectural role:** Platform Service
**Core purpose:** Secure, permanent document storage organized by domain, linked to the Institutional Record through Registry Events.

#### Capabilities

**Document Storage and Retrieval**
Vault accepts documents of all standard formats. Documents are stored permanently — no deletion, no expiration. Superseded documents are retained with prior-version designation.

Acceptance criteria:
- All document formats produce a stored artifact with upload metadata
- Documents carry: upload timestamp, contributor, source tier, linked Registry Event (where applicable), domain classification
- No document is deleted under any circumstances — superseded documents are flagged, not removed
- Retrieval is available to authorized participants through product surfaces

**Domain Organization**
Documents are organized within the Vault by domain classification, consistent with the domain registry established in Doc 12. Spatial & Site Documentation is a first-class domain.

Domains include (non-exhaustive, extensible per D-015):
- Structural
- Mechanical / HVAC
- Electrical
- Plumbing
- Roofing
- Spatial & Site Documentation (architectural drawings, plans, surveys, site maps, septic records, utility layouts, easements, as-built documentation)
- Legal / Title
- Financial / Insurance
- Environmental
- Appliances & Systems
- Permits & Inspections

Acceptance criteria:
- Every document is classified to at least one domain on upload
- Registry AI assists with domain classification, labeled as AI-suggested
- Homeowner may override AI-suggested classification

**Event Linking**
Documents in the Vault may be linked to Registry Events. The link is bidirectional — a Registry Event referencing a document provides access to the Vault document; a Vault document linked to an event surfaces the event on the Registry Timeline.

Acceptance criteria:
- Linking is optional but encouraged at upload time
- Registry AI suggests event links for uploaded documents, labeled as AI-suggested
- Unlinked documents are accessible in the Vault but do not appear on the Registry Timeline

**Non-goals for Registry Vault:**
- Vault does not define storage infrastructure or cloud implementation (Doc 26)
- Vault does not define encryption standards or access control implementation (Doc 20)

---

### Registry AI

**Architectural role:** Platform Service
**Core purpose:** The AI layer responsible for document extraction, event classification, gap identification, record analysis, and spatial document interpretation across all product surfaces.

#### Capabilities

**Document Extraction**
Registry AI extracts structured data from uploaded documents — invoices, inspection reports, permits, warranties, architectural drawings, site plans, and other property-related documents. All extracted data is attributed to Registry AI at the appropriate source tier and clearly labeled as AI-extracted.

Acceptance criteria:
- All AI-extracted data is labeled as AI-extracted with a confidence level
- Extracted data is presented for human review before being submitted as Registry Events
- No AI-extracted record is submitted to the Institutional Record without explicit contributor confirmation
- AI extraction confidence is visible alongside extracted data

**Spatial Document Interpretation**
Registry AI supports extraction and interpretation from spatial document types — architectural drawings, floor plans, site plans, surveys, septic system maps, utility layouts, and as-built documentation. Extracted spatial data (dimensions, locations, system routes) is structured as Registry Events in the Spatial & Site Documentation domain. (D-042)

Acceptance criteria:
- Spatial document types are recognized and routed to appropriate extraction workflow
- Extracted spatial attributes (system location, dimension, route) are structured data fields, not free text
- Interpretation confidence is displayed for spatial extractions
- AI-interpreted spatial data requires contributor confirmation before submission

**Gap Identification**
Registry AI analyzes the Institutional Record and identifies domain coverage gaps — areas where no records exist, where records are aging beyond recency thresholds, or where missing documentation is commonly associated with the property's age, type, or known history.

Acceptance criteria:
- Gap identification is based on domain coverage analysis against the domain registry (D-035)
- Gaps are presented as informational — never as mandatory actions or blocking conditions
- Gap analysis logic is traceable to the domain registry and recency decay settings, not to commercial priorities

**Event Classification**
Registry AI assists with classifying uploaded documents and submitted records into the correct Registry Event class (Occurrence, Observation, Document, Status, Correction) and domain. Classification is presented as AI-suggested and requires contributor confirmation.

Acceptance criteria:
- AI-suggested classifications display the classification and the basis for the suggestion
- Contributors may override any AI-suggested classification
- Overrides are recorded and used to improve classification accuracy over time

**Non-goals for Registry AI:**
- Registry AI does not determine verification levels — that is the Trust Framework's role (Doc 04)
- Registry AI does not assert facts — it extracts and classifies, with source attribution (Principle 3)
- Registry AI model selection, training, and infrastructure are defined in Doc 19

---

### Registry API

**Architectural role:** Platform Service
**Core purpose:** The developer platform through which third-party systems integrate with The Registry — reading from and contributing to the Institutional Record under defined access and attribution rules.

#### Capabilities

**Property Registry Read Access**
Authenticated third-party systems may read from the Institutional Record for properties within their authorized scope, subject to participant consent and access controls.

Acceptance criteria:
- All API access is authenticated, scoped to specific properties or property sets, and consent-gated
- Every API response includes source tier and verification level for each record
- API access is logged as a Status Event on the Institutional Record

**Registry Event Contribution**
Authenticated third-party systems may contribute Registry Events to the Institutional Record. Contributed events carry the source tier appropriate to the contributing system's institutional classification.

Acceptance criteria:
- Contributing systems are credentialed and assigned a source tier at onboarding
- All API-contributed events carry the contributing system's identifier and source tier
- No API contribution bypasses source attribution

**Registry ID Resolution**
Third-party systems may resolve Registry IDs from known identifiers (address, APN, MLS number) and resolve known identifiers from Registry IDs.

Acceptance criteria:
- Resolution is available for all identifier types in the Registry ID anchor table (D-021)
- Resolution responses include all known identifiers for the property
- Resolution access is logged

**Webhook and Event Streaming**
Third-party systems may subscribe to Registry Event streams for properties within their authorized scope, receiving notifications when new events are added or verification levels are updated.

Acceptance criteria:
- Webhook payloads include full source attribution and verification level
- Subscribers may filter by domain, event class, or verification level
- Delivery failures are retried with exponential backoff and logged

**Non-goals for Registry API:**
- Registry API does not define authentication standards or rate limiting implementation (Doc 17)
- Registry API does not define commercial API tiers or developer pricing (Doc 23)

---

### Registry Verify

**Architectural role:** Platform Service
**Core purpose:** The operational verification workflow — the process by which unverified or partially verified records are elevated through the verification hierarchy defined in the Trust Framework.

#### Capabilities

**Document Verification Workflow**
Registry Verify provides a structured workflow for submitting documents for verification review, tracking verification status, and recording verification outcomes as Status Events on the Institutional Record.

Acceptance criteria:
- Verification requests are anchored to specific Registry Events
- Verification status is always current and visible — pending, in review, verified, rejected
- Verification outcomes are recorded as Status Events — the original event is not modified (D-029)
- Rejected verification attempts are recorded — the rejection is itself a provenance record

**Contributor Identity Verification**
Registry Verify validates contributor identity and professional credentials, enabling source tier assignment for professional contributors in Registry Pro.

Acceptance criteria:
- Credential verification is required before professional source tier (S2, S3) is assigned
- Verification of credentials is a one-time onboarding process with periodic renewal
- Credential status is visible on all records contributed by the verified contributor

**Municipal Record Cross-Reference**
Registry Verify cross-references submitted permit and inspection records against available municipal databases, enabling S1 source tier assignment where municipal records confirm the submitted record.

Acceptance criteria:
- Cross-reference results are recorded regardless of match or mismatch
- Mismatches are recorded as Correction Event candidates, not silently resolved
- Municipal cross-reference availability is displayed per jurisdiction

**Non-goals for Registry Verify:**
- Registry Verify does not define verification standards — those are in the Trust Framework (Doc 04)
- Registry Verify does not adjudicate disputes — it records outcomes (Principle 3)

---

## Part IV — Institutional Artifacts

Institutional Artifacts are the persistent outputs produced by the platform — enduring representations of institutional knowledge anchored to the Registry ID.

---

### Property Registry

**Architectural role:** Institutional Artifact
**Core purpose:** The permanent, Registry ID-anchored record for a single property. The central artifact from which all other outputs are derived.

The Property Registry is fully specified in Doc 12. This document records its product-layer requirements — how it is presented, accessed, and experienced by participants.

#### Product-layer requirements

- The Property Registry is always presented as a unified record, not as separate domain silos
- Domain organization is a navigation aid — it does not suggest separate records exist per domain
- The Identity Layer (immutable) and Record Layer (accumulating) are distinguished in participant-facing views
- Participants are never shown a "blank" Property Registry — properties without records display their Registry ID and entry date, establishing that the record exists and is awaiting accumulation

---

### Registry Report

**Architectural role:** Institutional Artifact
**Core purpose:** The shareable, participant-facing report generated from the Institutional Record at a point in time. The primary external deliverable of the platform.

#### Capabilities

**Report Generation**
A Registry Report is generated from the current state of the Institutional Record. It carries a generation timestamp and represents the record at that moment.

Acceptance criteria:
- Reports display the generation timestamp prominently
- Reports include the Registry Confidence Score with all three component dimensions
- All records in the report carry source tier and verification level
- Reports are not editable by any participant — they are read-only representations of the Institutional Record

**Report Sharing**
Reports may be shared via link, PDF export, or direct participant invitation.

Acceptance criteria:
- Shared links are access-controlled — homeowner may revoke access at any time
- PDF exports carry a generation timestamp and watermark indicating point-in-time status
- Recipient access to reports is logged

**Non-goals for Registry Report:**
- Registry Report does not replace the Property Registry — it is a point-in-time view of it
- Registry Report format and visual design are defined in Doc 18

---

### Registry Timeline

**Architectural role:** Institutional Artifact
**Core purpose:** The chronological representation of a property's event history derived from the Institutional Record. A temporal view of the same data the Property Registry contains.

#### Product-layer requirements

- The Registry Timeline displays all Registry Events in chronological order, with date confidence indicators for events with date uncertainty (D-034)
- Events with DC-4 through DC-6 date confidence (estimated, approximate, unknown) display their confidence level visibly
- The Timeline is append-only in presentation — no events are removed from the Timeline view
- Ownership transitions appear on the Timeline as Stewardship Transition events — the Timeline does not restart at transitions (D-037)
- Domain filters allow participants to view domain-specific slices of the Timeline without suggesting separate records exist

---

### Registry ID

**Architectural role:** Institutional Artifact
**Core purpose:** The permanent, opaque, globally unique canonical identifier assigned to every property upon entry. The foundational key of the entire architecture.

The Registry ID is fully specified in Doc 13. Product-layer requirements:

- The Registry ID is displayed in every participant-facing view of a property record
- The Registry ID is copyable and shareable — it is the canonical reference for the property
- Participants may use the Registry ID to reference the property in communications, reports, and third-party systems
- The Registry ID is never presented as containing encoded information — it is opaque by design (D-019)

---

## Part V — Trust Framework Components

Trust Framework Components are mechanisms that express or measure trust. They implement the Trust Framework (Doc 04) at the product layer.

---

### Registry Confidence Score

**Architectural role:** Trust Framework Component
**Core purpose:** The quantified measurement of an Institutional Record's completeness and trustworthiness, expressed as a weighted composite of Coverage, Verification Depth, and Recency.

#### Product-layer requirements

- The Registry Confidence Score is always displayed with all three component dimensions visible (Coverage, Verification Depth, Recency) — never as a standalone number (Principle 5, D-032)
- The Score is presented as a measurement — its language never implies a verdict, rating, or grade
- Score changes are explainable — participants can understand what changed and why
- The Score is recalculated and current — it reflects the Institutional Record at the moment of display
- Domain-level confidence breakdowns are available for participants who want to understand coverage gaps by domain

**Non-goals:**
- The Score does not determine access, eligibility, or pricing for any participant
- The Score is not used as a gatekeeping mechanism for any Registry function

---

### Registry Verified

**Architectural role:** Trust Framework Component
**Core purpose:** The designation awarded to a property whose Institutional Record meets the threshold criteria established in the Trust Framework. A threshold designation, not a quality ranking.

#### Product-layer requirements

- Registry Verified is a binary designation — a property either meets the threshold or it does not
- The criteria for Registry Verified are visible to all participants — the threshold is not opaque
- Registry Verified status is displayed prominently on the Property Registry, Registry Report, and Registry Timeline
- Loss of Registry Verified status (if threshold is no longer met due to recency decay) is recorded as a Status Event

---

## Part VI — Platform Network & Intelligence

Platform Network & Intelligence capabilities operate across the platform, connecting participants and communicating meaningful changes derived from the Institutional Record.

---

### Registry Network

**Architectural role:** Platform Network & Intelligence
**Core purpose:** The ecosystem of institutional partners — manufacturers, contractors, lenders, insurers, municipalities — connected to The Registry through the Registry API and Registry Verify workflows.

#### Product-layer requirements

- Registry Network participants contribute to and read from the Institutional Record through defined API integrations
- Network participant contributions carry appropriate source tiers based on their institutional classification
- Network participants are visible in the Institutional Record as contributors — their participation is not anonymous
- Registry Network is not a marketplace — it is an institutional data exchange

---

### Registry Insights

**Architectural role:** Platform Network & Intelligence
**Core purpose:** Analytics and predictive intelligence derived from the Institutional Record, surfaced to homeowners and professionals as actionable property intelligence.

#### Capabilities

**Maintenance Predictions**
Derived from the Institutional Record — equipment age, service history, manufacturer data, and climate exposure — Registry Insights surfaces maintenance predictions for property systems.

Acceptance criteria:
- Predictions are always presented with their derivation basis — the records they are based on
- Predictions carry a confidence level derived from the quality of underlying records
- Predictions are not presented as facts — they are probabilistic intelligence

**Record Gap Analysis**
Registry Insights identifies domain coverage gaps and surfaces them as actionable intelligence, distinguishing between gaps that represent likely undocumented history and gaps that represent genuinely absent history.

---

### Registry Alerts

**Architectural role:** Platform Network & Intelligence
**Core purpose:** Participant notifications for maintenance reminders, warranty expirations, permit anniversaries, recall notifications, and other time-sensitive events derived from the Institutional Record.

#### Product-layer requirements

- All Alerts are derived from actual records in the Institutional Record — not from generic property schedules
- Alert source is always visible — the record that generated the alert is accessible from the alert
- Participants may manage alert preferences without affecting the Institutional Record
- Recall alerts are generated when a Registry Network manufacturer or government source submits a recall event matching equipment in the Institutional Record

---

## Part VII — Initial Property Scrub

When a property enters The Registry, an initial property scrub workflow attempts to locate and ingest available records from external sources before the homeowner contributes anything.

**Scrub sources (in order of source tier):**
1. County permit records and municipal databases (S1 — government/regulatory)
2. Assessor and recorder records (S1)
3. Survey and septic permit records (S1 — where available)
4. Well and utility permit records (S1 — where available)
5. Prior listing attachments and MLS records (S3 — verified business source)
6. Inspection reports from Registry Network participants (S3)
7. Homeowner-uploaded documents at onboarding (S4)

**Scrub acceptance criteria:**
- All scrubbed records carry the source tier of their origin — scrub origin does not elevate source tier
- Scrub results are presented to the homeowner for review before being committed to the Institutional Record
- Homeowner may suppress scrub results from display but may not delete them from the record
- Spatial & Site Documentation is included in the scrub scope — septic permits, survey records, architectural drawings where available (D-042)
- Scrub completeness varies by jurisdiction — the product does not imply comprehensive coverage where coverage is partial

---

## Constitutional Traceability

| Doctrine Belief | Product Expression |
|---|---|
| I — Property is the primary entity | Every surface anchors to the Registry ID, not the participant account |
| II — Records accumulate, never reset | No surface permits record deletion; ownership transition is a Stewardship Transition Event |
| III — We assemble, we do not create | Registry AI extracts and classifies — it never asserts facts without source attribution |
| IV — Source visibility is non-negotiable | Source tier and verification level are displayed in every record view across all surfaces |
| V — Verification increases value | Registry Verify workflow elevates verification levels; all levels are visible |
| VI — Confidence reduces uncertainty | Registry Confidence Score is the primary product expression of uncertainty reduction |
| VII — Trust is the market outcome | Registry Verified and the Registry Network build institutional trust record by record |
| VIII — Build for decades | No surface permits record deletion; Registry ID is permanent; Vault has no expiration |
| IX — Infrastructure, not product | Platform Services (Vault, AI, API, Verify) are infrastructure; surfaces use them |
| X — Every decision is a precedent | Product Principles are explicit and traceable; non-goals are explicitly stated |

---

## Related Documents

- **Upstream:** Docs 00–04 (Constitutional), Docs 07–08 (Participants/Stakeholders), Docs 09–13 (Data Architecture)
- **Downstream:** Doc 15 (System Architecture), Doc 18 (UX Design System), Doc 19 (AI Architecture), Doc 20 (Security & Privacy), Doc 22 (GTM Strategy), Doc 23 (Business Model), Doc 27 (MVP Definition)

---

## Downstream Dependencies

- **Doc 15 (System Architecture)** inherits the Product Principles and capability definitions as system requirements
- **Doc 17 (Registry API Specification)** inherits Registry API capabilities as the specification scope
- **Doc 18 (UX Design System)** inherits Product Principles 1–6 as design constraints
- **Doc 19 (AI Architecture)** inherits Registry AI capabilities as the AI system scope; Spatial Document Interpretation is a required capability
- **Doc 20 (Security & Privacy)** inherits access control requirements from Registry Pro, Registry API, and Registry Verify; Spatial & Site Documentation access rules are a required scope item
- **Doc 22 (GTM Strategy)** inherits product surface and artifact definitions as the go-to-market scope
- **Doc 23 (Business Model)** inherits the complete product definition as the capability set to be monetized
- **Doc 27 (MVP Definition)** inherits this document as the complete product vision and scopes down from it

---

## Decisions Established

- **D-044** (refined): Product element taxonomy by architectural role — two surfaces, four platform services, four institutional artifacts, two trust framework components, three platform network & intelligence elements
- All other decisions in this document inherit from D-001 through D-043. No new architectural decisions were required beyond D-044.
