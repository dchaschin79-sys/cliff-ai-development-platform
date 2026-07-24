# Governance Authority Model Architecture Design Proposal

| Field | Value |
| --- | --- |
| Proposal ID | CADP-ADP-GOVERNANCE-AUTHORITY-MODEL |
| Version | 0.3.0 |
| Revision | 3 |
| Status | Draft |
| Classification | Non-normative |
| Document type | Architecture Proposal |
| Governance authority | None |
| Implementation authority | None |
| Scope | Exploratory governance authority and decision-scoped applicability model |
| Repository baseline considered | `8277e268adeb3f50badb5b87f952bb9b8aa859f3` |

This proposal has no governance authority. It does not amend, interpret authoritatively, approve, adopt, supersede, or make Effective any existing artifact. It creates no authority assignment, approval, lifecycle event, Design Freeze, Product Binding, policy decision, implementation authorization, or operational permission.

The terms `must`, `required`, and `prohibited` in this document describe constraints of the proposed architecture only. They do not impose current governance obligations. Any normative effect would require separately governed source artifacts, exact revision binding, independent review, eligible human approval, effectiveness, and applicability under the accepted CADP governance model.

## 1. Executive Summary

CADP requires a deterministic way to establish which authority evidence and governance controls apply to a specific governance act. Revision 1 proposed three repository operating modes—Single Maintainer, Multi Maintainer, and Enterprise Governance—as the primary way to vary those requirements. Independent architecture review found that this approach combined unrelated facts, made authority evaluation circular, conflated applicability evaluation with control activation, assigned some controls to an unsound `Enterprise-only` category, mixed several authority-classification axes, left normative ownership unclear, and did not sufficiently protect legacy evidence.

Revision 2 replaced repository-mode selection with the proposed **Decision-Scoped Governance Applicability Model**. Revision 3 preserves that architecture and closes focused review findings concerning universal eligibility, complete rule discovery, Decision Context purity, semantic ownership, scope reconciliation, and cross-repository snapshot coherence.

Its principal architectural rule is:

> Governance requirements are derived from the context of a specific Governed Operation, not from a coarse classification of the repository or organization.

The proposed model has nine cooperating concepts:

1. **Governed Operation** defines the exact act being evaluated.
2. **Universal Eligibility Gate** applies mandatory source-authorization, confidentiality, provider, and purpose eligibility before information enters evaluation.
3. **Universal Authority Core** establishes a non-circular minimum authority and evidence boundary before contextual evaluation.
4. **Decision Context** records immutable independent facts relevant to applicability.
5. **Applicable Rule Universe** establishes the complete authoritative rule boundary for the operation.
6. **Applicability Evaluation** evaluates the complete rule universe for every Governed Operation.
7. **Governance Controls** are activated conditionally from the resolved context.
8. **Authority Assignments** connect attributable actors to bounded functions without conflating role, source, permission, or technical custody.
9. **Resolution Result** preserves eligibility, rule-universe closure, inputs, rules, evidence, unresolved conditions, and outcome needed for audit and later policy evaluation.

Eligibility gating and applicability evaluation are universal; individual governance controls may be conditional. Multiple controls can apply simultaneously and form a conjunctive requirement set unless a future Approved and Effective normative rule supplies an explicit precedence resolution. Missing eligibility, an incomplete rule universe, or missing context or evidence cannot silently produce a less restrictive result.

Labels such as Single Maintainer, Multi Maintainer, Enterprise Governance, open source, regulated, or federated may remain illustrative profiles. They have no authority and cannot determine requirements, replace Decision Context, bypass applicability evaluation, or operate as mutually exclusive normative modes.

Revision 3 retains the recommendation for one future normative owner, tentatively named the **Governance Applicability Contract**, for shared applicability semantics. Existing contracts would retain their own domain meanings. This proposal does not create that contract or authorize any contract or Foundation revision.

## 2. Problem Statement

Current CADP sources separate canonical identity, human authority, approval evidence, governance lifecycle, Policy Decisions, delegation, and Design Freeze. They also preserve provider neutrality, immutable history, exact revision binding, explicit scope, and fail-closed behavior.

The Phase 1 Step 4 Approval Remediation Package records a concrete unresolved case: the existing approval assertion cannot currently be relied upon deterministically because required identity, authority-source, eligibility, separation, conflict, confidentiality, delegation, and integrity evidence is incomplete. The package preserves the historical assertion and identifies current reliance as `Indeterminate`; it does not invalidate history or create corrected approval.

That case exposes a broader architectural question. Governance controls do not vary reliably with repository size or organizational label:

- a one-maintainer repository may have a security-sensitive or externally regulated decision requiring independent evidence;
- a collective open-source project may require quorum and dissent evidence without being an enterprise;
- an enterprise repository may have a low-impact documentation operation that does not require committee action;
- a cross-repository operation may require several authority sources even when each repository is small;
- a repository may contain concurrent decisions with different impact, confidentiality, reversibility, and external obligations.

Repository-level modes are therefore too coarse to determine governance requirements. They combine maintainer count, organizational formality, collective authority, external obligations, risk, actor independence, cross-repository scope, and decision impact into a single label even though those facts can change independently.

The architecture needs to answer, for each Governed Operation:

1. Which minimum authority and evidence facts are necessary before contextual rules can be evaluated?
2. Which independent contextual facts are relevant?
3. Which governance controls apply?
4. Which actor functions and relationships are required?
5. What evidence demonstrates satisfaction?
6. Which facts remain unresolved?
7. Which canonical rule revisions and evidence produced the result?
8. How is the result preserved when governance evolves?

The answer cannot rely on repository ownership, job title, technical access, AI inference, a repository profile, or a prior successful operation. It must remain compatible with the existing CADP authority hierarchy and provider-neutral Policy Decision outcomes.

## 3. Goals

Revision 3 preserves the Revision 2 architecture and is intended to:

1. make the specific Governed Operation the primary evaluation scope;
2. separate minimum authority validation from conditional governance control selection;
3. represent applicability through orthogonal and composable Decision Context facts;
4. make applicability evaluation universal without making every control universally active;
5. prevent organization labels from granting authority or weakening controls;
6. separate actor form, responsibility function, authority source, scope, operation permission, validity, delegation, and technical custody;
7. produce deterministic, attributable, revision-bound evaluation evidence;
8. support one-maintainer, multi-maintainer, collective, enterprise, regulated, and federated contexts without different authority architectures;
9. preserve historical decisions and legacy evidence without retroactive reclassification;
10. provide one future normative ownership boundary for shared applicability semantics;
11. preserve Foundation supremacy and existing contract separation of concerns;
12. remain product-independent, provider-neutral, auditable, and fail closed when protected decisions are unresolved; and
13. permit prospective governance evolution without rewriting historical meaning;
14. apply mandatory source, confidentiality, provider, and purpose eligibility before Decision Context construction;
15. prove closure of the Applicable Rule Universe before deterministic evaluation can succeed; and
16. prevent reviewer availability, emergency or exception assertions, and operational constraints from suppressing applicable controls.

These are design goals for later consideration. They are not adopted requirements.

## 4. Non-Goals

This proposal does not:

- implement or revise a normative contract;
- modify or reinterpret the Foundation Architecture;
- create a Governance Applicability Contract;
- define registered artifact types, authority classes, roles, context values, controls, result codes, or other registry values;
- define a schema, API, database, policy engine, workflow engine, implementation class, automation, adapter, or user interface;
- select an identity provider, signature system, Git host, model provider, or other vendor;
- assign authority to an individual, collective body, repository owner, maintainer, reviewer, approver, or release authority;
- create approval, effectiveness, adoption, withdrawal, supersession, retirement, archival, or another lifecycle event;
- create or lift Design Freeze protection;
- create delegation, emergency authority, variance, exception, Product Binding, release authorization, or implementation authorization;
- determine controls for a product-specific decision;
- amend or validate the existing Step 4 approval assertion;
- rewrite historical approval or lifecycle evidence;
- authorize a Foundation or contract revision;
- declare this architecture accepted, Approved, Effective, Adopted, or Design Frozen; or
- authorize implementation or operational use.

