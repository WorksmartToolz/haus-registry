# Living Repository Standard
**Project:** Haus Registry
**Document Type:** Governance Standard
**Status:** Accepted
**Purpose:** Define how sessions inherit, extend, and close against the repository.

---

## Living Repository Approach

The GitHub repository — not any conversation — is the single source of truth.

Every session begins by inheriting the repository.
Every session ends by strengthening the repository.

The objective is to ensure that knowledge, decisions, governance, and architecture become progressively more authoritative over time rather than being rediscovered in future conversations.

---

## Session Lifecycle

### 1. Repository First

Before drafting begins, review the repository in the following order:

1. Governance
2. Constitution
3. Decisions
4. Session Log
5. Current Document
6. Related Dependencies

This order is mandatory. Governance defines how we work. The Constitution defines what we believe. Everything else inherits from those two layers.

### 2. Governance Review (Required)

Every session must begin by reviewing and inheriting:

- Repository Authoring Standard
- DECISIONS.md
- Glossary (when available)
- Repository Map (when available)

These documents are considered authoritative. Do not reopen settled architectural or constitutional decisions unless explicitly instructed. Before asking a design question, first determine whether the answer already follows from the Authoring Standard, the Constitution, or an existing decision.

### 3. Constitutional Inheritance

Treat constitutional documents as settled architecture. Implementation documents inherit constitutional principles. They do not rediscover or renegotiate them.

### 4. Living Repository

The repository contains both project documents and governance documents. Project documents define the platform. Governance documents define how future documents are created. Both evolve together.

---

## Repository Meta Documents

The repository should always maintain:

- Repository Authoring Standard
- Living Repository Standard
- DECISIONS.md
- SESSION_LOG.md
- Glossary
- Repository Map

These documents are mandatory dependencies for future sessions.

---

## End-of-Session Requirements

Every session must conclude by:

1. Updating the document(s) completed.
2. Updating DECISIONS.md with any newly established architectural decisions.
3. Updating SESSION_LOG.md with:
   - documents completed,
   - architectural decisions,
   - unresolved questions,
   - recommended starting point for the next session.
4. Committing all repository changes.
5. Pushing those commits to GitHub.
6. Generating a Session Brief for the next AI session.

---

## Session Brief

The Session Brief should remain under approximately 200 words and include:

- Current phase
- Documents completed
- Governance changes
- New architectural decisions
- Active work
- Open questions
- Exact next action

The Session Brief is not the source of truth. It is only a fast-loading summary of the repository.

---

## Guiding Principle

Every new session should begin by inheriting the repository — not by rediscovering it.
Every completed session should leave the repository stronger than it found it.
The repository — not the conversation — is the enduring memory of Haus Registry.

---

*This document governs the session lifecycle for the Haus Registry repository.*
*It exists to ensure continuity across sessions, contributors, and implementation phases.*
