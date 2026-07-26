# Discovery Operation Evidence Contract Proposal

## 1. Document Control

| Field | Value |
| --- | --- |
| Contract identity | `CADP-CONTRACT-DISCOVERY-OPERATION-EVIDENCE` |
| Title | Discovery Operation Evidence Contract |
| Document type | Contract Proposal |
| Version | 0.2.1 |
| Previous version | 0.2.0 |
| Revision classification | Pre-acceptance Patch Maintenance Revision |
| Revision basis | Canonical Contract System Consistency Verification — bounded dependency-graph reconciliation |
| Status | Draft Contract Proposal |
| Review state | Graph reconciled — Pending bounded Independent Verification |
| Date | 2026-07-25 |
| Architecture domain | Governance Rule Discovery |
| Contract domain | Discovery Operation Evidence |
| Primary responsibility | Canonical semantics of one attributed Discovery Operation and the evidence describing what discovery attempted, under which Federation Boundary, within one exact Decision Context |
| Proposed canonical semantic owner | This contract |
| Repository | `dchaschin79-sys/cliff-ai-development-platform` |
| Source baseline | `5a8f18913e63215fbc000d02a47ac227c4c8eccc` |
| Methodology constraint | Contract Governance Framework Version 0.3.0 is fixed and is not revised or extended |
| Acceptance | Not created |
| Publication | Not created |
| Effectiveness | Not created |
| Normative effect | None |
| Implementation authority | None |
| Supersedes | Draft Proposal Version 0.1.0 for further review only; no normative supersession |

This document is the third Draft Contract Proposal developed under the CADP Contract Governance Framework Version 0.3.0.

It is not Accepted, not Published, not Effective, not implementation-authorizing, and not a Design Freeze. Its existence, authorship, review, Git history, or repository publication does not create Contract Acceptance, Publication, Effectiveness, adoption, or normative authority.

Normative keywords describe the semantics this contract would require only if the proposal later completes the applicable Independent Review, Maintenance Revision where required, Verification, human Acceptance, semantic-equivalent Publication, and Effectiveness stages. They have no current normative effect.

## 2. Authoritative Source Bindings

| Authoritative input | Exact binding | Use |
| --- | --- | --- |
| [Foundation Architecture](../FOUNDATION_ARCHITECTURE.md) | Version 0.2.0; Git object `005f1e0a9fca7d4c75b69a013f0d24710348a866` | Canonical ownership, authority separation, confidentiality, immutable history, product independence, provider neutrality, and fail-closed boundaries |
| [Governance Rule Discovery Architecture Decision Proposal](../architecture/GOVERNANCE_RULE_DISCOVERY_ARCHITECTURE_DECISION_PROPOSAL.md) | Version 0.1.1; Git object `5fc17613f5ef78fb5f546f17bdeded75465da9c0` | Accepted Governed Bounded-Closed Federation architecture, operation-bound discovery evidence, Decision Boundary, separation of concerns, and Category B containment |
| [Governance Rule Discovery Architecture Acceptance Record](../architecture/GOVERNANCE_RULE_DISCOVERY_ARCHITECTURE_ACCEPTANCE_RECORD.md) | Record `CADP-AAR-GRD-0001`, Version 1.0.0; Git object `19995bca6768b1de01c3db2055bc618404dbc9ec` | Architecture Acceptance and authorization for Contract Design and contract review only |
| [CADP Contract Governance Framework](../governance/CONTRACT_GOVERNANCE_FRAMEWORK.md) | Version 0.3.0 Draft; Git object `7d6ced000bb6135fe3ff6a4c3331fa9f6a458e74`; commit `24feb4baa0d89a91a157ab2746c9d4e175fa6c9d` | Task-applied contract ownership, lifecycle, review, Verification, human Acceptance, Publication, Effectiveness, change, and traceability methodology |
| [Governance Rule Discovery Contract Decomposition Plan](GOVERNANCE_RULE_DISCOVERY_CONTRACT_DECOMPOSITION_PLAN.md) | Version 0.2.0; Git object `c4c1fb6c459d72227b0f3342d6af388ba954a5cd`; commit `f26e52f63a9118991f8620cbe733bb6b80722664` | Discovery Operation Evidence primary responsibility, Source Resolver and Discovery Manifest consolidation, seven-contract dependency graph, exclusions, review order, and Category B impact |
| [Rule Source Catalog Contract Proposal](RULE_SOURCE_CATALOG_CONTRACT_PROPOSAL.md) | Version 0.2.1 Draft; Git object `d879876ee5ba9641b2b0d64eb1af7a92568e315c` | Exact upstream semantic candidate reconciled to the Contract Decomposition Plan Version 0.2.0 graph for catalog, source, identity, revision, reference, declaration, participation, scope, eligibility-reference, lifecycle-reference, and metadata-ownership meanings |
| [Rule Source Catalog Contract Acceptance Record](RULE_SOURCE_CATALOG_CONTRACT_ACCEPTANCE_RECORD.md) | Version 0.1.0; status `Pending Human Attestation`; Git object `744cff635ead171fe2694761330ad2e08a2a7377`; commit `d6bcc635ec9d6cc241c66ec0a62ba6435ab7b6a9` | Historical evidence for verified Rule Source Catalog Proposal Version 0.2.0 only; it does not verify or accept Version 0.2.1 |
| [Federation Boundary Contract Proposal](FEDERATION_BOUNDARY_CONTRACT_PROPOSAL.md) | Version 0.2.1 Draft; Git object `24459db26a4440c3ef8b21f0ce1e407b2a8ee648` | Exact upstream semantic candidate reconciled to the Contract Decomposition Plan Version 0.2.0 graph for Federation Identity, Federation Boundary Revision, Federation Boundary Scope, root or root-set basis, Federation Membership, composition relationships, Decision Context binding, and ownership preservation |
| [Federation Boundary Contract Acceptance Record](FEDERATION_BOUNDARY_CONTRACT_ACCEPTANCE_RECORD.md) | Version 0.1.0; status `Pending Human Attestation`; Git object `83e95f3883b1907ff929688fbc88496204ebd1e7`; commit `bb42644353ae6a90991dc3f8dc062fecd2f39739` | Historical evidence for verified Federation Boundary Proposal Version 0.2.0 only; it does not verify or accept Version 0.2.1 |

No other source is used to define this proposal.

The Rule Source Catalog and Federation Boundary proposals remain Draft dependencies. Their graph-reconciled Version 0.2.1 revisions require bounded independent Verification. Their existing Acceptance Records remain `Pending Human Attestation` and bind only the predecessor Version 0.2.0 revisions; neither current proposal is Accepted, Published, or Effective. This proposal consumes their exact Version 0.2.1 meanings only as fixed upstream design dependencies for bounded graph reconciliation. It does not verify or accept them, make them Effective, repair missing human attestation, or acquire their semantic ownership.

If either upstream proposal changes, fails to receive required human Acceptance, or acquires conditions affecting this contract boundary, this proposal must be reevaluated under the applicable contract lifecycle before its own human Acceptance. Downstream acceptance cannot establish or repair missing upstream acceptance.

## 3. Purpose

The Discovery Operation Evidence Contract establishes the canonical provider-neutral semantics of one attributed Discovery Operation and the immutable evidence describing what that operation attempted under one exact Federation Boundary and one exact Decision Context.

The contract exists so downstream closure, provenance, result, validation, audit, and review domains can consume a deterministic operation-level evidence boundary without:

- treating a discovery mechanism as a semantic owner;
- redefining Rule Source Catalog or Federation Boundary meanings;
- inferring an attempt from source presence, repository access, model output, or later results;
- treating an operation manifest as proof that its input set was complete;
- converting activity evidence into closure or provenance sufficiency;
- allowing incomplete or conflicting operation evidence to become a successful discovery claim;
- deciding rule applicability, conflict precedence, or Policy Decision outcomes; or
- selecting an API, schema, storage model, workflow, runtime, provider, or implementation topology.

This contract owns Discovery Operation Evidence only.

## 4. Primary Responsibility and Ownership Boundary

### 4.1 Single Primary Responsibility

The single primary responsibility of this contract is:

> Define the canonical semantics of one attributed Discovery Operation and the evidence describing what discovery attempted, under which exact Federation Boundary, within one exact Decision Context.

Every owned concept is subordinate to that responsibility. No owned concept establishes source identity, catalog participation, federation membership, Decision Context meaning, information-use eligibility, authority, closure, provenance sufficiency, complete or incomplete Rule Universe result meaning, validation, applicability, or Policy Decision outcomes.

### 4.2 Owned Semantic Concepts

This proposal defines the canonical meaning of:

1. Discovery Operation;
2. Discovery Operation Identity;
3. Discovery Operation Evidence;
4. Discovery Operation Evidence Revision;
5. Operation Context Binding;
6. Operation Attribution;
7. Discovery Operation Manifest;
8. Presented Source Route;
9. Source Route Treatment Evidence;
10. Source Resolution Activity Evidence;
11. Operation Observation; and
12. Attempted Source Route Set.

These are semantic concepts, not fields, types, objects, schemas, interfaces, APIs, files, logs, messages, services, jobs, workflow steps, database records, storage structures, or runtime components.

### 4.3 Explicit Ownership Boundary

This contract owns:

- the distinction between one logical Discovery Operation and an exact immutable revision of its evidence;
- the evidence relationship binding one Discovery Operation to one exact externally owned Decision Context;
- the evidence relationship binding the same Discovery Operation to one exact upstream Federation Boundary Revision and scope;
- the separate attributable associations between the recorded attempt and its independently governed Activity Actor identity, and between the Evidence Revision and its independently governed Evidence Asserter identity;
- the operation-level manifest meaning for one attempt;
- the distinction between a route presented to the operation and a route for which an attempt is evidenced;
- operation-bound evidence that an exact upstream source route was or was not attempted;
- operation-bound evidence describing source-resolution activity and observations without deciding source, closure, provenance, or result semantics;
- preservation of unresolved, unavailable, restricted, conflicting, or unverifiable operation observations without silent omission; and
- the aggregate meaning of the Attempted Source Route Set for that operation.