## 5. Architectural Position and Boundaries

### 5.1 Current repository facts

At the repository baseline considered by this proposal:

- the Foundation Architecture is Version 0.2.0 and Draft;
- the relevant governance contracts are Draft contract candidates;
- the Governance Document Model is descriptive and non-normative;
- the current deterministic reliance status of the Step 4 approval assertion is `Indeterminate`;
- no repository permission, commit, approval package, review verdict, or proposal creates governance authority; and
- the existing Policy Decision Contract defines `Allow`, `Deny`, `Indeterminate`, and `Not Applicable` as provider-neutral outcomes.

This proposal does not alter those facts.

### 5.2 Proposed architecture

The Decision-Scoped Governance Applicability Model is a proposed semantic architecture for future governance design. It explains how shared applicability facts, authority assignments, and controls could be resolved without changing the domain meaning owned by existing contracts.

### 5.3 Future normative work

If the architecture is later accepted through an eligible human governance process, separate future work would be needed to:

- create one normative owner for shared applicability semantics;
- establish exact controlled vocabularies and evidence requirements;
- define compatibility with existing contracts;
- determine any minimal Foundation recognition;
- define prospective adoption and legacy assessment boundaries; and
- independently review and approve every normative revision.

None of that future work is authorized by this proposal.

### 5.4 Architectural invariants

The proposed model preserves the following boundaries:

- Foundation Architecture remains architecturally supreme.
- One canonical source controls each governed artifact identity and effective revision.
- Human authority is explicit, attributable, bounded, and independently evidenced.
- AI cannot create human approval or governance authority.
- Approval, effectiveness, adoption, protection, implementation, release, and runtime remain independent.
- Technical custody does not create governance authority.
- Historical meaning is not rewritten by current evaluation.
- Missing or conflicting evidence is exposed rather than defaulted.
- Source authorization, confidentiality eligibility, provider eligibility where applicable, and purpose eligibility are resolved before information enters Decision Context.
- Applicability evaluation cannot succeed until the complete Applicable Rule Universe is established.
- Decision Context contains immutable contextual facts and cannot suppress an otherwise applicable control.
- Shared applicability semantics have one future normative owner.
- Domain contracts retain their existing semantic ownership.
- Provider-specific systems may project or evaluate the model but cannot redefine it.

## 6. Decision-Scoped Governance Applicability Model

The proposed conceptual flow is:

```text
Governed Operation
        ↓
Universal Eligibility Gate
        ↓
Universal Authority Core
        ↓
Decision Context
        ↓
Applicable Rule Universe
        ↓
Applicability Evaluation
        ↓
Conjunctive Governance Controls
        ↓
Authority Assignment and Evidence Validation
        ↓
Attributable Resolution Result
        ↓
Operation-specific Policy Decision
```

The Resolution Result would be an input to, not a replacement for, the existing operation-specific Policy Decision. It would not itself create `Allow`, lifecycle state, approval, or authority. A successful deterministic result would require both universal eligibility and a Complete Rule Universe.

### 6.1 Governed Operation

#### Purpose

A Governed Operation is the exact governance act being evaluated. It establishes the smallest meaningful decision boundary.

Illustrative operations include:

- approving an exact architecture proposal revision;
- adopting an exact governance contract for a declared scope;
- declaring an Approved artifact Effective for a scope and interval;
- creating or lifting a Design Freeze;
- authorizing a release;
- delegating a bounded operation;
- changing a governance applicability policy; or
- recording a cross-repository decision.

#### Rationale

One repository may contain operations with different impact, risk, confidentiality, reversibility, and external obligations. Evaluating the operation avoids assigning one governance posture to an entire repository or organization.

#### Relationship to existing CADP governance

The Governed Operation aligns with the Authority and Delegation Contract and Policy Decision Contract, which already evaluate a specific subject, operation, resource, scope, and interval. It also aligns with lifecycle transition evidence, which identifies the exact target dimension and intended state.

#### Boundary and limitations

The operation identity does not grant permission, supply authority, or determine applicable controls by itself. A broad label such as “approve” is insufficient without the subject, exact artifact revision, scope, purpose, and decision boundary needed by applicable governance.

#### Future normative ownership and migration

The future shared applicability owner would define the common operation-identification boundary. Domain contracts would retain ownership of the meaning and prerequisites of their own operations. Existing records would not be rewritten merely to add a modern operation envelope.

### 6.2 Universal Eligibility Gate

#### Purpose

The Universal Eligibility Gate determines whether information is eligible to enter authority validation, Decision Context construction, applicability evaluation, and the resulting evidence record.

At the architectural level, the gate validates:

- source authorization;
- confidentiality eligibility;
- provider eligibility where a provider boundary is involved; and
- purpose eligibility.

These gates are universal. They are not conditional Governance Controls and cannot be deactivated by Decision Context, repository profile, organization type, operation urgency, exception request, or evaluator preference.

#### Rationale

Applicability cannot safely be evaluated from information that the evaluator is not authorized to retrieve, process, disclose, or send across an applicable provider boundary. Eligibility therefore precedes both the Universal Authority Core and Decision Context construction.

The gate evaluates whether information may participate in the declared operation and purpose. It does not decide whether the information is authoritative, whether a context assertion is correct, whether a Governance Control applies, or whether the final operation is permitted.

#### Relationship to existing CADP governance

The gate preserves the Foundation security and confidentiality boundary, which requires authorization and confidentiality filtering before retrieval and context assembly. It also preserves the Policy Decision Contract sequence, in which source authorization and confidentiality eligibility precede authority, applicability, and protection evaluation.

This proposal does not redefine either source. The future applicability architecture would consume their eligibility results and preserve the exact sources, revisions, purpose, provider boundary, and evaluation time on which those results depend.

#### Boundary and limitations

Information that has not passed the gate cannot be used to:

- validate the Universal Authority Core;
- construct or complete Decision Context;
- establish the Applicable Rule Universe;
- activate or satisfy a Governance Control;
- support a Resolution Result; or
- support an operation-specific Policy Decision.

An eligibility failure does not prove that the requested operation is otherwise prohibited or that the source is invalid for every purpose. It establishes only that the information is ineligible for the evaluated operation, purpose, subject, and provider boundary.

Missing, conflicting, stale, or unverifiable required eligibility evidence remains unresolved and cannot default to public, authorized, purpose-compatible, provider-compatible, or harmless. Existing CADP policy determines the resulting `Indeterminate` and fail-closed behavior for protected operations.

#### Future normative ownership and migration

Foundation retains the universal security and confidentiality boundary, and the Policy Decision Contract retains its evaluation semantics. The future shared applicability owner would define only how eligible inputs are admitted to the applicability process and traced in its Resolution Result. It would not own or weaken confidentiality, source-authorization, provider, or purpose policy.

Legacy evidence remains preserved even when it cannot be admitted to a current evaluation. Current ineligibility does not rewrite whether the evidence historically existed.

### 6.3 Universal Authority Core

#### Purpose

After the Universal Eligibility Gate succeeds, the Universal Authority Core establishes the minimum attributable authority and evidence boundary needed before conditional applicability can be evaluated.

At the architectural level, the core contains:

- attributable actor identity;
- actor form;
- authority function being exercised;
- authority source identity;
- authority source revision or other exact canonical identity;
- scope;
- permitted operation;
- validity interval;
- decision timestamp;
- decision subject and exact governed resource where applicable;
- evidence integrity; and
- revocation status at the relevant decision time.

#### Rationale

Conditional controls cannot determine whether the context source was eligible if context eligibility itself depends on those controls. The Universal Authority Core provides a bootstrap boundary that does not depend on a repository mode or on the final control set.

