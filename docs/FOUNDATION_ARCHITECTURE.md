# Cliff AI Development Platform: Foundation Architecture

| Field | Value |
| --- | --- |
| Document ID | CADP-ARCH-FOUNDATION |
| Version | 0.2.0 |
| Lifecycle state | Draft |
| Scope | Cliff Group software engineering products |
| Authority class | Foundation architecture candidate |
| Approval | Requires explicit human approval |
| Revision note | Revision 1 resolves the findings accepted from the foundation architecture review. |

## 1. Vision

Cliff AI Development Platform (CADP) is the product-independent control plane for AI-assisted software engineering across Cliff Group. It establishes how engineering knowledge is governed, how instructions acquire authority, how context is assembled, how decisions are recorded, how conformance is evaluated, and how approved standards are adopted by products.

CADP exists to address recurring failure modes in AI-assisted development:

- instructions distributed across repositories, conversations, and tools with no reliable precedence;
- loss of architectural intent between sessions, teams, models, and products;
- undocumented or unauthorized changes to fundamental decisions;
- product-specific practices that diverge without an explicit exception;
- context assembled from stale, irrelevant, unauthorized, or lower-authority sources;
- review outcomes that cannot be reproduced or audited;
- dependence on one model, provider, hosting service, or repository topology;
- inability to determine which rule, decision, or memory was effective at a given time.

CADP is not an aggregation of guidance documents. It is a versioned engineering platform with four primary responsibilities:

1. **Governance control:** establish authority, approval, lifecycle, change-control, delegation, exception, and protection rules.
2. **Knowledge and context control:** classify durable and transient knowledge and assemble bounded, authorized, traceable context.
3. **Product adoption control:** bind products and their component scopes to explicit CADP versions, overlays, exceptions, and migration states.
4. **Conformance and audit control:** evaluate work against applicable standards and retain the evidence needed to reproduce each result.

Ordinary documentation informs a reader. CADP must additionally support deterministic identification, machine-readable classification, inheritance, policy evaluation, validation, traceability, and reproducible assembly. Human-readable documents remain necessary, but they are governed source artifacts rather than the entire platform.

Cliff Platform, HVAC Pro, SalesPro, and Estimate Pro are the initial consumers. Future products adopt CADP through governed onboarding and an explicit Product Binding; existence in Cliff Group or presence in a repository does not constitute adoption.

### 1.1 System boundary

CADP owns universal AI engineering governance and the mechanisms that distribute and validate it. Product repositories continue to own application code, domain architecture, delivery plans, operational state, and product-specific decisions unless an approved policy explicitly assigns a particular artifact to CADP.

CADP may register, reference, classify, index, or validate product-owned artifacts without silently becoming their owner. Product-specific ADRs normally remain canonical in the applicable product repository. CADP does not absorb product implementation or invent domain rules.

CADP does not replace source control, issue tracking, CI/CD, observability, security systems, or human accountability. It defines how those systems participate in governed AI engineering through provider-neutral contracts and replaceable adapters.

## 2. Architectural Principles

### 2.1 Single Source of Truth

Git is the initial canonical store and append-only change ledger for governed CADP source artifacts. A governed artifact is identified by a stable artifact identity together with an immutable Git source revision. Protected history, explicit supersession, and approval evidence preserve the meaning that was effective at a given time.

Git hosting is not part of CADP authority semantics. GitHub is one replaceable hosting and workflow adapter; equivalent Git hosting alternatives must be able to preserve the same canonical identities, revisions, approvals, and integrity evidence.

Databases, relational stores, vector indexes, search indexes, knowledge graphs, generated context bundles, caches, chat memory, and product-local projections are derived representations unless an approved source-of-truth transition explicitly migrates authority. Derived representations must declare their canonical source and must never silently become authoritative. A conflicting or unresolved copy produces an Indeterminate result and fails closed until canonical identity and revision are resolved.

The logical CADP architecture is independent of physical repository topology. It supports CADP and product monorepos, polyrepos, multiple repositories per product, and multiple products in one repository when every scope is explicitly registered in a Product Binding.

### 2.2 AI-first

Artifacts must be usable by people and automated reasoning systems. Each governed artifact uses a canonical artifact envelope and remains segmentable and addressable so an AI system can retrieve the smallest sufficient authorized context and cite its sources.

AI-first does not mean AI-controlled. AI systems may draft, compare, assemble, validate, recommend, and execute within an approved delegation. They may not approve their own fundamental architecture decisions, grant themselves authority, or waive non-delegable controls.