This contract does not own:

- Rule Source, Source Identity, Exact Source Revision Binding, Source Descriptor, Source Reference, Source Declaration, Source Participation, Catalog Identity, Catalog Revision, Catalog Scope, Source Eligibility References, Source Lifecycle References, or Source Metadata Ownership;
- Federation Identity, Federation Boundary Revision, Federation Boundary Scope, Federation Root, Federation Root Set, Federation Member, Federation Membership, Boundary Composition Relationship, or Boundary Ownership Preservation;
- Decision Context identity, contents, construction, validity, lifecycle, scope vocabulary, purpose meaning, evaluation-time meaning, or applicable-baseline meaning;
- Universal Eligibility, confidentiality, purpose eligibility, provider eligibility, information-use eligibility, authority, approval, lifecycle, or Product Binding semantics;
- route closure relevance, traversal policy, closure, completeness, provenance sufficiency, temporal-evidence sufficiency, complete or incomplete Rule Universe result meaning, or validation;
- rule applicability, normative conflict precedence, or Policy Decision outcomes; or
- implementation.

## 5. Discovery Operation

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Identify one bounded, attributable discovery attempt as the semantic subject of operation evidence. |
| Canonical definition | A Discovery Operation is one logically distinct attempt to process presented governed source routes for one exact Federation Boundary Revision within one exact Decision Context. |
| Semantically required invariants | A Discovery Operation represented by this contract MUST have one Discovery Operation Identity, one exact Operation Context Binding, one Operation Attribution containing both mandatory role qualifications, and at least one immutable Discovery Operation Evidence Revision. It MUST NOT be inferred from repository activity, source access, network activity, search output, model output, implementation state, a later Rule Universe result, or prior operation evidence. |
| Relationships | A Discovery Operation is identified by Discovery Operation Identity, described through Discovery Operation Evidence, bound through Operation Context Binding, attributed through Operation Attribution, and summarized within a Discovery Operation Manifest at each applicable Evidence Revision. |
| Ownership boundary | This contract owns the Discovery Operation as an evidence subject. It does not own or prescribe the execution mechanism, runtime operation, workflow, job, request, session, transaction, or process that may later produce evidence. |
| Explicit non-goals | This concept does not define operation initiation, scheduling, execution order, retries, timeouts, concurrency, cancellation, completion, success, failure, orchestration, or implementation lifecycle. |

A Discovery Operation is evidence-scoped. It does not become a complete discovery operation merely because it has evidence, and it does not establish that all required routes were presented, attempted, resolved, or accounted for.

This contract asserts the existence of a Discovery Operation only through evidence carrying both mandatory role qualifications and bound to at least one immutable Discovery Operation Evidence Revision. A presumed or reported operation with no such evidence remains outside the supported operation-evidence boundary and cannot be reconstructed by inference.

Two operations with equivalent inputs or observations remain distinct unless independently governed identity evidence establishes that they are the same Discovery Operation. Repetition does not merge operations, extend an earlier operation, or change its historical evidence.

## 6. Discovery Operation Identity and Evidence Revision

### 6.1 Discovery Operation Identity

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish one logical Discovery Operation from every other operation and from its evidence revisions or representations. |
| Canonical definition | Discovery Operation Identity is the stable logical identity of one Discovery Operation across its evidence revisions and derived representations. |
| Semantically required invariants | One logical operation MUST have one Discovery Operation Identity within its governed identity boundary. Equivalent Decision Context, Federation Boundary, presented routes, observations, or outputs MUST NOT establish identity equivalence. A change in representation, repository location, custodian, or evidence revision MUST NOT create a new logical identity. |
| Relationships | Discovery Operation Identity is the subject of Discovery Operation Evidence Revision, Operation Context Binding, Operation Attribution, and Discovery Operation Manifest. |
| Ownership boundary | This contract owns the logical operation-identity meaning. Canonical artifact governance retains identity integrity, source-of-truth, and revision-evidence semantics. |
| Explicit non-goals | This concept does not define identifier syntax, namespaces, hashes, keys, storage addresses, correlation identifiers, or identity-resolution algorithms. |

### 6.2 Discovery Operation Evidence

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Preserve attributable statements about what one Discovery Operation was presented, what it attempted, and what it observed. |
| Canonical definition | Discovery Operation Evidence is the operation-owned semantic evidence associated with one Discovery Operation Identity and one exact Operation Context Binding. |
| Semantically required invariants | Evidence MUST remain attributable, revision-bound, context-bound, and distinguishable from the source, boundary, eligibility, authority, closure, provenance, result, or validation meanings it references. Evidence MUST NOT grant authority, establish eligibility, repair an upstream defect, prove closure, establish provenance sufficiency, or determine an applicable rule or Policy Decision outcome. |
| Relationships | Discovery Operation Evidence is fixed by an Evidence Revision. Every Evidence Revision MUST have one Operation Attribution and one canonical Discovery Operation Manifest meaning. Presented Source Routes, Source Route Treatment Evidence, Source Resolution Activity Evidence, and Operation Observations are included only as asserted for that exact revision. |
| Ownership boundary | This contract owns the meaning of operation-bound activity evidence. Canonical artifact governance owns the integrity and canonical-source evidence for a particular artifact representation. |
| Explicit non-goals | This concept does not define an event, log, record format, audit-store object, message, document schema, telemetry item, trace, or serialization. |

Evidence is not self-validating. The fact that an operation, actor, mechanism, source owner, or evidence artifact asserts an action does not independently establish the assertion’s integrity, completeness, provenance sufficiency, or validation result.

The mandatory semantic core of every Evidence Revision is:

1. one Discovery Operation Identity;
2. one exact immutable Evidence Revision;
3. one exact Operation Context Binding;
4. one Operation Attribution containing the two mandatory role-qualified relationships defined in Section 8; and
5. one canonical Discovery Operation Manifest meaning.

Route-level evidence remains conditional on what the exact revision asserts. Its conditionality does not make the mandatory semantic core optional. When no Presented Source Route or route-level evidence is asserted, the manifest must preserve that fact explicitly under Sections 9 and 10; an empty or absent representation cannot supply the assertion by inference.

### 6.3 Discovery Operation Evidence Revision

Within this proposal, the shorthand **Evidence Revision** means one Discovery Operation Evidence Revision.

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish one exact immutable semantic state of Discovery Operation Evidence from earlier or later evidence states. |
| Canonical definition | Discovery Operation Evidence Revision is the exact immutable state of the evidence associated with one Discovery Operation Identity at one revision boundary. |
| Semantically required invariants | An Evidence Revision MUST belong to exactly one Discovery Operation Identity and MUST bind one exact Operation Context Binding. A later correction, clarification, supplementation, or reassessment MUST create a new Evidence Revision and MUST NOT mutate an earlier revision. Equivalent content MUST NOT be assumed to identify the same revision without canonical revision evidence. |
| Relationships | An Evidence Revision fixes the Operation Attribution, manifest, presented routes, treatment evidence, resolution-activity evidence, observations, and upstream references asserted at that revision. |
| Ownership boundary | This contract owns the distinction between logical operation identity and exact operation-evidence state. Canonical artifact governance owns revision identifiers, integrity mechanisms, lineage mechanisms, and canonical-source mechanics. |
| Explicit non-goals | This concept does not define version numbering, hashes, commit mechanics, timestamps, storage, synchronization, publication, supersession, or archival mechanisms. |

An Evidence Revision does not claim that the Discovery Operation finished, succeeded, failed, reached closure, produced a complete universe, or captured every relevant event. It fixes only the evidence asserted at that revision.

## 7. Operation Context Binding

### 7.1 Canonical Meaning

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Bind one Discovery Operation to the exact externally owned context and federation boundary under which its evidence is interpreted. |
| Canonical definition | Operation Context Binding is the operation-owned relationship connecting one Discovery Operation Identity and Evidence Revision to one exact immutable Decision Context binding and one exact upstream Federation Boundary Revision and Scope. |
| Semantically required invariants | The Decision Context binding MUST be the same exact binding consumed by the referenced Federation Boundary Revision. The Federation Identity, Federation Boundary Revision, Federation Boundary Scope, and Decision Context source revision MUST be explicit and immutable. A missing, conflicting, stale, unauthorized, ineligible, or unverifiable required binding is `Indeterminate` for the asserted operation relationship and MUST NOT be repaired through inference or convenience. |
| Relationships | Operation Context Binding qualifies Operation Attribution, the Discovery Operation Manifest, every Presented Source Route, Source Route Treatment Evidence item, Source Resolution Activity Evidence item, Operation Observation, and the Attempted Source Route Set. |
| Ownership boundary | This contract owns only the relationship binding its evidence to exact upstream meanings. Decision Context and Federation Boundary meanings remain externally owned. |
| Explicit non-goals | This concept does not define Decision Context fields, values, purpose, time, scope, baseline selection, eligibility, authority, boundary membership, or federation composition. |

### 7.2 Decision Context Consumption

The Operation Context Binding consumes the exact canonical Decision Context source and immutable revision already bound by the upstream Federation Boundary.

Without redefining them, that binding preserves the externally owned contextual meanings required by the accepted architecture, including:

- the Governed Operation or decision subject;
- target and requested scope;
- purpose;
- evaluation time;
- applicable governance baselines; and
- required Universal Eligibility and Governance Authority result references.

