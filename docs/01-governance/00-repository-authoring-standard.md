# Repository Authoring Standard
## Constitutional Inheritance Rule

**Project:** Haus Registry  
**Document Type:** Governance Standard  
**Status:** Proposed for Repository Governance  
**Purpose:** Establish how future documents inherit, apply, and preserve prior decisions.

---

## 1. Purpose

The purpose of this repository is to progressively define the philosophy, governance, architecture, product, and implementation of Haus Registry.

As the repository matures, earlier documents become authoritative dependencies for later documents.

Later documents inherit these decisions.

They do not revisit, reinterpret, or renegotiate them unless an explicit architectural revision has been approved.

This standard exists to prevent repeated rediscovery of settled principles and to ensure that each document advances the repository rather than reopening decisions already made.

---

## 2. Constitutional Authority

Documents designated as Constitutional Documents establish enduring principles of the platform.

These documents are considered authoritative once accepted.

Later documents must treat constitutional principles as architectural constraints, not open discussion topics.

Implementation documents must faithfully inherit constitutional principles.

They should not redefine:

- the purpose of Haus Registry,
- the role of the Institutional Record,
- the property as the primary entity,
- stewardship language,
- Registry identity principles,
- verification philosophy,
- confidence philosophy,
- or any other concept already settled by the Constitution.

---

## 3. Single Responsibility

Every document owns one layer of understanding.

No document should duplicate, replace, or redefine another document's purpose.

If a question has already been answered by an earlier document, later documents should inherit that answer rather than reopen it.

Each document should clearly state:

- what it inherits,
- what it defines,
- what it defers,
- and what it must not redefine.

---

## 4. Inheritance Before Discovery

Before introducing new concepts or asking new architectural questions, every author must first determine whether the answer has already been established elsewhere in the repository.

Implementation documents inherit philosophy.

They do not rediscover it.

When a question appears to have multiple plausible answers, first determine whether the answer already follows logically from established constitutional principles before introducing a new design decision.

Only if the existing principles do not resolve the issue should a new decision be proposed.

---

## 5. Progressive Specificity

The repository progresses from philosophy to implementation.

Each document should become more specific than the one before it.

Earlier documents define principles.

Later documents define implementation.

Implementation details should not be pushed upward into constitutional documents.

Constitutional principles should not be renegotiated inside implementation documents.

The expected progression is:

```text
Constitution
    ↓
Governance
    ↓
Architecture
    ↓
Product
    ↓
Implementation
```

---

## 6. Deferred Detail

A document should define only the level of detail appropriate to its responsibility.

For example:

- Doc 09 establishes the nature of the Institutional Record.
- Doc 10 defines the Event Data Model.
- Doc 11 defines the Verification Model.
- Doc 12 specifies schemas, enumerations, validation rules, and implementation-level details.
- Doc 13 defines the Registry ID.

If a question belongs to a later document, note the dependency and defer it rather than resolving it early.

Deferral is not avoidance.

Deferral preserves document boundaries.

---

## 7. Canonical Vocabulary

Canonical terminology established by earlier documents should be reused consistently.

Do not introduce synonyms, alternate terms, or replacement language unless an explicit architectural revision is approved.

Current canonical terms include, but are not limited to:

- Property
- Institutional Record
- Registry ID
- Registry Event
- Primary Steward
- Stewardship
- The Registry
- Registry Confidence
- Verification
- Trust
- Persistent Institutional Record
- Property lifecycle

Consistent language is part of the architecture.

Terminology drift creates conceptual drift.

---

## 8. Open Questions

A question should only be raised if all three conditions are true:

1. The issue has not already been answered elsewhere.
2. The current document owns the decision.
3. The decision cannot be logically inferred from earlier documents.

If any of these conditions are false, the question should not be reopened.

Instead, the author should inherit the existing principle, apply it, and continue.

---

## 9. Architectural Revisions

Constitutional decisions may only be revised through an explicit architectural revision.

Routine drafting should assume constitutional principles are settled.

If a contradiction is discovered, the author should not silently reinterpret the prior decision.

Instead, they should:

1. identify the contradiction,
2. cite the affected documents,
3. propose an explicit revision,
4. log the decision if approved,
5. update downstream documents accordingly.

---

## 10. Document Status

Every document should carry a status that reflects its authority.

Recommended statuses:

- **Settled** — authoritative and should not be reopened except by explicit revision.
- **Accepted** — approved for use, but may receive limited refinement.
- **Draft** — actively being developed.
- **Under Review** — awaiting review or approval.
- **Experimental** — exploratory and not authoritative.
- **Deprecated** — superseded by another document.

Future AI sessions and human contributors should treat document status as part of the governance model.

---

## 11. Required Opening for Future Documents

Every major document should begin with a short inheritance section answering:

### Inherits From

Which prior documents does this document depend on?

### Settled Principles

Which principles are already considered authoritative?

### This Document Defines

What is this document responsible for defining?

### This Document Does Not Define

What topics are explicitly out of scope or deferred?

This prevents later documents from reopening settled questions.

---

## 12. Required Closing for Future Documents

Where appropriate, major documents should end with:

### Constitutional Traceability

How does this document map back to constitutional principles?

### Related Documents

Which prior and future documents does this document depend on or inform?

### Downstream Dependencies

Which future documents, product areas, data models, APIs, or workflows will rely on this document?

### Decisions Established

What decisions should future documents treat as settled?

---

## 13. Authoring Test

Before asking a design question, verify:

1. Has this already been decided?
2. Does this document own the decision?
3. Is this the correct level of abstraction?
4. Does answering this create duplication elsewhere?
5. Does the answer already follow from constitutional principles?

If the answer indicates the question has already been resolved, the document should inherit the existing decision rather than reopening it.

---

## 14. Practical Example

If Doc 09 establishes that the Institutional Record represents a property's lifecycle, Doc 10 should not ask whether Registry Events include both occurrences and observations.

That follows from the established principle.

Doc 10 should implement it.

Similarly, if Doc 10 defines that Registry Events include date confidence, Doc 10 does not need to enumerate every allowable date precision value if Doc 12 owns schema enumerations and validation rules.

Doc 10 should establish the field.

Doc 12 should specify the allowed values.

---

## 15. Governing Rule

From this point forward, the objective is implementation fidelity, not philosophical rediscovery.

The Constitution is a dependency.

Governance is the operating standard.

Architecture implements the inherited principles.

Product implements the architecture.

Code implements the product.

Each layer must respect the layer above it.

---

*This document governs how the Haus Registry repository is authored, extended, and maintained.*  
*It exists to preserve conceptual continuity across documents, sessions, contributors, and implementation phases.*
