# Governance Lifecycle Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-GOVERNANCE-LIFECYCLE |
| Version | 0.1.1 |
| Lifecycle state | Draft |
| Scope | Governance lifecycle dimensions for governed CADP artifacts |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Foundation reference | CADP-ARCH-FOUNDATION v0.2.0 |
| Canonical artifact reference | CADP-CONTRACT-CANONICAL-ARTIFACT v0.1.0 |
| Metadata registry reference | CADP-CONTRACT-METADATA-REGISTRY v0.1.1 |
| Approval record reference | CADP-CONTRACT-APPROVAL-RECORD v0.1.1 Draft |
| Authority and delegation reference | CADP-CONTRACT-AUTHORITY-DELEGATION v0.1.1 |
| Policy decision reference | CADP-CONTRACT-POLICY-DECISION v0.1.1 |
| Step 3 baseline | Git revision `0cb09c68f26e97e4215fcdcc616c2c79ae007c62` |

## 1. Purpose and Scope

This contract defines the governance lifecycle dimensions that determine how a governed artifact moves from existence and review into approval, operational effectiveness, scoped adoption, transition, archival, and retirement.

The lifecycle is governance semantics. It is not an implementation workflow, deployment pipeline, runtime state machine, database model, issue status, branch strategy, or CI/CD process.

This contract creates no lifecycle event, approval, effectiveness decision, adoption, Product Binding, Design Freeze record, registry value, schema, workflow engine, or implementation state.

## 2. Orthogonal Lifecycle Model

Governed artifact state is a composite of independent dimensions. No single label can represent the complete state of an artifact.

| Dimension | Question answered | Principal governance states or evidence |
| --- | --- | --- |
| Existence and identity | Does the governed artifact and exact revision exist canonically? | Stable artifact identity, semantic version, immutable source revision. |
| Review workflow | Where is the revision in governed review? | Draft, Review, Approved, Rejected review disposition, Archived. |
| Approval evidence | Is there a valid attributable approval for the exact revision and scope? | Valid, absent, revoked, superseded, or Indeterminate approval evidence under the Approval Record Contract. |
| Operational effectiveness | May the approved revision exercise normative effect for a scope and interval? | Effective, Expired, or not Effective, with exact scope and temporal boundary. |
| Adoption | Has an eligible governed scope adopted the Effective revision? | Adopted or not Adopted for an exact scope, version, and interval. |
| Change disposition | How is the revision treated relative to active consideration and successors? | Deprecated, Withdrawn, Superseded, or no such disposition. |
| Archival | Is the record inactive and retained as history or evidence? | Archived or active record. |
| Retirement | Has current and future governed use ended for the declared scope? | Retired or not Retired. |
| Protection | Is an Approved and Effective baseline protected by a separate freeze decision? | Unprotected or Design Frozen under the Design Freeze Contract. |

The dimensions are orthogonal, but not every theoretical combination is valid. Cross-dimension constraints are explicit and evaluated without collapsing the dimensions.

This contract consumes the Canonical Artifact Contract meanings for `Review`, `Rejected`, and `Expired`. `Review` is review-workflow evidence for an immutable candidate. `Rejected` is the retained review disposition of a candidate that did not gain approval or normative authority; it is evaluated with the review evidence and cannot be inferred from missing approval. `Expired` is an applicability result after the controlling effective interval ends. None of these states supplies approval, adoption, protection, implementation, deployment, or authority.

This contract defines or consumes the meanings of the named governance states. It does not create serialized registry values. Exact controlled values and mappings require later registration under the Metadata Registry Contract before normative machine use.

## 3. Prohibition on a Single Lifecycle Status

CADP must not collapse lifecycle into one status field, linear enum, maturity number, folder, branch name, label, or implementation state.

A single status such as `active`, `approved`, `done`, `live`, or `archived` cannot safely answer all of these questions:

- Does the artifact exist canonically?
- Was the exact revision approved by an eligible human?
- Is it Effective for this scope and time?
- Has this product or governed scope Adopted it?
- Has it been Deprecated, Withdrawn, or Superseded?
- Is it Archived?
- Is it Retired?
- Is it protected by a Design Freeze?

An implementation may present a derived summary only when the underlying dimensions remain independently stored, resolvable, auditable, and authoritative. A summary cannot replace the canonical state evidence.

## 4. State Semantics

### 4.1 Draft

`Draft` is a proposed governed artifact revision that may change and has no normative authority. Creation, authorship, commit, publication, or review activity does not move a Draft to Approved.

