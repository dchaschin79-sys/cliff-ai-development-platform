# Foundation Architecture Review

| Field | Value |
| --- | --- |
| Reviewed document | `docs/FOUNDATION_ARCHITECTURE.md` |
| Reviewed version | 0.1.0 |
| Reviewed lifecycle state | Draft |
| Review scope | Enterprise platform architecture, AI governance, and long-term maintainability |
| Review disposition | Advisory; does not constitute approval |

## Executive Assessment

**Overall verdict: PASS WITH REQUIRED REVISIONS**

The foundation establishes a credible platform boundary and correctly treats CADP as more than a documentation repository. It clearly introduces governance, knowledge, context, conformance, contracts, tooling, and assurance as distinct concerns. It also establishes several sound controls: human approval for fundamental decisions, explicit source identity, versioned authority, non-authoritative generated artifacts, conflict refusal, supersession rather than silent rewriting, product-scoped overlays, and vendor-neutral canonical contracts.

The document is nevertheless incomplete at the level required for approval. Several concepts that determine whether CADP can be safe and enforceable are deferred too far into Phase 1 or are represented ambiguously in the foundation itself. The most material gaps are:

- the initial canonical store is called a repository but is not explicitly defined as Git, while a mandatory monorepo and GitHub-specific enforcement surface are implied;
- the exception model is listed inside the authority hierarchy without a clear non-waivable safety boundary;
- the memory levels lack owners, permitted writers, update cadence, concrete retention, and complete promotion or archival contracts;
- `Frozen` is used both as a document lifecycle state and as a design-control mechanism;
- product inheritance lacks version pinning, compatibility, multi-repository scope, migration, rollback, and partial-adoption semantics;
- confidentiality and context-egress boundaries are not established at foundation level.

These issues do not invalidate the architecture. They require revision before the document is submitted for formal human approval. The appropriate next state is continued drafting.

### Criteria summary

| Criterion | Assessment | Summary |
| --- | --- | --- |
| Separation of concerns | Partial pass | Major planes are distinct, but normative versus operational material and several canonical storage locations remain ambiguous. |
| Authority hierarchy | Partial pass | Precedence and fail-closed conflict handling are strong; exception position and non-waivable controls require correction. |
| Memory hierarchy | Required revision | Purpose and high-level authority are present; operational ownership and retention contracts are absent. |
| Canonical source of truth | Required revision | Derived artifacts are correctly non-authoritative, but Git and future database/search derivation are not explicit. |
| Document lifecycle | Required revision | Core states are useful, but applicability, disposition, and freeze protection are conflated. |
| Design Freeze | Required revision | A future boundary is reserved, but it overlaps the `Frozen` document state. |
| Vendor neutrality | Partial pass | Model, storage, and orchestration neutrality are explicit; GitHub and monorepo assumptions remain. |
| Product inheritance | Required revision | Registration and overlays are anticipated; version adoption and compatibility mechanics are missing. |
| Scalability | Partial pass | Product count and bounded retrieval are addressed; repository topology, concurrency, and partial adoption are not. |
| Auditability and history | Partial pass | Lineage and approval evidence are strong; authorship, rationale, rollback, and snapshot identity need explicit contracts. |
| Security and confidentiality | Required revision | Access policy and bounded context are mentioned, but trust and data-handling boundaries are not reserved. |
| Executability | Pass with revisions | Schemas, validation, context compilation, gates, and tests are anticipated; enforcement outcomes and provider-neutral integration need definition. |
| Simplicity | Partial pass | The conceptual planes are useful, but duplicate registries, profiles, and storage locations could create bureaucracy. |

## Critical Findings

### C-01 — Canonical Git source and repository topology are not defined consistently

**References:** Sections 1.1, 2.1, 2.6, 3, 3.1, and 3.2; specifically the statements that the authoritative copy resides in “the CADP repository,” that the repository “is organized as a platform monorepo,” and that `.github/` is an enforcement surface.

