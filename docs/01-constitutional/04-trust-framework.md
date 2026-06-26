# 04 – The Trust Framework
**Status:** COMPLETE — CONSTITUTIONAL DOCUMENT
**Owner:** Founder
**Last Updated:** 2026-06-24
**Document Version:** 1.0
**Constitutional Role:** Defines the operating model for trust.
**Question Answered:** How is trust created, measured, preserved, verified, and communicated?

---

## Constitutional Role of This Document

This document is the fourth and final constitutional document governing Haus Registry.

```
00 — Founder's Insight          Why did this company need to exist?
01 — Founding Thesis            What are we building and why?  [companion]
02 — The Missing Memory Layer   What is fundamentally broken?
03 — The Haus Registry Doctrine What do we believe because of it?
04 — The Trust Framework        How is trust created and preserved?   ← This document
```

The Doctrine established the belief sequence:

```
Verification increases value
  ↓
Confidence reduces uncertainty
  ↓
Reduced uncertainty creates trust
  ↓
Trust creates more efficient markets
```

This document operationalizes that sequence. It defines precisely what verification
means at each level, how confidence is measured, how trust is communicated, and
how the integrity of the entire model is preserved over time.

Every product feature, data model decision, API contract, UI pattern, and
partnership agreement that touches verification, confidence, or trust must derive
from this document.

---

## 1. The Trust Model: Four Layers

Trust in a property record is not binary. It is the product of four distinct
layers, each building on the one before it.

```
LAYER 1 — SOURCE
Who contributed this record, and are they in a position to know?

LAYER 2 — VERIFICATION
Has the record been confirmed by a source with authority to confirm it?

LAYER 3 — CONFIDENCE
Given the source and verification level, how reliable is this record?

LAYER 4 — TRUST
Given consistent confidence across many records over time, how much
can a participant rely on this Property Registry as a whole?
```

These layers are not interchangeable. A record can have a known source without
being verified. A record can be verified without producing high confidence if the
verifying source has limited authority. Confidence in individual records accumulates
into trust in the Registry — but only when records are consistently verified at
appropriate levels over time.

The Trust Framework governs each of these layers precisely.

---

## 2. Source Hierarchy

Every record in The Registry has a source. Sources are not equal. The Trust
Framework defines a hierarchy of sources based on their position to know, their
accountability for what they contribute, and their susceptibility to motivated
error.

### Source Levels (highest to lowest authority)

**S1 — Government / Municipal Authority**
Records originating from governmental entities with legal authority over the
property. Includes: county assessor records, municipal permit records, building
inspection approvals, environmental assessments, tax records, recorded deeds.
These sources carry the highest inherent authority because they are produced by
entities with legal accountability and public record obligations.

**S2 — Licensed Professional**
Records contributed by licensed professionals acting within their professional
scope. Includes: licensed home inspectors, licensed contractors, licensed
appraisers, licensed engineers, licensed surveyors, registered architects.
Authority derives from professional licensing, liability exposure, and the
professional obligation to report accurately within their scope of expertise.

**S3 — Verified Business Entity**
Records contributed by verified business entities with a documented relationship
to the property. Includes: insurance carriers, manufacturers, warranty providers,
utility companies, property management companies. Authority derives from the
entity's business records and their operational accountability for what they report.

**S4 — Homeowner Submitted**
Records contributed by the current or prior verified owner of the property.
Includes: receipts, invoices, photographs, maintenance logs, appliance records,
warranty cards. Authority is real but limited — the homeowner has direct knowledge
of their property but also has potential incentive to present it favorably.
Homeowner-submitted records are always labeled as such and never elevated to
higher verification levels without corroboration.

**S5 — Registry AI Extracted**
Records extracted or inferred by Registry AI from documents, photographs, or
other submitted materials. Includes: AI-parsed invoice data, AI-classified
photograph content, AI-estimated system ages from contextual records. Registry AI
extraction is never presented as verification — it is a mechanism for structuring
and surfacing knowledge that exists in submitted materials. AI-extracted records
are always labeled as AI-extracted and always carry the confidence characteristics
of the underlying source material, not an independent authority level.

**S6 — Unverified / Unknown**
Records whose source cannot be confirmed or whose contributing party cannot be
identified. These records are retained in the Registry — information that exists
is better than information that doesn't — but are always displayed with explicit
source uncertainty and carry the lowest confidence weight.