This contract does not define the Decision Context identity, constituent facts, representation, construction, authorization, eligibility, validation, lifecycle, or temporal sufficiency. Contextual facts cannot be selected or altered by operation evidence to suppress an otherwise applicable upstream requirement.

### 7.3 Federation Boundary Consumption

Every Discovery Operation MUST bind one exact:

- Federation Identity;
- Federation Boundary Revision;
- Federation Boundary Scope;
- root or root-set basis as referenced by that revision;
- Federation Membership and Boundary Composition Relationship state as referenced by that revision; and
- Decision Context binding already fixed by the boundary.

Operation evidence cannot add, remove, narrow, expand, reinterpret, or infer Federation Membership, create a Federation Root, change a Boundary Composition Relationship, or repair missing boundary eligibility. Observed access to a catalog, source route, repository, or service does not establish federation participation.

A later Federation Boundary change creates a prospective boundary revision and does not silently mutate the Operation Context Binding or any historical Discovery Operation Evidence Revision.

### 7.4 Rule Source Catalog Consumption

For each referenced source or catalog route, operation evidence consumes the exact applicable upstream meanings, including where available:

- Catalog Identity, Catalog Revision, and Catalog Scope;
- Rule Source and Source Identity;
- Exact Source Revision Binding;
- Source Reference and Source Declaration;
- Source Participation;
- Source Eligibility References;
- Source Lifecycle References;
- Source Metadata Ownership; and
- Canonical Logical Source Identity.

This contract does not create, correct, classify, register, authorize, or make Effective a source or catalog assertion. A route may be presented to a Discovery Operation only as operation evidence; presentation does not establish Source Participation, Federation Membership, eligibility, authority, closure relevance, or applicability.

## 8. Operation Attribution

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Make the asserted discovery attempt attributable without assigning governance authority or defining provenance sufficiency. |
| Canonical definition | Operation Attribution is the explicit operation-owned relationship associating one Discovery Operation Evidence Revision with two separately role-qualified identity relationships: Activity Actor Attribution for the recorded discovery attempt and Evidence Asserter Attribution for the assertion of the operation evidence. |
| Semantically required invariants | Both role-qualified relationships MUST identify exact externally governed identity references and MUST remain bound to the same Operation Context Binding and Evidence Revision. The roles MUST remain semantically distinct even when independently governed evidence establishes that the same identity fulfills both. Each role MUST remain distinguishable from custodian, author, repository owner, source owner, reviewer, and downstream evidence consumer. |
| Relationships | Operation Attribution qualifies the Discovery Operation Manifest, Source Route Treatment Evidence, Source Resolution Activity Evidence, and Operation Observations at one Evidence Revision. It may reference independently governed authority, eligibility, integrity, custody, and temporal evidence without redefining them. |
| Ownership boundary | This contract owns the attributable relationship for Discovery Operation Evidence. Identity eligibility, actor authority, delegation, confidentiality, integrity assurance, custody, and provenance sufficiency remain externally owned. |
| Explicit non-goals | This concept does not define a user, service account, agent, model, process identity, governance role, approver, verifier, authority tier, authentication method, signature, credential, or provenance chain. |

Operation Attribution contains these mandatory role qualifications:

1. **Activity Actor Attribution** — associates the recorded discovery attempt with the exact independently governed identity or identities asserted to have performed the discovery-directed activity.
2. **Evidence Asserter Attribution** — associates the Evidence Revision with the exact independently governed identity or identities responsible for asserting that evidence.

These are role qualifications within Operation Attribution, not separate authority roles, governance tiers, provenance owners, actor types, or implementation identities. They do not define identity eligibility or how identity evidence is represented.

One identity may fulfill both role qualifications only when independently governed evidence establishes that relationship. The two qualifications must still be recorded separately so an evidence author, custodian, repository owner, mechanism operator, or later reviewer is not silently treated as the actor whose activity is asserted.

Attribution is not authority. A named actor, mechanism, AI system, repository owner, contract author, source owner, or evidence producer does not acquire discovery, approval, eligibility, or policy authority merely because operation evidence is attributed to it.

Missing, ambiguous, conflicting, or unverifiable Activity Actor Attribution or Evidence Asserter Attribution makes Operation Attribution `Indeterminate` and prevents the Evidence Revision from supporting an attributable-attempt claim. It does not permit either role qualification to be inferred from repository history, network identity, tool access, authorship, custody, or prior behavior.

## 9. Discovery Operation Manifest

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Provide one operation-level semantic aggregate of the evidence asserted for a Discovery Operation at an exact revision. |
| Canonical definition | A Discovery Operation Manifest is the operation-owned aggregate that relates one Discovery Operation Identity and Evidence Revision to its exact Operation Context Binding, both role qualifications within Operation Attribution, Presented Source Routes, Source Route Treatment Evidence, Source Resolution Activity Evidence, Operation Observations, and exact references to the externally owned determinations and evidence used by the operation. |
| Semantically required invariants | A manifest MUST identify one Discovery Operation Identity, one exact Evidence Revision, one exact Operation Context Binding, one Activity Actor Attribution, and one Evidence Asserter Attribution. It MUST preserve every evidence category in Section 9.1 or an explicit `Indeterminate` state for a required category that is missing, conflicting, or unverifiable. Every included assertion MUST be attributable to that revision and context. A manifest MUST NOT assert or imply that its Presented Source Route set is the full Federation Boundary, that its Attempted Source Route Set is complete, that discovery closure was demonstrated, or that a Rule Universe result is complete or incomplete. |
| Relationships | The manifest aggregates operation evidence without acquiring ownership of any referenced upstream or downstream meaning. It may be consumed by Discovery Evidence Provenance, Discovery Closure Evidence, Rule Universe Result, Discovery Validation, audit, and review domains. |
| Ownership boundary | This contract owns the operation-level aggregate meaning. Closure-supporting evidence, discovery lineage, temporal coherence, complete or incomplete result meaning, and conformance results remain downstream-owned. |
| Explicit non-goals | This concept does not define a file, manifest format, field set, log, collection, event stream, database table, message, index, report, API payload, or storage object. |

A Discovery Operation Manifest cannot prove its own completeness. It cannot establish that every Federation Member, closure-relevant source route, conditional route, exclusion, or required evidence condition was presented or processed.

One Evidence Revision has one canonical Discovery Operation Manifest meaning. Multiple permitted representations of that manifest are derived evidence and cannot diverge in semantic content. Competing, incomplete, or unverifiably related manifest assertions are `Indeterminate`; convenience, format, or location cannot select a canonical meaning.

The Discovery Operation Manifest has no independent semantic revision axis. Its canonical meaning is fixed by the same Evidence Revision that fixes the other operation evidence it aggregates.

Absence of a source route, treatment assertion, or observation from a manifest means only that the manifest does not assert it at that Evidence Revision. Absence cannot be interpreted as non-membership, non-relevance, ineligibility, successful processing, or permission to omit the route.

### 9.1 Mandatory Manifest Evidence Boundary

For one exact Evidence Revision, the manifest MUST preserve:

1. the mandatory semantic core defined in Section 6.2;
2. every source route the operation evidence asserts was considered, represented as a Presented Source Route under one qualifying basis from Section 10.1.1;
3. the exact independently owned route-relevance determination reference used for each considered route, or an explicit `Indeterminate` state when that required reference is missing, conflicting, or unverifiable;
4. every externally governed exclusion determination and exact exclusion-evidence reference used by the operation, without evaluating its sufficiency, or an explicit `Indeterminate` state when a required exclusion reference is unavailable;
5. every exact source identity and source revision association asserted by Source Resolution Activity Evidence, together with its operation-level disposition under Section 10.3;
6. the exact Universal Eligibility, confidentiality, purpose, provider, authority, lifecycle, and other externally owned result references used for each dependent route or evidence path, or an explicit unresolved reference state;
7. every Source Route Treatment Evidence assertion and associated Source Resolution Activity Evidence;
8. duplicate, unavailable, restricted, conflicting, failed, and otherwise unresolved conditions asserted as Operation Observations; and
9. an explicit operation-evidence assertion when no Presented Source Route, exclusion, source association, or observation is asserted.

The manifest records which external determinations and evidence the operation used; it does not make those determinations. In particular, recording route-relevance, exclusion, eligibility, source-resolution, conflict, failure, or unresolved-condition evidence does not establish its validity or sufficiency and does not decide closure, provenance, a Rule Universe result, Validation, applicability, or a Policy Decision.

## 10. Presented Source Routes and Attempt Evidence

### 10.1 Presented Source Route

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Identify an exact upstream governed source route that operation evidence asserts was presented for possible treatment in one Discovery Operation. |
| Canonical definition | A Presented Source Route is the operation-owned reference to one exact upstream route under exactly one of the two closed qualifying bases in Section 10.1.1, as presented under one Operation Context Binding. |
| Semantically required invariants | The route reference MUST identify exactly one qualifying basis and preserve the complete immutable identity tuple required by that basis, including upstream identities, exact revisions, scope, owner, boundary relationship, eligibility references, lifecycle references, and Decision Context relationship. A candidate satisfying neither basis, or appearing to satisfy both without independently governed disambiguation, is `Indeterminate` and MUST NOT be represented as a Presented Source Route. Presentation MUST NOT be inferred from source accessibility, repository location, search results, prior operations, or later outputs. |
| Relationships | A Presented Source Route may have Source Route Treatment Evidence, Source Resolution Activity Evidence, and Operation Observations. |
| Ownership boundary | This contract owns only the fact asserted by operation evidence that the exact upstream route was presented. The route’s identity, membership, relationship type, eligibility, authority, closure relevance, and source meaning remain externally owned. |
| Explicit non-goals | This concept does not admit a route to the Federation Boundary, make it closure-relevant, establish availability, require traversal, or determine whether it contains a rule. |