Section 2.1 correctly makes generated indexes, caches, bundles, and reports non-authoritative. It does not explicitly establish Git as the initial canonical content store and change ledger. “Repository” could mean a Git working tree, a GitHub repository, a future database repository, or a logical artifact repository. The document also does not explicitly state that chat memory, vector indexes, relational databases, search indexes, and knowledge-graph stores are derived representations.

At the same time, Section 3 mandates a platform monorepo and gives GitHub-specific configuration a top-level architectural role. This conflicts with the stated vendor neutrality and the review requirement to support monorepos, polyrepos, and multiple repositories per product. Git can be the initial canonical mechanism without making GitHub or one physical layout part of the platform semantics.

**Required resolution:** Define Git as the initial canonical source and append-only change ledger for governed CADP artifacts. Define one canonical artifact identity and version, require all databases, search/vector indexes, graphs, caches, chat memories, and product-local projections to declare that source, and treat GitHub as one replaceable integration adapter. Recast the folder tree as the initial physical layout implementing a logical architecture, not the only supported repository topology.

### C-02 — Exception precedence can be interpreted as permitting implicit safety bypass

**References:** Sections 2.2, 2.3, 5, 5.1, and 7.5.

The authority hierarchy numbers a time-bounded exception below ADRs, while conflict resolution later says to “apply” an exception authorized by higher authority. An exception is therefore represented partly as an authority level and partly as a delegated operation. This makes it unclear what an exception can override and whether an operational policy could delegate waiver of a safety control.

Section 2.2 also permits AI action under “a separately approved policy” without defining which decisions are non-delegable. Section 5 protects constitutional constraints only if a future Constitution defines the mechanism, but the Constitution does not yet exist. Until it does, the foundation must still prevent implicit waiver of foundational safety, confidentiality, approval, and authority controls.

**Required resolution:** Remove exceptions from the authority ranking and model them as scoped, time-bounded delegations issued under a specific rule. Require an exception to identify the authorizing rule, affected requirement, approver, rationale, risk acceptance, effective interval, rollback or expiry action, and non-waivable constraints. Define that missing, invalid, expired, or ambiguous exception authority produces an indeterminate result that fails closed. Fundamental approvals and designated safety boundaries must remain non-delegable to AI.

### C-03 — The memory hierarchy is classificatory but not operational

**References:** Sections 2.5, 4, 4.1, 4.2, and Phase 1 Step 4.

The hierarchy gives each level a useful purpose and a broad authority or retention description. It does not define a responsible owner, permitted writers, update or verification cadence, maximum or minimum retention, expiry trigger, archival destination, or complete promotion prerequisites. The most operationally volatile levels—Current State, Working Memory, and Conversation Cache—have the least precise controls.

Deferring all of these properties to Phase 1 leaves a foundational ambiguity: the platform cannot determine who may assert current state, when that assertion becomes stale, or who may promote transient material into an authoritative record. “Retained only when useful” and “short-lived” are not enforceable retention policies.

**Required resolution:** Extend the foundation-level memory model to require, for every level, an accountable owner class, allowed writer classes, validation source, update trigger or cadence, freshness/expiry semantics, retention class, promotion gate, archival or deletion rule, confidentiality classification, and authority eligibility. Numeric retention durations may remain policy decisions, but the required control fields and default fail-closed behaviour cannot be deferred.

### C-04 — Document lifecycle and Design Freeze are conflated

**References:** Sections 6, 8 (`Design Freeze`), and Phase 1 Step 5.

`Frozen` is defined as a state in the lifecycle of every governed document, and Draft → Review → Approved → Frozen is described as the normal progression when protection is required. The future Design Freeze component is separately described as protection of an architectural baseline for a scope and period. These are two different dimensions:

- a document has a review and disposition state;
- a version may be effective, deprecated, superseded, or expired;
- a set of artifacts may be temporarily protected by a design freeze;
- a product or release has a maturity and release status.

Treating freeze as the next document lifecycle state will create incorrect transitions when a design freeze covers many already approved artifacts, or when the freeze ends but those artifact versions remain approved.

The current lifecycle also says Deprecated artifacts may have limited legacy use, while Section 5 says only Approved or Frozen artifacts may be normative. `Superseded` and `Expired` are used elsewhere but are not lifecycle states, so their authority is not deterministic.

