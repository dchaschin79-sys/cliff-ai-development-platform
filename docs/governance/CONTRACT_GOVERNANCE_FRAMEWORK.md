# CADP Contract Governance Framework

## 1. Document Control

| Field | Value |
| --- | --- |
| Document ID | `CADP-GOV-CONTRACT-FRAMEWORK` |
| Document type | Governance Methodology |
| Version | 0.2.0 |
| Previous version | 0.1.0 |
| Revision classification | Minor Governance Maintenance Revision |
| Revision purpose | Clarify AI-assisted Acceptance Record preparation while preserving exclusive human acceptance authority |
| Lifecycle state | Draft |
| Date | 2026-07-24 |
| Scope | Platform-wide |
| Applicability | Every future canonical CADP contract |
| Repository | `dchaschin79-sys/cliff-ai-development-platform` |
| Source baseline | `1e1e34ac7f7b53ea452536b3d303985df7bf286d` |
| Approval requirement | Requires explicit eligible human acceptance |
| Effectiveness | Not created |
| Contract created by this document | None |
| Architecture effect | None |
| Implementation authority | None |

This framework defines the platform-wide methodology for governing canonical contracts in the Cliff AI Development Platform.

It is not an architecture document, Architecture Decision Proposal, contract, Contract Decomposition Plan, Contract Review, approval record, or implementation specification. It does not define a specific contract or modify an existing contract.

As a Draft, this document has no current normative effect. When separately Accepted and made Effective through eligible governance, it governs future canonical CADP contracts. A Git commit or publication does not create that acceptance or effectiveness.

## 2. Purpose

Canonical contracts exist to assign one stable owner to provider-neutral meanings that must be interpreted consistently across CADP products, governance activities, evidence, and replaceable implementations.

This framework governs:

- the definition and purpose of a Canonical Contract;
- contract ownership;
- contract lifecycle;
- status and disposition;
- authoring, review, verification, Acceptance Record preparation, acceptance, and effectiveness;
- versioning and compatibility;
- revision and change classification;
- breaking-change control;
- dependency direction;
- supersession;
- archival; and
- traceability.

This framework applies platform-wide. A domain-specific architecture, acceptance record, or Contract Decomposition Plan may narrow the scope of a contract candidate but may not bypass this methodology once the framework is Accepted and Effective.

## 3. Authority and Relationship to Existing Governance

This framework is subordinate to the [Foundation Architecture](../FOUNDATION_ARCHITECTURE.md) and to every higher, Accepted, Effective, and applicable CADP governance source.

It consumes without redefining:

- canonical artifact identity and revision ownership;
- authority and delegation;
- human approval evidence;
- governance lifecycle;
- applicability;
- Policy Decision;
- Design Freeze;
- confidentiality and source authorization; and
- immutable history.

Where this framework uses `Accepted`, it identifies the contract-specific acceptance gate supported by valid attributable human approval evidence. It is a specialization of the platform’s generic approved review state, not a second approval system or a new authority tier.

The framework does not grant Contract Authority, Architecture Authority, reviewer eligibility, verifier eligibility, or effectiveness authority. Those roles require independently valid authority for the exact operation, artifact, revision, scope, and interval.

## 4. Canonical Contract

### 4.1 Definition

A **Canonical Contract** is the single governed source for a bounded set of provider-neutral semantic obligations, responsibilities, invariants, relationships, and interpretation rules assigned to one contract identity and one primary responsibility.

A Canonical Contract:

- has a stable identity;
- has one canonical repository source;
- binds every governed version to an immutable source revision;
- has one canonical semantic owner;
- has one primary responsibility;
- declares its scope and exclusions;
- identifies its architecture and governance basis;
- identifies upstream dependencies and downstream consumers;
- uses explicit versioning;
- preserves revision and supersession lineage;
- remains implementation-independent; and
- acquires normative effect only through separate valid acceptance and effectiveness decisions.

### 4.2 Why Contracts Exist

Contracts exist to:

- make responsibility boundaries explicit;
- prevent different products or implementations from inventing incompatible meanings;
- make interpretation deterministic;
- preserve semantic lineage across versions;
- expose dependencies and incompatibilities;
- support independent review;
- support attributable acceptance and effectiveness decisions;
- allow implementations to remain replaceable; and
- make historical decisions reproducible.

Contracts do not exist to prescribe technology, centralize all representations, or convert implementation choices into governance authority.

### 4.3 Canonical Source and Derived Representations

One contract identity and version has one canonical source revision.

Copies, indexes, generated references, rendered forms, registries, schemas, implementation types, documentation extracts, and product-local projections are derived representations unless an independently governed source-of-truth transition states otherwise.

A derived representation may carry or translate contract meaning. It may not become a second canonical semantic owner, alter the source meaning, or resolve a conflict by convenience.

## 5. Mandatory Contract Principles

Every future Canonical Contract shall satisfy the following principles.

### 5.1 One Canonical Semantic Owner

Each semantic responsibility belongs to exactly one Canonical Contract or to an identified upstream governance source. No responsibility may have two independent canonical owners.

### 5.2 One Primary Responsibility

Each contract has one primary responsibility. Supporting responsibilities are permitted only when they are inseparable from the primary responsibility and do not create an unrelated semantic domain.

### 5.3 Semantic Immutability After Acceptance

An Accepted contract revision is immutable in historical meaning. Correction, clarification, extension, or replacement creates a new source revision and, where applicable, a new semantic version.

No later revision may silently reinterpret what an earlier Accepted revision meant.

### 5.4 Deterministic Interpretation

Equivalent eligible inputs evaluated against the same exact contract revisions, scope, and temporal evidence must produce the same interpretation independent of model, vendor, repository host, or implementation.

Ambiguous, conflicting, missing, stale, or unverifiable required contract evidence must remain explicit and fail closed for protected operations under applicable governance.

### 5.5 Explicit Versioning

Every contract declares a semantic version and exact immutable source revision. Version identity and source revision are separate and both are required for deterministic traceability.

### 5.6 Backward Compatibility

Compatibility is evaluated against contract meaning and governed consumer expectations, not merely file shape or implementation behavior.

A revision classified as backward compatible must preserve every existing accepted obligation and interpretation within its declared compatibility scope. A consumer is not required to infer compatibility from version numbering alone.

### 5.7 Explicit Breaking-Change Process

A breaking semantic change must be declared, analyzed, independently reviewed, verified, accepted, and transitioned explicitly. It cannot be introduced as an editorial or minor revision.

### 5.8 No Semantic Duplication

A contract may cite or consume another contract. It may not copy another contract’s meaning in a form that can diverge or become independently authoritative.

### 5.9 No Cyclic Semantic Ownership

Contract dependencies form a directed acyclic ownership graph. Two contracts may not depend on each other to define their own canonical meanings.

Operational call cycles or implementation topology do not change this rule and are outside this framework.

### 5.10 Implementation Independence

Contract meaning cannot depend on a programming language, schema language, database, API style, serialization, protocol, model provider, cloud, repository host, policy engine, workflow engine, or deployment topology.

Provider-specific bindings may implement or represent an Accepted and Effective contract. They may not redefine it.

## 6. Contract Lifecycle

The normal Contract Governance lifecycle is:

```text
Proposal
    ↓
Independent Review
    ↓
Maintenance Revision
    ↓
Verification
    ↓
Acceptance Record
(Pending Human Attestation)
    ↓
Acceptance
    ↓
Effectiveness
    ↓
Supersession
    ↓
Archival
```

This sequence is a governance progression, not a single status field or implementation workflow. Review, verification, Acceptance Record preparation, human acceptance, effectiveness, supersession, and archival remain distinct evidence dimensions.

### 6.1 Proposal

Proposal begins when an authorized contract-design activity produces a Draft candidate bound to an accepted architecture, architecture acceptance record, and Contract Decomposition Plan.

A Proposal has no normative authority. Authorship, repository presence, publication, validation, or elapsed time does not create acceptance.

### 6.2 Independent Review