For context supplied by a human actor, the core would establish the actor's bounded eligibility to declare or attest the relevant context. For context derived from canonical sources, the core would establish the source identity, revision, provenance, and authorized derivation boundary. In both cases, the information must already have passed the Universal Eligibility Gate.

#### Relationship to existing CADP governance

The core does not replace the Authority and Delegation Contract, Approval Record Contract, or Canonical Artifact Contract. It organizes the minimum shared inputs those contracts already require: identity, source, exact revision, scope, operation, interval, integrity, and revocation evidence.

#### Boundary and limitations

Passing the Universal Authority Core would not:

- authorize the final Governed Operation;
- satisfy a conditionally activated control;
- establish approval, effectiveness, adoption, or Design Freeze;
- validate a delegation merely because one is referenced;
- make a context claim correct; or
- produce a Policy Decision `Allow`.

It establishes only that contextual evaluation can proceed from attributable and canonically resolvable inputs. Missing, conflicting, stale, out-of-scope, or unverifiable core evidence would prevent less restrictive defaulting and would be carried forward as unresolved.

#### Future normative ownership and migration

The Authority and Delegation Contract remains the owner of authority eligibility, authority dimensions, delegation validity, revocation, and authority evaluation results. The future shared applicability owner would own only the composition of the Universal Authority Core as a prerequisite for applicability evaluation: which existing authority results are required and how their identities and revisions are bound into the evaluation.

The shared applicability owner would not redefine or independently validate authority. Identity, lifecycle, canonical-source, approval, integrity, and confidentiality meanings remain with their existing owners. Legacy evidence would be assessed under contemporaneous rules rather than retrofitted into a fabricated core record.

### 6.4 Decision Context

#### Purpose

Decision Context records immutable independent facts that may affect which governance controls apply to the Governed Operation. It contains applicability facts, not resource availability, processing choices, exception requests, or conclusions that controls were satisfied.

Candidate dimensions include:

| Candidate dimension | Architectural question |
| --- | --- |
| Operation type | What exact governance act is being evaluated? |
| Artifact class | What kind of governed subject is affected? |
| Scope | Which platform, product, repository, component, cross-repository, or other bounded scope is affected? |
| Impact | What is the bounded consequence if the operation proceeds? |
| Reversibility | Can the operation be safely reversed, and under what boundary? |
| Security relevance | Does the operation affect security constraints or controls? |
| Safety relevance | Does the operation affect a declared safety boundary? |
| Legal or regulatory obligation | Does an external legal or regulatory source govern the operation? |
| Contractual obligation | Does an external contractual source activate governance evidence? |
| Confidentiality | Which handling or eligibility constraints affect the operation and evidence? |
| Cross-repository effect | Does the operation change or rely upon more than one canonical repository scope? |
| Collective authority requirement | Does a valid authority source require action by a collective body? |

These are candidate dimensions, not registered fields or values. `Immutable` means that each fact or attributable classification is fixed to its canonical evidence and revision for the evaluated snapshot. A changed fact or classification creates new context evidence; it does not mutate the context used by an earlier evaluation.

#### Rationale

The dimensions are orthogonal and composable. A decision may simultaneously be high impact, security relevant, cross-repository, contractually constrained, and subject to collective authority. No one label replaces those facts.

#### Relationship to existing CADP governance

Decision Context would reference canonical identity, scope, confidentiality, lifecycle, authority, and current-state evidence already owned by applicable CADP sources. It would not copy or reinterpret those source meanings.

#### Boundary and limitations

Decision Context cannot:

- grant authority;
- declare a control unnecessary without an applicable rule;
- infer missing facts from repository size or organization name;
- override a higher-authority source;
- convert an emergency assertion into valid emergency authority; or
- replace an immutable input manifest or Policy Decision.

Context facts must remain distinct from compliance conclusions. For example, “collective authority required” is a context fact sourced from an authority instrument; “quorum satisfied” is evidence evaluated against an activated control.

Reviewer availability, staffing, scheduling, operational capacity, emergency declarations, exception or variance requests, and asserted inability to satisfy a control are not applicability facts. They may affect execution sequencing, escalation, exception processing, or the evidence supplied during Control Satisfaction. They cannot deactivate, narrow, waive, or make `Not Applicable` an otherwise applicable control.

Decision Context is monotonic with respect to control protection: a contextual fact may activate a control or support a conclusive normative determination that a rule does not govern the operation, but absence, unavailability, inconvenience, urgency, or a requested exception cannot suppress a control. Missing or disputed contextual facts remain unresolved.

#### Scope reconciliation

The architecture uses several deliberately distinct scope relationships:

- **requested-operation scope** identifies what the Governed Operation proposes to affect;
- **eligibility scope** identifies the information, purpose, subject, and provider boundary admitted by the Universal Eligibility Gate;
- **authority scope** identifies where an actor or authority source may exercise a permitted operation;
- **contextual scope** records immutable facts about the affected platform, product, repository, component, or cross-repository boundary;
- **control scope** identifies the boundary governed by an activated control; and
- **result scope** identifies the exact intersection evaluated by the Resolution Result.

These scopes are not copies of one field and cannot supply one another. The Governed Operation is the canonical source of requested-operation identity. Other scopes reference that operation and state their own bounded relationship to it.

A successful deterministic evaluation requires every required scope relationship to be compatible. The result scope is the intersection of the eligible, authoritative, contextual, and control scopes; it cannot be broadened by union, inference, profile, or technical capability. Missing or conflicting scope relationships remain unresolved and cannot produce a successful deterministic result.

#### Future normative ownership and migration

The future shared applicability owner would define a minimal common vocabulary and the boundary for adding domain-specific facts. Consuming contracts could supply domain facts within that boundary without independently redefining shared dimensions. Prospective adoption would avoid forcing current structures onto earlier decisions.

### 6.5 Applicable Rule Universe

#### Purpose

The Applicable Rule Universe is the authoritative, scope-bound set of every rule source that could govern the exact Governed Operation at the evaluated point in time. It establishes rule-discovery completeness before individual applicability and control activation are evaluated.

#### Authoritative rule sources

Candidate authoritative sources include only canonically resolved, eligible sources recognized under the existing CADP authority hierarchy and lifecycle model, such as:

- applicable Foundation constraints and other higher-authority sources;
- the future shared applicability owner and its exact effective revision;
- applicable platform governance and contracts;
- applicable product-scoped governance, overlays, and bindings where independently valid;
- applicable ADRs within their exact scope;
- applicable authority instruments, delegations, and non-delegable boundaries;
- applicable external legal, regulatory, or contractual sources when a recognized governing source binds them to the operation; and
- explicit legacy bindings preserved under applicable governance.

This list describes source classes, not current authority, registry values, or a fixed rule catalog. Draft, unapproved, ineffective, ineligible, non-canonical, out-of-scope, or superseded sources do not acquire authority through inclusion in discovery.

#### Rule-discovery boundary

Discovery is bounded by the exact:

- Governed Operation and subject;
- requested-operation, authority, contextual, control, and result scopes;
- purpose;
- evaluation time;
- canonical artifact and rule revisions;
- applicable CADP version;
- applicable Product Binding version where one independently exists;
- confidentiality, source-authorization, and provider eligibility;
- authority hierarchy and effective intervals; and
- preserved legacy relationships.

The boundary identifies where authoritative rules must be sought. It does not define a search algorithm or implementation.

#### Completeness expectation and closure condition

Rule-universe closure requires evidence that:

1. every source class required by the discovery boundary has been accounted for;
2. every discovered source has a canonical identity and exact revision;
3. eligibility, lifecycle, scope, interval, hierarchy, and legacy status have been resolved;
4. restricted sources have been evaluated through an eligible path rather than silently omitted;
5. conflicts, inaccessible required sources, missing bindings, and unresolved source claims are recorded; and
6. no unresolved source gap could add, remove, narrow, or change an applicable control.

The Resolution Result classifies closure as:

- **Complete Rule Universe:** the discovery boundary is fully accounted for and no unresolved source gap could change the applicable control set.
- **Incomplete Rule Universe:** one or more required source classes, identities, revisions, eligibility results, bindings, or conflicts remain unresolved.