**Required resolution:** Separate review lifecycle, applicability/disposition, and protection status. Retain Draft, Review, Approved, and Archived as workflow/history states; represent Deprecated, Superseded, and Expired as distinct applicability outcomes; represent Frozen as an orthogonal protection placed on an explicit baseline. `Proposed` is unnecessary because it duplicates Draft. `Rejected` should be a review disposition retained with evidence rather than an authoritative state. `Emergency Override` should be a controlled exception type, not a lifecycle state.

### C-05 — Product inheritance is missing version-adoption and compatibility semantics

**References:** Sections 1, 2.7–2.10, 3.2, 5, 7.1, and Phase 1 Step 3.

The architecture correctly states that products inherit universal rules and may declare bounded overlays. It does not define the minimum relationship between a product and a CADP release. Missing foundation concepts include:

- exact version or compatible version-range pinning;
- effective and target CADP versions;
- compatibility checks for schemas, rules, and tooling;
- migration plans and rollback references;
- adoption state for products that are unregistered, partially governed, migrating, conformant, excepted, or out of compliance;
- registration of multiple repositories, branches, and components under one product identity;
- precedence when a product-local projection is stale relative to CADP;
- behaviour when only part of a product can adopt a new rule.

Without these concepts, “future products automatically inherit” is not deterministic and dozens of products could silently operate against different assumptions.

**Required resolution:** Define a product binding as a versioned relationship among a stable product identity, its repository/component scopes, its current and target CADP versions, inherited modules, approved overlays, active exceptions, compatibility result, and migration/rollback state. Require explicit adoption rather than treating repository presence or synchronization as inheritance.

### C-06 — Security, confidentiality, and context-egress boundaries are not foundational

**References:** Sections 1.1, 4.2, 7.5, 9 Step 2, and 9 Step 4.

The document mentions access policy, bounded context, sensitive sources, and a future security policy. It does not establish the architectural boundary needed when AI agents operate across restricted repositories, tenant data, customer data, personal information, credentials, production data, and third-party model endpoints.

This is not a request for detailed security policy. It is a requirement that the foundation define security classification and context minimization as inputs to retrieval, session building, tooling, validation, and audit. Without that boundary, a correctly ranked artifact could still be impermissible to retrieve or send to a provider.

**Required resolution:** Add a foundation principle establishing least privilege, data classification, source authorization, purpose limitation, context minimization, provider/region eligibility, secrets exclusion, output handling, and auditable egress as mandatory controls. Require authorization and confidentiality filtering to occur before semantic retrieval and context assembly. Reserve detailed policies and classification values for later approved specifications.

## Important Findings

### I-01 — Normative governance and operational instructions need a sharper authority boundary

**References:** Sections 1, 3.1 (`operating-manual/` and `governance/`), 4 Level 1, and 5.

The folder responsibilities distinguish governance from the Operating Manual, but Level 1 combines “governance, operating, review, context, and development rules” into one authority class. It is therefore unclear whether an operating procedure can introduce a new obligation or merely implement an existing normative requirement.

The foundation should state that governance defines obligations and constraints; the Operating Manual defines approved procedures within those constraints; procedures must trace to authorizing requirements and cannot create or weaken higher-order policy without the appropriate governance process.

### I-02 — Several artifact classes have more than one apparent canonical location

**References:** Sections 3 and 4.

ADRs appear under `decisions/` and as Memory Level 3. Roadmaps appear under `docs/roadmaps/` and as Memory Level 4. Product knowledge may live under both `memory/products/` and `products/`. Session information may live under `context/sessions/`, Working Memory, or Conversation Cache. Evaluation policy could live under `governance/`, `validation/policies/`, or `prompts/evaluations/`.

These may be classification views rather than duplicates, but the document does not say so. Each artifact type needs exactly one canonical source location; indexes and projections must point to it. Otherwise the Single Source of Truth principle cannot be enforced.

### I-03 — Concurrent agents, branches, and sessions lack snapshot and merge semantics

