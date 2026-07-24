# CADP Governance Document Model

This document is a descriptive map of the governance document classes used by the Cliff AI Development Platform. It explains their responsibilities, relationships, authority boundaries, and repository locations. It does not define governance policy, amend an existing contract, or create a governance state.

## 1. Purpose

CADP governance is intentionally divided into document classes. Each class has:

- a distinct responsibility;
- a distinct authority boundary;
- a distinct lifecycle;
- explicit relationships with other classes; and
- explicit limits on what it can establish.

No single document performs every governance function. Architecture sources describe the governing system, contracts define bounded rules, reviews evaluate candidates, history preserves context, and approval materials prepare or retain evidence of human decisions. Keeping these responsibilities separate makes source authority, review status, historical facts, and lifecycle evidence independently traceable.

Document class does not by itself establish authority. Authority depends on the applicable governance rules, canonical identity, exact revision, scope, approval evidence, effective interval, and current lifecycle and applicability evidence.

## 2. Core Document Classes

In the **Normative** column, `YES — conditional` means that the class can define rules, but an individual artifact exercises normative authority only when the applicable governance requirements for approval, effectiveness, scope, identity, and revision are satisfied.

| Category | Purpose | Normative | Lifecycle Driven | Examples | Authority |
| --- | --- | --- | --- | --- | --- |
| Foundation Architecture | Describes the platform-wide architectural model, foundational boundaries, authority hierarchy, and system responsibilities. | YES — conditional | YES | [`FOUNDATION_ARCHITECTURE.md`](FOUNDATION_ARCHITECTURE.md) | Foundational only when the exact revision is authorized, Approved, Effective, and applicable. Draft foundation material has no normative authority. |
| Contracts | Define bounded governance rules, evidence requirements, state semantics, and relationships owned by a specific contract. | YES — conditional | YES | [`contracts/`](contracts/) | A contract governs only within its declared subject, scope, version, and effective interval after the required approval and effectiveness evidence exists. |
| Reviews | Evaluate candidate artifacts, record findings, verify revisions, and state review verdicts. | NO | YES | [`reviews/`](reviews/) | Review evidence is advisory. A verdict does not approve a candidate, make it Effective, grant authority, or replace the reviewed source. |
| History | Preserves verified chronology, milestone context, decision lineage, and navigation to source evidence. | NO | YES | [`history/`](history/) | Historical records explain and reference. They do not override normative sources or create current lifecycle authority. |
| Approvals | Prepares evidence for human consideration or records separately authorized approval evidence. | NO | YES | [`approvals/PHASE_1_STEP_4_APPROVAL_PACKAGE.md`](approvals/PHASE_1_STEP_4_APPROVAL_PACKAGE.md) | An approval package has no approval authority. An approval record is evidence of an external eligible human decision; the document does not create approver eligibility or broader authority. |
| Future ADRs | Record a bounded architecture decision, its context, rationale, consequences, scope, evidence, and supersession lineage. | YES — conditional | YES | No standalone normative CADP ADR has been created. Future canonical global ADRs are assigned by the Foundation Architecture to `decisions/global/`; explanatory historical ADR records are reserved under `docs/history/decisions/`. | An ADR has authority only when it is canonical, Approved, Effective, in scope, and otherwise eligible under the authority hierarchy. Its name or location grants no authority. |
| Future Diagrams | Visualize an architecture, relationship, sequence, or historical baseline while citing the sources represented. | NO | YES | No architecture diagram has been created. Historical explanatory diagrams are reserved under `docs/history/diagrams/`. | A diagram has no independent authority and cannot replace or reinterpret its cited source. |

## 3. Normative and Non-Normative Documents

Normative documents define rules, obligations, constraints, authority boundaries, or governed state semantics. The Foundation Architecture, contracts, and future ADRs are normative-capable classes. A document in one of these classes is not automatically authoritative: Draft, unapproved, ineffective, out-of-scope, expired, superseded, or non-canonical material cannot exercise normative authority except where an applicable governance rule explicitly preserves a valid legacy binding.

Non-normative documents may:

- explain;
- summarize;
- review;
- record;
- prepare;
- navigate; or
- visualize.

They never override an applicable normative source. Reviews do not replace the artifact reviewed. History does not convert chronology into authority. Approval packages do not create approval. Diagrams do not establish architecture by depiction.

Whenever a conflict exists, the applicable normative contract governs, subject to the higher-order authority and conflict-resolution rules of the Foundation Architecture. A non-normative statement remains subordinate even when it is newer, easier to retrieve, more detailed, or located beside a normative artifact.

## 4. Document Relationships

The intended governance progression is:

**Foundation → Contracts → Reviews → Draft Baseline → History → Approval Package → Human Approval → Approved → Effective → Adopted**

This flow illustrates progression and evidence relationships. It is not a single document lifecycle and does not imply automatic transitions.

- The Foundation supplies architectural boundaries within which contracts are drafted.
- Contracts define bounded governance semantics and evidence requirements.
- Reviews evaluate exact candidate revisions without changing those revisions.
- A Draft Baseline fixes an immutable repository revision for consideration; it is not approval.
- History records verified chronology and milestone context without creating lifecycle state.
- An Approval Package assembles candidate scope and evidence without approving it.
- Human Approval is an attributable external decision by an eligible human authority.
- Approved state requires a separately authorized lifecycle action and valid approval evidence.
- Effective state requires its own applicability decision and boundary.
- Adopted state requires its own scope-specific adoption evidence.

Each arrow means “may provide an input to” or “may precede.” It does not mean “automatically changes.” A later document may cite an earlier document without modifying it, inheriting all of its authority, or transferring authority between classes.

