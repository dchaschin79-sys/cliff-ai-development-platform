# Policy Decision Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-POLICY-DECISION |
| Version | 0.1.1 |
| Lifecycle state | Draft |
| Scope | Provider-neutral policy evaluation and decision evidence |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Foundation reference | CADP-ARCH-FOUNDATION v0.2.0 |
| Canonical artifact reference | CADP-CONTRACT-CANONICAL-ARTIFACT v0.1.0 |
| Metadata registry reference | CADP-CONTRACT-METADATA-REGISTRY v0.1.1 |
| Step 2 baseline | Git revision `a9f41d31875883df48e404f6787cc51b0ce7a941` |
| Related Draft contracts | CADP-CONTRACT-AUTHORITY-DELEGATION v0.1.1; CADP-CONTRACT-DELEGATED-VARIANCE v0.1.1 |

## 1. Purpose

A policy decision is the evidence-backed evaluation of applicable governed rules for a specific subject, requested operation, target resource, scope, purpose, context, and point in time.

The decision records what was evaluated, which canonical revisions controlled, which authority, delegation, variance, confidentiality, and state evidence was used, and why one provider-neutral outcome was produced.

A policy decision does not create a rule, authority class, delegation, variance, approval, or Product Binding. It applies only to the exact evaluated inputs and does not become precedent by repetition or caching.

## 2. Decision Inputs

Every policy evaluation requires an immutable input manifest identifying:

- subject identity;
- subject roles;
- requested operation;
- target resource or artifact identity and revision;
- scope;
- declared purpose;
- evaluation time;
- canonical rule identities and exact revisions;
- authority and delegation evidence;
- variance evidence when asserted;
- confidentiality and source-authorization context;
- relevant current-state evidence and freshness;
- evaluator identity and version.

Inputs remain independently classified. A subject role does not imply delegation, a target path does not resolve artifact identity, and a prior decision does not replace current rule or confidentiality evidence.

Missing a required input does not default to an empty, public, harmless, or authorized value.

## 3. Decision Outcomes

Policy decisions use only these outcomes:

- **Allow:** the requested operation is permitted for the exact subject, resource, scope, purpose, inputs, constraints, and interval evaluated.
- **Deny:** an applicable controlling rule prohibits the operation. The decision identifies the controlling prohibition without disclosing unauthorized information.
- **Indeterminate:** required facts, canonical identity, authority, confidentiality, integrity, or other authoritative evidence cannot be resolved safely.
- **Not Applicable:** the evaluated rule does not govern the declared request. For an aggregate decision, this outcome is valid only when no evaluated rule governs the request.

Allow is not general permission and cannot be widened by analogy. Deny does not amend its controlling rule. Indeterminate is not a weak Deny or conditional Allow. Not Applicable does not establish that some other rule allows the operation.

## 4. Evaluation Sequence

At contract level, evaluation proceeds in this order:

1. Resolve the subject, target, canonical artifact identities, and immutable revisions.
2. Apply source authorization and confidentiality eligibility for retrieval, evaluation, rationale, provider use, and tool execution.
3. Determine applicable authority sources and their hierarchy.
4. Resolve scope, purpose, effective interval, lifecycle, applicability, and protection status.
5. Validate delegation identity, chain, operations, constraints, interval, and revocation state.
6. Enforce non-delegable and non-waivable boundaries.
7. Validate any delegated variance, source-rule permission, scope, approval, controls, and interval.
8. Resolve rule, delegation, and variance conflicts.
9. Produce and retain the provider-neutral outcome and evidence.

This sequence defines semantic dependencies rather than a policy-engine implementation. Confidentiality filtering may prevent the evaluator or requester from receiving otherwise relevant source content; ineligibility must be handled without unauthorized disclosure.

## 5. Higher-Authority and Deny Behavior

Evaluation follows these principles:

- an explicit applicable higher-authority prohibition controls over a lower Allow;
- lower authority cannot negate, reinterpret, or bypass higher authority;
- a valid bounded variance applies only when its source rule or a higher authority permits it;
- a variance cannot bypass a non-waivable boundary or amend its source rule;
- missing evidence never becomes Allow;
- an invalid or unresolved delegation cannot supply authority;
- conflicting applicable authority that cannot be resolved produces Indeterminate;
- Indeterminate fails closed for protected operations.

This contract does not prescribe a universal conflict-resolution algorithm beyond these safety and precedence boundaries. Applicable authority contracts may define more specific deterministic behavior without changing the four outcomes.

## 6. Decision Evidence

Every retained policy decision identifies:

- stable decision ID;
- immutable input manifest identity and revision;
- canonical rule identities and revisions;
- authority and delegation records;
- variance records when evaluated;
- outcome;
- full internal rationale or stable reference;
- controlling rule or the reason no rule applied;
- evaluation timestamp;
- evaluator identity and version;
- integrity evidence;
- decision expiry or re-evaluation triggers.

Decision evidence also records relevant constraints, redaction state, confidentiality class, and affected operation. The evidence must allow an authorized reviewer to reproduce the decision without relying on a conversation, transient cache, or unversioned model state.

An outcome label without its evidence envelope is not a valid retained policy decision.

## 7. Decision Freshness

A decision requires re-evaluation when any relevant bound input changes, including:

- rule identity, revision, lifecycle, or effective interval;
- authority class, source, or approval revision;
- delegation validity, scope, interval, or revocation state;
- variance revision, controls, monitoring state, expiry, or revocation;
- confidentiality classification, provider eligibility, or source authorization;
- subject identity or role;
- target artifact identity or revision;
- purpose or requested operation;
- current-state evidence or freshness;
- evaluator policy or version where compatibility is not established.

Freshness is evaluated at use time. A decision may be historically valid and currently stale; history is retained, but stale decisions cannot authorize protected operations.

## 8. Explainability

A policy decision must be explainable to an authorized reviewer while protecting information the requester is not permitted to view.

The evidence model supports:

- a full internal rationale for authorized audit and review;
- a redacted requester rationale that explains the outcome without exposing restricted rules, data, identities, or security controls;
- stable reason codes in a later controlled registry.

Redaction cannot falsify the outcome or substitute a different controlling rule. When even the existence of a source is restricted, the requester-facing explanation may be bounded, while the protected internal evidence remains reconstructable.

This contract defines no reason-code values.

## 9. Caching and Reuse

A prior decision may be reused only when every bound input remains equivalent, authorized, compatible, and fresh. Reuse records the prior decision identity and the evidence used to establish equivalence.

A cached Allow must never outlive:

- the source rule's validity;
- authority and delegation validity;
- variance validity and compensating-control evidence;
- confidentiality and provider eligibility;
- subject role and scope eligibility;
- target artifact revision;
- current-state freshness requirements;
- the decision's expiry.

Failure to establish equivalence produces Indeterminate for protected operations. Cache availability, age alone, prior success, or matching request text is insufficient.

Deny and Not Applicable decisions also require freshness before operational reuse. Historical decisions remain audit evidence after operational expiry.

## 10. Evaluation Failure

Evaluation returns Indeterminate when:

- an authoritative rule is missing or cannot be resolved;
- canonical source claims conflict;
- required source or evidence revisions are stale;
- subject, evaluator, or target identity is unresolved;
- scope, purpose, operation, or effective interval is unresolved;
- delegation is invalid, expired, revoked, excessive, or cyclic;
- variance eligibility or validity is uncertain;
- confidentiality classification, source authorization, or provider eligibility is missing;
- the evaluator fails or its version cannot be established;
- integrity evidence is missing or broken;
- applicable rules conflict without a valid resolution.

Indeterminate fails closed for protected operations and is retained with failure evidence. Evaluator failure must not be converted to Allow by a caller, adapter, or cache.

## 11. Human Review and Escalation

The decision process reserves human escalation when:

- policy requires explicit human approval;
- an Indeterminate outcome affects a consequential operation;
- applicable rules or authority sources conflict;
- a delegated variance is requested or requires review;
- emergency authority is invoked;
- confidentiality policy requires restricted human adjudication.

Escalation is a request for a governed human action. It does not imply approval, permission, variance eligibility, or a different policy outcome. The human decision must cite its authority source and exact evaluated revisions.

AI may prepare escalation evidence and recommendations but cannot record human approval or expand its authority through escalation.

## 12. Audit and Privacy

Decision evidence must be:

- attributable to identified subjects, evaluators, and decision actors;
- immutable or tamper-evident;
- bound to canonical input revisions;
- confidentiality-aware and purpose-limited;
- retained according to the applicable evidence policy;
- sufficient for authorized reconstruction;
- protected from unauthorized rationale, rule, identity, or data disclosure;
- linked to re-evaluation, supersession, rollback, or recovery events.

Logging and derived indexes inherit the decision evidence's confidentiality constraints. An audit record may prove that a protected rule controlled without exposing the rule to an ineligible requester.

Deletion of disposable caches cannot delete retained decision evidence required by audit policy.

## 13. Deferred Decisions

Later Phase 1 work will define:

- policy engine and execution architecture;
- rule language;
- reason-code registry values;
- caching technology and equivalence implementation;
- evidence schema;
- identity-provider integration;
- enforcement, Git-host, CI/CD, and tool adapters;
- retention periods and redaction implementation.

Deferral creates no policy decision, approval, delegation, variance, registry value, or authorization.
