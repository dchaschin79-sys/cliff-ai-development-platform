# Approval Record Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-APPROVAL-RECORD |
| Version | 0.1.1 |
| Lifecycle state | Draft |
| Scope | Approval evidence for governed CADP artifacts and decisions |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Foundation reference | CADP-ARCH-FOUNDATION v0.2.0 |
| Canonical artifact reference | CADP-CONTRACT-CANONICAL-ARTIFACT v0.1.0 |
| Metadata registry reference | CADP-CONTRACT-METADATA-REGISTRY v0.1.1 |
| Authority and delegation reference | CADP-CONTRACT-AUTHORITY-DELEGATION v0.1.1 |
| Delegated variance reference | CADP-CONTRACT-DELEGATED-VARIANCE v0.1.1 |
| Policy decision reference | CADP-CONTRACT-POLICY-DECISION v0.1.1 |
| Governance lifecycle reference | CADP-CONTRACT-GOVERNANCE-LIFECYCLE v0.1.1 Draft |
| Step 3 baseline | Git revision `0cb09c68f26e97e4215fcdcc616c2c79ae007c62` |

## 1. Purpose and Scope

This contract defines the evidence required to prove that an eligible human approver made an approval decision about an exact governed artifact revision within a declared scope. It defines approval evidence only.

An approval record is a governed evidence artifact. It records an external, attributable human decision; it does not create approver eligibility, artifact authority, operational effectiveness, adoption, implementation authorization, or Design Freeze protection.

This contract creates no approval record, company role, approval workflow, schema, registry value, signature implementation, Product Binding, or approval decision.

## 2. Approval Separation

Approval is independent from:

- document existence;
- authorship;
- repository ownership or administration;
- review participation;
- Git history;
- authority class;
- operational effectiveness;
- adoption;
- implementation or deployment;
- execution capability;
- Design Freeze protection.

An artifact can exist, be versioned, reviewed, committed, or published without being Approved. An Approved artifact is not automatically Effective, Adopted, implemented, deployed, or Design Frozen.

The following rules are explicit:

- A Git commit, push, merge, tag, or release is not approval.
- A document author is not an approver merely because the author created or changed the document.
- A repository owner, administrator, or maintainer is not an approver merely because of repository control.
- File location, merge status, branch protection, publication, signatures on unrelated objects, or successful validation do not constitute approval.
- An AI system cannot create, infer, ratify, or impersonate human approval.

## 3. Approval Identity and Evidence Envelope

Every approval record identifies:

- stable approval identity;
- approval-record version and immutable source revision;
- approval decision;
- approver identity;
- approver eligibility evidence;
- approval timestamp;
- approved artifact identity;
- approved artifact semantic version;
- exact approved artifact source revision;
- approval scope;
- approved operations or authority consequences, when the controlling rule requires them;
- approval conditions and limitations;
- approval rationale or stable rationale reference;
- approval effective boundary when distinct from the decision timestamp;
- approval supersession and revocation references, when applicable;
- approval integrity evidence;
- confidentiality classification and handling constraints;
- canonical lineage and audit references.

The approval identity is distinct from the approved artifact identity. Approval text embedded in the approved artifact is self-asserted metadata unless a separate, externally verifiable approval record binds the eligible approver's decision to the exact artifact revision.

## 4. Approver Identity and Eligibility

Approver eligibility is evaluated under the Authority and Delegation Contract for the exact:

- human identity;
- recognized role or authority source;
- approval operation;
- artifact and artifact class;
- scope;
- effective interval;
- authority-source revision;
- delegation chain, when approval delegation is permitted;
- separation-of-duty and conflict-of-interest requirements;
- non-delegable boundaries;
- confidentiality and source-authorization constraints.

Eligibility at the approval decision time determines whether the approval can be valid historical evidence. Current operational reliance on that approval is a separate temporal evaluation under Section 7.

Identity alone does not establish eligibility. A role name, job title, repository permission, document ownership, tool access, prior approval, or technical capability cannot substitute for current authority evidence.

Approval delegation is valid only where the controlling authority explicitly permits it. Every delegation link must remain complete, valid, bounded, and independently reconstructable. Foundational approval and other non-delegable decisions cannot be approved through an ineligible delegation.

## 5. Artifact and Revision Binding

Approval binds to one exact artifact identity, semantic version, immutable source revision, scope, and decision. It does not float to:

- later commits;
- later semantic versions;
- sibling artifacts;
- copied or derived representations;
- other scopes;
- other products or repositories;
- later changes that appear editorial but alter governed meaning.

A changed source revision requires renewed approval evaluation. Compatibility or lineage may inform that evaluation but cannot transfer approval automatically.

If the artifact identity, version, source revision, or canonical source cannot be resolved consistently, approval validity is `Indeterminate` and fails closed for protected operations.

## 6. Approval Scope and Conditions

Approval scope declares the exact boundary within which the decision applies. It includes applicable artifact, organizational, platform, product, repository, component, operation, confidentiality, purpose, and time boundaries when relevant.

Approval outside the approver's valid authority is invalid. Approval cannot:

- override a higher authority;
- waive a non-delegable or non-waivable control;
- expand its own scope;
- approve a different revision by analogy;
- establish operational effectiveness or adoption implicitly;
- authorize implementation or deployment unless a separate applicable decision explicitly does so;
- create or release a Design Freeze implicitly.

Conditions attached to approval remain part of the approval evidence. Missing or unresolved conditions prevent the approval from supporting protected normative use.

## 7. Approval Timestamp and Temporal Validity

The approval timestamp records when the eligible human decision occurred. A Git author date, commit date, merge date, publication date, file timestamp, or system-ingestion timestamp is not the approval timestamp unless separately proven to be the attributable decision event.

Approval validity is evaluated for the relevant point in time. Historical approval and current operational use are distinct:

- a valid historical approval remains immutable evidence;
- later revocation, supersession, authority loss, scope change, expiry, or artifact change does not rewrite the historical decision;
- current use must evaluate the approval's present validity together with artifact lifecycle, applicability, scope, and any later evidence.

Later loss of the approver's role, scope, effective interval, or authority is a prospective reevaluation event at the attributable authority-loss boundary. It does not revoke the approval automatically and does not make the historical approval false.

For current operational reliance after that boundary:

1. the approval's revocation, supersession, scope, conditions, artifact revision, and controlling authority evidence must be evaluated;
2. an applicable Approved and Effective specialized contract may impose a stricter current-validity rule for the use it governs;
3. an applicable Approved and Effective governing rule may expressly preserve current reliance within a bounded scope and interval;
4. when no applicable rule resolves whether current reliance persists, current approval validity is `Indeterminate` and fails closed for protected operations.

The Delegated Variance Contract owns the stricter current operational-validity rule for variance use. This general contract does not weaken or replace that rule.

Any authority-loss event or other changed input that may affect current reliance requires reevaluation and invalidation of cached decisions bound to the prior approval-validity result. Current approval validity remains approval evidence only; it does not establish artifact effectiveness, adoption, or operation-specific authorization.

An unresolved event identity, effective boundary, controlling rule, or applicability result produces `Indeterminate` and fails closed for protected operations.

## 8. Approval Integrity

Approval integrity evidence must be sufficient to establish:

- the exact approval record content;
- the exact approved artifact revision;
- the attributable approver identity;
- the approver's eligibility evidence;
- decision time and scope;
- absence of undetected alteration;
- lineage to revocation or supersession events.

The contract is provider-neutral. It does not mandate a signature algorithm, certificate authority, identity provider, Git host, key-management system, or attestation product.

An integrity mechanism proves evidence integrity only within its governed assurance boundary. A cryptographic signature, commit signature, account login, or tool assertion does not by itself prove approval eligibility or approved scope.

## 9. Revocation of Approval

Approval revocation is a separate attributable governance decision. It identifies:

- the approval identity and exact revision being revoked;
- revoking authority identity and eligibility evidence;
- revocation scope;
- revocation decision timestamp and effective boundary;
- rationale or stable rationale reference;
- affected artifacts, decisions, adoptions, freezes, and operational uses;
- transition, rollback, or recovery references;
- audit and integrity evidence.

Revocation acts prospectively from its recorded effective boundary unless a higher Approved and Effective rule explicitly establishes another lawful treatment. Revocation does not delete, rewrite, or make false the fact that approval existed historically.

Approval revocation changes only current reliance on the identified approval evidence within its recorded scope. It does not by itself Withdraw the artifact from operational applicability, Supersede an artifact revision, Archive or Retire historical material, end an effectiveness or adoption interval, or identify a successor. Each such result requires its own eligible decision and evidence under the Governance Lifecycle Contract.

If revocation authority, scope, boundary, or integrity is unresolved, current approval validity is `Indeterminate` and fails closed for protected operations. Cached decisions that relied on the approval must be invalidated or reevaluated.