### 2.3 Human approval

Fundamental decisions require attributable human approval. This includes adoption or amendment of constitutional material, authority and inheritance rules, approval boundaries, product admission criteria, Design Freezes, exceptions to normative controls, source-of-truth transitions, and changes that alter the meaning of previously approved records. Absence of a response is not approval.

Human approval is an evidence-backed event bound to a specific artifact revision and scope. Approval text authored inside the artifact is not sufficient proof of approval.

### 2.4 Immutable history and change evidence

Approved source artifacts are never edited in a way that obscures their prior meaning. Corrections and changes create a new immutable revision with explicit lineage. Deprecation, supersession, expiry, rejection, and archival preserve the earlier artifact, its effective period, and its evidence.

Governed changes retain author and owner identity, reviewer identities, approval evidence, rationale, change reason, affected artifacts, effective date, immutable source revision, supersession references, rollback or recovery references, and integrity evidence. Detailed event schemas are deferred, but these evidence categories are mandatory.

### 2.5 Layered memory

Memory class is a classification and retrieval concept. It does not combine authority, durability, factual recency, retention, retrieval priority, confidentiality, or lifecycle into one ranking. Those dimensions remain independent and explicit.

Promotion between memory classes is governed. Repetition, storage, retrieval ranking, or inclusion in a session does not turn temporary or descriptive memory into policy.

### 2.6 Vendor-neutral

Core identities, authority rules, lifecycle states, schemas, context contracts, policy outcomes, and validation semantics cannot depend on a proprietary model, prompt syntax, database, cloud, programming language, orchestration product, Git host, or CI/CD service. Provider-specific adapters may translate canonical contracts but must not redefine them.

### 2.7 Security and confidentiality boundary

CADP applies least privilege, source authorization, data classification, purpose limitation, context minimization, secrets exclusion, credential protection, production-data restrictions, customer and tenant-data controls, personal-information controls, restricted-repository boundaries, provider eligibility, applicable regional restrictions, output handling, logging classification, retention controls, and auditable external egress.

Authorization and confidentiality filtering occur before semantic retrieval, memory lookup, context assembly, prompt construction, external-provider transmission, and tool execution. A valid authoritative artifact may still be ineligible for a session because of authorization, purpose, provider, regional, or confidentiality restrictions.

Detailed classifications and policy values are deferred. The gates themselves are mandatory, non-waivable foundation controls. Later policies may define eligibility within those gates but may not eliminate them.

### 2.8 Product-independent

CADP defines universal AI engineering behavior and inheritance mechanisms. Domain-specific policy remains within an approved product scope and cannot be presented as a universal CADP rule. All product integrations use the same Product Binding and conformance contracts.

### 2.9 Extensible

New products, artifact types, memory stores, validators, context sources, and adapters can be added through registered interfaces and versioned contracts. Extension must not require modification of unrelated consumers or weaken authority, confidentiality, or audit boundaries.

### 2.10 Versioned

Normative content, contracts, Product Bindings, derived artifacts, and the platform itself have explicit versions. Compatibility and migration are evaluated independently: a document revision, a schema revision, a Product Binding revision, and a tooling release are related but are not interchangeable.

### 2.11 Composable

Platform policy, product scope, task context, memory, and validation rules are independently identifiable units assembled under deterministic applicability rules. Composition preserves source identity and exposes conflicts rather than resolving them through prompt order, retrieval score, or model preference.

## 3. Logical Architecture and Initial Repository Layout

### 3.1 Logical architecture

The logical architecture defines platform responsibilities independently of storage, hosting, or repository topology:

| Plane | Responsibility |
| --- | --- |
| Authority and governance | Normative obligations, approval boundaries, delegation, exceptions, state transitions, change control, and Design Freeze. |
| Knowledge and memory | Classified governed knowledge, factual state, transient memory, retention, provenance, and promotion. |
| Product binding | Product identities, repository and component scopes, CADP adoption, overlays, compatibility, migration, and exceptions. |
| Contracts | Canonical artifact envelopes, derived-representation contracts, policy decisions, context manifests, and interoperability rules. |
| Context compilation | Authorized selection of applicable sources, immutable snapshots, session records, permissions, and provenance. |
| Validation and policy evaluation | Structural, authority, compatibility, confidentiality, freshness, and conformance evaluation. |
| Audit and evidence | Attributable decisions, immutable revisions, rationales, approvals, generated evidence, supersession, and recovery references. |
| Execution and integration | Future tooling and replaceable adapters that consume canonical contracts without owning policy meaning. |