These are rule-discovery completeness classifications, not lifecycle states, authority classes, or new Policy Decision outcomes.

An Incomplete Rule Universe cannot produce a successful deterministic applicability evaluation. It results in an unresolved applicability result and supplies `Indeterminate` to the operation-specific Policy Decision under the existing Policy Decision Contract. Inaccessible, unknown, or omitted rules cannot be treated as non-applicable.

#### Future normative ownership and migration

The future shared applicability owner would own the discovery boundary, completeness expectation, and closure semantics. Existing sources would retain their authority, lifecycle, and domain meanings. The owner would not create authority merely by discovering a source.

This proposal defines no catalog implementation, query mechanism, registry, algorithm, or source adapter.

### 6.6 Applicability Evaluation

#### Purpose

Applicability Evaluation determines which rules in the Complete Rule Universe govern the exact operation and immutable Decision Context.

#### Rationale

Applicability and control satisfaction are different questions:

- Applicability asks whether a control governs the operation.
- Activation adds every applicable control to the requirement set.
- Satisfaction asks whether valid authority and evidence meet that control.

Applicability Evaluation is universal for every Governed Operation. An individual control may be `Not Applicable`, but evaluation of whether it applies is never optional. Evaluation cannot begin from an Incomplete Rule Universe and cannot declare completion while rule-universe closure remains unresolved.

#### Relationship to existing CADP governance

The model preserves the Policy Decision Contract's distinction between `Not Applicable` and permission. A rule being `Not Applicable` does not establish that another rule permits the operation. The final operation still requires the existing provider-neutral Policy Decision over every applicable input.

#### Boundary and limitations

Applicability cannot be selected by convenience, AI confidence, repository profile, contributor count, reviewer availability, operational capacity, emergency or exception assertion, or the desired outcome. A rule evaluation would need exact rule identity and revision, triggering facts, scope, effective interval, precedence, normative source, and attributable rationale.

Missing required context, an incomplete rule universe, or unresolved rule identity would not default the control to inactive. It would remain unresolved and fail closed where the operation is protected under existing governance.

Applicability resolution is monotonic with respect to protections. Resource unavailability, urgency, an emergency declaration, an exception or variance request, or inability to satisfy a control may add escalation, alternative-path, ratification, or exception-processing requirements. None may remove an otherwise applicable control or convert it to `Not Applicable`.

#### Future normative ownership and migration

The future shared applicability owner would own common applicability semantics, rule-universe closure, rule identity, precedence, and multi-condition resolution. This proposal defines no rule language, algorithm, schema, or registry values.

### 6.7 Governance Controls

#### Purpose

A Governance Control is a conditionally activated requirement that must be evaluated before the Governed Operation can receive its final Policy Decision.

Illustrative controls include:

- independent review;
- separation of duty;
- conflict-of-interest evaluation;
- delegation evidence;
- quorum;
- recorded vote;
- dissent capture;
- external review;
- release authorization;
- multi-party approval;
- emergency ratification; and
- periodic recertification.

These examples do not create current controls or applicability rules.

Source authorization, confidentiality eligibility, provider eligibility where applicable, and purpose eligibility are not conditional Governance Controls. They belong to the Universal Eligibility Gate and are evaluated before Decision Context construction.

#### Rationale

Controls are activated from actual context conditions rather than organization labels. Quorum, for example, follows from a valid collective authority source—not from an `Enterprise` label. Independent review follows from an applicable risk, impact, authority, contract, or other governing condition—not from maintainer count alone.

#### Relationship to existing CADP governance

Each domain contract retains the meaning of its own control. The Approval Record Contract continues to own approval meaning and evidence. The Governance Lifecycle Contract continues to own lifecycle transitions. The Design Freeze Contract continues to own freeze semantics and freeze-safe evidence. The Authority and Delegation Contract continues to own delegation validity.

#### Boundary and limitations

The proposal removes `Enterprise-only` as a normative category. It does not make committee, quorum, dissent, recertification, or separation controls universal. Their applicability would be derived from actual conditions and an applicable normative source.

Applicable controls form a conjunctive set: every activated control remains independently necessary unless an explicit Approved and Effective higher or governing rule resolves a conflict. One satisfied control cannot cure an invalid independent input.

#### Future normative ownership and migration

The future shared applicability owner would define activation and composition semantics. Domain contracts would retain control meaning and domain-specific evidence requirements. This avoids duplicating approval, lifecycle, freeze, or authority semantics inside the shared contract.

### 6.8 Authority Assignments

#### Purpose

Authority Assignments connect an attributable actor to a bounded responsibility without treating a title, repository permission, or actor form as self-validating.

The proposed model separates these axes:

| Axis | Question answered | Illustrative values or evidence |
| --- | --- | --- |
| Actor form | What kind of entity acted? | Individual human, collective human body, external legal or regulatory authority. |
| Responsibility function | What governance function was performed? | Context declarer, reviewer, approver, architecture authority, release authority, compliance reviewer, records custodian. |
| Authority source | Why may the actor perform the function? | Canonical charter, appointment, approved delegation, board resolution, contract, law, regulation, or other governed instrument. |
| Scope | Where and over what subject may the authority be exercised? | Platform, product, repository, component, artifact, operation class, or another explicit boundary. |
| Permitted operation | Which exact act may the actor perform? | Review, approve, declare Effective, adopt, freeze, release, delegate, or another explicitly sourced operation. |
| Validity interval | When is the assignment eligible? | Exact start and end or explicitly continuing boundary, subject to current revocation and supersession evidence. |
| Delegation | Is eligibility direct or supplied through a valid bounded chain? | Exact delegation identity, source, revision, operations, scope, interval, constraints, and revocation state. |
| Technical custody | Who can technically administer or change the repository or system? | Repository ownership, hosting administration, merge capability, deployment access, or records custody. |

#### Rationale

Revision 1 mixed actor forms, functions, and technical custody in one authority-type list. That allowed labels such as Repository Owner, Approver, Release Authority, and Governance Board to appear equivalent even though they answer different questions.

Revision 2 established, and Revision 3 preserves, the following normalization:

- an individual or collective body is an actor form;
- reviewer or approver is a responsibility function;
- a charter, appointment, delegation, contract, law, or resolution is an authority source;
- permission is bounded to an operation, scope, and validity interval;
- delegation is a separately validated source path; and
- repository ownership is technical custody, not governance authority.

#### Relationship to existing CADP governance

The Authority and Delegation Contract remains the normative-capable owner of authority eligibility and delegation mechanics. The Approval Record Contract remains the owner of approval evidence. This proposal adds no role, authority class, or assignment.

#### Boundary and limitations

A single person may hold several functions only where applicable higher governance permits that combination and required conflict or separation controls are satisfied. Several function labels cannot simulate independent actors. A collective body would need attributable evidence that it validly acted under its authority source. An automated system may supply supporting evidence but cannot become the human authority or create human approval.

Technical custody may coexist with governance authority only when separate authority evidence establishes it. Tool access or successful execution never fills a missing assignment axis.

#### Future normative ownership and migration

The future shared applicability owner would define how applicable controls request authority functions and relationships. Authority assignment validity would continue to be evaluated under the Authority and Delegation Contract. Existing title-based records would be assessed from their actual evidence rather than automatically translated into new roles.

### 6.9 Resolution Result

#### Purpose

The Resolution Result is the attributable evidence of applicability resolution for one Governed Operation.

At the architectural level, it records:

- evaluated operation and exact subject;
- Universal Eligibility Gate inputs, source revisions, and results;
- Decision Context identity or revision;
- canonical context sources and revisions;
- Applicable Rule Universe identity or bound manifest;
- rule-discovery boundary and authoritative source classes evaluated;
- rule-universe closure classification as Complete Rule Universe or Incomplete Rule Universe;
- unresolved, inaccessible, conflicting, or missing rule sources;
- applicability rules evaluated and their exact revisions;
- applicable controls;
- non-applicable controls and attributable rationale;
- authority assignments evaluated;
- evidence required;
- evidence supplied;
- unresolved conditions and conflicts;
- evaluation timestamp;
- evaluator identity and version;
- integrity and lineage evidence;
- re-evaluation triggers; and
- final evaluation status.