A Draft cannot be Effective, currently Adopted as normative policy, or Design Frozen. It may later be Withdrawn, Superseded by another proposal, or Archived as retained history without ever being Approved.

### 4.2 Review, Rejected, and Approved

`Review` identifies an immutable candidate revision under defined human review. Review activity, elapsed time, technical validation, or reviewer participation does not create approval or normative authority.

`Rejected` consumes the Canonical Artifact Contract meaning: retained review evidence for a candidate that did not gain normative authority. Rejection is not withdrawal of an Effective artifact, revocation of historical approval, supersession, archival, or retirement. A rejection requires attributable review evidence and cannot be inferred from absent or incomplete approval evidence.

`Approved` identifies an immutable artifact revision with valid, external, attributable human approval evidence bound to its exact identity, semantic version, source revision, scope, and decision.

Approved does not imply Effective, Adopted, implemented, deployed, Design Frozen, or currently preferred. Approval history remains even after revocation, supersession, archival, or retirement; current approval validity is evaluated separately.

### 4.3 Effective

`Effective` means an independently Approved artifact revision is operationally applicable for a declared scope, purpose, and effective interval under an eligible effectiveness decision.

Approval is required but is not sufficient for effectiveness. Effectiveness requires its own attributable evidence and boundary. An Effective artifact may not yet be Adopted by a particular product or governed scope.

`Expired` consumes the Canonical Artifact Contract meaning: the revision is outside its approved applicability interval for the evaluated scope and time. Expiry acts prospectively at the recorded boundary, preserves the prior Effective interval, and does not revoke approval, withdraw or supersede the artifact, retire history, or authorize an operation.

Draft, Review, Rejected, or Archived material cannot be Effective. Expired or Retired material cannot exercise current normative effect. Deprecated or Superseded material may remain Effective only within an explicit transition interval or preserved legacy binding.

Effective is applicability evidence only. It does not by itself produce a Policy Decision `Allow`, subject authority, delegation, confidentiality eligibility, variance validity, execution authorization, implementation authorization, deployment, or runtime state.

### 4.4 Adopted

`Adopted` means an eligible governed scope has explicitly bound itself to a specific Effective artifact version or governed baseline for a declared interval and scope.

Repository presence, copied files, package installation, retrieval, synchronization, implementation similarity, prior use, or successful validation does not establish adoption. Product adoption requires a future valid Product Binding under Foundation Architecture Section 7; this contract creates no Product Binding or adoption record.

An artifact may be Effective at the platform level but not Adopted by a particular product. Adoption does not expand the artifact's authority, scope, effectiveness interval, or permitted variance.

Adoption is governance evidence only. It is distinct from implementation and deployment and does not by itself create operation-specific authorization or a Policy Decision `Allow`.

### 4.5 Deprecated

`Deprecated` marks a revision as disfavored for new use and subject to transition toward an identified replacement or end state. Deprecation records rationale, affected consumers, transition interval, legacy scope, replacement when one exists, and migration and recovery references.

Deprecated does not automatically mean non-Effective, Superseded, Archived, or Retired. A Deprecated revision may remain Effective for an explicitly preserved legacy scope during transition. New adoption is prohibited unless a higher Approved and Effective rule expressly permits a bounded legacy case.

### 4.6 Withdrawn

`Withdrawn` records that an eligible governance actor has removed a revision from active consideration or future use within a declared scope. Withdrawal retains the artifact and all prior review, approval, and use evidence.

Withdrawal is not deletion, rejection, revocation of historical approval, supersession, archival, or retirement. If the withdrawn revision was Effective or Adopted, separate effectiveness and adoption decisions must define the prospective operational boundary. Until conflicting current-state evidence is resolved, new protected use is `Indeterminate` and fails closed.

### 4.7 Superseded

`Superseded` identifies an explicit predecessor-successor relationship between exact artifact versions or revisions. It records the successor, scope, rationale, compatibility, transition interval, effective boundary, affected consumers, and rollback or recovery references.

Superseded does not erase the predecessor. A Superseded revision may remain Effective during a bounded transition or within an explicit legacy binding. Supersession does not automatically approve, make Effective, or cause adoption of the successor.

### 4.8 Archived

`Archived` identifies an inactive record retained as history or evidence. Archival preserves canonical identity, content, lineage, decisions, scope, timestamps, confidentiality, and integrity evidence.