These planes are architectural boundaries, not mandatory services or deployment units.

### 3.2 Initial physical repository layout

The following tree is the initial physical layout of the CADP Git repository. It implements the logical architecture but is not a mandatory topology for every future deployment.

~~~text
cliff-ai-development-platform/
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── .github/
│   ├── CODEOWNERS
│   ├── ISSUE_TEMPLATE/
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/
├── constitution/
│   ├── versions/
│   └── amendments/
├── operating-manual/
│   ├── roles/
│   ├── protocols/
│   ├── workflows/
│   └── escalation/
├── governance/
│   ├── authority/
│   ├── approvals/
│   ├── lifecycle/
│   ├── change-control/
│   ├── exceptions/
│   └── design-freezes/
├── decisions/
│   ├── global/
│   └── product-index/
├── roadmaps/
│   ├── platform/
│   └── product-index/
├── memory/
│   ├── platform/
│   ├── current-state/
│   ├── lessons-learned/
│   └── indexes/
├── context/
│   ├── selection-policies/
│   ├── manifests/
│   ├── session-records/
│   └── provenance/
├── products/
│   ├── registrations/
│   │   ├── cliff-platform/
│   │   ├── hvac-pro/
│   │   ├── salespro/
│   │   └── estimate-pro/
│   ├── bindings/
│   └── projections/
├── prompts/
│   ├── definitions/
│   ├── fragments/
│   ├── compositions/
│   └── evaluations/
├── registry/
│   ├── artifact-types/
│   ├── authority-classes/
│   └── catalogs/
├── templates/
│   ├── governance/
│   ├── decisions/
│   ├── memory/
│   ├── reviews/
│   └── product-registration/
├── schemas/
│   ├── artifacts/
│   ├── governance/
│   ├── memory/
│   ├── context/
│   ├── products/
│   └── validation/
├── validation/
│   ├── policies/
│   ├── rulesets/
│   ├── conformance/
│   ├── reports/
│   └── evidence/
├── tooling/
│   └── adapters/
├── tests/
│   ├── contracts/
│   ├── conformance/
│   ├── integration/
│   └── regression/
└── docs/
    ├── FOUNDATION_ARCHITECTURE.md
    ├── FOUNDATION_ARCHITECTURE_REVIEW.md
    ├── architecture/
    ├── concepts/
    ├── reference/
    └── glossary/
~~~

### 3.3 Top-level folder responsibilities

| Folder | Responsibility |
| --- | --- |
| `.github/` | Optional GitHub hosting and workflow adapter. It may enforce canonical CADP decisions on GitHub but is not a source of governance meaning or a core dependency. |
| `constitution/` | Reserved boundary for the future global AI Constitution, its versions, and amendments. This architecture creates no constitutional content. |
| `operating-manual/` | Approved procedures for satisfying governance requirements, including roles, protocols, workflows, and escalation paths. |
| `governance/` | Canonical authority, approval, state, change-control, exception, and Design Freeze policies. |
| `decisions/` | Canonical global CADP ADRs and indexes or projections of registered product ADRs. |
| `roadmaps/` | Canonical CADP platform roadmaps and indexes or projections of product-owned roadmaps. |
| `memory/` | Canonical CADP memory records and indexes or projections of registered product memory. |
| `context/` | Context-selection policy, immutable input manifests, session-record declarations, and provenance. |
| `products/` | Product registration, Product Bindings, and explicitly labeled product-local projections. |
| `prompts/` | Canonical governed prompt definitions, reusable fragments, compositions, and evaluations. Prompts are execution inputs, not authority. |
| `registry/` | Common controlled catalogs for artifact types, authority classes, and cross-domain discovery, avoiding independent registry semantics in every subsystem. |
| `templates/` | Controlled artifact shapes. A template constrains form but grants no approval or authority. |
| `schemas/` | Future machine-readable contracts. Schemas express structure and compatibility; approved source artifacts retain policy meaning. |
| `validation/` | Canonical validation policies, rulesets, results, and retained evidence. Reports cannot change platform rules. |
| `tooling/` | Reserved integration boundary for future adapters. Detailed runtime packaging follows approved component architecture rather than premature generic subdivisions. |
| `tests/` | Contract, conformance, integration, and regression verification for future schemas and tooling. |
| `docs/` | Foundation architecture, explanatory concepts, references, and terminology. Authority depends on registered type, state, scope, and approval rather than location alone. |

### 3.4 Canonical locations and projections