#### Rationale

An outcome without its inputs and rules cannot be reproduced or audited. The result therefore preserves both activated and non-activated controls, including why a control was not applicable.

#### Relationship to existing CADP governance

The result would be a governed input to the operation-specific Policy Decision. It would align with the Policy Decision Contract's immutable input manifest, source authorization, confidentiality eligibility, explainability, freshness, audit, and four provider-neutral outcomes.

#### Boundary and limitations

The result would not:

- create a lifecycle state;
- grant authority;
- create approval;
- replace the domain contracts;
- become precedent through repetition;
- authorize implementation or execution; or
- permit reuse when bound inputs have changed.

This proposal does not define a new status registry. Exact per-control evaluation states and their mapping to `Allow`, `Deny`, `Indeterminate`, and `Not Applicable` remain future normative decisions. Unresolved required inputs must remain visible and cannot be summarized as satisfaction.

A result based on an Incomplete Rule Universe cannot state or imply successful deterministic evaluation, satisfaction, permission, or `Not Applicable` for the aggregate operation. It retains the incomplete discovery evidence and supplies an unresolved result to the Policy Decision.

#### Future normative ownership and migration

The future shared applicability owner would define the conceptual result semantics. Serialization, storage, evaluator architecture, and machine interfaces remain separate implementation work.

## 7. Deterministic Evaluation Order

The proposed resolution order is:

### Step 1 — Identify the Governed Operation

Resolve the requested act, subject, exact artifact or resource identity, immutable revision where applicable, scope, purpose, and evaluation time.

### Step 2 — Apply the Universal Eligibility Gate

Validate source authorization, confidentiality eligibility, provider eligibility where applicable, and purpose eligibility before information is used for authority validation or context construction. Ineligible or unresolved information cannot enter later phases.

### Step 3 — Validate the Universal Authority Core for context declaration

Establish the attributable actor or canonical source permitted to supply each required context fact. Validate the source identity and revision, function, scope, operation, validity interval, integrity, and relevant revocation status without relying on a repository profile or the conditional control set being computed.

The future applicability owner composes the required authority results; the Authority and Delegation Contract remains the owner of authority validation and its result.

### Step 4 — Resolve Decision Context from eligible canonical evidence

Assemble immutable independent context facts only from sources admitted by the Universal Eligibility Gate. Preserve their identities, revisions, effective boundaries, confidentiality constraints, and provenance. Record missing or conflicting facts as unresolved. Keep reviewer availability, operational constraints, emergency declarations, and exception or variance requests outside applicability facts.

### Step 5 — Establish and close the Applicable Rule Universe

Apply the rule-discovery boundary, account for every required authoritative source class, bind exact rule revisions, and resolve eligibility, scope, lifecycle, hierarchy, interval, legacy, and conflict evidence.

If closure cannot be established, classify the universe as Incomplete Rule Universe and stop successful deterministic applicability resolution. Preserve the incomplete evidence for an `Indeterminate` Policy Decision.

### Step 6 — Evaluate every rule in the Complete Rule Universe

Evaluate every rule in the Complete Rule Universe against the immutable Decision Context. Record applicable and non-applicable outcomes with exact normative rule identities, revisions, and rationale. Evaluation is universal even when a specific control is not activated.

### Step 7 — Produce the conjunctive control set

Activate every control whose conditions are met. Controls apply together. Conflicts require an explicit normative precedence rule; repository labels and evaluator preference cannot discard a control.

Reviewer unavailability, operational constraint, urgency, and an emergency, exception, or variance assertion cannot remove an activated control.

### Step 8 — Resolve required authority functions and evidence

For each activated control, identify the required actor functions, relationships, independence conditions, authority evidence, and domain evidence without yet treating them as satisfied. Processing-path and escalation facts may determine how evidence is sought but cannot change applicability.

### Step 9 — Validate Authority Assignments

Evaluate actor form, responsibility function, authority source, exact revision, scope, permitted operation, validity interval, delegation, revocation, conflicts, confidentiality, and technical-custody separation.

### Step 10 — Validate satisfaction of every activated control

Evaluate the supplied evidence for each control independently. One valid input cannot substitute for another. Record missing, stale, conflicting, out-of-scope, or unverifiable evidence.

### Step 11 — Produce the attributable Resolution Result

Preserve the eligibility evidence, scope relationships, rule-universe closure, complete evaluation basis, and unresolved conditions. Submit the result with all other required inputs to the operation-specific Policy Decision.

### 7.1 Circularity removed

Revision 1 permitted this cycle:

```text
Authority validates repository mode
        ↓
Repository mode determines authority evidence
        ↓
Authority validates repository mode
```

Revision 3 preserves Revision 2's removal of repository mode and makes the admissibility and completeness boundaries explicit:

```text
Universal eligibility is validated independently
        ↓
Minimum source authority is validated independently
        ↓
Canonical Decision Context is resolved
        ↓
The Applicable Rule Universe is closed
        ↓
Applicable controls determine additional authority and evidence needs
        ↓
Assignments and control evidence are validated
```

The Universal Authority Core is intentionally narrower than final operation authority. It validates the admissibility and attribution of context inputs, not permission to complete the Governed Operation. Conditional controls can therefore add stronger or additional authority requirements without retroactively determining whether the context source existed.

### 7.2 Missing evidence and fail-closed behavior

No missing eligibility result, context dimension, rule source, rule-universe closure evidence, authority source, assignment, or control evidence may silently default to:

- low impact;
- no external obligation;
- no conflict;
- no separation requirement;
- no collective authority;
- no confidentiality constraint;
- complete rule discovery;
- no active protection;
- no delegation;
- `Not Applicable`; or
- permission.

An Incomplete Rule Universe always prevents successful deterministic applicability evaluation. Where existing CADP governance classifies the operation as protected, any unresolved required evidence produces `Indeterminate` and fails closed. This proposal does not broaden existing safe-handling rules for non-protected cases.

## 8. Multiple Conditions and Illustrative Profiles

### 8.1 Multiple simultaneous conditions

The model supports several context conditions at once. For example, an architecture approval could be high impact, security relevant, contractually constrained, cross-repository, and subject to collective authority. Every rule activated by those facts contributes to the conjunctive control set.

The model does not select one “dominant” profile. An explicit normative precedence rule may resolve a genuine control conflict, but cannot be inferred from label order, organizational size, repository ownership, or convenience.

### 8.2 Named profiles

Single Maintainer, Multi Maintainer, Enterprise Governance, regulated, open-source, or similar labels may remain non-normative convenience templates or examples. A template may suggest candidate context facts for human review, but it must expand into explicit dimensions and be evaluated under the same rules as any other context.

A named profile cannot:

- determine governance requirements;
- function as a mutually exclusive normative mode;
- override Decision Context;
- act as an authority source;
- establish actor eligibility;
- bypass Applicability Evaluation;
- make a control automatically satisfied;
- weaken a higher rule;
- resolve missing evidence; or
- become a lifecycle, authority, maturity, or protection state.

### 8.3 Illustrative profile evolution

A repository may appear to evolve from a single maintainer to several maintainers and later to formal collective governance. Under the Revision 3 architecture, that evolution is represented by prospective changes to actual authority sources, assignments, scopes, external obligations, and decision contexts—not by a repository-wide normative mode transition.

The same repository can therefore support:

- a low-impact operation performed through one eligible actor;
- a security operation requiring independent review;
- a collective decision requiring quorum;
- a cross-repository decision requiring several approvals; and
- a later operation governed by a revised authority instrument.

No historical decision is reclassified merely because the organization later changes.

## 9. Normative Ownership and Contract Integration