The set of Presented Source Routes is not the Federation Boundary, Rule Source Catalog, closure-relevant route set, Rule Corpus, or Rule Universe. A route not presented remains an absence in operation evidence, not evidence of non-membership or irrelevance.

An Evidence Revision may assert that no route was presented only through explicit attributable operation evidence. An empty manifest, a missing route list, or silence does not establish that assertion and remains `Indeterminate`.

### 10.1.1 Closed Presented Source Route Qualifying Bases

A Presented Source Route MUST use exactly one of these upstream relationship bases:

1. **Federation Membership route basis** — one exact Federation Membership within the bound Federation Boundary Revision, together with its qualifying member class, exact member identity and revision, Federation Boundary Scope, Decision Context binding, and the exact upstream Catalog Identity, Catalog Revision, Source Participation, Source Declaration or Source Reference, Canonical Logical Source Identity, and Exact Source Revision Binding applicable to the route.
2. **Boundary Composition route basis** — one exact Boundary Composition Relationship within the bound Federation Boundary Revision, together with every participating Federation Identity and Boundary Revision, Federation Boundary Scope, Decision Context binding, externally governed relationship type and governing revision, retained ownership, and required upstream eligibility and lifecycle references.

These bases consume the upstream meanings already bound by this proposal. They do not create or redefine Source Participation, Federation Membership, Boundary Composition Relationship, source identity, route eligibility, authority, closure relevance, or traversal behavior.

The immutable identity tuple for a Presented Source Route is the selected qualifying basis plus every exact upstream identity, revision, scope, relationship, and Operation Context Binding required by that basis. Repeated operation activity directed to the same immutable tuple does not create another Presented Source Route; the repeated activity remains separately attributable within Source Resolution Activity Evidence.

When the qualifying basis, identity tuple, or independently governed disambiguation is missing, conflicting, stale, or unverifiable, the candidate remains an Operation Observation with an `Indeterminate` route relationship. It cannot enter the Presented Source Route set or Attempted Source Route Set.

### 10.2 Source Route Treatment Evidence

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish what the Discovery Operation evidence asserts was attempted from what it does not establish as attempted. |
| Canonical definition | Source Route Treatment Evidence is the attributable, revision-bound operation evidence classifying whether the minimum semantic evidence of a discovery-directed operation action against one exact Presented Source Route is present for the fixed Operation Context Binding. |
| Semantically required invariants | `Attempted` requires every element of the Minimum Attempt Evidence in Section 10.2.1. `Not Attempted` requires the explicit negative operation assertion and consistency conditions in Section 10.2.2; silence or absence MUST NOT be converted into `Not Attempted`. When either classification lacks its required evidence, or when treatment and activity evidence conflict, treatment is `Indeterminate` and MUST NOT be represented as attempted, not attempted, processed, resolved, or successful. |
| Relationships | Treatment Evidence refers to one Presented Source Route and may relate to Source Resolution Activity Evidence and Operation Observations. |
| Ownership boundary | This contract owns only the operation-evidence distinction among `Attempted`, `Not Attempted`, and `Indeterminate`. It does not own route eligibility, traversal obligations, closure relevance, closure consequences, discovery result classification, or validation. |
| Explicit non-goals | This concept does not define execution status, retries, progress, success, failure, completion, performance, ordering, concurrency, or operational workflow. |

The three treatment meanings are semantic evidence classifications, not implementation states, lifecycle states, registry values, schema values, or Policy Decision outcomes.

An `Attempted` assertion does not establish that the route was resolved, that every source behind it was processed, that the operation was correct, or that closure was achieved. A `Not Attempted` or `Indeterminate` assertion records operation evidence only; downstream owners determine any closure, result, remediation, or validation consequence.

#### 10.2.1 Minimum Attempt Evidence

For this contract, a **discovery-directed operation action** means an attributable evidence assertion that discovery processing was directed to the exact immutable identity tuple of one Presented Source Route under the fixed Operation Context Binding. It is a semantic evidence relationship, not a runtime action type, command, request, call, job, event, algorithm, or implementation step.

A treatment is `Attempted` only when the same Evidence Revision preserves:

1. the exact Presented Source Route and its one qualifying basis;
2. the exact Discovery Operation Identity, Evidence Revision, and Operation Context Binding;
3. the Activity Actor Attribution for the asserted action;
4. the Evidence Asserter Attribution for the action evidence;
5. an explicit attributable assertion that at least one discovery-directed operation action occurred against that route;
6. the exact immutable evidence and integrity references supporting that action assertion; and
7. no conflicting `Not Attempted` assertion or other evidence that makes the action relationship unverifiable.

The minimum establishes only that the operation evidence supports an attempt assertion. It does not establish source accessibility, successful resolution, correct processing, route relevance, closure, provenance sufficiency, a Rule Universe result, Validation, applicability, or a Policy Decision outcome.

#### 10.2.2 Treatment and Activity Consistency

A treatment is `Not Attempted` only when the same Evidence Revision contains an explicit, attributable operation-level assertion that no discovery-directed operation action occurred against the exact Presented Source Route and contains no Source Resolution Activity Evidence asserting such activity for that route.

The following consistency rules apply:

- Source Resolution Activity Evidence that satisfies the Minimum Attempt Evidence requires treatment `Attempted`.
- Source Resolution Activity Evidence that lacks any Minimum Attempt Evidence element makes treatment `Indeterminate`; it cannot support `Attempted`.
- A `Not Attempted` assertion and Source Resolution Activity Evidence for the same route and Evidence Revision conflict; the treatment becomes `Indeterminate`.
- An Operation Observation, source-access observation, returned reference, provider statement, or implementation record does not independently establish `Attempted` unless it satisfies every Minimum Attempt Evidence element.
- Silence, an empty manifest, absence of Source Resolution Activity Evidence, or absence of an observed source does not establish `Not Attempted`.

These rules classify operation evidence only. They do not define execution status, failure status, validation, assurance sufficiency, or downstream consequence.

### 10.3 Source Resolution Activity Evidence

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Record operation-bound evidence describing activity directed toward resolving an exact Presented Source Route and the operation-level disposition asserted for that activity, without defining a resolver implementation or source-resolution authority. |
| Canonical definition | Source Resolution Activity Evidence is the attributable, revision-bound operation evidence of activity directed toward associating one Presented Source Route with exact upstream source, catalog, boundary, eligibility, lifecycle, and revision references under the fixed Operation Context Binding. It records exactly one operation-level disposition under Section 10.3.1. |
| Semantically required invariants | Activity Evidence MUST preserve exact upstream identities and revisions used or observed, distinguish asserted activity from its operation-level disposition and observed conditions, and retain unresolved or conflicting references without silent normalization. Activity Evidence MUST satisfy the treatment-consistency rules in Section 10.2.2. It MUST NOT create Source Identity, Source Participation, Federation Membership, eligibility, authority, canonical ownership, provenance sufficiency, closure, or a complete or incomplete Rule Universe result. |
| Relationships | Activity Evidence is subordinate to one Source Route Treatment Evidence item and may be associated with Operation Observations. Exact source meanings remain upstream; closure, provenance, result, and validation meanings remain downstream. |
| Ownership boundary | This contract owns the operation-bound meaning of the recorded activity. It does not own the source route, resolver mechanism, retrieval behavior, traversal semantics, evidence assurance, or downstream interpretation. |
| Explicit non-goals | This concept does not define lookup, query, search, retrieval, parsing, traversal, recursion, network access, repository access, model behavior, ranking, caching, retries, algorithms, or runtime success. |

Observed source accessibility, returned content, a matching identity, or an exact revision reference does not independently prove that the source was eligible, authoritative, canonically resolved, fully processed, or sufficient for closure.

#### 10.3.1 Resolution Activity Disposition

Each Source Resolution Activity Evidence assertion has exactly one operation-level disposition:

1. **Source Association Asserted** — the operation evidence explicitly associates the Presented Source Route with one or more exact upstream source identities and revisions observed for the activity.
2. **No Source Association Asserted** — the operation evidence explicitly asserts that the activity produced no source association within that Evidence Revision.
3. **Indeterminate** — the activity disposition or required source identity, revision, attribution, context, integrity, or relationship evidence is missing, conflicting, stale, ambiguous, or unverifiable.

`Source Association Asserted` records what the operation evidence asserts it observed. It does not establish canonical source identity, successful resolution, eligibility, authority, provenance sufficiency, closure, correctness, or validation. `No Source Association Asserted` does not prove source absence, non-membership, non-relevance, failure, or incompleteness. An `Indeterminate` disposition cannot be promoted by inference, implementation behavior, later output, or downstream demand.

Operation Observations preserve unavailable, restricted, duplicate, conflicting, failed, or otherwise unresolved conditions associated with the disposition. They do not replace the disposition or determine its downstream consequence.

### 10.4 Attempted Source Route Set

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Aggregate the exact Presented Source Routes having attributable `Attempted` treatment evidence for one Discovery Operation Evidence Revision. |
| Canonical definition | Attempted Source Route Set is the operation-owned set of exact Presented Source Route references for which the same Evidence Revision records `Attempted` Source Route Treatment Evidence. |
| Semantically required invariants | Every member MUST have exact route identity and revision references, the same Operation Context Binding, and attributable `Attempted` evidence. Routes with `Not Attempted` or `Indeterminate` treatment MUST NOT be included. Equivalent route labels, locations, or returned content MUST NOT be treated as identity equivalence without upstream evidence. |
| Relationships | The set is derived semantically from the treatment evidence within the one canonical Discovery Operation Manifest meaning fixed by the same Evidence Revision. The manifest has no independent revision identity. |
| Ownership boundary | This contract owns the attempt-evidence aggregation only. Federation Boundary owns membership; Discovery Evidence Provenance owns attributable lineage and temporal coherence; Discovery Closure Evidence owns closure-supporting evidence interpretation; Rule Universe Result owns complete-versus-incomplete result meaning. |
| Explicit non-goals | This concept does not represent the full boundary, closure-relevant route set, successfully resolved route set, Rule Corpus, Complete Rule Universe Snapshot, or Incomplete Discovery Result. |