| Artifact class | Canonical source | Other CADP occurrences |
| --- | --- | --- |
| Global governance, Operating Manual, prompt, and validation policy | Applicable CADP Git folder | Registries, indexes, bundles, and adapters are references or derived projections. |
| Global CADP ADR | `decisions/global/` | Memory and context systems reference the ADR identity and revision. |
| Product ADR | Registered product repository unless an approved policy assigns central ownership | `decisions/product-index/` contains registration metadata, index entries, or projections only. |
| CADP platform roadmap | `roadmaps/platform/` | Context and memory views reference the canonical roadmap. |
| Product roadmap | Registered product repository | `roadmaps/product-index/` contains registration metadata, index entries, or projections only. |
| CADP memory and current-state record | Applicable `memory/` location | Indexes and context bundles are derived. |
| Product memory and current-state record | Source declared by the Product Binding, normally the product repository | CADP retains only registered metadata, indexes, or explicitly labeled projections unless authority is migrated. |
| Session Record | Registered session or evidence location identified by its immutable manifest | Context bundles, conversations, and tool logs are contained references with independent classifications. |
| Lessons Learned | `memory/lessons-learned/` for CADP or the Product Binding-declared product source | Retrieval indexes and session references are derived; the observation is non-authoritative until promoted. |
| Generated evidence | `validation/evidence/` or another registered evidence store | Reports and indexes reference the retained evidence identity and source inputs. |

A single artifact cannot have two canonical sources for the same identity and effective revision. A Product Binding declares any product-owned canonical location. CADP registration, indexing, or synchronization does not transfer ownership or authority.

### 3.5 Structural rules

1. Normative source, operational procedure, machine contract, executable tooling, projection, and evidence remain distinguishable.
2. Every governed source artifact has one stable identity, one canonical source for an effective revision, and a canonical artifact envelope.
3. Copies and projections declare their canonical source and source revision.
4. Generated artifacts never overwrite source artifacts or acquire authority through storage location.
5. Product adoption uses explicit Product Bindings rather than copied universal rules.
6. Archived, rejected, deprecated, superseded, and expired records remain discoverable through lineage and evidence.
7. Folder location narrows expected artifact type but does not determine authority, memory class, lifecycle, scope, or confidentiality.
8. Unregistered artifact types and authority classes have no normative effect.

## 4. Foundation Contracts

### 4.1 Canonical artifact envelope

Every governed artifact requires a canonical envelope containing categories for:

- artifact identity and artifact type;
- authority class and scope;
- owner, author, and allowed writer class;
- artifact version and immutable source revision;
- review workflow state, applicability or disposition, and protection status;
- effective interval and confidentiality class;
- lineage and approval evidence;
- rationale, affected artifacts, and supersession references;
- rollback or recovery reference and integrity evidence.

This is a foundation contract, not a detailed schema. Artifact type, authority class, memory class, folder location, lifecycle, scope, and confidentiality are independent dimensions. Controlled registries govern artifact types and authority classes; unregistered values have no normative effect.

### 4.2 Derived-representation contract

Every generated or indexed representation declares:

- canonical source identity and immutable source revision;
- input manifest;
- generator identity and version;
- generation timestamp;
- confidentiality class;
- freshness status;
- retention class;
- invalidation rule;
- reproducibility expectation;
- evidence classification.

Derived representations are classified as disposable caches, reproducible projections, generated operational artifacts, or retained audit evidence. Their retention follows that classification: a disposable cache may be deleted when invalidated, while generated evidence may require retention even when it can be regenerated.

A source-of-truth transition requires explicit human approval, migration evidence, conflict resolution, and rollback planning. Availability or popularity of a derived store never constitutes migration.

### 4.3 Snapshot and concurrency contract

Every session, context manifest, review, validation result, approval, policy decision, migration, and generated evidence record binds to immutable source revisions and the relevant CADP and Product Binding versions.

The architecture must support parallel agents, branches, and sessions; detect stale sources; and use optimistic conflict detection or an equivalent governed conflict mechanism. Governed merge and promotion preserve authorship, evidence, and lineage. Last-writer-wins behavior is prohibited for governed artifacts.

Implementation mechanisms are deferred, but any implementation must make the evaluated snapshot reproducible and expose conflicts before protected state changes.

### 4.4 Policy decision contract

Provider-neutral policy outcomes are:

- **Allow:** the evaluated operation is permitted for the declared subject, scope, inputs, and effective interval.
- **Deny:** an applicable rule prohibits the operation.
- **Indeterminate:** CADP cannot establish a safe, authoritative decision.
- **Not Applicable:** the evaluated rule does not govern the declared subject or scope.

Each decision records the evaluated rule identity and version, input source revisions, subject and scope, evidence, rationale, decision timestamp, and evaluator identity and version.

Missing or stale required input, unauthorized sources, conflicting authority, invalid exceptions, and unresolved canonical identity produce Indeterminate unless an approved higher-authority rule explicitly defines another safe result. Indeterminate fails closed for protected operations.

GitHub Actions and other CI/CD systems consume policy outcomes through adapters. They do not define CADP policy semantics.

## 5. Memory Classification Model

### 5.1 Independent control dimensions

Every memory class requires the following control fields:

- accountable owner class and allowed writer classes;
- validation source;
- update trigger or cadence;
- freshness or expiry semantics;
- retention class;
- promotion gate;
- archival or deletion rule;
- confidentiality classification;
- authority eligibility.

Phase 1 defines detailed values and numeric retention periods. Until required fields are present and valid, memory cannot be promoted or treated as authoritative.

### 5.2 Memory classes

Memory labels support retrieval and policy selection; their identifiers do not create a universal authority ranking.

| Class | Purpose | Ownership and writers | Update, retention, and authority |
| --- | --- | --- | --- |
| Constitution | Future universal, non-negotiable principles and limits for AI-assisted engineering. | Accountable human constitutional authority; only authorized authors and approvers may change it. | Formal amendment only; permanent history; highest authority when approved and effective. No constitutional content is defined here. |
| Platform Rules | Universal CADP governance, review, context, and development obligations. | Designated CADP governance owner; authorized governance writers. | Governed change; permanent lineage; normative only when approved, effective, and applicable. |
| Product Constitution | Product-scoped inherited constraints and permitted overlays. It is not sovereign and cannot override the global AI Constitution or platform rules. | Designated product governance owner; registered product policy writers and required approvers. | Governed Product Binding change; permanent lineage; normative only within its registered product scope. |
| ADR | A bounded architectural decision with context, rationale, consequences, evidence, and supersession path. | Architecture owner for the declared scope; authorized proposers, reviewers, and approvers. | Event-driven; permanent decision history; normative only when approved, effective, and within scope. |
| Roadmap | Sequencing, milestones, dependencies, and intended outcomes. | Accountable planning owner; authorized planning writers. | Updated by planning events or cadence; expires or is superseded; directive for planning, not permanent engineering policy. |
| Current State | Verified observation of repository, deployment, capability, risk, or active versions at a stated time. | Designated state owner; authorized humans or systems named by policy. | Updated by observation event or cadence; freshness and expiry are mandatory; descriptive and never overrides normative policy. |
| Working Memory | Task hypotheses, intermediate analysis, unresolved questions, and provisional summaries. | Task or product knowledge owner; authorized session participants and tools. | Updated during work; limited retention; non-authoritative; promotion requires evidence and review. |
| Conversation Cache | Raw or condensed interaction material used for short-term continuity. | Session owner; authorized participants and session systems. | Interaction-driven, short-lived, and non-authoritative; deleted or archived under confidentiality policy and cannot promote directly beyond Working Memory. |
| Lessons Learned | Post-event observations about outcomes, failures, or effective practices. | Relevant platform or product knowledge owner; authorized contributors. | Event-driven, reviewed for freshness and duplication; non-authoritative until evidence and review promote it into an ADR, procedure, rule, or verified state record. |

### 5.3 Session Records

A Session Record is a container, not an authority or memory level. It references classified artifacts, immutable input revisions, the applicable CADP and Product Binding versions, permissions, context manifests, outputs, decisions, tool actions, conversations, and evidence. Each contained reference retains its own authority, confidentiality, retention, and lifecycle.

A Conversation Cache is temporary session material. A Session Record may retain evidence about the cache without retaining the full conversation when minimization or retention policy prohibits it.

### 5.4 Promotion, archival, and retrieval

Promotion is an explicit governed action. A conversation may enter Working Memory; verified Working Memory may become Current State or Lessons Learned; a reviewed proposal may become an ADR, procedure, or rule. Repetition, summarization, indexing, or AI confidence cannot perform promotion.

Obsolete governed records are deprecated, superseded, expired, rejected, or archived according to the orthogonal state model. They are not silently demoted because that would obscure historical authority.