An eligible reviewer independent of the contract’s authorship evaluates the exact candidate revision and records findings, rationale, scope, and outcome.

Review evidence does not alter the candidate, create acceptance, or make it Effective.

### 6.3 Maintenance Revision

The author prepares a new candidate revision addressing accepted review findings. The revision preserves the original responsibility and architecture boundary unless the review demonstrates that a new architecture or decomposition decision is required.

Maintenance Revision is a lifecycle stage, not a change classification. A maintenance revision may contain editorial, minor, major, or breaking changes depending on the candidate’s current state and the authorized scope.

### 6.4 Verification

An eligible verifier evaluates whether the recorded findings were resolved in the new exact revision and whether the corrections introduced a direct regression.

Verification does not reopen unrelated design issues, approve the contract, or make it Effective.

### 6.5 Acceptance Record (Pending Human Attestation)

After successful Verification, an Acceptance Record may be prepared for the exact verified contract identity, semantic version, immutable source revision, scope, Decision Boundary, and evidence lineage.

An Acceptance Record in this stage:

- has status `Pending Human Attestation`;
- is an unsigned governance evidence artifact;
- may be prepared by an AI system or a human operating within authorized preparation scope;
- may contain verified non-attestation evidence, including artifact identity, revision, review and resolution lineage, verification outcome, semantic ownership boundary, preserved deferrals, limitations, and the requested next governance phase;
- MUST leave every human attestation field incomplete;
- MUST NOT state or imply that Acceptance has occurred;
- MUST NOT create acceptance, effectiveness, implementation authority, Design Freeze, or any other governance decision; and
- does not change the verified contract candidate from Draft status.

The minimal human attestation consists of:

1. **Contract Authority** — the attributable human identity or eligible human body making the decision;
2. **Authority Basis** — the independently valid authority source and exact revision supporting eligibility for the decision;
3. **Decision Timestamp** — the attributable date and time at which the human decision is made;
4. **Scope** — the exact contract, revision, Decision Boundary, and organizational or operational boundary accepted;
5. **Eligibility Statement** — the human attestation that applicable authority, interval, separation-of-duty, conflict-of-interest, delegation, confidentiality, and other required eligibility conditions have been evaluated and satisfied; and
6. **Acceptance Statement** — the explicit human decision accepting the exact contract candidate within the declared scope and limitations.

No digital signature is required by this framework. Other applicable governance may require additional integrity, identity, confidentiality, or evidence controls without weakening these minimum semantics.

Only an attributable eligible human Contract Authority may complete the attestation, change the Acceptance Record status from `Pending Human Attestation` to `Accepted`, and authorize the contract-acceptance decision. Completion creates a new immutable Acceptance Record source revision; it does not rewrite a committed Pending Human Attestation revision.

If any required attestation field, authority evidence, eligibility evidence, candidate binding, or integrity evidence is missing, ambiguous, stale, conflicting, or unverifiable, the record remains `Pending Human Attestation` and Acceptance fails closed. A change to the verified candidate revision invalidates the pending record for acceptance and requires the applicable earlier lifecycle stages to be satisfied for the changed revision.

### 6.6 Acceptance

An eligible human Contract Authority records acceptance of one exact contract identity, semantic version, source revision, scope, and decision boundary.

Acceptance requires the necessary architecture, decomposition, review, resolution, verification, authority, eligibility, rationale, and integrity evidence. A commit, author statement, reviewer verdict, or AI assertion is not acceptance.

Acceptance does not necessarily imply Effective.

### 6.7 Effectiveness

Effectiveness is a separate attributable governance decision that activates an Accepted contract for an explicit scope, purpose, and interval.

Effectiveness does not create implementation, adoption, deployment, Product Binding, release authority, or Design Freeze.

### 6.8 Supersession

Supersession identifies an exact successor contract or revision. It preserves predecessor history and does not silently rewrite prior meaning.

A Superseded contract may remain Effective for an explicit transition interval or preserved legacy scope. Supersession alone does not end effectiveness, revoke acceptance, Archive the predecessor, or authorize migration.

### 6.9 Archival