The Attempted Source Route Set cannot prove that every required route was attempted. Its cardinality, apparent coverage, repeated use, provider confidence, or similarity to an earlier set cannot establish closure or completeness.

## 11. Operation Observations

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Preserve attributable conditions observed during treatment of a Presented Source Route without resolving their upstream or downstream semantic consequence. |
| Canonical definition | An Operation Observation is an operation-owned evidence assertion that a condition was observed in relation to one Discovery Operation, Presented Source Route, treatment assertion, or source-resolution activity under the exact Operation Context Binding. |
| Semantically required invariants | An observation MUST identify its Discovery Operation Identity, Evidence Revision, Operation Context Binding, attribution, and exact related upstream references. Missing, restricted, unavailable, conflicting, stale, ambiguous, or unverifiable conditions MUST remain explicit when asserted and MUST NOT be silently omitted, normalized, downgraded, or converted into success. |
| Relationships | Observations may describe source unavailability, restricted handling, identity ambiguity, revision disagreement, relationship conflict, returned evidence, or unresolved upstream references. Their eligibility, confidentiality, authority, closure, provenance, result, and validation consequences remain externally owned. |
| Ownership boundary | This contract owns only the operation-level evidence assertion that a condition was observed. It does not own the condition’s canonical source meaning, normative precedence, assurance level, disclosure treatment, closure consequence, result classification, or validation outcome. |
| Explicit non-goals | This concept does not define error codes, exception types, event classes, severity, remediation, retry policy, conflict resolution, disclosure format, or operational response. |

Operation evidence may record duplicate references, overlapping scopes, competing identities or revisions, inaccessible sources, and other observed conflicts. Recording a conflict does not decide whether competing rules apply, which source controls, whether equivalence exists, or whether the operation is complete.

Restricted information may be represented only through independently eligible evidence paths. This contract defines no entitlement to access, disclose, redact, summarize, encrypt, transform, or expose restricted information. A protected or non-disclosing reference cannot be treated as absent merely because its underlying content is not visible to an evidence consumer.

## 12. Evidence Integrity and Historical Preservation

Discovery Operation Evidence must preserve:

- the exact Discovery Operation Identity;
- the exact immutable Evidence Revision;
- the exact Operation Context Binding;
- the exact upstream Federation Boundary and Decision Context bindings;
- separate Activity Actor Attribution and Evidence Asserter Attribution references;
- exact Presented Source Route references;
- Source Route Treatment Evidence;
- Source Resolution Activity Evidence;
- Operation Observations;
- externally owned integrity, eligibility, authority, lifecycle, and temporal evidence references where required; and
- the distinction between asserted evidence, missing evidence, conflicting evidence, and later evidence.

This contract defines the semantic requirement for immutable operation evidence but does not define integrity algorithms, signatures, hashes, storage, audit systems, canonical-source mechanics, retention intervals, or validation procedures.

A later operation, evidence revision, boundary revision, source revision, reassessment, review, or result MUST NOT:

- mutate an earlier Evidence Revision;
- backfill an action that the earlier revision did not evidence;
- erase a route, treatment assertion, observation, ambiguity, restriction, unavailability, or conflict;
- convert missing or indeterminate operation evidence into an attempted or successful assertion;
- change the Decision Context or Federation Boundary to which historical evidence was bound; or
- reinterpret historical operation evidence through a later provider or implementation behavior.

Corrections or supplemental evidence create a new attributable Evidence Revision and preserve predecessor meaning and lineage. Whether that evidence is sufficient for provenance, closure, a Rule Universe result, validation, or later reassessment remains owned elsewhere.

## 13. Semantic Relationship Map

| From | Relationship | To | Ownership rule |
| --- | --- | --- | --- |
| Discovery Operation Identity | is described at | Discovery Operation Evidence Revision | This contract owns the operation-to-evidence relationship |
| Discovery Operation Evidence Revision | is qualified by | Operation Context Binding | This contract owns the binding relationship only |
| Operation Context Binding | references exactly | Decision Context binding | Decision Context remains externally owned |
| Operation Context Binding | references exactly | Federation Identity, Boundary Revision, and Scope | Federation Boundary remains upstream-owned |
| Discovery Operation Evidence Revision | is attributed through | Activity Actor Attribution and Evidence Asserter Attribution | This contract owns the two role-qualified attribution relationships; identity, authority, eligibility, and provenance sufficiency remain external |
| Discovery Operation Manifest | aggregates and preserves exact references to | Presented Source Routes, externally owned route-relevance and exclusion determinations, eligibility results, source associations, Treatment Evidence, Activity Evidence, and Observations | This contract owns only the operation-level aggregate and reference relationships; it does not own or evaluate the referenced meanings |
| Presented Source Route | is qualified by exactly one | Federation Membership route basis or Boundary Composition route basis | This contract owns only presentation evidence; Rule Source Catalog and Federation Boundary retain the complete canonical route-basis meanings |
| Source Route Treatment Evidence | classifies operation evidence as | `Attempted`, `Not Attempted`, or `Indeterminate` under the minimum evidence and consistency rules | This contract owns the evidence distinction, not downstream consequences |
| Source Resolution Activity Evidence | records activity and exactly one operation-level disposition concerning | Presented Source Route | This contract owns activity evidence and the operation-level assertion; source identity, canonical resolution, and result semantics remain external |
| Attempted Source Route Set | aggregates | Routes with `Attempted` evidence | This contract owns attempt aggregation, not completeness |
| Operation Observation | records an observed condition concerning | Operation, route, treatment, or activity | This contract owns the observation assertion, not canonical condition or outcome meaning |
| Discovery Evidence Provenance | consumes | Discovery Operation Evidence | Provenance contract cannot redefine operation evidence |
| Discovery Closure Evidence | consumes | Discovery Operation Evidence | Closure-evidence contract cannot redefine operation evidence |
| Rule Universe Result | consumes through governed dependencies | Operation and closure-supporting evidence | Result contract owns complete-versus-incomplete result meaning |
| Discovery Validation | evaluates conformance of | Discovery Operation Evidence | Validation contract owns validation outcome |

No relationship transfers canonical semantic ownership. A downstream reference to Discovery Operation Evidence does not acquire operation-evidence ownership, and this contract does not acquire the upstream or downstream meaning of what it references.

## 14. Contract Invariants

If later Accepted, Published, and made Effective, this contract would require:

1. **One primary responsibility:** Discovery Operation Evidence is the only primary responsibility.
2. **One operation identity:** every evidence assertion belongs to one exact Discovery Operation Identity.
3. **Immutable evidence revision:** every asserted evidence state is fixed by one exact revision and is never silently mutated.
4. **Exact context binding:** every operation evidence revision consumes one exact immutable Decision Context binding.
5. **Exact boundary binding:** every operation consumes one exact Federation Identity, Boundary Revision, and Scope carrying the same Decision Context binding.
6. **Role-qualified attributable evidence:** every Evidence Revision has separately recorded Activity Actor Attribution and Evidence Asserter Attribution, each bound to an exact independently governed identity reference.
7. **Attribution is not authority:** evidence attribution cannot create authority, eligibility, approval, or canonical ownership.
8. **Upstream ownership preservation:** source-catalog and federation meanings remain owned by their exact upstream contracts.
9. **Closed presentation basis:** every Presented Source Route has exactly one complete qualifying basis defined in Section 10.1.1; an absent, incomplete, or ambiguous basis is `Indeterminate`.
10. **Presentation is not membership:** presenting a route does not create Source Participation, Federation Membership, closure relevance, authority, eligibility, or applicability.
11. **Attempt evidence is explicit and consistent:** `Attempted` requires all minimum evidence in Section 10.2.1; `Not Attempted` requires an explicit attributable negative assertion and no contradictory activity evidence; silence or inconsistent evidence is `Indeterminate`.
12. **Disposition is explicit:** every Source Resolution Activity Evidence assertion records exactly one operation-level disposition without establishing canonical source resolution.
13. **Indeterminate remains explicit:** missing, conflicting, stale, ambiguous, restricted, or unverifiable required evidence cannot be converted into a positive assertion.
14. **Manifest evidence boundary is mandatory:** the manifest preserves every evidence category and exact external reference required by Section 9.1, or an explicit `Indeterminate` state, without deciding the referenced meaning.
15. **Manifest is not closure:** a Discovery Operation Manifest cannot prove its own completeness.
16. **Attempted set is not complete universe:** the Attempted Source Route Set is not a closure-relevant route set, Rule Corpus, or Rule Universe result.
17. **Observation is not resolution:** recording a condition does not resolve its source, membership, precedence, closure, provenance, result, or validation consequence.
18. **No silent omission:** unavailable, restricted, conflicting, or inconvenient operation observations cannot be silently dropped when asserted or required by the operation evidence boundary.
19. **No retroactive mutation:** later boundaries, contexts, sources, evidence, results, or decisions do not rewrite historical operation evidence.
20. **No discovery-to-closure collapse:** this contract does not determine closure or completeness.
21. **No discovery-to-provenance collapse:** this contract does not determine provenance sufficiency or temporal coherence.
22. **No discovery-to-result collapse:** this contract does not create Complete Rule Universe Snapshots or Incomplete Discovery Results.
23. **No discovery-to-validation collapse:** operation evidence does not validate itself.
24. **No discovery-to-applicability collapse:** operation evidence cannot decide that a rule applies.
25. **No discovery-to-Policy-Decision collapse:** operation evidence cannot decide normative precedence or a Policy Decision outcome.
26. **Fail-closed interpretation:** missing or unverifiable required operation bindings prevent the unsupported claim; they never create permission or success.
27. **Provider neutrality:** equivalent evidence has the same semantic meaning regardless of model, repository host, database, policy engine, workflow product, or implementation.
28. **Implementation independence:** software behavior, telemetry, logs, files, services, and storage cannot redefine the canonical semantics.

