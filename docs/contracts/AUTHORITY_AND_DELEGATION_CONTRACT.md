# Authority and Delegation Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-AUTHORITY-DELEGATION |
| Version | 0.1.1 |
| Lifecycle state | Draft |
| Scope | CADP authority evaluation, delegation, and decision eligibility |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Foundation reference | CADP-ARCH-FOUNDATION v0.2.0 |
| Canonical artifact reference | CADP-CONTRACT-CANONICAL-ARTIFACT v0.1.0 |
| Metadata registry reference | CADP-CONTRACT-METADATA-REGISTRY v0.1.1 |
| Step 2 baseline | Git revision `a9f41d31875883df48e404f6787cc51b0ce7a941` |

## 1. Purpose and Scope

This contract defines authority as the governed eligibility of an artifact, human role, delegated actor, or recorded decision to affect another artifact or operation. Authority is evaluated for a specific subject, operation, resource, scope, effective interval, and canonical source state.

Authority is not inferred from:

- authorship or repository ownership;
- file path or publication;
- job title alone;
- model capability or confidence;
- tool access, technical ability, or successful execution;
- popularity, repetition, or retrieval rank.

Possession of technical capability does not establish permission. An artifact or actor exercises authority only when the applicable authority source, approval evidence, lifecycle, scope, confidentiality eligibility, and immutable revision are valid.

This contract defines authority and delegation mechanics. It does not create authority classes, company roles, approval records, product policy, or an AI Constitution.

## 2. Authority Hierarchy

This contract consumes the Foundation Architecture hierarchy without changing it.

| Layer | Authority boundary |
| --- | --- |
| Human authority | Attributable decision or approval eligibility held by a human for a defined role, scope, operation, and interval. Human authority is an actor eligibility source, not permission to bypass higher governed constraints. |
| AI Constitution | Future highest normative artifact class for universal AI engineering constraints. No Constitution content or authority is created here. |
| Platform Rules | Approved and Effective universal CADP obligations within constitutional limits. |
| Product Constitution | Approved and Effective product-scoped constraints and overlays; subordinate to the AI Constitution and Platform Rules. |
| ADR | Approved and Effective architectural decision within its recorded scope. |
| Roadmap | Planning direction within its scope; it cannot override a higher normative artifact. |
| Memory | Classified evidence or context whose authority eligibility depends on its artifact class; memory classification alone is not authority. |
| Task | Current requested operation, constrained by every applicable higher layer, delegation, confidentiality gate, and policy decision. |

The hierarchy does not make every layer a normative tier. Artifact precedence remains governed by Foundation Architecture Section 6. Lifecycle state, applicability, scope, approval evidence, effective interval, confidentiality eligibility, and canonical revision determine whether any artifact can exercise authority.

Where a human proposes, reviews, or approves an artifact, the human's authority is evaluated independently from the artifact's authority class. A human decision cannot silently amend a higher-authority source.

## 3. Authority Dimensions

Authority evaluation keeps these dimensions independent:

- authority class;
- subject identity;
- subject role;
- scope;
- requested operation;
- target resource or artifact;
- effective interval;
- delegation source;
- approval evidence;
- constraints and conditions;
- non-delegable boundaries;
- revocation state.

Matching one dimension never supplies another. A valid role without matching scope, operation, interval, or source authority is insufficient. Authority records bind these dimensions to immutable source revisions under the Canonical Artifact Contract.

## 4. Human Authority

Normative human action requires:

- attributable human identity;
- a recognized role or approval eligibility source;
- defined scope and permitted operations;
- a valid effective interval;
- conflict-of-interest evaluation where required;
- separation of proposal, review, and approval where the controlling rule requires it;
- external approval and integrity evidence bound to the exact decision revision.

Anonymous or unattributable normative approval is prohibited. A job title, account ownership, or repository administration permission alone does not establish approval eligibility.

A policy may allow one person to perform more than one function only when the higher authority explicitly permits it and conflict controls are satisfied. Foundational decisions requiring independent human approval cannot be self-approved by their proposer unless a higher approved rule expressly establishes that bounded process.