---

## 3. Verification Levels

Source tells us who contributed a record. Verification tells us whether that
record has been confirmed by a party with authority to confirm it.

The Trust Framework defines six verification levels. Every record in The Registry
carries exactly one verification level at any given time. Verification levels can
be upgraded as additional confirmation is received. They can also be downgraded
under specific conditions defined in Section 6.

### VL-1: Government Verified
The record originates directly from a government or municipal system, or has been
confirmed by such a system as accurate. This is the highest verification level.
Government-verified records are treated as authoritative within their scope.
Disputes against government-verified records require engagement with the issuing
authority, not with Haus Registry.

*Examples: County permit records pulled directly from municipal databases,
recorded deed transfers, municipal inspection approvals, tax assessment records.*

### VL-2: Professionally Verified
The record has been confirmed by a licensed professional acting within their
professional scope, with their license number on record. The professional's
identity, license status, and license currency are confirmed at the time of
contribution.

*Examples: Inspection findings signed by a licensed inspector, structural
assessments signed by a licensed engineer, appraisal records submitted by a
licensed appraiser, contractor completion records submitted by a licensed contractor.*

### VL-3: Business Verified
The record has been confirmed by a verified business entity with a documented
operational relationship to the property or the event being recorded. The
business entity's identity and relationship are confirmed at the time of
contribution.

*Examples: Insurance claim records submitted by the carrier, manufacturer
warranty registrations submitted by the manufacturer, utility consumption
records submitted by the utility, warranty service records submitted by the
warranty provider.*

### VL-4: Document Verified
The record is supported by a primary source document — an invoice, receipt,
permit copy, photograph, or contract — that has been submitted to the Registry
Vault and reviewed for internal consistency. Document verification does not
confirm that the underlying event occurred, only that the submitted document is
consistent with the claim and shows no indicators of modification.

*Examples: Homeowner-submitted contractor invoice with matching dates, amounts,
and contractor identification; permit copy submitted by homeowner matching
public record; dated photograph consistent with claimed improvement.*

### VL-5: Homeowner Attested
The record has been submitted and attested to by the verified current or prior
owner of the property. No supporting document has been submitted or verified.
The homeowner's identity and ownership at the relevant time are confirmed.
The record reflects their attestation, not independent verification.

*Examples: Homeowner's statement that HVAC was serviced, undocumented recollection
of prior repair, self-reported maintenance activity without invoice.*

### VL-6: Unverified
The record exists in the Registry but has not been attributed to a confirmed
source or supported by any verification process. Unverified records are retained
and displayed but are clearly labeled and carry minimal confidence weight.

*Examples: Records transferred from prior systems without source attribution,
historical entries contributed without documentation, AI-inferred data points
without supporting evidence.*

---

## 4. The Registry Confidence Score

The Registry Confidence Score is the quantitative expression of how much
uncertainty has been eliminated about a specific property through its accumulated
verified records.

It is not a quality rating. It is not a condition assessment. It is not an
estimate of property value. It is a measure of documentation completeness and
verification depth across the property's recorded history.

### What the Score Measures

The Registry Confidence Score reflects three dimensions:

**Coverage** — What proportion of the property's expected history has been
documented? A property with a complete record of every major system replacement,
renovation, and maintenance event scores higher on coverage than one with
sparse documentation. Coverage is assessed against a model of what events are
expected for a property of that age, type, and location.

**Verification Depth** — At what verification levels are the existing records
held? A property whose records are predominantly Government Verified and
Professionally Verified scores higher on verification depth than one whose
records are predominantly Homeowner Attested or Unverified.

**Recency** — How current is the documentation? A property whose records extend
to recent activity scores higher on recency than one whose last documented event
is years or decades old. Recency reflects the likelihood that the current state
of the property is accurately represented.

### Score Calculation Principles

The Registry Confidence Score is calculated as a weighted composite of Coverage,
Verification Depth, and Recency. The precise weighting formula is defined in the
Registry AI Architecture document and may be refined over time as the model
improves. The following principles govern any version of the formula:

**Higher verification levels carry disproportionately higher weight.** A single
Government Verified record contributes more to the score than multiple Homeowner
Attested records. This reflects the actual difference in evidentiary value.

**Coverage gaps are visible, not hidden.** The score reflects the absence of
expected records, not only the presence of existing ones. A property with no
documented roof history for a 30-year-old home does not score as if that history
is simply unknown — it scores as if a meaningful coverage gap exists.