Archived is not deletion and does not imply Retired. A rejected proposal, withdrawn Draft, expired record, or completed evidence artifact may be Archived without ever having been operationally Retired.

Under the Foundation Architecture, Archived material has no current normative authority and therefore cannot remain Effective. Moving an Effective artifact to Archived requires a separately resolved effectiveness boundary.

### 4.9 Retired

`Retired` records that current and future governed operational use has ended for the declared scope at an explicit boundary. Retirement requires affected-scope analysis, transition and recovery references, disposition of active adoptions, and preserved lineage.

Retired does not delete the artifact, approval record, prior effectiveness interval, adoption evidence, or audit history. A Retired artifact may remain unarchived while transition evidence or audit obligations remain active. It may later be Archived without changing the historical retirement boundary.

Retired material is not Effective for current operations and cannot receive new adoption. Historical uses remain reconstructable.

## 5. Required State Combinations

The lifecycle explicitly supports these combinations:

| Combination | Required meaning |
| --- | --- |
| Approved but not Effective | Human approval exists for the exact revision, but no operational applicability decision has activated it. |
| Effective but not yet Adopted | The revision is operationally applicable at its governing scope, but the evaluated product or other adopting scope has not bound itself to it. |
| Superseded but still Effective | A successor is identified, while the predecessor remains applicable during an explicit transition interval or legacy binding. |
| Archived without being Retired | An inactive proposal or evidence record is retained even though it never entered operational use or retirement. |
| Retired without deleting history | Operational use has ended, while the artifact and all lifecycle, approval, adoption, and lineage evidence remain retained. |

Orthogonality does not authorize impossible combinations. Draft or Archived material cannot be Effective. Retired material cannot be currently Effective. A Design Freeze cannot be active on a revision that is not independently Approved and Effective.

## 6. Transition Evidence

Every lifecycle transition identifies:

- stable transition identity;
- artifact identity, semantic version, and exact source revision;
- source dimension and state evidence;
- target dimension and intended state;
- transition authority identity and eligibility;
- scope;
- decision timestamp and effective boundary;
- rationale or stable rationale reference;
- prerequisites and conditions;
- affected artifacts, approvals, adoptions, decisions, freezes, and consumers;
- predecessor, successor, deprecation, withdrawal, supersession, archival, or retirement references as applicable;
- transition, migration, rollback, or recovery references;
- confidentiality and integrity evidence.

A transition changes only the declared dimension. It cannot silently change approval, effectiveness, adoption, protection, scope, authority, or another disposition.

Where a transition records more than one disposition or relationship, the evidence must identify each asserted disposition, its independent authority, scope, interval, effect, and compatibility with every concurrent disposition. Missing compatibility or conflicting effect evidence is `Indeterminate` and fails closed for protected operations.

The transition evidence categories are conceptual contract requirements, not a schema or workflow implementation.

## 7. Approval, Effectiveness, and Adoption Sequence

The safe dependency order is:

1. Resolve canonical artifact identity, semantic version, and immutable source revision.
2. Complete governed review for an immutable candidate revision.
3. Resolve valid human approval evidence for the exact revision and scope.
4. Record a separate effectiveness decision for a scope and interval.
5. Record separate adoption evidence for each adopting scope where adoption is required.

These are semantic dependencies, not a workflow engine. A later step cannot backfill a missing earlier decision. Adoption cannot create effectiveness; effectiveness cannot create approval; approval cannot be inferred from document existence.

Effective and Adopted are independently evaluated inputs to an operation-specific Policy Decision. Neither state creates `Allow`, subject authority, delegation, variance validity, confidentiality eligibility, execution authorization, implementation authorization, deployment, or runtime state. Every requested operation requires a current Policy Decision over all applicable identity, authority, delegation, lifecycle, protection, variance, confidentiality, scope, interval, and freshness evidence.

## 8. Deprecation, Withdrawal, Supersession, Archival, and Retirement

Each disposition answers a different governance question:

- Deprecation discourages new use and governs transition while legacy use may continue.
- Withdrawal removes a revision from active consideration or future use without erasing its history.
- Supersession identifies a successor and transition relationship.
- Archival retains an inactive record as history or evidence.
- Retirement ends current and future operational use for a declared scope while retaining history.

None may be used as a synonym for another. A transition involving more than one dimension requires explicit evidence for each affected dimension and their effective boundaries.

Change disposition is a set of independently evidenced current or historical relationships, not one linear status:

- Deprecation and Supersession may coexist when an identified successor and an explicit transition or legacy interval make their effects compatible.
- Supersession requires an identified successor. It does not by itself Withdraw the predecessor, revoke its approval, end its effectiveness or adoption, Archive it, or Retire it.
- Withdrawal is an independent prospective prohibition on active consideration or future use for its declared scope. It may coexist historically with deprecation or supersession, but current withdrawal controls new use within an overlapping scope and interval.
- Deprecation does not negate Withdrawal. A legacy transition under deprecation or supersession cannot preserve new or current use in scope where an applicable Withdrawal has ended that use.
- A disposition applying in one scope or interval does not automatically control another.

Concurrent dispositions are compatible only when their identities, scopes, intervals, effects, authorities, and transition evidence can all be satisfied without contradiction. Incompatible or unresolved claims for the same artifact revision, scope, and interval are `Indeterminate` and fail closed for protected operations.

## 9. Temporal and Scope Semantics

Lifecycle state is evaluated for an exact artifact revision, scope, and point in time. Platform, product, repository, component, task, legacy, and confidentiality scopes do not inherit one another automatically.

Historical and current state are distinct. A state transition acts prospectively from its recorded boundary and does not rewrite a prior interval. Backdating cannot authorize an operation that lacked valid authority at the time it occurred.

An artifact may have different adoption or legacy treatment in non-overlapping scopes. Conflicting claims for the same dimension, scope, and interval are `Indeterminate` until governed resolution.

## 10. Authority and Human Decision Boundary

Every approval, effectiveness, adoption, deprecation, withdrawal, supersession, archival, retirement, and Design Freeze decision requires authority appropriate to its operation, scope, and interval.

Authority is evaluated under the Authority and Delegation Contract. Technical ability, repository ownership, authorship, automation, AI output, or prior successful use does not create transition authority.

AI may prepare transition evidence, compare states, identify conflicts, and recommend action. AI cannot record human approval, make a fundamental lifecycle decision, expand authority, create adoption, or impose or lift a Design Freeze.

An artifact's Effective or Adopted state does not create transition authority, subject authority, delegation, or permission to perform an operation. Authority and the operation-specific Policy Decision remain independently required.

## 11. Fail-Closed Behavior

Lifecycle evaluation returns `Indeterminate` when required identity, revision, authority, approval, scope, interval, transition, adoption, disposition, protection, confidentiality, lineage, or integrity evidence is missing, stale, conflicting, or unverifiable.

`Indeterminate` fails closed for protected operations. In particular:

- missing approval cannot become Effective;
- missing effectiveness cannot become Adopted;
- unresolved supersession cannot select a successor automatically;
- unresolved disposition compatibility cannot select, preserve, or end current use automatically;
- unresolved withdrawal or retirement boundaries cannot authorize new use;
- missing legacy binding cannot preserve Deprecated or Superseded authority;
- unresolved archival conflict cannot preserve current normative effect;
- unresolved Design Freeze state cannot authorize changes to protected scope;
- Effective or Adopted evidence alone cannot produce `Allow` or authorize execution, implementation, or deployment.

File order, timestamps alone, Git operations, tool success, deployment state, repeated use, or AI confidence cannot resolve an Indeterminate governance state.

## 12. Immutable Lifecycle History

Lifecycle history preserves:

- every canonical artifact revision;
- review and approval evidence;
- effectiveness scopes and intervals;
- adoption scopes and intervals;
- deprecation, withdrawal, supersession, archival, and retirement decisions;
- protection and freeze decisions;
- transition authority and rationale;
- affected artifacts and consumers;
- conflicts, reevaluations, rollbacks, recovery, and closure;
- confidentiality and integrity evidence.

Current-state indexes and summaries are derived. Removing or regenerating them cannot delete canonical event history or change prior state meaning.

## 13. Provider Neutrality

Lifecycle semantics do not depend on a model provider, Git host, database, programming language, policy engine, workflow product, ticket system, deployment platform, CI/CD system, or user-interface status.

Provider-specific adapters may project the dimensions but cannot redefine, merge, or infer them. When a provider cannot represent the required dimensions independently, its projection is incomplete and cannot serve as the canonical lifecycle source.

## 14. Deferred Decisions

Later work may define exact registered lifecycle values, transition-record serialization, state compatibility tables, Product Binding adoption evidence, retention intervals, workflow routing, notifications, signing, and validation implementation.

Deferral creates no registry value, transition, approval, effectiveness decision, adoption, Product Binding, implementation state, or Design Freeze.