This contract defines no company-specific job titles or individuals.

## 5. AI Authority Boundary

Within valid scope and delegation, an AI system may:

- draft;
- analyze;
- classify;
- recommend;
- validate;
- execute already-authorized operations.

An AI system may not:

- approve its own authority or delegation;
- create a new authority class;
- expand its own scope, operations, or effective interval;
- waive a non-delegable control;
- approve foundational governance;
- silently convert analysis or a recommendation into a decision;
- treat tool access or successful execution as authorization.

AI-generated evidence identifies the model or evaluator version and remains subject to human approval where required. Delegating execution to AI does not delegate approval unless a separate approved authority source explicitly and validly permits that category, and no non-delegable boundary is implicated.

## 6. Delegation Contract

Delegation is a bounded transfer of decision or execution eligibility from an authorized delegator to a delegate. It does not transfer ownership of the source authority or create an independent authority tier.

Every delegation identifies:

- stable delegation identity;
- delegator and delegate identities;
- canonical authority source and exact revision;
- delegated operations;
- scope and target resource classes;
- constraints and conditions;
- effective interval;
- revocation conditions;
- approval evidence;
- audit and integrity evidence;
- applicable non-delegable boundaries.

The delegate receives only the intersection of the source authority and the recorded delegation. A delegation chain must remain acyclic and reconstructable. Each link is evaluated independently and cannot repair invalid authority earlier in the chain.

Authority for one atomic requested operation must be established by one complete, valid authority and delegation chain. Separate delegations shall not be combined, unioned, composed, or accumulated to authorize one operation unless a future Approved and Effective governing contract explicitly defines and authorizes a delegation-composition mechanism. Absent that governing contract, implicit delegation composition supplies no authority. This contract defines no delegation-composition mechanism.

## 7. Delegation Types

Delegation type classifies the permitted function; it does not establish authority by itself.

| Type | Contract meaning |
| --- | --- |
| Decision delegation | Eligibility to make a defined class of decisions within the source authority and scope. |
| Approval delegation | Eligibility to record an approval only where the controlling authority expressly permits approval delegation. Foundational approval remains non-delegable unless a higher approved contract says otherwise. |
| Review delegation | Eligibility to perform and attest a defined review without implying approval. |
| Execution delegation | Eligibility to perform an already-authorized operation without changing the underlying decision. |
| Administrative delegation | Eligibility to maintain records or operate governance procedures without acquiring their normative authority. |
| Emergency delegation | Short-lived eligibility activated under pre-approved emergency conditions, with explicit expiry, evidence, and post-use review. |

Exact type registry values and role mappings remain deferred.

Every emergency activation must identify:

- stable activation identity;
- governing delegation;
- canonical authority source and exact revision;
- trigger evidence;
- activation scope;
- activation start;
- explicit expiry;
- closure evidence;
- post-use review;
- audit and integrity evidence.

Each emergency activation is independent. A later activation is not a continuation, renewal, or extension of an earlier activation. Repeated activation shall not create continuous authority.

## 8. Delegation Constraints

A delegation must not:

- exceed the delegator's valid authority;
- extend beyond the source authority's scope or effective interval;
- override higher authority;
- bypass confidentiality or source authorization;
- bypass required approval evidence;
- become transferable unless the source explicitly authorizes further delegation;
- become permanent by default;
- survive revocation, expiry, supersession, or invalidation of its source authority;
- authorize self-approval where prohibited;
- convert a review, execution, or administrative function into decision authority.

Further delegation must be explicit, preserve the full lineage, and narrow or preserve—not expand—the original operations, scope, constraints, and interval.

## 9. Revocation and Expiry

Delegation validity ends through any applicable condition:

- explicit revocation by an authorized source;
- automatic expiry at the recorded interval boundary;
- revocation or expiry of source authority;
- termination or invalidation of the delegated role or identity;
- scope or target-resource invalidation;
- supersession of the source artifact where continued validity is not expressly preserved;
- emergency-delegation expiry or failure of its activation conditions.