## 15. Consumed Semantics and Upstream Dependencies

| Upstream source or domain | Consumed meaning | Retained ownership boundary |
| --- | --- | --- |
| Foundation Architecture | Canonical identity, authority separation, confidentiality gating, provider neutrality, product independence, fail-closed behavior, and immutable history | Foundation meanings remain unchanged and outside this contract |
| Accepted Governance Rule Discovery architecture | Operation-bound evidence, fixed discovery boundary, exact revisions, attribution, reproducibility, incomplete-evidence visibility, and separation from closure, applicability, and Policy Decision | Architecture family and Decision Boundary remain unchanged |
| Architecture Acceptance Record | Authorization for Contract Design and review within the accepted architecture | Does not approve this contract or authorize implementation |
| Contract Governance Framework Version 0.3.0 | Contract identity, lifecycle, review, Verification, human Acceptance, Publication, Effectiveness, change, and traceability methodology | Framework remains unchanged and outside this contract |
| Contract Decomposition Plan Version 0.2.0 | Discovery Operation Evidence responsibility, Source Resolver and Discovery Manifest consolidation, seven-contract dependency direction, exclusions, review order, and affected Category B items | Plan remains a fixed planning source and is not redefined |
| Rule Source Catalog Proposal Version 0.2.1 | Catalog, source, identity, revision, declaration, reference, participation, scope, eligibility-reference, lifecycle-reference, and metadata-ownership meanings | Graph-reconciled Draft retains every source-catalog meaning and requires bounded Verification |
| Rule Source Catalog Acceptance Record | Historical evidence for verified Proposal Version 0.2.0 and status `Pending Human Attestation` | Record creates no Acceptance and does not verify or accept Version 0.2.1 |
| Federation Boundary Proposal Version 0.2.1 | Federation identity, revision, scope, root or root-set basis, membership, composition, Decision Context binding, and ownership preservation | Graph-reconciled Draft retains every federation meaning and requires bounded Verification |
| Federation Boundary Acceptance Record | Historical evidence for verified Proposal Version 0.2.0 and status `Pending Human Attestation` | Record creates no Acceptance and does not verify or accept Version 0.2.1 |
| Decision Context | Governed Operation or decision subject, target and requested scope, purpose, evaluation time, applicable baselines, and required eligibility and authority references | Decision Context identity, facts, construction, lifecycle, and validation remain externally owned |
| Universal Eligibility and confidentiality governance | Source authorization, confidentiality, purpose, provider, and other information-use eligibility evidence | This contract preserves exact references and creates no eligibility or disclosure semantics |
| Governance Authority and lifecycle | Authority, ownership, approval, delegation, effective interval, supersession, and other externally governed evidence | This contract preserves exact references and creates no authority or lifecycle semantics |
| Canonical artifact governance | Canonical identity, revision, integrity, lineage, and source-of-truth evidence | This contract does not define artifact classes, formats, or integrity mechanisms |

Every consumed meaning is referenced at an exact immutable revision where required. This contract does not copy it into a second canonical owner, repair missing upstream evidence, or convert a Draft dependency into an Accepted, Published, or Effective Contract.

## 16. Downstream Consumers

The planned downstream consumers are:

1. **Discovery Evidence Provenance Contract candidate** — consumes the exact operation identity, context and boundary binding, attribution, manifest, route-treatment evidence, activity evidence, and observations when defining discovery lineage and discovery-specific temporal coherence.
2. **Discovery Closure Evidence Contract candidate** — consumes the exact operation identity, context and boundary binding, attribution, manifest, route-treatment evidence, activity evidence, and observations when composing closure-supporting evidence without acquiring operation-evidence ownership.
3. **Rule Universe Result Contract candidate** — consumes operation evidence only through the governed dependency boundary needed to own complete-versus-incomplete discovery-result meaning; it cannot reinterpret the operation evidence.
4. **Discovery Validation Contract candidate** — evaluates conformance of operation evidence and its relationships without acquiring operation-evidence ownership.
5. **Audit and review consumers** — reconstruct what one operation asserted it attempted, under which exact boundary and context, without treating reconstruction as Acceptance, closure, provenance sufficiency, validation, or implementation authority.

No downstream consumer may:

- change the Discovery Operation Identity or Evidence Revision;
- add or remove a Presented Source Route from historical evidence;
- convert silence into `Not Attempted` or `Attempted`;
- reinterpret an `Indeterminate` treatment as successful;
- use a manifest or Attempted Source Route Set as proof of closure or completeness;
- transfer source-catalog, federation, Decision Context, authority, eligibility, or lifecycle ownership to operation evidence;
- make operation evidence self-validating;
- infer a Complete Rule Universe Snapshot or Incomplete Discovery Result directly from activity evidence alone; or
- treat operation evidence as a rule-applicability or Policy Decision result.

This section defines semantic dependency direction only. It does not define software dependencies, calls, services, packages, messages, deployment, orchestration, or runtime sequence.

## 17. Cross-Contract Non-Overlap

### 17.1 Ownership Matrix

| Semantic concern | Rule Source Catalog owner | Federation Boundary owner | Discovery Operation Evidence owner | Downstream owner |
| --- | --- | --- | --- | --- |
| Logical source and catalog identity | Owns | References | References in operation evidence | References |
| Source and catalog revision | Owns exact source/catalog revision meaning | References | Records exact referenced revision | References |
| Source Declaration and Participation | Owns | Consumes where applicable | Records exact presented relationship | References |
| Federation identity and boundary revision | References | Owns | Binds exactly | References |
| Federation root, membership, and composition | Does not own | Owns | Records referenced boundary state only | References |
| Decision Context | Does not own | Consumes exact external binding | Consumes the same exact external binding | Consumes without redefinition |
| Discovery Operation identity and evidence revision | Does not own | Does not own | Owns | References |
| Presented route and attempt evidence | Does not own | Does not own | Owns operation-level evidence | Consumes |
| Source-resolution activity evidence | Does not own | Does not own | Owns operation-level evidence | Consumes |
| Discovery evidence lineage and temporal coherence | Does not own | Does not own | Does not own | Discovery Evidence Provenance owns |
| Closure-supporting evidence | Does not own | Does not own | Does not own | Discovery Closure Evidence owns |
| Complete-versus-incomplete result meaning | Does not own | Does not own | Does not own | Rule Universe Result owns |
| Conformance result | Does not own | Does not own | Does not own | Discovery Validation owns |
| Rule applicability and Policy Decision | Does not own | Does not own | Does not own | Governance Applicability and Policy Decision retain ownership |

### 17.2 Rule Source Catalog Separation

This contract does not define or alter any Rule Source Catalog concept. It records exact references to upstream source and catalog meanings only when describing operation activity.

Specifically:

- a Presented Source Route does not create a Rule Source, Source Declaration, or Source Participation;
- an observed identity or revision does not become canonical through operation evidence;
- source access, processing, or returned material does not create eligibility, authority, catalog participation, or lifecycle state;
- the Attempted Source Route Set is not a Rule Source Catalog or a catalog revision; and
- Operation Attribution does not replace Source Metadata Ownership.

### 17.3 Federation Boundary Separation

This contract does not define or alter any Federation Boundary concept. It binds one operation to the exact upstream boundary and records only operation activity within that binding.

Specifically:

- a Presented Source Route does not become a Federation Member through presentation or attempt;
- observed connectivity does not create a Boundary Composition Relationship;
- the Discovery Operation Manifest does not establish the boundary;
- the Attempted Source Route Set does not add to, subtract from, or replace Federation Membership;
- activity evidence cannot select a root or root-set topology; and
- an unavailable, restricted, or conflicting route does not permit the operation to rewrite the boundary.

### 17.4 Closure, Provenance, Result, and Validation Separation

This contract may preserve evidence consumed by downstream domains, but it does not:

- determine source-route closure relevance;
- establish that the presented or attempted route set was complete;
- determine whether evidence is sufficient for closure;
- establish provenance sufficiency or temporal coherence;
- classify the discovery result as complete or incomplete;
- create a Complete Rule Universe Snapshot or Incomplete Discovery Result;
- validate the operation evidence; or
- determine downstream remediation, applicability, precedence, or Policy Decision outcomes.

If a semantic assertion cannot be assigned deterministically to one owner in this matrix, the proposal remains Draft and the ambiguity must be resolved through the applicable contract-review process. No assertion may be duplicated for convenience.

## 18. Category B Unresolved Items

The Contract Decomposition Plan maps four accepted Category B items to Discovery Operation Evidence. They remain unresolved.