Archival preserves a contract and its lifecycle evidence as history while removing it from current normative use.

Archival is not deletion. An Effective contract cannot become Archived without a separately resolved effectiveness boundary. Archived contract history, acceptance, prior effective intervals, supersession lineage, reviews, and evidence remain immutable.

### 6.10 Rework and Failure Paths

A review or verification failure returns the candidate to bounded revision, further architecture work, or withdrawal as directed by eligible governance. Failure does not automatically create a new contract, rejection, supersession, or archival.

No later stage can backfill missing evidence from an earlier stage.

Preparation of an Acceptance Record cannot backfill missing Verification, authority, eligibility, or human attestation evidence. An incomplete or invalid attestation does not create partial Acceptance; the record remains `Pending Human Attestation` until an eligible human decision is completely and validly recorded or the candidate returns to an applicable earlier stage.

## 7. Official Contract Status Model

The core contract statuses and dispositions are:

| Status | Meaning | Explicit non-implications |
| --- | --- | --- |
| Draft | A mutable proposal under authoring or review with no normative authority. | Not Accepted, Effective, implemented, deployed, or Design Frozen. |
| Accepted | An exact immutable revision has valid contract-acceptance evidence. | Does not necessarily imply Effective, adopted, implemented, deployed, or Design Frozen. |
| Effective | An Accepted revision is operationally applicable for an explicit scope, purpose, and interval under a separate effectiveness decision. | Does not imply implementation, adoption, deployment, Product Binding, or operation-specific permission. |
| Superseded | An exact successor is identified for the same or replacing responsibility. | Does not automatically end effectiveness, revoke acceptance, Archive history, or authorize migration. |
| Archived | The retained revision has no current normative effect and remains available for audit and reconstruction. | Does not delete history or erase prior acceptance, effectiveness, or supersession evidence. |

`Pending Human Attestation` is the status of a prepared Acceptance Record, not an `Accepted` contract status and not a sixth normative contract status. While an Acceptance Record is pending, the verified contract candidate remains `Draft`. Repository publication, a commit, completion of non-attestation evidence, AI preparation, elapsed time, or successful validation cannot convert either artifact to `Accepted`.

These labels are orthogonal:

- a contract may be Accepted but not Effective;
- a contract may be Accepted and Effective;
- a Superseded contract may remain Effective during an explicit transition;
- a Superseded contract may remain unarchived;
- an Archived contract retains historical acceptance and prior effective intervals; and
- Draft and Archived contracts cannot be currently Effective; and
- a contract associated with an Acceptance Record in `Pending Human Attestation` status remains Draft and cannot be currently Effective.

The framework does not abolish other applicable platform lifecycle dispositions such as Rejected, Withdrawn, Deprecated, Expired, or Retired. Those meanings remain owned by the applicable governance lifecycle sources. They must not be collapsed into the five core contract labels.

## 8. Governance Roles

One human or body may perform multiple roles only where applicable governance permits it and separation-of-duty, conflict-of-interest, scope, and eligibility requirements remain satisfied.

### 8.1 Author

The Author:

- prepares the Draft contract candidate;
- preserves architecture and decomposition boundaries;
- records rationale and revision lineage;
- responds to accepted findings; and
- does not approve or independently verify the authored revision merely through authorship.

### 8.2 Reviewer

The Reviewer:

- independently evaluates an exact candidate revision;
- identifies architectural, ownership, lifecycle, consistency, compatibility, authority, and audit concerns;
- records findings and an evidence-based review outcome; and
- does not create acceptance or effectiveness.

### 8.3 Verifier

The Verifier:

- independently evaluates resolution of recorded findings;
- confirms the exact corrected revision;
- identifies regressions caused by the correction; and
- does not make the acceptance or effectiveness decision.

### 8.4 Architecture Authority

The Architecture Authority:

- owns architecture acceptance within independently granted scope;
- determines whether contract design remains inside the accepted architecture and Decision Boundary;
- decides whether a proposed contract change requires new architecture work; and
- does not acquire Contract Authority or effectiveness authority merely through this role.

