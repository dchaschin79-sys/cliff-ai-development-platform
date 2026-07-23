# Canonical Artifact Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-CANONICAL-ARTIFACT |
| Version | 0.1.0 |
| Lifecycle state | Draft |
| Scope | Governed CADP artifacts and registered product-scope artifacts |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Source baseline reference | CADP-ARCH-FOUNDATION v0.2.0 at Git revision `84052beb7e7d270e2aeba797c039e5f3a0b3ccc4` |

## 1. Purpose and Scope

This contract defines the foundation-level identity, metadata, source, version, lineage, integrity, and validation requirements for governed artifacts in the Cliff AI Development Platform (CADP). It elaborates Foundation Architecture Section 4.1 without defining a final serialization schema or granting approval to any artifact.

A **governed artifact** is a bounded record whose identity, authority, review, applicability, protection, scope, confidentiality, lineage, or retention is managed under CADP. Governed artifacts may include governance documents, Operating Manual procedures, architecture decisions, roadmaps, memory records, context manifests, prompt definitions, registry entries, reviews, validation results, and retained evidence.

The following are excluded unless explicitly registered as governed artifacts:

- application source code and binaries;
- unclassified working files and personal notes;
- disposable caches and raw chat material;
- external documents that CADP only links to;
- derived projections that have no independent retention or audit obligation.

Exclusion from artifact governance does not remove confidentiality, authorization, provenance, or tool-use controls. An excluded object used as input must still be referenced through an authorized manifest when another governed artifact depends on it.

## 2. Canonical Artifact Identity

Every governed artifact must be resolvable without relying on its file name or path alone.

| Identity element | Requirement |
| --- | --- |
| Stable artifact ID | A permanent identifier unique within its registered namespace. It must not be reassigned after deletion, archival, rejection, or supersession. |
| Artifact type | A value from the controlled artifact-type registry that determines the artifact's semantic category, not its authority. |
| Namespace | A registered ownership boundary that prevents collision among global, product, adapter, and other approved extensions. |
| Canonical source location | A resolvable repository and object location for the canonical source. A path is part of the locator but is not the artifact identity. |
| Immutable source revision | The Git revision and source object needed to reconstruct the exact artifact content evaluated by CADP. |
| Artifact version | A semantic version assigned to the artifact's meaning under Section 7. |
| Scope | The registered boundary within which the artifact can apply, such as platform, product, repository, component, or task scope. |
| Ownership | An accountable owner identity or owner class responsible for maintenance, review routing, and lifecycle decisions. |

Renaming or moving a file does not create a new artifact when stable identity and lineage are preserved. Reusing a path does not revive or replace the prior artifact. If the stable ID, namespace, canonical location, or immutable revision cannot be resolved consistently, the identity is unresolved.

## 3. Canonical Artifact Envelope

Every governed artifact requires one canonical metadata envelope. The envelope may be represented separately from the human-readable body, but both must bind to the same stable artifact ID and immutable source revision.

| Category | Foundation requirement |
| --- | --- |
| Artifact identity | Stable, namespace-qualified ID that is never reused. |
| Artifact type | Registered semantic category. |
| Authority class | Registered authority eligibility and precedence class; registration alone does not make an artifact authoritative. |
| Scope | Declared scope identifiers and scope types against which applicability is evaluated. |
| Owner | Accountable maintainer or governance owner. |
| Author | Identity of the person or authorized system that created the evaluated revision. |
| Allowed writer class | Registered class of actors permitted to propose or modify the artifact; it does not grant approval authority. |
| Artifact version | Semantic version of the artifact's meaning. |
| Immutable source revision | Git revision and object reference for the evaluated content. |
| Review workflow state | Draft, Review, Approved, or Archived. |
| Applicability or disposition | Effective, Deprecated, Superseded, Expired, or Rejected where applicable. |
| Protection status | Unprotected or Design Frozen, supported by a separate freeze record when frozen. |
| Effective interval | Start and, when bounded, end of applicability. An absent end must be an explicit unbounded value rather than an omitted decision. |
| Confidentiality class | Registered handling classification used before retrieval, context assembly, provider transmission, and tool execution. |
| Lineage | Predecessor, successor, derivation, amendment, correction, migration, and related-artifact relationships. |
| Approval evidence | External, attributable decision evidence bound to the artifact revision. |
| Rationale | Reason for creating or changing the artifact, or a stable reference to that reason. |
| Affected artifacts | Stable references to artifacts whose meaning, applicability, validation, or operation may change. |
| Supersession references | Explicit links between replaced and replacing versions. |
| Rollback or recovery reference | Governed recovery path or an explicit statement that rollback is not applicable, with rationale. |
| Integrity evidence | Evidence sufficient to detect content or approval tampering under the active integrity policy. |

The envelope defines required metadata categories, not a final JSON, YAML, database, or front-matter schema.

## 4. Independent Dimensions

The following dimensions are independent and must not be inferred from one another:

- artifact type;
- authority class;
- memory class;
- folder location;
- review workflow;
- applicability or disposition;
- protection status;
- scope;
- confidentiality;
- artifact version.