| Category B item | Effect on this proposal | Preserved boundary |
| --- | --- | --- |
| GRD-05 — Acyclic relationships and harmless bounded cycles | Operation evidence may record exact routes, repeated relationship encounters, and observations associated with an attempt, but the permitted graph-cycle and traversal policy remains undecided. | This proposal defines no traversal, recursion, termination, cycle, or bounded-cycle rule. A cycle observation cannot be converted into successful route processing or closure evidence by this contract. |
| GRD-06 — Restricted sources not disclosed to the requester | Operation evidence may preserve an attributable protected or non-disclosing reference to a restricted route or observed condition only through an independently eligible evidence path. | This proposal defines no access, visibility, disclosure, redaction, confidentiality, or non-disclosing evidence-sufficiency rule. Restricted information cannot be silently omitted or treated as absent. |
| GRD-11 — Conflict evidence allocation | Operation evidence owns only the attributable record that a conflict was observed during the attempt. Allocation of normative precedence and downstream consequences remains unresolved. | This proposal records exact conflicting references without choosing a controlling source, resolving membership or identity, deciding applicability, or producing a Policy Decision outcome. |
| GRD-15 — Emergency source incorporation | Operation evidence remains bound to the exact immutable boundary and context used for the attempt. It may reference externally governed emergency evidence but does not validate or authorize it. | Urgency cannot mutate operation evidence, add standing membership, change the active boundary, bypass authority, or resolve Category B. Any governed boundary change and reevaluation remain prospective and externally owned. |

No Category B classification, assumption, containment boundary, future owner, or reopening trigger is changed by this proposal.

The Category B items affecting Rule Source Catalog, Federation Boundary, Discovery Evidence Provenance, Discovery Closure Evidence, Rule Universe Result, or Discovery Validation are not imported merely because this contract consumes or supplies evidence to those domains.

Category B ownership remains with the future governance forums identified by the accepted Architecture Decision Proposal. This contract records impact and containment only; it does not become the owner of a deferred question.

## 19. Decision Boundary

### 19.1 Inside the Proposal Boundary

This proposal includes only:

- canonical Discovery Operation identity;
- exact immutable Discovery Operation Evidence revisions;
- one exact Operation Context Binding to the externally owned Decision Context and upstream Federation Boundary;
- Operation Attribution with separate Activity Actor Attribution and Evidence Asserter Attribution, without authority or provenance-sufficiency meaning;
- Discovery Operation Manifest meaning for one exact Evidence Revision, including its mandatory operation-evidence and external-reference boundary;
- Presented Source Route meaning under exactly one closed qualifying basis;
- `Attempted`, `Not Attempted`, and `Indeterminate` Source Route Treatment Evidence meanings, including minimum attempt evidence and treatment-activity consistency;
- operation-bound Source Resolution Activity Evidence with one explicit operation-level disposition;
- attributable Operation Observations;
- Attempted Source Route Set meaning without any completeness claim;
- historical preservation and fail-closed interpretation of missing, conflicting, restricted, stale, ambiguous, or unverifiable required operation evidence;
- provider-neutral and implementation-independent semantics; and
- containment of GRD-05, GRD-06, GRD-11, and GRD-15 without resolution.

### 19.2 Outside the Proposal Boundary

This proposal excludes:

- changes to the accepted architecture family or Decision Boundary;
- changes to Foundation, the Contract Governance Framework, or the Contract Decomposition Plan;
- Acceptance, Publication, Effectiveness, adoption, approval, Design Freeze, Product Binding, or governance authority;
- resolution or reclassification of any Category B item;
- GRD-16 Cache Invalidation Detail and GRD-21 Formal Comparative Weighting;
- Rule Source Catalog semantics;
- Federation Boundary semantics;
- Decision Context semantics;
- Universal Eligibility, confidentiality, purpose eligibility, provider eligibility, Governance Authority, delegation, lifecycle, or approval semantics;
- source-route closure relevance;
- traversal, recursion, cycle, ordering, or resolution algorithms;
- closure, completeness, provenance sufficiency, temporal-evidence sufficiency, complete or incomplete Rule Universe result meaning, or validation;
- rule applicability, conflict precedence, or Policy Decision outcomes;
- implementation, runtime behavior, APIs, schemas, storage, or provider-specific behavior; and
- product-specific, tenant-specific, or repository-specific rules.

The accepted Governance Rule Discovery architecture Decision Boundary remains unchanged. This proposal decomposes one contract domain within it and creates no new architecture decision.

## 20. Explicit Non-Goals

This proposal does not define:

- Rule Source semantics;
- Catalog Identity, Catalog Revision, Catalog Scope, Source Identity, Exact Source Revision Binding, Source Descriptor, Source Reference, Source Declaration, Source Participation, Source Eligibility References, Source Lifecycle References, Source Metadata Ownership, or Canonical Logical Source Identity;
- Federation Identity, Federation Boundary Revision, Federation Boundary Scope, Federation Root, Federation Root Set, Federation Member, Federation Membership, Boundary Composition Relationship, or Boundary Ownership Preservation;
- Decision Context semantics, fields, values, representation, construction, validation, or lifecycle;
- Universal Eligibility, source authorization, confidentiality eligibility, purpose eligibility, provider eligibility, information-use eligibility, Governance Authority, or authority eligibility;
- source-route closure relevance;
- closure;
- completeness;
- provenance sufficiency;
- temporal-evidence sufficiency;
- Complete Rule Universe Snapshot;
- Incomplete Discovery Result;
- Rule Corpus;
- Rule Universe;
- discovery validation or conformance outcomes;
- rule applicability;
- normative conflict precedence;
- Policy Decision outcomes;
- approval, Acceptance, Publication, Effectiveness, adoption, supersession, archival, or Design Freeze;
- Product Bindings;
- implementation;
- runtime behavior;
- algorithms;
- traversal;
- recursion;
- ordering;
- retries;
- timeouts;
- scheduling;
- orchestration;
- transactions;
- caching;
- synchronization;
- APIs;
- interfaces;
- schemas;
- fields;
- storage;
- databases;
- files;
- logs;
- events;
- telemetry formats;
- serialization;
- protocols;
- services;
- source code;
- repository layout;
- deployment;
- infrastructure;
- provider-specific behavior;
- registry values; or
- product-specific rules.

## 21. Fail-Closed Evidence Semantics

Discovery Operation Evidence fails closed at its own semantic boundary.

When any required Discovery Operation Identity, Evidence Revision, Operation Context Binding, Federation Boundary reference, Decision Context reference, Activity Actor Attribution, Evidence Asserter Attribution, Presented Source Route qualifying basis, route-relevance reference, exclusion reference, eligibility-result reference, source-association reference, treatment evidence, resolution-activity disposition, activity reference, or asserted observation is missing, conflicting, stale, ambiguous, unauthorized, ineligible, or unverifiable:

- the unsupported evidence relationship is `Indeterminate`;
- the missing relationship cannot be inferred from repository location, technical access, model output, source contents, prior operations, later results, or implementation behavior;
- silence cannot become `Not Attempted`;
- `Not Attempted` cannot coexist with activity evidence for the same route, operation, context, and Evidence Revision without becoming `Indeterminate`;
- observed access cannot become `Attempted` without every minimum evidence element in Section 10.2.1;
- an `Indeterminate` route cannot enter the Attempted Source Route Set;
- missing, restricted, unavailable, or conflicting evidence cannot be silently omitted;
- the manifest cannot claim completeness;
- the operation evidence cannot establish closure, provenance sufficiency, complete or incomplete result meaning, validation, applicability, or a Policy Decision outcome; and
- downstream consumers must preserve the unresolved evidence state rather than repair it by inference.

Fail-closed operation evidence does not itself classify the overall discovery result as incomplete; Rule Universe Result owns that classification using its required upstream evidence. It also does not determine closure failure or validation failure. It prevents only the unsupported operation-evidence claim within this contract’s ownership boundary.

No amount of repetition, elapsed time, implementation confidence, provider confidence, partial success, administrative convenience, or downstream demand changes an `Indeterminate` operation-evidence relationship into supported evidence.

## 22. Provider Neutrality and Implementation Independence

Discovery Operation Evidence semantics do not depend on:

- an AI model or provider;
- a repository host;
- a source-control system;
- a policy engine;
- a search engine;
- a crawler;
- a resolver implementation;
- a database;
- a storage system;
- a graph technology;
- an API style;
- a schema language;
- a serialization format;
- a workflow or orchestration product;
- a service topology;
- a network protocol;
- a logging or telemetry platform;
- a deployment model;
- a user interface; or
- a programming language.

Different providers or future mechanisms may produce or represent evidence only when separately authorized. Equivalent immutable evidence under the same exact bindings has the same semantic meaning regardless of producer or representation.

Implementation artifacts, logs, traces, messages, files, database rows, API payloads, model output, and generated summaries are not automatically Discovery Operation Evidence. Their canonical relationship, integrity, eligibility, attribution, and revision binding must be independently governed. Technical behavior cannot redefine an upstream source, federation boundary, Decision Context, operation-evidence classification, or downstream result.

This proposal defines no implementation, runtime, API, schema, storage, algorithm, service, workflow, database, or provider requirement.

## 23. Traceability

### 23.1 Architecture Traceability

| Proposal responsibility | Architecture or decomposition basis | Preserved boundary |
| --- | --- | --- |
| One operation-bound evidence domain | ADP Sections 3, 8.5, 9, 11, 14, and 15; Decomposition Plan Sections 5.5, 5.6, 6, and 7 | Evidence does not become authority, eligibility, closure, result, or validation |
| Exact Decision Context and Federation Boundary binding | ADP Sections 8.2, 8.6, 8.8, 15, and 18; Federation Boundary Proposal Sections 5–8 and 20 | Upstream meanings remain externally owned and immutable |
| Closed route presentation, minimum attempt evidence, and resolution-activity disposition | ADP Sections 9, 10, 11, 12, and 19; Decomposition Plan Sections 5.5 and 5.6 | Operation evidence remains deterministic without redefining source, boundary, canonical resolution, or result semantics |
| Discovery Operation Manifest and mandatory evidence boundary | ADP Sections 2, 7.3, 9, 11, 12, and 15 | Manifest preserves exact operation evidence and external determination references but cannot prove its own completeness or decide their validity |
| Role-qualified Operation Attribution and historical evidence | ADP Sections 4, 8.5, 12, 15, and 18; Foundation immutable-history principle | Activity Actor and Evidence Asserter relationships remain distinct; attribution does not create authority or provenance sufficiency |
| Conflict observation | ADP Sections 14, 19, and 20; GRD-11 containment | Discovery records evidence without deciding normative precedence |
| Restricted evidence | ADP Sections 8.7, 10.6, 13, 17, and 20; GRD-06 containment | Confidentiality does not permit silent omission; disclosure meaning remains external |
| Emergency immutability | ADP Sections 8.6, 15, 18, and 20; GRD-15 containment | Emergency change remains prospective and externally governed |
| Provider neutrality and fail-closed interpretation | ADP Sections 8.8, 8.9, 13, 15, and 24; Decomposition Plan Sections 13 and 14 | Mechanism cannot change semantics or convert incompleteness into support |