## 5. Authority Matrix

The matrix describes what each current core document class does by itself. `Creates Lifecycle State` and `Grants Authority` are `NO` because documents may define or record evidence, but the applicable authorized governance action is what establishes a state or authority consequence.

| Category | Defines Rules | Records Evidence | Summarizes | May Recommend | Creates Lifecycle State | Grants Authority |
| --- | --- | --- | --- | --- | --- | --- |
| Foundation | YES | NO | NO | NO | NO | NO |
| Contracts | YES | NO | NO | NO | NO | NO |
| Reviews | NO | YES | YES | YES | NO | NO |
| History | NO | YES | YES | NO | NO | NO |
| Approvals | NO | YES | YES | NO | NO | NO |

An approval package and an approval record are both included in the Approvals row, but their roles differ. A package prepares evidence for consideration. A valid approval record retains evidence of an independently made human decision. Neither creates the approver's eligibility, an Effective state, adoption, Design Freeze protection, implementation authority, or Product Binding authority.

## 6. Allowed Dependencies

Document classes may reference other classes when the reference is necessary for traceability, evaluation, or historical reconstruction.

| Referencing class | May reference | Intended relationship |
| --- | --- | --- |
| Foundation Architecture | Existing authoritative sources and accepted architecture evidence | Establishes traceable architectural context without converting cited evidence into a new authority tier. |
| Contracts | Foundation Architecture and applicable higher or peer contracts | Declares architectural basis, bounded dependencies, and semantic ownership. |
| Reviews | Foundation Architecture, contracts, prior review evidence, and exact candidate revisions | Evaluates consistency and resolution while preserving independence from the artifact reviewed. |
| History | Foundation Architecture, contracts, reviews, commits, milestones, and approval evidence | Reconstructs verified chronology and directs readers to canonical sources. |
| Approval packages | Candidate contracts, their review lineage, history records, and exact repository baselines | Assembles the evidence needed for an informed human decision. |
| Approval records | Exact artifact revisions, authority evidence, decision scope, and rationale references | Binds retained evidence to the external human decision without becoming the source of approver authority. |
| Future ADRs | Foundation Architecture, applicable contracts, earlier ADRs, and decision evidence | Records bounded architectural rationale and explicit relationships without silently superseding higher authority. |
| Future diagrams | Exact normative and historical sources represented | Provides a visual projection whose meaning remains controlled by the cited sources. |

References do not transfer authority. Citation by a higher-authority document does not automatically promote the cited document. Citation by a lower-authority or non-normative document does not weaken, amend, supersede, or reinterpret the source.

## 7. Repository Layout

The current governance documentation surface is organized under `docs/`:

| Location | Purpose |
| --- | --- |
| [`docs/`](./) | Foundation architecture and descriptive repository documentation. A file's location under `docs/` does not by itself determine authority. |
| [`docs/contracts/`](contracts/) | Draft and future governed contracts with bounded normative responsibilities. |
| [`docs/reviews/`](reviews/) | Internal, independent, revision, findings-analysis, and closure review evidence. |
| [`docs/history/`](history/) | Non-normative architecture history, timeline, milestone records, and navigation. |
| [`docs/approvals/`](approvals/) | Non-normative approval preparation packages and, only when separately authorized, retained approval evidence. |
| Future ADR locations | The Foundation Architecture assigns canonical global CADP ADRs to `decisions/global/`. The Architecture History subsystem reserves `docs/history/decisions/` for explanatory standalone historical decision records. Neither location is created by this document. |
| Future diagram location | The Architecture History subsystem reserves `docs/history/diagrams/` for non-normative historical explanatory diagrams. The location is not created by this document. |

The distinction between canonical ADRs and historical ADR records is intentional. A canonical ADR may become normative when all authority and lifecycle conditions are met. A historical decision record remains explanatory. A projection or historical copy cannot replace the canonical ADR.

## 8. Lifecycle Independence

The following are governance lifecycle or operational concepts, not document classes:

- Approval;
- Effective;
- Adopted;
- Design Freeze;
- Product Binding;
- Implementation.

Documents may define the meaning of these concepts or record evidence about them. Documents do not create those states or relationships unless an applicable governance process authorizes the underlying action and the required evidence is recorded.

Approval does not imply Effective. Effective does not imply Adopted. Adoption does not imply Product Binding unless the applicable binding requirements are independently satisfied. Design Freeze is a separate protection dimension. Implementation is not a governance document state and cannot be inferred from approval, effectiveness, adoption, repository location, commit status, or documentation completeness.

## 9. Maintenance Principles

Governance documentation is maintained according to these descriptive principles:

1. Keep document responsibilities separate.
2. Avoid duplicating normative language in non-normative documents.
3. Prefer exact references over copied source text.
4. Maintain traceability to canonical identities, versions, revisions, and evidence.
5. Preserve historical accuracy and prior meaning.
6. Correct errors transparently rather than silently reinterpreting earlier records.
7. Distinguish current applicability from historical validity.
8. Keep review conclusions separate from human approval.
9. Keep repository chronology separate from governance lifecycle chronology.
10. Treat summaries, indexes, packages, and diagrams as navigation or evidence aids, never substitute authority.

## 10. Out of Scope

This document does not define:

- technical architecture;
- runtime behavior;
- software implementation;
- approval authority or approver eligibility;
- contract language or contract semantics;
- product behavior;
- Product Binding requirements;
- lifecycle transition procedures;
- schemas, APIs, databases, or tooling; or
- any approval, effectiveness, adoption, or Design Freeze record.

Existing normative and non-normative sources remain unchanged. This document describes their document-class relationships and does not amend, approve, supersede, or make any source Effective.