**Recency decay is gradual, not cliff-edged.** Records do not suddenly lose
confidence value at a specific age. Their contribution to the Recency dimension
decreases gradually as time passes without corroborating updates.

**The score is never presented without its components.** Participants who access
the Registry Confidence Score always have access to the Coverage, Verification
Depth, and Recency sub-scores that compose it. A single number without context
is not useful to a participant who needs to understand what they can and cannot
rely on.

### What the Score Is Not

The Registry Confidence Score is not a pass/fail threshold. There is no score
below which a property is disqualified from anything, and no score above which
a property is guaranteed anything.

The score is not a substitute for professional inspection or assessment. A high
score means the property's documented history is well-verified and comprehensive.
It does not mean the property is in good condition.

The score is not static. It changes as records are added, verified, updated, or
as time passes without documentation activity. Participants who access the score
should understand that they are seeing it at a specific point in time.

---

## 5. Registry Verified

Registry Verified is the visible trust signal displayed on specific records within
a Property Registry. It is distinct from the Registry Confidence Score, which
applies to the Registry as a whole.

Registry Verified indicates that a specific record meets the minimum verification
threshold for professional reliance. It is the signal that a buyer, lender,
insurer, or appraiser can treat a specific record as sufficiently verified to
inform a professional decision.

### Registry Verified Criteria

A record is eligible for Registry Verified status when it meets all of the
following conditions:

**1. Verification Level VL-1, VL-2, or VL-3.**
Registry Verified is not available for Homeowner Attested (VL-5) or Unverified
(VL-6) records. Document Verified (VL-4) records may be eligible for Registry
Verified in specific circumstances defined below.

**2. Source identity confirmed.**
The contributing source's identity has been confirmed through the applicable
verification process for their source level. Anonymous or pseudonymous
contributions do not qualify.

**3. Internal consistency confirmed.**
The record's content is internally consistent — dates, amounts, descriptions,
and supporting documents do not contradict one another.

**4. No active dispute.**
The record is not currently subject to a formal dispute through the Registry
Verify workflow. Records under active dispute display a dispute indicator rather
than Registry Verified status.

**5. No superseding record.**
The record has not been superseded by a higher-verification record covering the
same event. When a higher-verification record exists for the same event, the
lower-verification record is retained but its Registry Verified status is
transferred to the higher-verification record.

### Document Verified Records and Registry Verified

A VL-4 Document Verified record may earn Registry Verified status when:
- The submitted document is a primary source document (original invoice, permit
  copy, dated photograph) rather than a summary or secondary reference
- The document has been reviewed and approved through the Registry Verify workflow
- No indicators of modification or inconsistency are present

### What Registry Verified Is Not

Registry Verified is not a guarantee that the described event occurred exactly
as recorded. It is a signal that the record meets the evidentiary standard for
professional reliance — that a reasonable professional could treat it as credible
input to a decision.

Registry Verified is not permanent. It can be revoked under the conditions
defined in Section 6.

Registry Verified is not transferable across records. A contractor's verified
status on one record does not elevate their other records automatically. Each
record is evaluated independently.

---

## 6. Record Integrity: Conflicts, Challenges, and Disputes

A registry that cannot handle conflicting information, challenged records, or
disputed claims is not a registry that can be trusted. The Trust Framework
defines precise protocols for each of these situations.

### Conflicting Records

Conflicting records occur when two or more records in a Property Registry
describe the same event with materially different information — different dates,
different outcomes, different parties.

**Conflict resolution protocol:**

When a conflict is detected — by Registry AI, by a participant, or through the
Registry Verify workflow — both records are flagged with a conflict indicator.
Neither record is deleted. Neither record's verification level is automatically
changed. The conflict is displayed to all participants who access the relevant
section of the Registry.

Resolution follows verification hierarchy. The record with the higher verification
level is treated as the operative record for confidence scoring purposes. The
lower-verification record is retained as a historical entry with its conflict
status noted.

When conflicting records have the same verification level, both are retained and
displayed with equal weight. The conflict indicator remains until one record is
elevated through additional verification or formally resolved through the dispute
process.

### Challenged Records

A challenged record is one that a participant — homeowner, buyer, contractor,
or other verified participant — believes is inaccurate, but where the challenge
has not yet been substantiated with evidence.