### 8.5 Contract Authority

The Contract Authority:

- makes or records the eligible human contract-acceptance decision;
- independently evaluates the prepared Acceptance Record and its exact candidate and evidence bindings;
- completes the human attestation fields through an attributable human act;
- is the only role permitted to change an Acceptance Record from `Pending Human Attestation` to `Accepted`;
- binds acceptance to the exact identity, version, revision, scope, and evidence;
- preserves conditions, limitations, and supersession lineage; and
- does not create effectiveness, implementation authority, or Design Freeze through acceptance.

### 8.6 Effectiveness Authority

The Effectiveness Authority:

- makes the separate decision to activate an Accepted contract for a declared scope and interval;
- verifies that acceptance and all effectiveness prerequisites remain valid; and
- does not authorize implementation, adoption, or deployment unless separately empowered for those operations.

### 8.7 Implementation Teams

Implementation Teams:

- implement only separately authorized, Accepted, Effective, and applicable contracts;
- preserve contract meaning and evidence boundaries;
- identify ambiguity or incompatibility rather than selecting a convenient interpretation; and
- cannot change contract meaning through code, configuration, deployment, or operational practice.

### 8.8 Consumers

Consumers:

- bind their use to exact eligible contract versions and revisions;
- preserve dependency and compatibility evidence;
- do not treat derived representations as new canonical owners; and
- cannot redefine upstream contract semantics locally.

### 8.9 AI Systems

AI systems may draft, compare, analyze, and verify evidence within authorized scope. After successful Verification, an AI system may prepare an unsigned Acceptance Record and populate non-attestation evidence for the exact verified candidate.

AI preparation is an evidence-assembly function, not Contract Authority, human attestation, or a governance decision. An AI-prepared Acceptance Record MUST:

- remain in `Pending Human Attestation` status;
- identify itself as prepared evidence without human acceptance;
- preserve exact candidate, review, resolution, verification, scope, ownership, limitation, and deferral references; and
- leave the Contract Authority, Authority Basis, Decision Timestamp, Scope attestation, Eligibility Statement, and Acceptance Statement for completion by the attributable eligible human Contract Authority.

An AI system MUST NOT:

- mark an Acceptance Record or contract `Accepted`;
- attribute acceptance to a human or body;
- fabricate, infer, select, or repair authority or eligibility evidence;
- complete, simulate, sign, or attest any human attestation field;
- treat a user request, repository role, authorship, Git event, tool access, silence, prior behavior, or AI-generated verification as human acceptance;
- create effectiveness, governance authority, or a waiver of required review; or
- convert successful preparation, validation, commit, publication, or tool execution into a governance decision.

Only the attributable eligible human Contract Authority owns the Acceptance decision. AI assistance does not reduce, transfer, delegate, or share that exclusive human authority.

## 9. Semantic Ownership and Dependencies

### 9.1 Unique Ownership

Every contract declares one primary responsibility and the semantic responsibilities it owns. The same review identifies what the contract explicitly does not own.

When ownership is unclear or duplicated, the candidate remains Draft and fails closed for acceptance.

### 9.2 References and Dependencies

Contracts may:

- reference other contracts;
- depend on exact upstream contract revisions;
- consume upstream meanings;
- specialize behavior only where an upstream contract explicitly permits specialization; and
- provide meanings to declared downstream consumers.

Contracts may never:

- redefine another contract;
- silently copy another contract’s meaning;
- infer authority from dependency;
- use a downstream contract to validate an upstream owner;
- create a cyclic semantic dependency; or
- make an implementation or derived representation authoritative.

### 9.3 Dependency Direction

Each Contract Decomposition Plan records an acyclic dependency graph. Review and acceptance proceed in dependency order.

A downstream contract cannot become valid by repairing, overriding, or filling a missing upstream contract meaning. An upstream revision that affects downstream interpretation requires compatibility and impact evaluation.

## 10. Versioning and Compatibility

### 10.1 Version Structure

Canonical Contracts use explicit semantic versions:

```text
MAJOR.MINOR.PATCH
```