Retrieval applies authorization and confidentiality gates first. It then filters by product and task scope, canonical revision, effective interval, applicability, freshness, and access policy before semantic ranking. Results preserve memory class, authority class, provenance, and source revision. Conflicts are surfaced to the policy decision process and are never blended.

## 6. Authority, Governance, and Exceptions

### 6.1 Authority hierarchy

Authority is determined by registered authority class, review state, applicability, scope, effective interval, source revision, and recorded approval. File order, folder location, prompt position, retrieval score, recency alone, or model confidence does not create authority.

Applicable normative artifacts have this precedence:

1. Approved and effective global AI Constitution.
2. Approved and effective universal platform governance and rules.
3. Approved and effective Product Constitution or product overlay within an active Product Binding.
4. Approved and effective ADR within its recorded scope.

A Product Constitution is subordinate to the global AI Constitution and platform governance. Roadmaps, Current State, Working Memory, Session Records, Conversation Cache, Lessons Learned, prompts, templates, context bundles, validation reports, and tooling outputs are not independent authority tiers.

Only an artifact that is Approved, Effective for the evaluated scope and time, canonically resolved, authorized for the subject, and not blocked by confidentiality or protection controls can exercise normative authority. Deprecated material remains applicable only to an explicitly identified legacy binding. Superseded or Expired material has authority only where an explicit legacy binding preserves it. Rejected and Archived material is retained as evidence or history and never has normative authority.

### 6.2 Governance and Operating Manual

Governance defines normative obligations, constraints, authority, and approval requirements. The Operating Manual defines approved procedures for satisfying governance.

Every operating procedure traces to its authorizing governance requirements. The Operating Manual cannot independently create, waive, weaken, or elevate normative obligations. A procedural change that alters an obligation must follow the governance process for that obligation.

### 6.3 Exceptions and delegated action

An exception is not an authority tier. It is a scoped, attributable, time-bounded, explicitly approved delegation or variance issued under a specific authorizing rule.

Every exception identifies:

- stable identity and authorizing rule;
- affected requirement and scope;
- approver and rationale;
- accepted risk;
- effective interval;
- expiry or rollback action;
- supporting evidence;
- non-waivable constraints.

Human approval boundaries, confidentiality controls, authority integrity, audit integrity, and explicit foundational safety boundaries are non-waivable. AI may recommend an exception or execute an allowed action under approved delegation. It may not approve its own fundamental architecture, expand its delegation, or waive a non-delegable control.

Missing, ambiguous, invalid, expired, or unauthorized authority is Indeterminate and fails closed for protected operations.

### 6.4 Conflict resolution

When artifacts appear to conflict, CADP:

1. applies authorization and confidentiality eligibility;
2. resolves canonical identity and immutable revision;
3. excludes artifacts outside scope, effective interval, applicability, or compatible CADP and Product Binding versions;
4. selects the higher registered authority class;
5. evaluates any valid exception only within its authorizing rule, scope, and interval;
6. follows explicit supersession lineage within the same authority and scope;
7. returns Indeterminate and requires human resolution if conflict remains.

Specificity may select among compatible rules at the same authority level. It never permits a lower-authority artifact to contradict a higher-authority artifact.

## 7. Product Binding and Adoption

A Product Binding is the versioned, governed relationship through which a product adopts CADP. It defines:

- stable product identity;
- product repository or repositories and component scopes;
- current and target CADP versions;
- inherited modules;
- approved overlays;
- active exceptions;
- compatibility result;
- adoption and migration state;
- rollback reference;
- effective interval.

The adoption model reserves semantics for Unregistered, Registered, Partial Adoption, Migrating, Conformant, Excepted, and Out of Compliance states. Phase 1 may refine names and transition rules, but implementations must distinguish these conditions rather than reduce adoption to a boolean.

Product Binding rules are explicit:

1. Repository presence does not imply adoption.
2. Synchronization does not imply conformance.
3. Product-local projections cannot override newer applicable canonical CADP revisions.
4. Partial adoption is declared by repository, component, or governed scope.
5. Compatibility is checked before a binding or migration becomes effective.
6. Migrations identify target versions, affected scopes, evidence, and rollback references.
7. Multiple repositories per product and multiple products per repository require explicit, non-overlapping scope registration.
8. Future products inherit through governed onboarding and an effective Product Binding, not automatically by existing.

A stale or incompatible Product Binding cannot be treated as Conformant. The applicable policy decision determines whether work is denied, permitted under an approved exception, or returned as Indeterminate.

## 8. Orthogonal State Model and Design Freeze