**Challenge protocol:**

Any verified participant may submit a challenge to any record in a Property
Registry to which they have legitimate access. The challenge must specify the
claimed inaccuracy and the basis for the claim.

Upon submission, the challenged record is flagged with a challenge indicator
visible to all participants. The record's verification level and Registry Verified
status are not changed at the time of challenge — challenges alone do not reduce
a record's standing.

The contributor of the original record is notified of the challenge and given the
opportunity to respond, provide additional supporting documentation, or acknowledge
the inaccuracy.

If the challenge is substantiated by the contributor's response or by independent
evidence, the record is updated or annotated accordingly.
If the challenge is not substantiated within 30 days, the challenge indicator
is removed and the record's original status is restored.

### Disputed Records

A formal dispute is elevated from a challenge when a participant provides
affirmative contradicting evidence — a document, a professional opinion, or a
government record that directly contradicts the challenged record.

**Dispute protocol:**

Formal disputes are routed through the Registry Verify workflow. A Registry
Verify case is opened, both the original contributor and the disputing party
are notified, and the supporting evidence from both sides is collected.

Registry Verify reviews the evidence and makes a determination:
- If the dispute is resolved in favor of the original record, the dispute is
  closed and the record's status is restored.
- If the dispute is resolved in favor of the disputing party, the original
  record is annotated with the dispute outcome, the contradicting evidence
  is added to the Registry, and the record's verification level is adjusted
  to reflect the resolution.
- If the evidence is genuinely inconclusive, both records are retained with
  a dispute-unresolved indicator and the conflict is noted in the Registry Report.

Haus Registry does not adjudicate factual disputes between parties. We collect
evidence, apply the verification hierarchy, and document the outcome. Participants
who require legal resolution of disputed property facts must pursue that resolution
through appropriate legal channels. The Registry documents the dispute and its
outcome — it does not replace legal process.

### Verification Revocation

A record's verification level or Registry Verified status may be revoked when:

- The contributing source's license or credential is found to have been invalid
  at the time of contribution
- The contributing business entity is found to have misrepresented its
  relationship to the property
- Submitted documents are found to be modified, fabricated, or inconsistent
  with external evidence
- A formal dispute is resolved against the original record
- A government authority issues a correction or retraction of a previously
  contributed government record

Revocation is always documented. The original record is retained with its
revocation status and the reason for revocation noted. Revocation history is
visible to participants with appropriate access. Nothing is deleted.

---

## 7. The Registry Report

The Registry Report is the primary deliverable generated from a Property Registry.
It is the document that buyers review before purchase, that lenders access during
underwriting, that insurers consult at policy issuance, and that sellers share
to substantiate the value of their improvements.

The Registry Report is not a dump of raw records. It is a structured, curated
presentation of the property's documented history, organized to serve the specific
needs of participants making high-stakes decisions.

### What the Registry Report Contains

**Property Identity**
Registry ID, property address, legal description, current Registry Confidence
Score with component breakdown, date of report generation.

**Registry Timeline**
A chronological presentation of all documented events in the property's history,
organized by category (construction, systems, maintenance, improvements, damage,
inspections, ownership). Each event displays its source, verification level,
and Registry Verified status where applicable.

**Systems Summary**
A summary of the current documented state of major property systems — roof,
HVAC, plumbing, electrical, foundation, exterior — including last documented
service or replacement, verification level of that documentation, and estimated
remaining useful life where calculable from documented history.

**Active Warranties**
All active warranty records associated with the property, including product,
coverage dates, transferability status, and manufacturer contact information.

**Open Items**
Permits without documented final inspections, maintenance items overdue based
on documented service history, active challenges or disputes, and coverage gaps
flagged by the Registry AI.

**Verification Summary**
A breakdown of the Registry's records by verification level, showing the
proportion of records at each level and the areas of the property history
with the strongest and weakest verification.

**Document Index**
A reference index of all documents stored in the Registry Vault associated
with this property, accessible to participants with appropriate authorization.

### What the Registry Report Is Not

The Registry Report is not a home inspection. It documents what has been recorded.
It does not assess current physical condition.

The Registry Report is not an appraisal. It does not estimate property value.

The Registry Report is not a legal disclosure document. It is not a substitute
for seller disclosure obligations under applicable law.

The Registry Report is not a warranty. The records it contains are as reliable
as their verification levels indicate — no more, no less.