For example, storing a file under `governance/` does not make it Approved, Effective, authoritative, globally scoped, or eligible for a particular session. A prompt definition can be Approved as an artifact while remaining non-normative. An ADR can be authoritative within one scope while its memory classification affects retrieval only.

## 5. Controlled Registries

Canonical envelopes use controlled registries for at least:

| Registry family | Control purpose |
| --- | --- |
| Artifact types | Defines recognized semantic artifact categories and required metadata applicability. |
| Authority classes | Defines eligibility for normative effect and precedence relationships. |
| Confidentiality classes | Defines recognized handling classifications and their policy references. |
| Writer classes | Defines recognized categories of actors that may propose or modify an artifact. |
| Scope types | Defines recognized scope shapes and the identifiers required to resolve them. |

Registry definitions are governed artifacts and follow this contract. Unregistered artifact types and authority classes have no normative effect. An unregistered confidentiality, writer, or scope value cannot be assumed valid; evaluation returns Indeterminate where that value is required for a protected operation.

Registration establishes a recognized value. It does not approve an artifact instance, grant a person permission, or make a scope applicable.

## 6. Canonical Source Rules

### 6.1 Single canonical source

One canonical source is permitted for each artifact identity and effective revision. Git is the initial canonical store and change ledger for governed CADP source artifacts. Git hosting is replaceable and has no authority semantics.

The canonical locator identifies the repository independently of its hosting provider, the object path, and the immutable Git revision. Mirrors, working copies, databases, search or vector indexes, knowledge graphs, generated bundles, and caches are derived representations.

### 6.2 CADP-owned and product-owned sources

CADP-owned artifacts use the registered CADP repository location. Product-owned artifacts use the source declared by the governing product registration mechanism. Product ADRs normally remain canonical in their product repositories; a CADP index or projection does not transfer ownership.

This contract defines the source distinction but does not create a Product Binding or assign any product-specific rule.

### 6.3 Source-of-truth transition

A source-of-truth transition must identify:

- the artifact identities and revisions in scope;
- the old and proposed canonical locations;
- the migration and cutover interval;
- content and lineage equivalence evidence;
- conflict and stale-copy handling;
- an accountable human approver;
- rollback or recovery instructions;
- invalidation or relabeling of prior projections.

The transition becomes valid only through the authority and approval process applicable to the affected artifact. Availability, synchronization, or use of a derived store cannot constitute a transition.

### 6.4 Conflict behavior

Conflicting canonical claims, ambiguous repository identity, mismatched content at the claimed revision, or an unresolved product-owned source produce Indeterminate. Protected operations fail closed until one canonical identity and revision are established through governed resolution.

## 7. Version and Revision Semantics

| Term | Meaning |
| --- | --- |
| Artifact semantic version | Human- and machine-readable version describing the artifact's intended semantic evolution. A Draft may have multiple Git revisions while its candidate semantic version is being prepared. Approved content cannot change under the same semantic version. |
| Immutable Git revision | Content-addressed repository revision used to reconstruct the exact evaluated source. It may include changes to multiple artifacts and does not express an individual artifact's compatibility. |
| Approval revision | Exact pair of artifact identity/version and immutable source revision to which approval evidence applies. Approval does not float to later commits. |
| Effective version | Approved artifact version selected for use in a declared scope and interval. Approval and effectiveness are separate decisions. |
| Superseded version | Earlier version replaced by an identified successor and without authority except where an explicit legacy binding preserves it. |

Semantic versions and Git commit hashes are not interchangeable. A semantic version expresses intended artifact evolution; a Git revision proves which content was evaluated. Consumers must resolve both.

Corrections that change approved meaning require a new semantic version and approval revision. Non-semantic presentation corrections still require a new Git revision and recorded lineage; whether they require a new semantic version is governed by the later versioning policy.

## 8. Lifecycle Integration

This contract consumes the orthogonal state model from Foundation Architecture Section 8.

### 8.1 Review workflow

- **Draft:** mutable proposal with no normative authority.
- **Review:** immutable candidate revision under defined human review.
- **Approved:** revision with attributable human approval.
- **Archived:** inactive record retained as history or evidence.

### 8.2 Applicability or disposition

- **Effective:** applicable within its scope and effective interval.
- **Deprecated:** retained for explicitly identified legacy scope during transition.
- **Superseded:** replaced by an identified successor.
- **Expired:** outside its approved interval.
- **Rejected:** retained review evidence that never gains normative authority.

### 8.3 Protection status

- **Unprotected:** not covered by an active Design Freeze.
- **Design Frozen:** protected by a separately approved freeze record tied to an explicit baseline.

These dimensions are evaluated together but do not imply one another. Draft or Review material cannot be Effective or Design Frozen. Approved material is not automatically Effective. Rejected and Archived material is never normative. Design Frozen requires Approved and Effective source revisions plus a separate valid freeze record. Design Freeze details remain outside this contract.

## 9. Approval Evidence

Minimum approval evidence categories are:

- approver identity;
- approver role or authority class;
- approved scope;
- artifact identity, semantic version, and immutable source revision;
- decision;
- decision timestamp;
- rationale or stable rationale reference;
- integrity evidence.