### 23.2 Contract Dependency Traceability

```text
Direct upstream contract edges:
Rule Source Catalog Proposal v0.2.1 ────────┐
                                            ├──> Discovery Operation Evidence Proposal v0.2.1
Federation Boundary Proposal v0.2.1 ───────┘

Direct downstream contract edges:
Discovery Operation Evidence Proposal v0.2.1 ──> Discovery Evidence Provenance
Discovery Operation Evidence Proposal v0.2.1 ──> Discovery Closure Evidence
Discovery Operation Evidence Proposal v0.2.1 ──> Rule Universe Result
Discovery Operation Evidence Proposal v0.2.1 ──> Discovery Validation
```

These are the exact direct edges for this contract in the Contract Decomposition Plan Version 0.2.0. They express semantic dependency direction, not implementation flow, runtime sequence, acceptance inheritance, or authority delegation. A downstream contract cannot repair an upstream Draft, missing Acceptance, invalid revision, or semantic ambiguity.

### 23.3 Required Future Traceability

Any later revision, review, Acceptance Record, Published Contract, or Effectiveness evidence for this contract must preserve:

- contract identity and semantic version;
- exact immutable source revision;
- accepted architecture and Architecture Acceptance Record bindings;
- Contract Governance Framework and Contract Decomposition Plan bindings;
- exact upstream Rule Source Catalog and Federation Boundary proposal or future Effective Contract bindings;
- Decision Context and Operation Context Binding ownership boundaries;
- review, finding, resolution, Verification, and human Acceptance lineage;
- all Category B deferrals and Category C exclusions;
- Decision Boundary;
- compatibility and supersession evidence; and
- explicit statements for Publication, Effectiveness, implementation authority, and Design Freeze.

## 24. Quality Gate Record

| Quality criterion | Proposal result |
| --- | --- |
| Exactly one primary responsibility | Satisfied — Discovery Operation Evidence only |
| Deterministic semantic owner | Satisfied — every owned operation-evidence concept maps to this contract |
| Rule Source Catalog overlap | None — exact upstream meanings are consumed only |
| Federation Boundary overlap | None — exact boundary revision and scope are consumed only |
| Decision Context ownership | External and unchanged |
| Closure ownership | Excluded |
| Provenance sufficiency ownership | Excluded |
| Rule Universe result ownership | Excluded |
| Validation ownership | Excluded |
| Applicability and Policy Decision ownership | Excluded |
| Provider neutrality | Preserved |
| Implementation independence | Preserved |
| Category B preserved unresolved | Satisfied — four mapped items |
| Category C excluded | Satisfied — GRD-16 and GRD-21 remain outside |
| Independent Review findings | Resolved and independently verified for Version 0.2.0 — MAJ-01, MAJ-02, MAJ-03, MIN-01, and MIN-02 |
| Graph reconciliation | Version 0.2.1 aligns the exact Decomposition Plan binding and direct upstream and downstream declarations; pending bounded independent Verification |
| Foundation changed | No |
| Accepted architecture changed | No |
| Decision Boundary changed | No |
| Contract Governance Framework changed | No |
| Contract Decomposition Plan changed | No |
| Rule Source Catalog Proposal changed | Graph-reconciled Version 0.2.1 consumed; semantic ownership unchanged |
| Federation Boundary Proposal changed | Graph-reconciled Version 0.2.1 consumed; semantic ownership unchanged |
| Acceptance created | No |
| Publication created | No |
| Effectiveness created | No |
| Implementation created or authorized | No |

## 25. Contract Lifecycle and Next Governance Action

| Lifecycle evidence | Current state |
| --- | --- |
| Proposal | Draft Contract Proposal Version 0.2.1 |
| Internal review | Not created |
| Independent Review | Completed — `REQUIRES MAJOR REVISION`; three Major and two Minor Findings |
| Semantic Maintenance Revision | Version 0.2.0 completed and independently verified |
| Graph Reconciliation Revision | Version 0.2.1 created to align exact dependency declarations with Contract Decomposition Plan Version 0.2.0 |
| Verification | Required for the bounded graph reconciliation in exact Version 0.2.1 |
| Acceptance Record | Existing Version 0.1.0 record binds Proposal Version 0.2.0 only and does not apply to Version 0.2.1 |
| Acceptance | Not created |
| Publication | Not created |
| Effectiveness | Not created |
| Supersession | None |
| Archival | No |

The next permitted governance action is bounded independent Verification of this exact Version 0.2.1 Draft revision against the Contract Decomposition Plan Version 0.2.0 dependency graph and the no-semantic-regression constraints of this reconciliation.

Verification must verify:

- one primary responsibility and deterministic ownership;
- exact binding to the externally owned Decision Context and graph-reconciled Federation Boundary revision;
- separation from Rule Source Catalog and Federation Boundary semantics;
- separation of attempt evidence from closure, provenance sufficiency, result, and validation;
- deterministic `Attempted`, `Not Attempted`, and `Indeterminate` evidence meanings;
- manifest and Attempted Source Route Set non-completeness;
- exact direct upstream edges from Rule Source Catalog and Federation Boundary;
- exact direct downstream edges to Discovery Evidence Provenance, Discovery Closure Evidence, Rule Universe Result, and Discovery Validation;
- absence of any obsolete combined downstream contract reference;
- preservation of GRD-05, GRD-06, GRD-11, and GRD-15;
- fail-closed evidence semantics, immutable history, provider neutrality, and implementation independence;
- continued exclusion of Category C; and
- no Foundation, architecture, Framework, decomposition, semantic ownership, lifecycle-state, or implementation change.

Verification does not create Acceptance, Publication, Effectiveness, implementation authority, adoption, or Design Freeze.

## 26. Methodology Validation Observations

None identified.

The fixed Contract Governance Framework Version 0.3.0 and Contract Decomposition Plan Version 0.2.0 were sufficient to establish this Draft Proposal’s lifecycle position, ownership boundary, dependency direction, upstream Draft handling, downstream separation, and review path. This statement does not approve, amend, reinterpret, or validate the methodology.

## 27. Revision History

| Version | Classification | Summary |
| --- | --- | --- |
| 0.1.0 | Initial Draft Contract Proposal | Establishes the Discovery Operation Evidence semantic candidate under the accepted Governance Rule Discovery architecture and fixed Contract Governance Framework Version 0.3.0. Consolidates the Source Resolver and Discovery Manifest candidates into one operation-evidence owner while preserving upstream source and federation ownership, downstream closure/provenance/result/validation ownership, four Category B deferrals, Category C exclusion, and the accepted Decision Boundary. |
| 0.2.0 | Pre-acceptance Major Maintenance Revision | Resolves the completed Independent Review findings by defining a mandatory role-qualified attribution core, closed Presented Source Route qualifying bases, minimum Attempt evidence and treatment consistency, explicit resolution-activity dispositions, a mandatory manifest evidence boundary, and one Evidence Revision axis for manifest meaning. Preserves the primary responsibility, ownership boundaries, Architecture, Framework, decomposition, Decision Boundary, four Category B deferrals, provider neutrality, and implementation independence. |
| 0.2.1 | Pre-acceptance Patch Maintenance Revision | Reconciles the proposal’s exact Contract Decomposition Plan binding and direct dependency declarations with Version 0.2.0 of the plan. Records Rule Source Catalog and Federation Boundary as direct upstream contracts and Discovery Evidence Provenance, Discovery Closure Evidence, Rule Universe Result, and Discovery Validation as direct downstream contracts. No semantic ownership, primary responsibility, Decision Boundary, fail-closed behavior, Category B mapping, provider-neutrality, or implementation-independence meaning changes. |

### 27.1 Independent Review Resolution Map

| Finding | Resolution | Affected sections |
| --- | --- | --- |
| MAJ-01 — Mandatory evidence core and attribution semantics are internally inconsistent | Requires both Activity Actor Attribution and Evidence Asserter Attribution within every Evidence Revision and keeps their externally governed identities and responsibilities distinct. | 6.2, 8, 9, 13, 14, 19, 21 |
| MAJ-02 — Presented-route qualification and attempt semantics are not deterministic | Defines two closed route-qualification bases, a minimum provider-neutral Attempt evidence boundary, and fail-closed consistency between treatment and activity evidence. | 10.1, 10.2, 13, 14, 19, 21 |
| MAJ-03 — The Manifest omits architecture-required discovery evidence | Requires exact references to the external route-relevance, exclusion, source-association, eligibility, treatment, conflict, failure, and unresolved-condition evidence used by the operation without acquiring or evaluating those meanings. | 9.1, 10.3, 13, 14, 19, 21 |
| MIN-01 — Manifest revision terminology is undefined | States that the Discovery Operation Manifest has no independent semantic revision axis and is fixed by the same Evidence Revision as its aggregated evidence. | 9, 10.4 |
| MIN-02 — Operation Observations use causal wording | Replaces causal production language with a non-causal semantic association between activity evidence and observations. | 10.3 |