**References:** Sections 2.10, 4.2, 7.1, 7.6, and 8 (`Session Builder`).

Determinism is defined for a “source state,” but that state has no required immutable identifier. Multiple agents can start from different branches or commits, promote conflicting memories, approve overlapping decisions, or generate context while the source changes.

The foundation should require every session, context manifest, review, validation, and approval to bind to immutable source revisions and product/CADP versions. Concurrent writes should use optimistic conflict detection or an equivalent governed merge process; no last-writer-wins behaviour should apply to governed artifacts.

### I-04 — Audit records do not yet require rationale and rollback references

**References:** Sections 2.2–2.4, 5, 6, and 7.2.

Stable identity, ownership, approval, actor, version, effective period, and lineage are anticipated. The foundation does not explicitly require author identity distinct from owner, reviewer identities, approval evidence, rationale, change reason, affected artifacts, rollback or recovery reference, and cryptographic/source revision identity.

These fields should be mandatory categories in the artifact and event envelope. Their detailed schemas may remain Phase 1 work.

### I-05 — Generated artifact retention and reproducibility boundaries are incomplete

**References:** Sections 2.1, 3.2, 4.2, and 7.6.

Generated indexes, reports, bundles, and projections are correctly non-authoritative. The architecture does not say which generated artifacts are ephemeral, which are audit evidence, when they may be deleted, how freshness is detected, or whether all must be byte-for-byte reproducible versus semantically reproducible.

A derived-representation contract should require source revision, generator identity/version, generation time, input manifest, classification, freshness status, retention class, and invalidation rule. Audit evidence should not be discarded under the same policy as a cache.

### I-06 — Session memory and lessons learned are not explicitly classified

**References:** Sections 3 (`context/sessions/`), 4 Levels 5–7, and 8 (`Session Builder`).

The requested distinction between session memory and conversation cache is not explicit. A session may contain a task declaration, compiled context, tool permissions, intermediate working notes, and raw conversation; these have different authority and retention. “Lessons learned” also has no defined path: it may be an observation, a verified current-state fact, a reusable operating insight, or a proposed rule.

The foundation should define session records as containers that reference classified artifacts, not as another authority level. Lessons learned should enter as non-authoritative working knowledge and be promoted to the appropriate artifact class only after evidence and review.

### I-07 — Artifact type and authority-class vocabularies are not closed or governed

**References:** Document metadata, Sections 2.2, 3.2, 5, and Phase 1 Step 2.

The reviewed document declares “Foundation architecture candidate” as an authority class, but the hierarchy does not define that class. Folder location, memory level, document type, authority rank, lifecycle state, and scope are separate dimensions; the current text sometimes treats them interchangeably.

The foundation should require controlled registries for artifact type and authority class, including which lifecycle states, approver roles, scopes, and exception capabilities are allowed for each. The concrete values can be defined in Phase 1, but unregistered authority classes must have no normative effect.

### I-08 — Enforcement outcomes and integration gates need provider-neutral semantics

**References:** Sections 3 (`.github/`, `validation/`, and `tooling/`), 7.6, 8 (`Validation Engine`), and Phase 1 Step 6.

The architecture anticipates schemas, validation, freeze checks, context compilation, approval gates, tests, and future tooling. It does not define the minimum policy-evaluation outcomes or how an external CI/CD system consumes them. A binary pass/fail result is insufficient when inputs may be missing, stale, unauthorized, or not applicable.

The foundation should reserve provider-neutral outcomes such as allow, deny, indeterminate, and not-applicable, each with evidence and source versions. Enforcement integrations—including GitHub Actions—should adapt those canonical outcomes rather than define them.

## Optional Improvements

### O-01 — Reconsider the name “Product Constitution”

Using “Constitution” at both Level 0 and Level 2 may imply that a product constitution is independently sovereign. “Product Governance Profile” or “Product Policy Overlay” would communicate inherited scope more clearly while preserving Level 0 as the single constitutional authority.

### O-02 — Reduce registry proliferation