Approval evidence must be external to the artifact's self-assertion and independently verifiable under the active policy. Text inside a document that claims it is approved is metadata or prose only and is not sufficient approval evidence.

Approval applies only to the recorded artifact revision and scope. A changed source revision requires renewed evaluation even if the semantic version text was not updated.

## 10. Lineage and Change Evidence

Lineage uses stable artifact identities and immutable revisions to preserve historical meaning.

| Relationship | Required meaning |
| --- | --- |
| Predecessor | Prior artifact or version from which the current artifact directly evolved. |
| Successor | Identified later artifact or version intended to follow the current artifact. |
| Supersession | Explicit replacement that records both replacing and replaced versions and their effective boundary. |
| Amendment | Approved change that modifies the governed meaning of an existing artifact through a new version. |
| Correction | Change that fixes an error and states whether semantic meaning changed. |
| Migration | Movement of consumers, content, or canonical source between versions or locations with compatibility evidence. |
| Rollback | Governed return to a previously valid version or state after an unsuccessful or reversed change. |
| Recovery | Restoration of canonical content, evidence, or operability after loss, corruption, or control failure. |

Each governed change records author, owner, change reason, affected artifacts, review and approval evidence where applicable, effective interval, and integrity evidence. History must allow a reviewer to reconstruct what an artifact meant, where it was canonical, who could use it, and which decision applied at any relevant time.

## 11. Integrity Requirements

The artifact model reserves support for:

- Git object identity;
- content checksums;
- signed commits or equivalent attestations;
- approval attestations;
- tamper-evident lineage and event records.

No specific signature algorithm, certificate authority, key-management system, or attestation product is mandated in this Draft. Phase 1 must select integrity mechanisms that remain provider-neutral at the contract boundary and are sufficient for the artifact's authority and confidentiality risk.

## 12. Validation Requirements

Artifact validation covers at least:

- required metadata presence;
- registered artifact type and authority class;
- canonical identity and namespace resolution;
- valid and retrievable source revision;
- valid review, applicability, and protection combination;
- valid effective interval;
- valid approval evidence when approval is claimed or required;
- confidentiality eligibility for the subject, provider, purpose, and operation;
- lineage and supersession integrity;
- duplicate canonical-source detection.

Validation produces provider-neutral outcomes:

- **Allow:** the artifact use is permitted for the evaluated subject, scope, inputs, and interval.
- **Deny:** an applicable requirement prohibits the use.
- **Indeterminate:** CADP cannot establish a safe, authoritative result.
- **Not Applicable:** the evaluated requirement does not govern the declared use.

Every result identifies the evaluated rules and versions, input source revisions, subject and scope, evidence, rationale, timestamp, and evaluator identity/version. Validation of structure alone never creates approval or authority.

## 13. Failure Behavior

The following conditions produce Indeterminate when relevant to the evaluated use:

- missing required metadata;
- unresolved canonical identity or namespace;
- conflicting canonical copies;
- stale, missing, or invalid source revision;
- unregistered or invalid authority class;
- invalid, absent, or revision-mismatched approval evidence;
- incompatible review, applicability, or protection states;
- unauthorized source or actor;
- missing or unresolved confidentiality classification where required;
- broken lineage or ambiguous supersession;
- unknown compatibility during source or version migration.

Indeterminate fails closed for protected operations. An approved higher-authority rule may define a safe outcome for a specific non-protected case, but it cannot bypass non-waivable approval, confidentiality, authority-integrity, audit-integrity, or safety boundaries.

## 14. Conceptual Examples

The labels below illustrate classification only. They do not register artifact types or authority classes, create product rules, or approve any artifact.

| Example | Canonical classification |
| --- | --- |
| Global CADP ADR | Stable CADP identity; global scope; canonical under the CADP global-decision source; ADR artifact type; architecture-decision authority eligibility; normative only if Approved and Effective. |
| Product-owned ADR | Stable product namespace identity; product or component scope; canonical in the registered product repository; CADP occurrence is an index or projection; cannot override higher CADP authority. |
| Current-state record | Stable observation identity; descriptive authority eligibility; observation time, validation source, freshness, expiry, confidentiality, and product or platform scope required. |
| Prompt definition | Stable prompt identity; canonical in the governed prompt source; execution-input classification; Approved status does not make the prompt a normative authority tier. |
| Generated validation evidence | Stable evidence identity when retention is required; derived from an immutable input manifest and evaluator version; canonical retained evidence location; non-normative and linked to the decision it supports. |

## 15. Deferred Decisions

Later Phase 1 work will define:

- exact schema syntax and serialization formats;
- field-level types, cardinality, conditional requirements, and validation rules;
- initial controlled registry values;
- semantic-versioning policy by artifact type;
- signing, attestation, and key-management mechanisms;
- storage, indexing, and evidence-retention implementations;
- source migration and recovery tooling;
- CI/CD and repository-host adapters.

Deferral of these decisions does not relax the identity, metadata-category, authority, confidentiality, lineage, or fail-closed requirements in this contract.