- `MAJOR` identifies a breaking semantic revision or a major responsibility-level revision permitted to retain the contract identity.
- `MINOR` identifies a backward-compatible semantic extension or clarification.
- `PATCH` identifies a verified editorial correction with no semantic change.

Version numbers are evidence labels, not proof of compatibility. Exact source revision, review, and compatibility evidence remain controlling.

### 10.2 Compatibility Expectations

Every non-editorial revision evaluates:

- compatibility with the immediately preceding Accepted revision;
- compatibility with all currently Effective revisions and declared transition scopes;
- effect on related upstream and downstream contracts;
- effect on derived representations and consumers;
- migration or coexistence implications; and
- effect on historical reconstruction.

Compatibility claims are explicit, attributable, and bounded. Silence does not mean compatible.

### 10.3 Consumer Expectations

Consumers identify the exact contract revisions they use and the compatibility range authorized by applicable governance. A consumer may not silently adopt a later version based solely on a matching major number.

## 11. Change Management

### 11.1 Change Classes

| Change class | Definition | Version expectation |
| --- | --- | --- |
| Editorial Change | Corrects spelling, formatting, broken references, or presentation without changing meaning, responsibility, obligation, interpretation, scope, or dependency. | Patch |
| Minor Revision | Adds or clarifies meaning while preserving backward compatibility, primary responsibility, ownership, and the accepted architecture boundary. | Minor |
| Major Revision | Substantially revises the contract while preserving a coherent successor identity and one primary responsibility; it may include breaking semantic change. | Major |
| Breaking Semantic Change | Changes an accepted meaning, obligation, interpretation, compatibility boundary, result, ownership relationship, or consumer expectation incompatibly. | Major or new contract identity |

Change classification is a governance conclusion supported by review evidence. The author’s label is not controlling.

### 11.2 Required Governance by Change Class

| Change class | Independent review | Verification | New acceptance | Entirely new contract |
| --- | --- | --- | --- | --- |
| Editorial Change | Bounded independent confirmation that meaning is unchanged | Required for the editorial classification and any recorded findings | Renewed acceptance evaluation required for the new exact revision before it replaces an Accepted revision | No, unless review finds semantic or ownership change |
| Minor Revision | Required | Required after findings are addressed | Required for the new version and exact revision | Normally no |
| Major Revision | Full independent review required | Required | Required | Required when identity or ownership continuity cannot be preserved |
| Breaking Semantic Change | Full independent review and architecture-impact evaluation required | Required | Required | Required when the change replaces the primary responsibility, changes the canonical owner, splits or merges ownership domains, or cannot preserve unambiguous lineage |

No change to an Accepted revision occurs in place. Every accepted successor is a new immutable source revision.

### 11.3 New Contract Identity

An entirely new contract is required when:

- the primary responsibility changes;
- canonical semantic ownership moves to a different domain;
- one contract is split into independently owned responsibilities;
- multiple contracts are merged under a new primary responsibility;
- the accepted architecture family or Decision Boundary changes;
- a successor cannot preserve unambiguous identity and semantic lineage; or
- maintaining the old identity would mislead consumers about compatibility.

A new contract identity does not erase the predecessor. Supersession and transition evidence preserve the relationship.

### 11.4 Emergency and Operational Pressure

Urgency, implementation failure, deployment schedule, consumer demand, security incident, or unavailable reviewer does not downgrade the required change class or bypass review, verification, acceptance, or effectiveness.

Applicable emergency governance may authorize a separately bounded operation. It does not silently amend a Canonical Contract.

## 12. Review, Resolution, Verification, Acceptance, and Effectiveness

### 12.1 Independent Review

Independent Review evaluates an exact immutable candidate against its accepted architecture, decomposition, governance sources, related contracts, predecessor revisions, and declared compatibility.

The review records findings and their severity, evidence, affected ownership boundary, and required disposition. It does not modify the candidate or make a governance decision reserved for another role.

### 12.2 Resolution

The Author resolves accepted findings in a new exact revision and records the relationship between each finding and its treatment.