### 9.1 One future normative owner

Revision 3 retains one future normative artifact, tentatively named the **Governance Applicability Contract**, as the sole owner of shared applicability semantics.

The future owner would be responsible for:

- the common Governed Operation boundary;
- admission of Universal Eligibility Gate results into applicability evaluation without redefining the underlying eligibility policies;
- composition of the Universal Authority Core prerequisite without redefining authority eligibility or validation;
- Decision Context vocabulary and shared dimensions;
- Applicable Rule Universe discovery boundaries, completeness, and closure;
- applicability rule identity, revision, scope, interval, and precedence;
- shared control activation semantics;
- multi-condition and conjunctive resolution;
- the common applicability Resolution Result;
- profile expansion boundaries;
- governance-change protection for shared applicability policy; and
- prospective and legacy applicability boundaries.

The final artifact name, authority class, scope, lifecycle, and contents remain unresolved and would require separate governance.

### 9.2 Consuming contract ownership

Existing contracts would retain their domain-specific meanings:

| Existing source | Retained semantic ownership | Proposed relationship to future shared owner |
| --- | --- | --- |
| Foundation Architecture | Architectural supremacy, authority hierarchy, canonical and lifecycle boundaries, conflict and fail-closed principles. | May later recognize decision-scoped applicability and the single-owner boundary without embedding detailed matrices. |
| Canonical Artifact Contract | Canonical identity, namespace, semantic version, immutable source revision, envelope categories, lineage, and integrity. | Supplies canonical identities and revisions consumed by applicability evaluation. |
| Authority and Delegation Contract | Actor eligibility, authority dimensions, delegation chains, revocation, non-delegable boundaries, and authority failure behavior. | Validates assignments requested by activated controls. |
| Approval Record Contract | Approval identity, human decision evidence, exact artifact binding, temporal validity, revocation, and supersession. | Retains approval meaning while shared applicability identifies which additional controls govern the approval operation. |
| Governance Lifecycle Contract | Orthogonal review, approval, effectiveness, adoption, disposition, archival, retirement, and protection relationships. | Retains transition meaning while shared applicability identifies context-derived authority and control needs. |
| Design Freeze Contract | Freeze identity, exact protected baseline, freeze authority, safe paths, protection interval, lifting, expiry, and immutable history. | Retains freeze semantics while shared applicability resolves common context and control activation. |
| Policy Decision Contract | Operation-specific evaluation, source and confidentiality eligibility, four provider-neutral outcomes, input manifest, freshness, explainability, caching, and audit. | Supplies governing eligibility and outcome semantics and consumes the applicability Resolution Result as one independently bound input. |

### 9.3 Dependency direction

The future dependency direction should prevent cycles:

1. Foundation establishes architectural precedence and separation.
2. Foundation and the Policy Decision Contract govern the Universal Eligibility Gate semantics.
3. Authority, identity, lifecycle, and evidence contracts produce their independently owned validation results.
4. The shared applicability owner defines input admission, prerequisite composition, Decision Context, Applicable Rule Universe closure, and common applicability semantics without redefining those upstream results.
5. Domain contracts own their bounded meanings and expose domain facts or controls through the shared composition boundary.
6. The shared applicability process resolves the complete conjunctive control set.
7. The Policy Decision evaluates the exact operation and complete evidence set.

Domain contracts should not independently redefine shared authority applicability. The shared owner should not absorb approval, lifecycle, freeze, canonical identity, delegation, or Policy Decision semantics.

### 9.4 Foundation boundary

A future Foundation revision may minimally recognize:

- Governed Operation as the scope of applicability evaluation;
- the mandatory pre-context eligibility boundary;
- the existence of one shared normative applicability owner;
- complete rule-universe closure as a prerequisite to deterministic applicability evaluation;
- the precedence relationship between Foundation, the shared owner, and consuming contracts; and
- a prohibition against contract-local redefinition of shared applicability semantics.

The Foundation should not contain detailed Decision Context vocabularies, control matrices, organization profiles, or mutable applicability rules. This proposal does not modify or authorize modification of Foundation.

## 10. Legacy and Historical Treatment

### 10.1 Principles

Governance evolution is prospective. Legacy records must not receive retroactive repository modes or profiles, and modern context structures must not be fabricated for decisions that did not record them.

The absence of a decision-scoped Decision Context does not automatically invalidate historical evidence. The original record, its contemporaneous rules, and unresolved facts remain independently preserved.

### 10.2 Conceptual legacy classes

The future normative owner should distinguish at least these conceptual conditions:

| Legacy condition | Architectural treatment |
| --- | --- |
| Evidence sufficient under contemporaneous rules | Preserve the original decision and its historical validity under the rules applicable at the time. |
| Substantively sufficient evidence lacking modern structure | Preserve the original evidence and permit a separately attributable, non-destructive derived assessment. |
| Material evidence missing | Preserve the record and report the applicable invalid or `Indeterminate` result under the governing contract; do not infer missing facts. |
| No contemporaneous rule can be established | Preserve the record, identify the missing rule boundary honestly, and require explicit historical assessment without fabricating a profile. |

These are architectural categories, not registry values or current decision outcomes.

### 10.3 Derived assessments

A derived assessment may cite legacy evidence and record:

- the exact legacy decision and evidence evaluated;
- the contemporaneous rules that could be established;
- the evaluator identity and authority;
- the assessment timestamp;
- facts established;
- facts that remain unknown;
- current reliance implications under applicable governance; and
- integrity and lineage back to the original record.

The assessment must remain separate from the original decision and cannot edit, backdate, ratify, or replace it.

### 10.4 Prospective boundary

If a future applicability contract becomes Approved and Effective, it should define an explicit prospective adoption boundary. Decisions before that boundary remain evaluated under contemporaneous rules unless a new Governed Operation requires current reevaluation.

A new reliance decision, supersession, adoption, effectiveness decision, freeze, or release is a new operation and may require current evidence without rewriting the earlier event.

### 10.5 Current Step 4 approval evidence

Revision 3 does not re-evaluate or repair the existing Step 4 approval assertion. The Approval Remediation Package and Approval Status Notice remain the sources describing its current `Indeterminate` reliance status and permitted corrective path. Any corrected human approval would require separate attributable evidence and governance.

## 11. Governance Change and Downgrade Protection

Applicability policy is itself governance. A future normative owner should prevent actors from weakening the controls for an operation while that operation is being evaluated.

At the architectural level, future governance should provide that:

- the Decision Context and applicable rule revisions are fixed and traceable for the evaluated operation;
- the Applicable Rule Universe and its discovery boundary are fixed, complete, and traceable for the evaluated operation;
- changing applicability policy is a separate Governed Operation;
- a rule change cannot retroactively remove controls from an open decision;
- a less restrictive proposed policy cannot authorize its own adoption;
- missing context cannot be resolved by selecting a lighter profile;
- reviewer unavailability, operational constraints, emergency declarations, and exception or variance requests cannot suppress applicable controls;
- emergency or exception assertions require their own valid authority and evidence;
- emergency use remains explicit, bounded, reviewable, and non-reusable where the governing contract requires it;
- the exact rule set used remains part of immutable decision evidence; and
- later policy evolution triggers prospective reevaluation rather than historical rewriting.

This proposal creates none of those controls. It defines the architecture risk and proposed ownership boundary for future normative work.

## 12. Cross-Repository and Federated Governance

Cross-repository governance is represented through composition, not a `Federated Mode`.

A cross-repository Governed Operation may involve:

- one common canonical decision identity;
- explicitly bounded repository and component scopes;
- multiple canonical authority sources;
- repository-specific approval or lifecycle evidence;
- a coordinating authority whose scope is independently sourced;
- conjunctive satisfaction of every required repository or shared control;
- explicit conflict and precedence rules; and
- immutable lineage across the contributing evidence.

A coordinating authority does not absorb or imply repository-specific authority. One repository's approval does not authorize another repository unless an applicable authority source explicitly establishes that scope. Missing evidence for one required scope cannot be cured by complete evidence from another.