Separate `registry/` directories under Constitution, Decisions, Memory, and Products may be justified, but they can lead to different indexing rules. A common registry contract and naming convention would reduce maintenance cost without requiring a single physical catalog.

### O-03 — Clarify duplicate uses of “profile”

`context/profiles/` and `prompts/profiles/` are likely different concepts. More specific names such as context policies and prompt compositions would reduce retrieval and onboarding ambiguity.

### O-04 — Delay vague execution-plane subdivisions

`tooling/core/`, `tooling/services/`, and `tooling/components/` overlap until component boundaries are approved in Phase 1 Step 7. Retaining only an execution-plane boundary in the foundation would avoid prematurely constraining implementation packaging.

## Contradictions or Ambiguities

1. **Canonical ownership of product decisions:** Section 1.1 says product repositories own product-specific decisions, while Section 2.1 says every CADP-controlled artifact is authoritative in the CADP repository and Section 3 places ADRs in `decisions/`. The document must state whether CADP stores product ADR sources, registrations, or projections.
2. **Repository neutrality:** Section 2.6 rejects vendor-specific core semantics, but Section 3 defines a monorepo and `.github/` enforcement as the target architecture. The logical platform structure and its initial GitHub-hosted realization are not separated.
3. **Authority implied by memory level:** Section 4 says higher levels are “more authoritative,” yet Roadmaps at Level 4 are planning directives and Current State at Level 5 may provide newer factual evidence than an ADR. Authority, durability, and retrieval priority should not be represented as one scalar hierarchy.
4. **Exception position:** Section 5 lists exceptions as the fifth precedence level, but Section 5.1 applies an exception after selecting the higher authority. An exception is a delegated variance, not a standalone authority tier.
5. **Deprecated authority:** Section 5 permits normative use only for Approved or Frozen artifacts, while Section 6 permits limited legacy use of Deprecated artifacts. The conditions under which deprecated content remains effective are undefined.
6. **Superseded and expired records:** Sections 2.4, 3, 4, and 5 rely on supersession and expiry, but Section 6 has neither Superseded nor Expired semantics.
7. **Freeze semantics:** Section 6 defines Frozen as a document state; Section 8 and Phase 1 Step 5 define Design Freeze as protection of a scoped architectural baseline. Ending a freeze must not change document approval history.
8. **ADR canonical location:** ADRs are first-class records in `decisions/` and also Memory Level 3. It is unclear whether the memory layer stores the source ADR, an index, or a retrieved projection.
9. **Roadmap canonical location:** Roadmaps are Memory Level 4 and also appear under `docs/roadmaps/`. The source and projection roles are not stated.
10. **Session and conversation boundaries:** `context/sessions/`, Working Memory, and Conversation Cache can all contain session material. Their ownership, authority, and retention boundaries are not defined.
11. **Operating authority:** `operating-manual/` cannot override governance according to Section 3.1, but Level 1 combines operating and governance rules without a sub-order or traceability requirement.
12. **Product count:** The context for this review refers to five products now, but the foundation names four current products. The architecture should avoid cardinality assumptions and depend on the product registry as the source of current membership.

## Missing Architectural Concepts

Only the following additions are required at foundation level; their detailed policies and schemas can remain Phase 1 deliverables.

1. **Canonical artifact envelope:** required identity, type, authority class, scope, owner, author, allowed writer class, version, source revision, lifecycle, effective interval, confidentiality class, lineage, approval, and integrity fields.
2. **Derived-representation contract:** a universal rule for projections, caches, search/vector indexes, databases, context bundles, and knowledge graphs to declare canonical source, generation inputs, freshness, and invalidation.
3. **Product binding and adoption model:** the relationship among product identity, repositories/components, CADP version, overlays, exceptions, compatibility, migration, rollback, and partial-adoption state.
4. **Trust and confidentiality boundary:** classification and authorization gates that precede retrieval, context assembly, provider egress, logging, and retention.
5. **Concurrency and snapshot model:** immutable input revisions, session isolation, conflict detection, branch semantics, and governed merge or promotion for parallel agents.
6. **Orthogonal state model:** separate review lifecycle, effective applicability, review disposition, and design-freeze protection.
7. **Policy decision contract:** provider-neutral evaluation outcomes, evidence, and fail-closed handling for missing, stale, unauthorized, or conflicting inputs.
8. **Cross-artifact integrity model:** required relationships among source requirements, procedures, ADRs, exceptions, reviews, validations, approvals, migrations, and rollback references.