Revocation and expiry are retained as audit evidence. They do not delete historical uses of the delegation.

When revocation, expiry, identity, scope, or source validity is unresolved, the delegation is Indeterminate and fails closed for protected operations. Cached decisions relying on it must be invalidated or re-evaluated.

When required closure, post-use review, or remediation evidence for an emergency activation is due and missing, the activation is Indeterminate and fails closed until the required evidence exists. Decision evidence from one activation identity shall not be reused for another activation identity without fresh evaluation.

## 10. Conflict Resolution

Authority evaluation addresses:

- overlapping delegations;
- conflicting authority sources;
- explicit higher-authority prohibition;
- stale delegation or source revisions;
- duplicate delegation identities or records;
- conflicting scope resolution;
- delegation-chain cycles.

Conflict handling follows these principles:

1. Apply source authorization and confidentiality eligibility.
2. Resolve canonical identities and immutable revisions.
3. Evaluate the applicable hierarchy and non-delegable boundaries.
4. Intersect each delegation with its source authority, scope, operation, constraints, and interval.
5. Apply explicit higher-authority prohibition over lower permission.
6. Return Indeterminate when conflict or required evidence remains unresolved.

Provider-neutral outcomes remain:

- **Allow**;
- **Deny**;
- **Indeterminate**;
- **Not Applicable**.

Indeterminate fails closed for protected operations. No outcome is inferred from tool behavior or prior success.

## 11. Non-delegable Boundaries

Unless a higher Approved and Effective contract explicitly establishes a safe mechanism, delegation cannot include:

- foundational human approval;
- removal of self-approval prohibitions;
- changes to confidentiality boundaries;
- alteration or deletion of audit history;
- removal of integrity evidence;
- unauthorized expansion of authority;
- creation or release of a Design Freeze;
- registry-bootstrap self-ratification;
- any operation designated non-delegable by an applicable higher rule.

This list is a minimum boundary, not an exhaustive registry of non-delegable operations. A lower authority cannot declare a higher control delegable.

## 12. Audit and Lineage

Authority and delegation history must allow reconstruction of:

- canonical authority source and exact revisions;
- delegator, delegate, roles, and approval eligibility;
- the complete delegation chain;
- delegated scope, operations, constraints, and interval;
- creation, amendment, use, renewal, revocation, and expiry;
- each emergency activation identity, governing delegation, authority source, trigger evidence, scope, start, expiry, closure, post-use review, and required remediation;
- decisions and operations that relied on the delegation;
- conflicts, failures, and escalations;
- affected artifacts;
- rollback or recovery references;
- approval and integrity evidence.

Changing a delegation requires a new reviewed revision. Audit history is retained even when a delegation is expired, revoked, rejected, superseded, or archived.

## 13. Failure Behavior

Authority or delegation evaluation returns Indeterminate when:

- subject or delegator identity is unresolved;
- the authority source is missing, non-canonical, or invalid;
- delegated authority exceeds its source;
- the source or delegation revision is stale;
- scope, operation, resource, or interval is ambiguous;
- approval evidence is missing, invalid, or revision-mismatched;
- the delegation is expired or revoked;
- a delegation chain contains a cycle or unresolved link;
- authority for the requested operation depends on implicit combination, union, composition, or accumulation of separate delegations;
- required emergency-activation closure, post-use review, or remediation evidence is due and missing;
- confidentiality eligibility is unresolved;
- a non-delegable boundary may be implicated;
- revocation state cannot be established.

Indeterminate fails closed for protected operations. A higher approved rule may define safe handling for a specific non-protected case but cannot remove foundational non-delegable controls.

## 14. Deferred Decisions

Later Phase 1 work will define:

- exact authority classes and precedence registry entries;
- exact role and writer-class registries;
- identity-provider integration;
- delegation schema and field-level validation;
- signature and attestation mechanisms;
- approval-workflow implementation;
- emergency activation and revocation tooling.

Deferral creates no authority, role, delegation, or approval record.