Every cross-repository evaluation requires one coherent evaluation snapshot bound to:

- the common canonical Governed Operation identity;
- every participating repository identity and immutable revision;
- every applicable CADP and Product Binding version where a binding independently exists;
- every authority source and rule revision;
- the Complete Rule Universe for the combined scope;
- one declared evaluation time and the effective intervals evaluated at that time;
- the scope relationships among repositories, components, authorities, controls, and results; and
- conflicts, stale inputs, and concurrency evidence.

Snapshot coherence does not require one physical repository or transaction system. It requires that the complete evidence state can be reproduced and that no participating source is silently evaluated at an incompatible revision or time. An unresolved repository revision, required binding, authority source, rule source, effective interval, or cross-scope relationship makes the combined snapshot unresolved and prevents a successful deterministic result.

This composition model supports federated governance without adding a repository mode, flattening source ownership, or creating a new authority tier.

## 13. Foundation Alignment

The proposed architecture aligns with the Foundation Architecture as follows:

| Foundation concern | Revision 3 alignment |
| --- | --- |
| Single Source of Truth | Context, rules, assignments, and results bind to canonical identities and immutable revisions; named profiles are non-authoritative. |
| Human approval | The Universal Authority Core and Authority Assignments require attributable human authority evidence where human governance is involved; AI cannot create approval. |
| Security and confidentiality boundary | The Universal Eligibility Gate applies source authorization, confidentiality, provider, and purpose eligibility before authority validation or Decision Context construction; these gates are never conditional controls. |
| Immutable history | Context, rules, results, legacy evidence, and derived assessments preserve lineage without rewriting prior meaning. |
| Layered memory | Retrieval or repetition cannot create authority or applicability; evidence classification remains independent. |
| Vendor neutrality | The proposal defines semantics without choosing a model, Git host, identity provider, database, policy engine, or workflow system. |
| Product independence | Applicability is operation- and scope-based rather than tied to one product's roles or organizational form. |
| Versioning | Rules, authority sources, context, artifacts, and results use exact versions or immutable revisions. |
| Composability | Independent context dimensions and controls compose conjunctively while conflicts remain explicit. |
| Deterministic completeness | A Complete Rule Universe is required before applicability evaluation can succeed; missing or inaccessible rule sources remain unresolved. |
| Authority hierarchy | Foundation and applicable higher sources retain precedence; profiles, technical custody, and Resolution Results create no tier. |
| Fail-closed behavior | Missing required facts remain unresolved and produce `Indeterminate` for protected operations under existing governance. |
| Orthogonal lifecycle | Applicability context and results remain independent from approval, effectiveness, adoption, protection, implementation, release, and runtime. |

The proposal does not assert that Draft Foundation or contracts are Approved or Effective. It preserves their declared lifecycle states.

## 14. Migration and Governance Evolution

Migration is architectural and prospective, not automatic.

### Stage 1 — Review Revision 3

Perform an independent architecture review of this exact proposal revision for determinism, authority boundaries, normative ownership, legacy safety, and Foundation consistency.

### Stage 2 — Record an eligible architecture decision

If review findings are resolved, a separately governed human process may decide whether to accept the architectural direction. This proposal does not select the decision artifact type or create the decision.

### Stage 3 — Design the future normative owner

Define the scope and dependencies of a Governance Applicability Contract or other accepted single owner. Establish Universal Eligibility Gate input admission, Universal Authority Core composition, the minimum Decision Context vocabulary, Applicable Rule Universe closure, and shared applicability semantics without absorbing upstream or domain semantics.

### Stage 4 — Determine minimal Foundation recognition

Evaluate whether Foundation requires a bounded revision to recognize the architecture and precedence boundary. Any revision would remain separate, versioned, independently reviewed, and human approved.

### Stage 5 — Calibrate consuming contracts

Evaluate contract impacts independently. A likely analysis order is:

1. Approval Record Contract;
2. Governance Lifecycle Contract;
3. Design Freeze Contract;
4. Authority and Delegation Contract and Policy Decision Contract where dependency clarification is required; and
5. Canonical Artifact Contract only where shared identity or revision categories require clarification.

This order is an analysis recommendation, not authorization to edit.

### Stage 6 — Establish the prospective boundary

Define when new applicability evidence becomes required and how legacy records receive non-destructive assessment.

### Stage 7 — Validate before implementation

Repeat the architecture baseline audit and perform contract-level independent review before any schema, tooling, automation, or operational enforcement is considered.

Repository growth would not require rewriting governance contracts merely to rename a mode. Evolution would occur through revised authority sources, assignments, Decision Context, and applicable rules under stable shared semantics.

## 15. Resolution of Independent Review Findings

| Finding | Decision-scoped resolution retained in Revision 3 |
| --- | --- |
| M-01 — Conflated Governance Modes | Replaces repository modes with Governed Operation scope and orthogonal Decision Context dimensions. Named profiles remain illustrative only. |
| M-02 — Circular Dependency | Adds a Universal Authority Core and a deterministic sequence that validates context-source authority before conditional controls. |
| M-03 — Applicability Versus Activation | Makes Applicability Evaluation universal and separates it from conditional Control Activation and later satisfaction. |
| M-04 — Enterprise-only Category | Removes `Enterprise-only` as a normative category. Controls derive from actual collective-authority, external-obligation, risk, impact, scope, contractual, safety, security, and other governed conditions. |
| M-05 — Mixed Authority Classification Axes | Separates Actor Form, Responsibility Function, Authority Source, Scope, Permitted Operation, Validity Interval, Delegation, and Technical Custody. |
| M-06 — Normative Ownership | Recommends one future Governance Applicability Contract for shared semantics while preserving each existing contract's domain ownership. |
| M-07 — Backward Compatibility | Defines prospective adoption, four conceptual legacy evidence conditions, and attributable non-destructive derived assessments without retroactive profiles or rewritten history. |

Resolution in this table means the proposal text addresses the design finding. It does not mean the architecture is accepted, the finding is formally closed, or any normative source has changed. Closure requires independent review.

### 15.1 Revision 3 review findings

| Review finding | Revision 3 architectural correction |
| --- | --- |
| R3-01 — Universal Eligibility Gate | Adds a universal pre-context gate for source authorization, confidentiality eligibility, provider eligibility where applicable, and purpose eligibility. Removes confidentiality eligibility from conditional Governance Controls. |
| R3-02 — Rule Universe Closure | Adds the Applicable Rule Universe, authoritative source classes, discovery boundary, completeness expectation, closure condition, and explicit Complete versus Incomplete classifications. |
| R3-03 — Decision Context Purity | Restricts Decision Context to immutable applicability facts and prohibits reviewer availability, emergency or exception assertions, and operational constraints from suppressing controls. |
| Minor — Universal Authority Core ownership | Assigns authority semantics and validation to the Authority and Delegation Contract; the future applicability owner owns only prerequisite composition. |
| Minor — Scope reconciliation | Distinguishes requested-operation, eligibility, authority, contextual, control, and result scopes and requires compatible intersections. |
| Minor — Cross-repository snapshot consistency | Requires one reproducible cross-repository evaluation snapshot with exact revisions, rule universe, evaluation time, intervals, and scope relationships. |

These corrections remain proposed architecture. Their inclusion does not constitute independent review closure.

## 16. Risks