## Recommended Revisions

1. **Revise Section 2.1, Single Source of Truth.** State that Git is the initial canonical store and history mechanism for governed source artifacts. Define canonical artifact URI/ID plus revision, and explicitly classify chat memory, databases, knowledge graphs, search/vector indexes, generated bundles, and product-local copies as derived unless separately designated through an approved migration.
2. **Revise Sections 2.6 and 3.** Describe the tree as the initial physical monorepo layout implementing a repository-neutral logical model. Move GitHub-specific enforcement under an integration example or identify `.github/` as a replaceable adapter surface. State that product registration supports monorepos, polyrepos, and multiple repositories.
3. **Revise Sections 2.2, 2.3, 5, and 5.1.** Separate authority tiers from exceptions; define non-delegable controls; require attributable human approval and explicit delegation; make invalid or ambiguous authority fail closed.
4. **Revise Section 4.** Expand the memory table with owner, allowed writers, update trigger/cadence, freshness, retention class, promotion gate, archival/deletion rule, and confidentiality requirements. Explain that memory level does not combine authority, durability, and factual recency into a single ranking.
5. **Revise Sections 3 and 4.** Assign one canonical location to ADRs, roadmaps, product memory, session records, lessons learned, validation policy, and generated evidence. Mark every other occurrence as an index, projection, or container reference.
6. **Revise Section 6 and all references to Frozen.** Use separate dimensions for workflow state, applicability/disposition, and protection. Add materially distinct Superseded and Expired semantics. Treat rejection as a review outcome, Proposed as equivalent to Draft, and Emergency Override as an exception type.
7. **Revise Sections 2.7–2.10, 3.2, 7.1, and Phase 1 Step 3.** Establish the product binding/adoption model, including repository/component scope, version pinning, compatibility, partial adoption, migration, rollback, stale-projection behaviour, and approved exceptions.
8. **Add a foundation security and confidentiality principle after Section 2.6 or as a new architectural principle.** Reserve mandatory controls for secrets, credentials, production/customer/tenant/personal data, restricted repositories, purpose limitation, context minimization, provider eligibility, egress, and audit without defining detailed policy values.
9. **Revise Sections 2.4 and 7.2.** Require authorship, rationale, review and approval evidence, effective dates, affected artifacts, immutable source revision, supersession, and rollback/recovery references for governed changes.
10. **Revise Sections 4.2, 7.6, 8, and Phase 1 Step 6.** Require context, validation, review, and approval records to bind to immutable snapshots. Reserve concurrency conflict handling, stale-memory detection, and provider-neutral policy outcomes for enforcement integrations.
11. **Revise Sections 3.1 and 4 Level 1.** State that the Operating Manual operationalizes traceable governance requirements and cannot independently create, waive, or elevate normative obligations.
12. **Revise the Phase 1 roadmap ordering.** Resolve the six critical foundation issues before ratification in Step 1. The current ordering asks humans to ratify the foundation before the metadata, security, inheritance, memory, exception, and freeze contracts needed to interpret it are established.

## Approval Recommendation

The foundation is ready for **continued drafting**.

It is not ready for formal human approval or freeze. A human may review the current draft and this review as working material, but the foundation should not enter its formal approval review until all critical findings are resolved and the resulting revision has been checked for internal consistency.

This review does not approve the foundation document and does not authorize creation of the AI Constitution, product-specific rules, or implementation tooling.

FILES_CHANGED
- docs/FOUNDATION_ARCHITECTURE_REVIEW.md

REVIEW_VERDICT
PASS WITH REQUIRED REVISIONS

CRITICAL_FINDINGS_COUNT
6

IMPORTANT_FINDINGS_COUNT
8

READY_FOR_HUMAN_REVIEW
NO