Resolution remains within the authorized change scope. A finding requiring architecture, decomposition, ownership, or Decision Boundary change is escalated rather than silently absorbed into contract text.

### 12.3 Verification

Verification determines whether the accepted findings are resolved and whether the resolution introduced a direct regression.

Verification binds to the baseline reviewed revision and the corrected revision. It is evidence for acceptance, not acceptance itself.

### 12.4 Acceptance Record Preparation

Acceptance Record preparation begins only after successful Verification of the exact candidate revision.

The preparer may assemble:

- the Acceptance Record identity and preparation revision;
- the exact contract identity, semantic version, immutable source revision, and canonical source;
- architecture, Architecture Acceptance Record, Contract Decomposition Plan, and framework bindings;
- review, resolution, and Verification evidence;
- the verified semantic ownership and Decision Boundary;
- unresolved deferrals, conditions, limitations, compatibility evidence, and non-authorizations; and
- the proposed next phase permitted only if human Acceptance is later recorded.

Preparation MUST produce status `Pending Human Attestation` and MUST preserve the six human attestation fields in Section 6.5 for completion by the attributable eligible human Contract Authority. Prepared evidence may support human evaluation but cannot decide, imply, or predict the human outcome.

A prepared record is deterministically ineligible to support Acceptance when it is bound to a different candidate revision, lacks successful Verification evidence, contains completed or attributed human attestation not supplied by the identified eligible human authority, or otherwise lacks required traceability. Such a record remains pending and fails closed.

### 12.5 Acceptance

Acceptance is an attributable human governance decision for one exact candidate revision and scope.

The attributable eligible human Contract Authority reviews the prepared evidence, completes the minimal attestation in Section 6.5, and records the decision in a new immutable Acceptance Record revision. The accepted record identifies the decision, authority basis, artifact identity, version, immutable source revision, scope, conditions, rationale, evidence lineage, and integrity boundary required by applicable governance.

Only the completed human attestation can change the Acceptance Record status to `Accepted` and establish contract Acceptance. AI preparation, a Draft record, or an incomplete attestation has no acceptance effect.

Acceptance does not imply Effectiveness.

### 12.6 Effectiveness

Effectiveness requires a separate attributable decision after acceptance. The effectiveness decision identifies the applicable scope, purpose, start boundary, end boundary where applicable, dependencies, transition treatment, and affected consumers required by applicable governance.

An Accepted contract that lacks valid effectiveness evidence remains non-operative.

## 13. Supersession and Transition

### 13.1 Superseding Revision or Contract

A supersession decision identifies:

- the predecessor identity and exact revision;
- the successor identity and exact revision;
- the relationship between them;
- compatibility classification;
- affected scope;
- transition boundary;
- coexistence or legacy treatment where applicable; and
- retained historical evidence.

These are governance evidence categories, not a schema.

### 13.2 Transition

Transition may permit a predecessor and successor to remain Effective for different scopes or intervals. Every concurrent use remains explicit and attributable.

A successor does not automatically:

- become Effective;
- deactivate the predecessor;
- migrate consumers;
- modify Product Bindings;
- authorize implementation;
- end a Design Freeze; or
- Archive the predecessor.

### 13.3 Historical Meaning

Supersession acts prospectively. Historical decisions remain bound to the exact contract versions and evidence that governed them at the relevant time.

## 14. Archival and Retention

Archival preserves:

- the canonical contract revision;
- all prior versions;
- architecture and decomposition references;
- reviews and verification;
- prepared Acceptance Records in `Pending Human Attestation` status and their immutable revisions;
- acceptance and effectiveness evidence;
- compatibility decisions;
- supersession and transition lineage;
- related contract references;
- consumer-impact evidence where governed; and
- integrity and audit history.

Archival never deletes or rewrites contract meaning. An Archived revision is excluded from current normative use but remains available for audit, reconstruction, and historical explanation under applicable authorization and confidentiality controls.

## 15. Contract Traceability

Every Canonical Contract references exact revisions of:

1. its governing architecture;
2. the applicable Architecture Acceptance Record;
3. the applicable Contract Decomposition Plan;
4. the Contract Governance Framework;
5. all upstream related contracts;
6. all downstream contract relationships known at acceptance;
7. the immediately preceding revision, or an explicit statement that none exists;
8. every superseded revision or contract, or an explicit statement that none exists;
9. every superseding contract or revision known at the evaluated time, or an explicit statement that none exists;
10. applicable review, resolution, verification, Acceptance Record preparation, human attestation, acceptance, effectiveness, and compatibility evidence; and
11. applicable transition, deprecation, archival, or legacy evidence.

A reference identifies the stable artifact identity, semantic version, immutable source revision, relationship, and applicable scope. A floating filename, branch name, repository location, or latest-version reference is insufficient for authoritative traceability.

Missing or conflicting required traceability prevents acceptance or current operational reliance until resolved under applicable governance.

## 16. Existing and Future Contracts

This framework is designed for every future Canonical Contract in CADP.

Existing contract history is not rewritten. When an existing contract is revised after this framework becomes Accepted and Effective, the new revision must:

- preserve the earlier immutable record;
- identify its prior governance basis;
- declare its relationship to this framework;
- undergo the applicable change classification and governance process; and
- avoid retroactively asserting that historical evidence satisfied requirements that did not yet exist.

This framework does not automatically invalidate, accept, make Effective, supersede, or Archive an existing contract.

Version 0.2.0 is backward compatible with contracts and lifecycle evidence prepared under Version 0.1.0 because it:

- does not change Proposal, Independent Review, Maintenance Revision, or Verification requirements;
- does not weaken or replace any Acceptance prerequisite;
- does not reinterpret a prior review, Verification, acceptance assertion, or Accepted record;
- permits an exact successfully verified candidate to proceed to `Acceptance Record (Pending Human Attestation)` without repeating earlier satisfied stages, provided its candidate revision and governing evidence have not changed;
- does not convert any existing Draft, review, Verification, approval package, approval assertion, or Acceptance Record into `Accepted`; and
- preserves the same exclusive eligible human Contract Authority decision boundary.

Existing acceptance evidence remains subject to the governance requirements and validity evaluation applicable to its exact decision and record. This revision does not repair missing historical attestation or authority evidence by declaration.

## 17. Non-Goals

This framework does not define:

- a specific contract;
- contract-specific obligations;
- APIs;
- schemas;
- storage;
- serialization;
- protocols;
- implementation;
- source code;
- databases;
- services;
- runtime behavior;
- deployment;
- infrastructure;
- technology selection;
- workflow tooling;
- registry values;
- Product Bindings;
- product-specific rules;
- implementation acceptance;
- production authorization; or
- Design Freeze.

It also does not replace architecture, an Architecture Acceptance Record, a Contract Decomposition Plan, a Contract Review, a contract acceptance record, or an effectiveness decision.

## 18. Framework Change Control

This framework is subject to the governance principles it defines without approving itself.

A future revision:

- creates a new immutable source revision;
- declares its change class;
- preserves prior meaning;
- undergoes independent review and verification;
- requires separate eligible human acceptance; and
- requires separate effectiveness before governing current contract work.

A revision that changes contract authority, lifecycle separation, acceptance boundaries, effectiveness, semantic ownership, breaking-change treatment, or historical preservation requires architecture-impact evaluation.

## 19. Revision History

| Version | Classification | Summary | Compatibility |
| --- | --- | --- | --- |
| 0.1.0 | Initial Draft | Established the platform-wide Contract Governance methodology. | Initial version |
| 0.2.0 | Minor Governance Maintenance Revision | Adds the `Acceptance Record (Pending Human Attestation)` preparation stage, the six-field minimal human attestation, deterministic fail-closed transition rules, and explicit AI preparation limits. Human Acceptance authority, Acceptance prerequisites, architecture ownership, and implementation boundaries are unchanged. | Backward compatible with Version 0.1.0 contract candidates and lifecycle evidence |

This revision remains Draft. Its repository publication, review, or use to prepare evidence does not approve the framework, make it Effective, accept a contract, or authorize implementation.