| Risk | Architectural consequence | Proposed mitigation boundary |
| --- | --- | --- |
| Excessive context dimensions | Applicability becomes difficult to understand and maintain. | Keep a minimal shared vocabulary; require separate architecture review for new shared dimensions; leave domain facts with domain owners. |
| Ineligible input admission | Unauthorized or purpose-ineligible information enters authority or applicability evaluation. | Apply the Universal Eligibility Gate before authority validation and Decision Context construction; never treat eligibility as a conditional control. |
| Hidden or incomplete rules engine | Machine evaluation becomes opaque, irreproducible, or silently omits controlling rules. | Require a human-readable discovery boundary, Complete Rule Universe closure, exact rule revisions, attributable rationale, and complete Resolution Results. |
| Context manipulation | An actor understates impact, external obligations, or resource availability to avoid controls. | Require attributable immutable context sources and prohibit availability, urgency, emergency, and exception assertions from suppressing controls. Missing or disputed facts remain unresolved. |
| Universal Authority Core overreach | Passing the core is mistaken for final authority. | State explicitly that the core validates context admissibility only and cannot authorize the operation or satisfy conditional controls. |
| Contract dependency cycle | Shared and domain contracts recursively determine one another's applicability. | Use one shared owner, explicit dependency direction, and domain ownership boundaries. |
| Control conflict | Several applicable rules impose incompatible requirements. | Preserve the conflict and require explicit normative precedence; do not use profile order or evaluator preference. |
| Profile re-emergence | Convenience templates become de facto authority or exemptions. | Require expansion into explicit context and full applicability evaluation; profiles remain non-normative and non-authoritative. |
| Technical custody treated as authority | Repository administrators are assumed eligible to approve or release. | Keep custody as a separate axis and require independent authority-source evidence. |
| Legacy overreach | Modern rules are retroactively applied or historical evidence is rewritten. | Use prospective adoption and non-destructive derived assessments. |
| Governance downgrade | Applicability rules change during a disputed operation. | Treat policy change as a separate operation and bind the original operation to exact context and rule revisions. |
| False completeness | A detailed Resolution Result is mistaken for `Allow`. | Preserve the separate operation-specific Policy Decision and all other independently required inputs. |
| Excessive process | Low-impact operations become unusable. | Make evaluation universal but controls conditional on actual governed context rather than organization labels. |
| Inconsistent domain triggers | Consuming contracts redefine shared applicability. | Place shared semantics in one normative owner and define a bounded extension relationship. |
| Cross-repository authority leakage | Authority from one scope is assumed valid in another. | Require explicit scopes, multiple authority sources where needed, and conjunctive satisfaction. |

## 17. Alternatives Considered

### 17.1 Repository governance modes

Classify a repository as Single Maintainer, Multi Maintainer, or Enterprise Governance and use the active mode to select evidence.

This is easy to explain but combines unrelated dimensions, creates transition and circularity problems, and misclassifies high-risk small repositories and low-risk enterprise operations. Rejected as the primary architecture. Retained only as illustrative profile terminology.

### 17.2 Named organizational profiles

Define profiles such as solo, open source, regulated, commercial, enterprise, or federated.

Profiles can aid onboarding but overlap, proliferate, obscure actual conditions, and become a second policy language. Rejected as the authoritative mechanism. A profile may only expand into explicit context for normal evaluation.

### 17.3 One universal enterprise control set

Require separation, committee action, quorum, voting, recertification, and formal conflict procedures for all operations.

This is uniform but imposes nonexistent organizational structures and encourages fictional evidence. Rejected. Applicability evaluation is universal; controls are conditional.

### 17.4 Contract-local applicability

Allow each domain contract to define shared authority and context applicability independently.

This keeps text near its consumer but duplicates semantics, creates drift, complicates audit, and increases dependency cycles. Rejected in favor of one future shared owner with domain-specific semantic boundaries.

### 17.5 Organization-chart or repository-owner authority

Infer governance authority from corporate title, reporting line, repository ownership, or administrative control.

This confuses employment or technical custody with operation-specific authority and does not establish scope, interval, delegation, or permitted operation. Rejected.

### 17.6 Case-by-case human interpretation without a shared model

Resolve every applicability question through local prose or review judgment.

This avoids a new shared artifact but prevents deterministic evaluation, cross-contract consistency, and reliable migration. Rejected as a long-term architecture.

### 17.7 Decision-scoped applicability

Evaluate an exact operation through a Universal Authority Core, orthogonal Decision Context, universal applicability evaluation, conjunctive controls, explicit Authority Assignments, and an attributable Resolution Result.

Recommended for further independent review because it separates the relevant dimensions while preserving existing CADP semantic ownership.

## 18. Open Questions

The architectural direction is sufficiently bounded for review, but the following decisions remain deliberately unresolved:

1. What is the minimum shared Decision Context vocabulary?
2. Which facts are declared by an eligible actor, and which are derived from canonical sources?
3. Which responsibility function may attest or validate each category of context?
4. What exact rule-precedence model resolves incompatible activated controls?
5. How may a domain contract introduce domain facts or triggers without redefining shared semantics?
6. Which per-control evaluation states are needed, and how do they map to the existing four Policy Decision outcomes?
7. What evidence is sufficient to establish decision-time revocation status?
8. How are collective actors canonically identified, versioned, and related to their members?
9. What governance process changes shared applicability rules?
10. What exact prospective adoption boundary protects open decisions during migration?
11. Which Foundation section would contain the minimal architecture recognition if a Foundation revision is later authorized?
12. Is `Governance Applicability Contract` the correct final title for the normative owner?
13. Which historical record should be the first non-destructive migration assessment?
14. How are context confidentiality and requester-facing explanations separated from protected audit evidence?
15. Which controls require independent evidence that cannot be supplied by the context declarer?
16. What exact governed evidence demonstrates Applicable Rule Universe closure for each supported scope shape?
17. How are restricted rule sources evaluated without exposing their content to an ineligible requester or evaluator?

These questions do not grant discretion to bypass existing governance. They identify future normative decisions that must be resolved before implementation.

## 19. Recommendation

Submit Revision 3 for independent architecture review as a Draft, non-normative proposal.

The review should determine whether the Decision-Scoped Governance Applicability Model:

- eliminates repository modes as the authoritative selector;
- applies universal source, confidentiality, provider, and purpose eligibility before context construction;
- removes circular authority evaluation;
- proves Applicable Rule Universe closure before deterministic applicability evaluation can succeed;
- keeps applicability evaluation distinct from control activation and satisfaction;
- prevents availability, emergency, exception, and operational-path facts from suppressing controls;
- preserves authority, lifecycle, identity, approval, freeze, and Policy Decision ownership;
- supports deterministic multi-condition resolution;
- protects legacy evidence and prospective governance evolution;
- prevents profiles and technical custody from acquiring authority; and
- defines a credible single normative ownership boundary.

If the proposal passes independent review, the next action should be an eligible human architecture decision about the direction. No contract drafting, Foundation amendment, registry work, schema design, implementation, approval, effectiveness, adoption, Product Binding, Design Freeze, or release action follows automatically.

## 20. Revision History

| Revision | Proposal version | Summary | Governance effect |
| --- | --- | --- | --- |
| Revision 1 | 0.1.0 | Used Single Maintainer, Multi Maintainer, and Enterprise Governance repository modes as the primary applicability model. | None; Draft and non-normative. |
| Independent review | Not a proposal revision | Found conflated applicability dimensions, circular authority evaluation, applicability/activation ambiguity, an unsound `Enterprise-only` category, mixed authority axes, unclear normative ownership, and incomplete legacy treatment. | Review evidence only; no approval or lifecycle effect. |
| Revision 2 | 0.2.0 | Replaces primary repository modes with the Decision-Scoped Governance Applicability Model. Adds the Universal Authority Core, orthogonal Decision Context, universal Applicability Evaluation, conditional conjunctive controls, separated Authority Assignment axes, one future normative owner, and non-destructive legacy treatment. Named profiles remain illustrative only. | None; remains Draft, non-normative, and without governance or implementation authority. |
| Revision 3 | 0.3.0 | Preserves Revision 2 and adds the Universal Eligibility Gate, Applicable Rule Universe closure, Decision Context purity, explicit Universal Authority Core ownership, scope reconciliation, and coherent cross-repository snapshots. | None; remains Draft, non-normative, and without governance or implementation authority. |

Revision 3 has not been accepted, Approved, made Effective, Adopted, Design Frozen, or authorized for implementation.