## 10. Approval Supersession

Approval supersession replaces an approval record with an identified successor approval record. Supersession requires:

- predecessor and successor approval identities and exact revisions;
- successor approver eligibility;
- exact approved artifact identity and revision for each decision;
- scope and effective boundary;
- rationale;
- compatibility and affected-use analysis;
- transition, rollback, or recovery references;
- audit and integrity evidence.

A successor approval does not rewrite its predecessor or approve an artifact revision not explicitly identified by the successor. The predecessor may remain applicable only within an explicit preserved scope and interval. Ambiguous overlap or missing lineage is `Indeterminate` and fails closed for protected operations.

Approval supersession replaces approval evidence. It is distinct from artifact supersession, which identifies an artifact predecessor and successor under the Governance Lifecycle Contract. Neither event implies the other.

## 11. Immutable Approval History

Approval history is append-only in meaning. It retains:

- proposals and review evidence relevant to the decision;
- the approval event and exact evidence envelope;
- artifact and approval revisions;
- approver and eligibility evidence;
- scope, conditions, rationale, and timestamp;
- reliance by effectiveness, adoption, policy, change, and freeze decisions;
- amendments, corrections, revocations, supersessions, expiries, and closure;
- conflicts, failures, reevaluations, and recovery;
- confidentiality and integrity evidence.

Removal from an active index, cache, branch view, or user interface cannot delete canonical approval history. Redaction required by confidentiality policy must preserve authorized reconstructability and cannot falsify the decision.

A commit, push, merge, tag, release, synchronization, or publication event cannot create a new approval event, alter an existing approval decision, or substitute for canonical approval lineage.

## 12. AI Boundary

An AI system may, within authorized scope:

- prepare a Draft approval-evidence envelope;
- identify missing evidence;
- validate identities, revisions, and consistency;
- compare scope and authority evidence;
- recommend approval, rejection, escalation, or reevaluation;
- assemble authorized evidence for human review.

An AI system cannot:

- make or record the human approval decision;
- represent its own output as human approval;
- ratify a decision as human approval;
- impersonate a human approver or attribute AI output to one;
- approve its own authority, work, or evidence;
- infer approval from silence, prior behavior, a Git commit, push, merge, or tool success;
- expand the approver's authority or approval scope;
- revoke or supersede approval without a separately eligible human decision.

AI preparation or validation never converts a Draft approval record into valid approval evidence.

## 13. Failure Behavior

Approval evaluation returns `Indeterminate` when required evidence is missing, stale, conflicting, unauthorized, revision-mismatched, unverifiable, or outside scope. This includes unresolved:

- approval identity;
- approver identity or eligibility;
- artifact identity, version, or revision;
- approval decision, scope, conditions, or timestamp;
- authority or delegation chain;
- revocation or supersession state;
- confidentiality eligibility;
- integrity or canonical lineage.

`Indeterminate` fails closed for protected operations. Missing approval never becomes approval through default, elapsed time, repetition, publication, Git history, AI confidence, or successful execution.

Later loss of approver authority produces the prospective reevaluation result defined in Section 7. Missing or conflicting evidence about that loss, its effective boundary, an asserted preservation rule, or a stricter specialized rule is `Indeterminate`; it cannot be treated as continuing approval validity by default.

## 14. Relationship to Other Governance States

Approval is one input to governance lifecycle evaluation and to an operation-specific Policy Decision. It does not by itself produce a Policy Decision `Allow` or establish:

- Effective applicability;
- Adopted scope;
- Deprecated, Withdrawn, Superseded, Archived, or Retired disposition;
- Design Frozen protection;
- implementation, deployment, or runtime state.

Those conditions require their own eligible decisions and evidence under the applicable contracts. A later state decision cites the exact approval record on which it relies.

Approval of a delegated variance satisfies only the variance's approval-evidence requirement. It does not create variance eligibility, effectiveness, authority, delegation, waiver, adoption, implementation, deployment, or execution authorization. Those results remain subject to the Delegated Variance, Authority and Delegation, Governance Lifecycle, and Policy Decision Contracts as applicable.

## 15. Deferred Decisions

Later Phase 1 work may define approval-record serialization, signature and attestation mechanisms, identity-provider integration, retention periods, redaction methods, approval routing, and validation implementation.

Deferral creates no approval record, approval decision, authority, schema, registry value, adoption, implementation authorization, or Design Freeze.