### Report Access and Sharing

The current homeowner controls access to the Registry Report. They may share it
with specific participants — buyers, agents, lenders — through time-limited,
permissioned access links. They may authorize read access for professional
participants during transactions. They may revoke access at any time outside of
a transaction in progress.

Certain records within the Registry may be designated as property-public by
their contributing source — government records and municipal permits, for example,
are public records and their inclusion in the Registry Report does not require
homeowner authorization to share.

---

## 8. Trust Accumulation Over Time

The Trust Framework is designed around a fundamental insight from the Doctrine:
trust compounds. Each verified record added to a Property Registry does not merely
add to the count of records. It increases the reliability of the Registry as a
whole by providing context, corroboration, and continuity for every other record.

**Corroboration** — When multiple records from different sources and different
verification levels describe the same event consistently, each record becomes more
reliable. A homeowner's attestation that the roof was replaced in 2019 becomes
more reliable when a VL-4 contractor invoice from 2019 exists in the same Registry.
The invoice becomes more reliable when a municipal permit from 2019 also exists.
None of these records alone is as trustworthy as all three together.

**Continuity** — A Registry that documents a property's history continuously over
years and ownership cycles is more trustworthy than one that documents only recent
events, even if the recent events are well-verified. Continuity demonstrates that
the Registry has been actively maintained, that its coverage gaps are genuine
absences rather than failures of documentation, and that the historical record
has been preserved rather than reconstructed.

**Pattern Consistency** — When a property's documented maintenance pattern is
internally consistent — regular HVAC service, timely system replacements, no
unusual gaps — that pattern itself is evidence of reliability. Registries with
internally consistent patterns score higher on confidence and produce more useful
signals for underwriting decisions than those with fragmented or erratic
documentation histories.

Trust accumulation is the mechanism by which The Registry becomes more valuable
over time — not just to the current owner, but to every future participant who
will ever need to understand the property's history.

---

## 9. What This Framework Governs

Every system, feature, and workflow in the Haus Registry platform that touches
verification, confidence, or trust must derive from this document.

**Registry AI** must classify records according to the Source Hierarchy, assign
verification level recommendations, calculate confidence score inputs, detect
conflicts, and flag coverage gaps — all according to the definitions in this
framework.

**Registry Verify** must execute the challenge and dispute protocols defined in
Section 6, manage the verification workflow for VL-1 through VL-3 records, and
govern Registry Verified status issuance and revocation.

**Registry Vault** must store documents in a manner that preserves their integrity
for verification purposes, supports the document review required for VL-4
verification, and maintains the document index referenced in the Registry Report.

**Registry Report** must present verification levels, confidence scores, and
Registry Verified status according to the definitions in this document — never
obscuring the underlying verification reality, never presenting uncertain records
as certain ones.

**Registry API** must expose verification levels, confidence scores, and Registry
Verified status as first-class data elements — not secondary metadata — so that
third-party participants who integrate with The Registry can build their own
decision systems on reliable trust signals.

**Registry Pro** must present verification information to professional participants
in a form that supports their professional decision-making — with full source
attribution, verification level transparency, and access to the underlying
documents that support each record.

---

## Summary

| Component | Definition |
|---|---|
| **Source Hierarchy** | Six levels from Government Authority (S1) to Unverified/Unknown (S6) |
| **Verification Levels** | Six levels from Government Verified (VL-1) to Unverified (VL-6) |
| **Registry Confidence Score** | Weighted composite of Coverage, Verification Depth, and Recency |
| **Registry Verified** | Badge indicating a record meets the threshold for professional reliance |
| **Conflict Protocol** | Both records retained, flagged, higher verification level operative |
| **Challenge Protocol** | Flagged, contributor notified, resolved within 30 days |
| **Dispute Protocol** | Registry Verify case opened, evidence collected, outcome documented |
| **Revocation** | Documented, original record retained with revocation status, nothing deleted |
| **Registry Report** | Structured presentation of property history for high-stakes decisions |
| **Trust Accumulation** | Corroboration + Continuity + Pattern Consistency compound over time |

---

*This is a constitutional document.*
*It defines the operating model by which Haus Registry creates, measures,*
*preserves, verifies, and communicates trust.*
*Every product feature, data model, API contract, and UI pattern that touches*
*verification, confidence, or trust must derive from this document.*
*It was written to be true in 2026 and still true in 2076.*