State is represented along independent dimensions so document review, applicability, protection, product maturity, release status, and deployment status cannot be confused.

### 8.1 Review workflow

| State | Meaning |
| --- | --- |
| Draft | Author-controlled material under development with no normative authority. This includes proposed material; a separate Proposed state is unnecessary. |
| Review | An immutable candidate revision under defined human review. It remains non-normative until approval. |
| Approved | A revision with attributable human approval. Approval alone does not establish applicability outside its scope or effective interval. |
| Archived | An inactive record retained for history, audit, or legal requirements. |

### 8.2 Applicability and disposition

| State | Meaning |
| --- | --- |
| Effective | Applicable within the declared scope and effective interval, subject to authority and eligibility controls. |
| Deprecated | Discouraged for new work and applicable only to explicitly identified legacy scopes during a transition. |
| Superseded | Replaced by an identified revision and without authority outside preserved legacy bindings. |
| Expired | Outside its approved effective interval and without authority outside preserved legacy bindings. |
| Rejected | Retained review evidence that never acquires normative authority. |

Rejected is a disposition recorded from Review, not an approval state. Emergency Override is an exception type governed by Section 6.3, not a workflow or applicability state.

### 8.3 Protection status and Design Freeze

Protection status is either Unprotected or Design Frozen.

A Design Freeze is an approved temporary protection applied to an explicit baseline. Its record identifies:

- the protected artifact revisions and scope;
- effective interval;
- approved reopen conditions;
- approver;
- change-control and exception evidence.

A Design Freeze can protect multiple Approved and Effective artifacts without changing their review or applicability states. Ending a Design Freeze removes or changes protection only; it does not alter historical approval, effective-period, or supersession evidence.

Design Freeze is not product maturity, release status, deployment status, or permanent architectural immutability.

## 9. Design Goals

### 9.1 Scalable

The same identity, Product Binding, context, and conformance contracts support the initial products and future portfolios. The architecture supports monorepos, polyrepos, shared repositories, multiple agents, parallel branches, concurrent sessions, partial adoption, and stale-source detection without creating product-specific governance mechanisms.

### 9.2 Auditable

For any governed action, CADP can identify the effective rules, source revisions, Product Binding, context inputs, actors, approvals, exceptions, validation results, rationale, supersession, and rollback or recovery references. Historical reconstruction does not depend on a chat remaining available.

### 9.3 LLM-agnostic

Canonical artifacts and decisions remain valid across models and providers. Model-specific formatting, transport, and credentials are adapter concerns. Changing a model cannot change authority, confidentiality, inheritance, or policy semantics.

### 9.4 Reusable

Universal standards, contracts, templates, validators, and context policies are authored once and composed for registered scopes. Reuse occurs through identities and versioned dependencies, not uncontrolled copying.

### 9.5 Safe

CADP defaults to least privilege, explicit scope, bounded context, human approval for fundamental change, conflict refusal, non-waivable controls, traceable exceptions, and auditable egress. Missing or ambiguous governance fails closed for protected operations.

### 9.6 Deterministic

Given the same immutable source revisions, CADP version, Product Binding version, task declaration, effective time, and authorized inputs, CADP selects the same applicable artifacts and policy inputs. Model output may be probabilistic; governance selection, policy outcomes, and provenance must not be.

### 9.7 Maintainable

Canonical ownership is explicit, registry semantics are shared, profile names are domain-specific, and future tooling packages follow approved component boundaries. New abstraction is introduced only when it has a distinct authority, lifecycle, or operational responsibility.

## 10. Future Components

The following components are within the intended platform boundary. Their detailed interfaces, technologies, schemas, and implementation plans require separate approved design work.

| Component | Conceptual purpose |
| --- | --- |
| AI Constitution | Establish the highest-order principles, non-delegable constraints, and amendment boundary for AI-assisted engineering. It is not defined or created by this architecture. |
| Operating Manual | Translate approved governance into traceable procedures, roles, workflows, and escalation paths. |
| Memory Framework | Classify, retain, retrieve, promote, expire, and trace knowledge under the memory controls. |
| Design Freeze | Apply orthogonal protection to an approved, explicit baseline for a scope and interval. |
| ADR System | Register global and product-owned architectural decisions, evidence, dependencies, scope, and supersession without changing canonical ownership. |
| Context Builder | Select authorized applicable sources and produce a bounded context package with an immutable manifest and provenance. |
| Review Engine | Coordinate structured evaluation while separating findings, evidence, recommendations, policy outcomes, and human decisions. |
| Prompt Library | Manage versioned prompt definitions, fragments, and compositions without treating prompts as policy or coupling them to one provider. |
| Validation Engine | Evaluate structure, authority, compatibility, inheritance, freshness, confidentiality, and conformance and produce provider-neutral policy outcomes. |
| Knowledge Graph | Provide a derived relationship view among rules, products, decisions, artifacts, versions, owners, and evidence without becoming authoritative. |
| Session Builder | Assemble a task-specific session from identity, Product Binding, authority, context policy, memory, confidentiality, and tool permissions. |
| Memory Index | Provide a derived, version-aware discovery layer that preserves canonical source, memory class, freshness, scope, confidentiality, and provenance. |

