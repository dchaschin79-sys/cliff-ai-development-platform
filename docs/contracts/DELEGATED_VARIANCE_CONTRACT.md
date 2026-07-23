# Delegated Variance Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-DELEGATED-VARIANCE |
| Version | 0.1.1 |
| Lifecycle state | Draft |
| Scope | Bounded deviations from applicable CADP rules |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Foundation reference | CADP-ARCH-FOUNDATION v0.2.0 |
| Canonical artifact reference | CADP-CONTRACT-CANONICAL-ARTIFACT v0.1.0 |
| Metadata registry reference | CADP-CONTRACT-METADATA-REGISTRY v0.1.1 |
| Step 2 baseline | Git revision `a9f41d31875883df48e404f6787cc51b0ce7a941` |

## 1. Purpose

A delegated variance is a bounded, explicitly approved deviation from an otherwise applicable CADP rule. It allows a recorded operation or artifact scope to satisfy a higher-authorized alternative under defined risk, evidence, monitoring, and termination controls.

A variance is not:

- an authority tier;
- a permanent override;
- a hidden waiver;
- an informal agreement;
- precedent by default;
- permission to alter the source rule;
- evidence that the source rule is defective.

The variance derives eligibility from the rule that permits variance or from a higher authority that expressly permits consideration. It has no authority independent of that source.

This contract defines variance mechanics only. It creates no variance record, non-waivable registry value, product rule, or approval.

## 2. Required Variance Identity

Every variance is a governed artifact under the Canonical Artifact Contract and identifies:

- stable variance ID;
- requesting subject identity and role;
- approving authority identity and eligibility evidence;
- canonical source rule identity and exact revision;
- affected operation, resource, or artifact;
- scope;
- rationale;
- risk analysis;
- compensating controls;
- effective interval and explicit expiry;
- revocation conditions and authority;
- monitoring obligations;
- rollback or recovery reference;
- approval and integrity evidence.

File location, issue discussion, verbal agreement, or tool configuration cannot substitute for the variance identity and envelope. Approval binds to the exact variance and source-rule revisions.

## 3. Eligibility

A variance may be considered only when:

- the applicable source rule explicitly permits variance; or
- a higher Approved and Effective authority explicitly authorizes variance consideration for that rule and scope.

Permission to consider a variance is not approval of the requested variance. The requesting subject, approving authority, scope, source revision, risk evidence, and non-waivable boundaries are evaluated independently.

A lower authority cannot create a variance against a non-waivable higher rule. Technical ability, operational urgency, prior similar treatment, or repeated requests do not create eligibility.

## 4. Non-waivable Categories

At minimum, a variance cannot waive the following unless a higher Approved and Effective authority changes the governing rule through its authorized process:

- human approval requirements;
- authority-integrity controls;
- confidentiality restrictions;
- audit preservation;
- canonical source and revision integrity;
- prohibition on AI self-approval;
- prohibition on authority self-expansion;
- registry-bootstrap boundaries;
- safety controls explicitly designated non-waivable;
- legal or regulatory prohibitions;
- Design Freeze controls where the freeze record provides no variance path.

This is a minimum set rather than an exhaustive registry. An unclassified or ambiguous boundary is not presumed waivable.

## 5. Temporary and Minimum Scope

Every variance must be:

- narrowly scoped to identified subjects, operations, resources, and artifacts;
- time-bounded by an explicit effective interval;
- least permissive relative to the documented need;
- independently reviewable;
- revocable;
- auditable and bound to immutable evidence.

Open-ended variances are prohibited unless a higher authority explicitly defines a bounded renewal mechanism with re-evaluation. An interval without a defined end or termination condition is invalid. Similar products, repositories, components, or tasks do not inherit the variance automatically.

## 6. Compensating Controls

When a variance substitutes another control, the variance records:

- the source control objective;
- the substituted or additional control;
- evidence that the substitute addresses the relevant risk;
- accountable owner;
- monitoring method and cadence;
- failure threshold;
- termination or escalation condition;
- rollback or recovery action.

Compensating controls do not amend the source rule. Failure, staleness, or missing evidence for a required compensating control invalidates continued variance use unless an applicable higher rule defines a safer result.

## 7. Variance Lifecycle

Variance state follows the Foundation Architecture's orthogonal model.

### Review workflow

- **Draft:** proposed variance with no authority.
- **Review:** immutable candidate under defined review.
- **Approved:** variance revision with attributable human approval.
- **Archived:** inactive record retained for history and audit.