No component may create an alternate authority system or bypass canonical policy decisions inside its implementation.

## 11. Deliverables: Phase 1 Roadmap

Phase 1 defines the contracts needed to interpret and govern the architecture before formal approval and before production tooling implementation. No step is complete merely because it appears in this roadmap.

### Step 1 — Confirm Revision 1 consistency

- Review this revision for internal consistency, scope control, terminology, and traceability to accepted findings.
- Record unresolved issues without granting approval.

**Exit criterion:** the draft is coherent enough to specify its governing contracts.

### Step 2 — Define canonical artifact and metadata contracts

- Define controlled artifact-type and authority-class registries.
- Define the canonical artifact envelope, source identity, revision, lineage, evidence, and source-of-truth transition contracts.

**Exit criterion:** every governed artifact can be identified and classified without relying on folder location.

### Step 3 — Define authority, delegation, exception, and policy-decision contracts

- Define authority eligibility, non-delegable controls, human approval evidence, exception requirements, conflict handling, and provider-neutral policy outcomes.

**Exit criterion:** authority and protected-operation decisions are deterministic and fail closed when indeterminate.

### Step 4 — Define memory-class and retention contracts

- Define owners, writers, validation sources, freshness, retention, promotion, archival, deletion, confidentiality, and authority eligibility for each memory class.

**Exit criterion:** memory classes can be governed without confusing authority, recency, durability, or retrieval priority.

### Step 5 — Define Product Binding and adoption contracts

- Define product and component identities, repository scopes, CADP version pinning, overlays, exceptions, compatibility, adoption states, migration, and rollback.

**Exit criterion:** current and future products can adopt CADP through one explicit versioned model.

### Step 6 — Define confidentiality and context-egress contracts

- Define classification, authorization, minimization, provider and regional eligibility, logging, retention, and external-egress gates.

**Exit criterion:** ineligible sources cannot enter retrieval, context, prompts, providers, or tools.

### Step 7 — Define lifecycle, applicability, and Design Freeze contracts

- Define workflow transitions, dispositions, effective intervals, legacy bindings, protection baselines, reopen conditions, and change evidence.

**Exit criterion:** review, authority, applicability, and freeze protection cannot be conflated.

### Step 8 — Define context, snapshot, and concurrency contracts

- Define task and session declarations, immutable manifests, source snapshots, stale-source detection, concurrent-session conflict handling, and governed merge or promotion.

**Exit criterion:** context and decisions can be reproduced under parallel work.

### Step 9 — Define validation and derived-representation contracts

- Define structural, authority, compatibility, confidentiality, freshness, inheritance, and provenance validation.
- Define cache, projection, operational artifact, and audit-evidence behavior.

**Exit criterion:** derived systems remain traceable, invalidatable, and non-authoritative.

### Step 10 — Perform formal human architecture review

- Review the revised foundation and completed foundation contracts as one system.
- Resolve blocking findings and record the review disposition.

**Exit criterion:** designated human reviewers recommend approval or return the architecture to Draft.

### Step 11 — Approve the Foundation Architecture

- Bind approval to an immutable reviewed revision and its required contracts.
- Publish its effective scope and version without rewriting draft or review history.

**Exit criterion:** designated human approvers explicitly place the foundation revision in Approved workflow state and Effective applicability.

### Step 12 — Begin Constitution drafting only after approval

- Open a separate, human-authorized process for the AI Constitution after the Foundation Architecture is Approved and Effective.
- Preserve this document's architectural boundary; approval does not itself create constitutional content.

**Exit criterion:** Constitution drafting has explicit authorization, scope, owners, and approval boundaries.

### Phase 1 completion gate

Phase 1 is complete only after designated human approvers accept the foundation and the contracts required to interpret it. This Revision 1 remains Draft. It does not authorize production tooling, product-specific rules, or an AI Constitution.