### Applicability or disposition

- **Effective:** active within the recorded scope and interval while every control remains valid.
- **Expired:** outside the approved interval.
- **Revoked:** terminated early by authorized action or a recorded invalidating condition.
- **Rejected:** reviewed request that never gained authority.
- **Superseded:** replaced by an identified variance revision.

`Revoked` is a variance-specific disposition candidate and requires later controlled registration before normative use. It is not an authority class. Approval and effectiveness remain separate; only an Approved and Effective variance can apply.

Historical approval validity and current operational validity are distinct. An approval that was valid when recorded remains immutable historical evidence. It shall not be rewritten, invalidated, or removed merely because the approving authority later loses its role or scope, expires, or is revoked.

Later loss of the approving authority is a prospective reevaluation event at the effective authority-loss boundary. Unless a higher Approved and Effective governing contract explicitly preserves operational validity, current operational use of the variance is Indeterminate and fails closed from that boundary until a new governed variance revision receives valid approval. This prospective result does not retroactively revoke the historical approval or create a new lifecycle state.

Archived records retain their historical disposition. Expired, Revoked, Rejected, Superseded, or Archived variances have no current effect except for historical reconstruction or an explicitly preserved legacy evaluation.

## 8. Renewal

Renewal is a new governed decision, not an automatic extension. It requires:

- fresh operational and monitoring evidence;
- renewed risk assessment;
- exact current source-rule identity and revision;
- a new immutable variance revision;
- new approval evidence;
- confirmation that correcting or clarifying the permanent rule is not more appropriate;
- a new bounded interval and termination conditions.

No automatic, tacit, or usage-based renewal is permitted. A renewal request submitted after expiry does not retroactively authorize operations during the gap.

## 9. Conflict and Precedence

A variance:

- cannot override higher authority;
- applies only to its recorded subject, operation, resource, scope, and interval;
- does not amend the source rule;
- does not automatically apply to similar cases;
- loses effect if the source rule is superseded unless the variance is re-evaluated against the successor;
- loses effect if required compensating controls fail or become unverifiable;
- cannot combine with another variance to produce authority neither variance possesses independently.

Where variances overlap, CADP evaluates each approving authority, source rule, revision, scope, effective interval, compensating control, and non-waivable boundary. Higher-authority prohibition controls over a lower variance. Unresolved overlap or conflict is Indeterminate.

## 10. Failure Behavior

Variance evaluation returns Indeterminate when:

- the canonical source rule or exact revision cannot be resolved;
- approving authority is missing, invalid, or outside scope;
- variance scope, subject, operation, or resource is ambiguous;
- the variance is expired, revoked, or not Effective;
- required compensating-control evidence is missing or stale;
- the source rule changed without re-evaluation;
- the variance conflicts with a non-waivable boundary;
- multiple variances conflict or produce ambiguous combined scope;
- approval evidence is missing, stale, self-asserted, or revision-mismatched;
- confidentiality eligibility or integrity evidence is unresolved.

Indeterminate fails closed for protected operations. Missing evidence never becomes permission, and operational urgency does not change the outcome.

Later loss of the approving authority's role, scope, effective interval, or valid authority produces the prospective Indeterminate result defined in Section 7 unless an applicable higher Approved and Effective governing contract explicitly preserves operational validity or a new governed variance revision has received valid approval.

## 11. Audit and Learning

Variance evidence retains:

- request and requester identity;
- source rule and revision;
- review and decision;
- approving authority and approval evidence;
- authority-loss event and effective timestamp;
- prospective reevaluation and cache-invalidation evidence;
- resulting disposition or new approved variance revision;
- rationale and risk analysis;
- compensating-control evidence and monitoring history;
- incidents and control failures;
- amendments, renewals, revocation, expiry, and closure;
- affected decisions and operations;
- rollback or recovery actions;
- integrity and confidentiality evidence.

Closure review should determine whether repeated or structurally similar variances indicate ambiguity, infeasibility, or a defect in the source rule. A repeated pattern may inform a future governed rule revision, but repetition does not itself amend policy, establish precedent, or create authority.

## 12. Deferred Decisions

Later Phase 1 work will define:

- variance schema and field-level validation;
- risk-scoring method;
- compensating-control monitoring implementation;
- renewal and revocation workflow tooling;
- exact non-waivable registry values;
- variance-specific disposition registration;
- signing and attestation mechanisms.

Deferral creates no variance, registry value, approval, or authorization.
