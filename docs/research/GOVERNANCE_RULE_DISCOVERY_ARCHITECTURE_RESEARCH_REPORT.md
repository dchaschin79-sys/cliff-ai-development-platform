# Governance Rule Discovery Architecture Research Report

| Field | Value |
| --- | --- |
| Document type | Architecture Research Report |
| Short name | Governance Rule Discovery ARR |
| Version | 0.1.0 |
| Status | Draft |
| Normative status | Non-normative |
| Governance authority | None |
| Decision authority | None |
| Implementation authority | None |
| Research subject | Complete discovery and closure of the Applicable Rule Universe for a Governed Operation |
| Scope | CADP platform-wide architecture research |

## Authority and Use Notice

This report researches architectural options. It is not an Architecture Decision Proposal, contract, approval, Design Freeze, Product Binding, registry, schema, or implementation specification.

The terms, candidate structures, comparisons, and recommendation in this report have no repository governance authority. They do not amend the Foundation Architecture, the Governance Authority Model Architecture Design Proposal, or any CADP contract. Statements using words such as “requires,” “would,” or “should” describe the properties of a researched candidate architecture only.

## 1. Executive Summary

CADP cannot safely declare that it has evaluated every applicable governance rule merely because it evaluated every rule it happened to discover. Completeness requires a bounded and authoritative answer to a prior question: where could governing rules validly come from for this exact operation, scope, and time?

Pure open-world discovery cannot prove that no undiscovered rule exists. A single central rule registry can provide closure, but it concentrates ownership and does not naturally preserve product, repository, external-obligation, and cross-repository boundaries. An operation-specific manifest can preserve exact evidence, but it cannot prove completeness unless its source list is derived from an independently authoritative source-of-sources.

The researched architecture recommended by this report is a **Governed Bounded-Closed Rule Discovery Architecture**. It combines:

1. an authoritative, versioned source-of-sources boundary;
2. federated scope-specific rule-source declarations;
3. explicit inheritance and external-incorporation relationships;
4. an operation-bound discovery boundary;
5. a temporally fixed rule-source snapshot;
6. separate discovery, applicability, and conflict results; and
7. an attributable closure evidence record.

Under this model, CADP would not claim to prove that no rule exists anywhere. It would prove the narrower and governable proposition that every rule source authorized to govern the declared operation under the exact source-of-sources revision, scope bindings, inheritance relationships, and evaluation time has been accounted for.

The model remains extensible because new sources can be added prospectively through governed source declarations. It remains deterministic because an open decision evaluates a fixed source-of-sources revision and fixed source snapshots. A missing source produces an incomplete universe. A conflict among completely discovered rules is a separate conflict condition. Neither condition can produce a successful deterministic evaluation.

## 2. Architectural Problem Statement

The [Governance Authority Model Architecture Design Proposal](../proposals/GOVERNANCE_AUTHORITY_MODEL_ADP.md) introduces the Applicable Rule Universe as the authoritative, scope-bound set of every rule source that could govern a Governed Operation at the evaluated point in time. It requires a Complete Rule Universe before applicability evaluation can succeed.

That proposal identifies candidate rule-source categories, discovery boundaries, and closure evidence. The unresolved architectural question is how completeness can be demonstrated without relying on an evaluator’s unsupported assertion that nothing was omitted.

The problem has five parts:

1. **Authority:** only recognized governance sources may contribute rules.
2. **Discovery:** every recognized source that could govern the operation must be located or explicitly accounted for.
3. **Applicability:** rules found in those sources must be evaluated against the operation and its context.
4. **Conflict:** incompatible discovered rules must be preserved and resolved under governing precedence.
5. **Evidence:** a later reviewer must be able to reconstruct why discovery was considered complete at the decision time.

These parts must remain separate. Discovering a document does not make it authoritative or applicable. Failing to locate a source is not evidence that the source has no applicable rule. Discovering two conflicting rules does not mean discovery was incomplete. Resolving a conflict does not repair an omitted source.

## 3. Existing CADP Architectural Constraints

Any future rule-discovery architecture must remain consistent with existing CADP boundaries:

- The [Foundation Architecture](../FOUNDATION_ARCHITECTURE.md) makes canonical identity, exact revision, scope, effective interval, approval, applicability, and authority independent inputs.
- Foundation requires authorization and confidentiality filtering before retrieval or context assembly.
- Foundation requires reproducible snapshots and exposes stale or conflicting sources before protected state changes.
- Foundation authority is layered: platform governance, product governance within a Product Binding, scoped ADRs, and other governed sources do not acquire authority from file location or retrieval order.
- The [Canonical Artifact Contract](../contracts/CANONICAL_ARTIFACT_CONTRACT.md) owns stable identity, canonical location, immutable revision, lineage, and integrity semantics.
- The [Policy Decision Contract](../contracts/POLICY_DECISION_CONTRACT.md) owns the provider-neutral outcomes `Allow`, `Deny`, `Indeterminate`, and `Not Applicable`.
- The [Authority and Delegation Contract](../contracts/AUTHORITY_AND_DELEGATION_CONTRACT.md) owns authority eligibility, hierarchy consumption, scope, delegation, revocation, and non-delegable boundaries.
- The [Governance Lifecycle Contract](../contracts/GOVERNANCE_LIFECYCLE_CONTRACT.md) keeps approval, effectiveness, adoption, disposition, archival, retirement, and protection orthogonal.
- The [Governance Document Model](../GOVERNANCE_DOCUMENT_MODEL.md) distinguishes normative-capable sources from reviews, history, research, and approval-preparation material.

Rule discovery must consume these meanings. It must not redefine them or turn a discovery system into a new authority tier.

## 4. Terminology

### 4.1 Governed Operation

The exact proposed governance act being evaluated, including subject, requested operation, target artifact or resource, scope, purpose, and evaluation time.

### 4.2 Rule

A normative statement that can constrain, require, prohibit, permit, qualify, or establish evidence requirements for a Governed Operation when the source is authoritative, valid, in scope, and applicable.

### 4.3 Rule Source

A canonically identifiable governed artifact or recognized external source that may contain one or more rules. Discovery of a Rule Source does not establish that every contained rule applies.

### 4.4 Rule-Source Declaration

A governed assertion that identifies a Rule Source, its owning scope, source class, canonical identity, inheritance or incorporation relationships, and the authority by which the source may participate in discovery.

This is a researched concept, not a current CADP artifact or registry value.

### 4.5 Authoritative Rule Registry

A governed collection that identifies individual rules or rule-containing artifacts recognized for discovery. It may centralize entries or aggregate entries owned elsewhere.

### 4.6 Authoritative Source-of-Sources

The authoritative boundary that identifies which rule-source declarations and subordinate source catalogs must be consulted for a specified governance scope. It answers where authoritative rules may be found; it does not decide whether a discovered rule applies.

### 4.7 Discovery Boundary

The operation-specific boundary formed from the Governed Operation, affected scopes, CADP and Product Binding versions, inheritance relationships, external-incorporation relationships, evaluation time, and eligible source-of-sources revision.

### 4.8 Applicable Rule Universe

The exact set of authoritative rule sources and rule revisions discovered within the declared boundary and evaluated for potential applicability to the Governed Operation.

### 4.9 Closure Claim

The proposition that every source path authorized by the discovery boundary has been accounted for and that no unresolved discovery gap could change the set of potentially applicable rules.

### 4.10 Closure Evidence

The attributable, immutable evidence supporting or rejecting a Closure Claim.

### 4.11 Discovery Conflict

An inconsistency about source identity, source ownership, revision, binding, scope, or membership in the discovery boundary.

### 4.12 Rule Conflict

An incompatibility among rules that have already been discovered and whose authority and applicability cannot be reconciled under governing precedence.

### 4.13 Negative Source Declaration

An attributable statement by the authority responsible for a declared source boundary that no subordinate rule source exists for the stated class, scope, and interval.

A negative declaration is evidence about a closed source boundary. It is not evidence that no external fact, law, or document exists outside that boundary.

## 5. Research Basis: Open World and Closed World

The open-world and closed-world distinction is central to rule-universe completeness.

The W3C OWL 2 Primer explains the open-world assumption by distinguishing absent information from false information: a fact absent from an ontology may simply be unknown. In contrast, conventional closed-world systems often treat absence as false. The distinction is described in the [OWL 2 Primer](https://www.w3.org/TR/owl2-primer/#What_is_OWL_2).

The W3C Shapes Constraint Language illustrates a narrower, declared form of closure: a closed shape permits only properties explicitly enumerated by that shape, subject to stated exclusions. This demonstrates that useful closure depends on an explicit boundary rather than a global claim about all possible information. See [SHACL closed shapes](https://www.w3.org/TR/shacl/#ClosedConstraintComponent).

For CADP:

- An **open-world rule model** assumes that additional governing sources may exist unless proven otherwise. It is extensible but cannot independently support a Complete Rule Universe.
- A **global closed-world model** assumes that the repository or registry contains every possible governing source. This is too strong when products, repositories, contracts, laws, and restricted sources can be independently governed.
- A **bounded closed-world model** treats a versioned, authoritative source boundary as complete for a declared operation, scope, and time. Sources outside that boundary cannot silently govern the operation; they must first be incorporated through a recognized governance relationship.

The bounded model does not deny the existence of unknown external facts. It limits normative participation to sources that CADP governance has authoritatively connected to the evaluated scope.

## 6. Rule-Source Domains

### 6.1 Platform Rules

Platform rules are universal or platform-scoped CADP governance sources recognized under the Foundation authority hierarchy. Their discovery route originates from the authoritative CADP platform source boundary.

Platform discovery must preserve:

- exact canonical artifact identity;
- immutable revision;
- lifecycle and effective interval;
- authority class and precedence;
- global or bounded platform scope; and
- supersession and legacy relationships.

### 6.2 Product Binding Rules

A Product Binding is the governed relationship through which a product adopts CADP versions, overlays, and product-scoped governance. Rule discovery should treat the binding as an explicit edge between the platform source boundary and the product source boundary.

The binding identifies which CADP baseline and product overlay versions participate. Discovery cannot infer a Product Binding from repository naming, code imports, organizational ownership, or repeated use.

### 6.3 Repository-Local Rules

Repository-local rules may participate only when an authoritative source declaration establishes:

- the repository’s stable identity;
- the local governance root;
- the scopes governed locally;
- the relationship to platform and product governance;
- whether local additions are permitted;
- the exact effective revision; and
- the treatment of absence, supersession, and legacy rules.

A repository scan alone cannot establish completeness because a rule could be stored outside the scanned path, generated from another source, or inherited through a binding.

### 6.4 Component Rules

Component-specific rules are subordinate scoped sources. A component path or package name does not independently grant authority. The source-of-sources boundary must establish which component declarations are part of the affected scope.

### 6.5 Inherited Governance

Inheritance is an explicit governed relationship, not filename similarity or transitive repository proximity. Each inheritance edge identifies:

- predecessor and successor scopes;
- inherited source identity and revision;
- included or excluded rule classes;
- effective interval;
- permitted overlay behavior;
- precedence; and
- supersession or legacy treatment.

An omitted, ambiguous, cyclic, or revision-unbound inheritance edge prevents closure.

### 6.6 External Obligations

Laws, regulations, contracts, licenses, customer commitments, and other external materials may exist under open-world conditions. CADP cannot prove that all such materials in the world have been discovered.

External obligations enter the bounded governance universe only through an authoritative incorporation relationship. That relationship identifies:

- the external source or controlled source class;
- the reason it governs the declared scope;
- the accountable authority for maintaining the relationship;
- jurisdictional, contractual, product, customer, or subject boundary;
- effective interval and known temporal version;
- confidentiality constraints;
- canonical or authoritative retrieval reference; and
- change-detection or reevaluation responsibility.

The incorporation relationship does not rewrite the external source and does not make CADP the legal authority for interpreting it. It makes the existence and scope of the dependency explicit for governance discovery.

### 6.7 Dynamic Rule Incorporation

A rule source discovered through an ungoverned runtime reference, conversation, web search, model memory, or tool result cannot silently join an active Rule Universe.

Dynamic incorporation is best treated as a separate governed source-boundary change. Once valid, it affects operations prospectively or triggers explicit reevaluation according to its independently valid effective interval. It does not mutate the evidence basis of an already completed decision.

## 7. Candidate Architectures

### 7.1 Candidate A — Open Discovery

The evaluator searches known repositories, documents, indexes, references, and external sources at decision time.

**Advantages**

- Low initial governance overhead.
- Naturally accepts new and previously unknown sources.
- Useful for research, advisory review, and identifying possible missing governance.

**Disadvantages**

- Cannot prove absence of an undiscovered source.
- Search coverage depends on tools, permissions, indexing, naming, and evaluator knowledge.
- Results may change without a governed source-boundary revision.
- Restricted sources may be omitted without visible evidence.

**Architectural risks**

- False completeness.
- Non-reproducible decisions.
- Retrieval ranking mistaken for authority.
- Inconsistent results across providers and evaluators.

**Assessment**

Open discovery is useful for gap detection but insufficient as the sole basis for a Complete Rule Universe.

### 7.2 Candidate B — Central Authoritative Rule Registry

Every governing rule or rule source is registered in one platform-wide authoritative collection.

**Advantages**

- Clear global closure boundary.
- Direct enumeration of known sources.
- Simplified audit and conflict inspection.
- Consistent source classification.

**Disadvantages**

- Central ownership can absorb product, repository, and external-source responsibilities.
- Every scoped change may require a global registry change.
- Federation and restricted-source ownership become awkward.
- Registry availability and accuracy become systemic dependencies.

**Architectural risks**

- Central bottleneck.
- Stale registry entries.
- Accidental authority creation through registration.
- Conflict between the registry and source-owned lifecycle evidence.

**Assessment**

A central registry provides closure but is insufficiently composable as the sole CADP architecture.

### 7.3 Candidate C — Federated Rule Registries

Platform, product, repository, component, and external-obligation authorities each maintain their own rule-source collections.

**Advantages**

- Preserves local semantic ownership.
- Scales across products and repositories.
- Supports confidentiality boundaries.
- Allows independent lifecycle management.

**Disadvantages**

- A caller still needs an authoritative list of registries to consult.
- Federation can introduce cycles, duplicate sources, and incompatible timestamps.
- Local completeness claims may use inconsistent boundaries.

**Architectural risks**

- Missing federation member.
- Scope leakage across registries.
- Divergent source classification.
- Partial snapshots represented as complete.

**Assessment**

Federation is necessary for scale but does not prove global operation-bound closure without an authoritative source-of-sources.

### 7.4 Candidate D — Operation-Bound Rule Manifest

Each Governed Operation carries an immutable manifest of every rule source evaluated.

**Advantages**

- Strong decision traceability.
- Exact revisions and evaluation time can be preserved.
- Supports reproducibility and caching boundaries.
- Does not require central storage of rule contents.

**Disadvantages**

- A manifest proves what was evaluated, not that every required source was discovered.
- Manual assembly can reproduce evaluator blind spots.
- Dynamic or inherited sources can be omitted before the manifest is fixed.

**Architectural risks**

- Complete-processing evidence mistaken for complete-discovery evidence.
- Self-asserted closure.
- Manifest divergence across related operations.

**Assessment**

An operation manifest is necessary closure evidence but cannot serve as its own source-of-sources.

### 7.5 Candidate E — Governed Bounded-Closed Federation

A versioned authoritative source-of-sources identifies the complete set of scoped source declarations that must be traversed for an operation. Each declaration can resolve to a federated rule-source collection. The resulting operation manifest binds the traversal and every exact source revision.

**Advantages**

- Provides an explicit closure root.
- Preserves platform, product, repository, component, and external-source ownership.
- Supports exact operation and time boundaries.
- Separates source discovery from rule applicability and conflict resolution.
- Supports restricted sources without centralizing their contents.
- Allows prospective extension through governed declaration changes.

**Disadvantages**

- Requires disciplined governance of source declarations and inheritance edges.
- Closure depends on the integrity and timeliness of the authoritative source boundary.
- Cross-repository composition is more complex than a central registry.
- Negative source declarations require attributable ownership.

**Architectural risks**

- Incorrect source-of-sources authority.
- Cyclic or ambiguous inheritance.
- Stale scope catalogs.
- Improperly incorporated external obligations.
- False negative declarations.

**Assessment**

This candidate provides the strongest balance of determinism, federation, auditability, and extensibility.

## 8. Comparative Assessment

| Criterion | Open discovery | Central registry | Federated registries | Operation manifest | Bounded-closed federation |
| --- | --- | --- | --- | --- | --- |
| Can establish a closure root | No | Yes | No, not alone | No | Yes |
| Preserves local ownership | Strong | Weak | Strong | Neutral | Strong |
| Operation-specific scope | Variable | Moderate | Moderate | Strong | Strong |
| Temporal reproducibility | Weak | Moderate | Moderate | Strong | Strong |
| Cross-repository scalability | Weak | Moderate | Strong | Moderate | Strong |
| Restricted-source support | Weak | Moderate | Strong | Moderate | Strong |
| Distinguishes discovery from applicability | Weak | Moderate | Moderate | Strong | Strong |
| Supports governed extension | Informal | Centralized | Distributed | Per operation | Distributed and bounded |
| Primary failure mode | Silent omission | Central staleness | Missing registry | Self-asserted completeness | Invalid closure root or source edge |

## 9. Recommended Research Architecture

This report recommends **Candidate E — Governed Bounded-Closed Federation** as the architectural direction for further proposal and contract work.

This is a research recommendation only. It does not establish the architecture as CADP governance.

### 9.1 Architectural Principle

Closure is not a claim that every possible rule in the world is known. Closure is a proof that every source authorized to govern the declared operation under a fixed, authoritative source boundary has been accounted for.

The source boundary is closed for one exact:

- Governed Operation;
- subject and target;
- requested scope;
- purpose;
- evaluation time;
- CADP version;
- Product Binding version where applicable;
- source-of-sources revision;
- inheritance graph;
- external-incorporation set; and
- cross-repository composition.

### 9.2 Conceptual Layers

The researched architecture has four conceptual layers.

#### Layer A — Authority and Canonical Identity

Existing CADP governance determines whether a source declaration, binding, rule source, or external-incorporation relationship is authoritative, canonical, Approved, Effective, in scope, and temporally valid.

Discovery consumes these results. It does not create them.

#### Layer B — Authoritative Source-of-Sources

The source-of-sources identifies the governed roots from which discovery begins and the subordinate source declarations that may participate for each scope class.

It identifies source routes, not necessarily rule contents.

#### Layer C — Federated Rule-Source Declarations

Platform, product, repository, component, and external-obligation authorities maintain declarations within their bounded ownership. Each declaration exposes canonical identity, revision, scope, temporal status, and relationships necessary for traversal.

#### Layer D — Operation-Bound Closure Evidence

For one operation, the discovery activity records the fixed boundary, every traversed declaration, every source result, exclusions, unresolved conditions, and closure classification.

### 9.3 Root-of-Trust Property

The source-of-sources cannot authorize itself. Its authority, lifecycle, canonical identity, effective interval, and scope must be established by higher or independently governing CADP sources.

A discovered source cannot add itself to the active discovery boundary merely by containing a reference to itself or to another source. Every expansion edge requires authority from the already established boundary or another independently recognized incorporation relationship.

### 9.4 Bounded Extensibility

The architecture is closed during evaluation but open to governed evolution.

Adding a new repository, product overlay, legal source, or component source changes the source boundary prospectively. An open or completed decision does not silently acquire the new source. Applicable temporal rules determine whether the change requires reevaluation, affects only future operations, or applies to a declared historical interval.

## 10. Rule Discovery Boundary

The discovery boundary is derived from independently resolved inputs rather than chosen by the evaluator.

It includes:

1. the exact Governed Operation;
2. the requested-operation scope;
3. the canonical target identity and revision;
4. platform and product identities;
5. affected repositories and components;
6. CADP and Product Binding versions;
7. evaluation time and required effective intervals;
8. applicable source-of-sources identity and revision;
9. inheritance and overlay relationships;
10. external-obligation incorporation relationships;
11. confidentiality and source-authorization constraints;
12. legacy bindings; and
13. cross-repository composition relationships.

The boundary identifies where authoritative sources are permitted to exist for the operation. It does not identify which discovered rules apply; that remains a later evaluation.

### 10.1 Boundary Expansion

Boundary expansion may occur only through an explicit relationship already recognized by the fixed boundary, such as:

- a Product Binding;
- a platform-to-product inheritance edge;
- a repository or component source declaration;
- a recognized external-obligation incorporation;
- an explicit legacy binding; or
- a cross-repository operation relationship.

An unrecognized hyperlink, import, search result, conversational reference, or model suggestion may identify a possible governance gap. It cannot silently expand the authoritative universe.

### 10.2 Boundary Contraction

The evaluator cannot narrow the boundary because a source is inaccessible, inconvenient, expensive to review, confidential, temporarily unavailable, or likely irrelevant.

An authoritative source may be excluded from the Applicable Rule Universe only through a conclusive, attributable determination that it is outside scope, outside its effective interval, ineligible under governing source policy, or otherwise excluded by an applicable higher rule. Unresolved exclusion evidence prevents closure.

## 11. Rule Universe Closure Proof

### 11.1 Nature of the Proof

The researched closure proof is a governance evidence proof, not a mathematical proof that no unknown document exists.

It demonstrates that:

1. the authoritative source-of-sources was valid for the operation and evaluation time;
2. every source route declared by that boundary was traversed;
3. every required federated declaration returned a resolved source set, a valid negative declaration, or an explicit unresolved result;
4. every inheritance and incorporation edge was resolved;
5. every participating source was bound to an exact canonical revision and temporal state;
6. restricted sources were accounted for through an eligible evaluation path;
7. duplicate source identities were reconciled without losing lineage;
8. no unresolved discovery conflict could change source membership; and
9. the complete traversal was fixed in an operation-bound evidence record.

### 11.2 Closure Evidence

Closure evidence would conceptually identify:

- stable discovery activity identity;
- Governed Operation identity;
- source-of-sources identity and exact revision;
- CADP and Product Binding versions;
- requested and evaluated scopes;
- evaluation time and relevant effective intervals;
- every participating source declaration and revision;
- every rule source and revision;
- inheritance, overlay, external-incorporation, and legacy edges;
- negative source declarations;
- inaccessible, confidential, unavailable, stale, or unresolved sources;
- exclusions and their controlling authority;
- duplicate and alias reconciliation;
- source and rule discovery conflicts;
- evaluator identity and version;
- evidence-generation timestamp;
- integrity and provenance evidence; and
- reevaluation triggers.

The W3C PROV family is informative research evidence for the general separation of entities, activities, agents, derivation, attribution, and provenance bundles. It is not prescribed as a CADP representation. See the [W3C PROV Overview](https://www.w3.org/TR/prov-overview/).

### 11.3 Closure Classifications

The research supports two discovery-closure classifications:

- **Complete Rule Universe:** every authorized source route in the fixed boundary is accounted for, and no unresolved discovery condition could change source membership.
- **Incomplete Rule Universe:** at least one required source route, declaration, identity, revision, binding, temporal state, or discovery relationship remains unresolved.

These are discovery classifications only. They do not create lifecycle states or replace Policy Decision outcomes.

### 11.4 Prohibited Closure Inferences

Completeness cannot be inferred solely from:

- repository search success;
- absence of matching files;
- a central index result;
- semantic-search confidence;
- a model statement;
- the number of discovered rules;
- successful evaluation of discovered rules;
- no observed conflict;
- prior decision success;
- unchanged request text;
- tool or network success;
- repository ownership; or
- elapsed time.

## 12. Discovery, Applicability, Satisfaction, and Conflict

The architecture should preserve four independent questions:

| Question | Architectural concern | Non-success condition |
| --- | --- | --- |
| Discovery | Were all authorized source routes accounted for? | Incomplete Rule Universe |
| Applicability | Which discovered rules govern this exact operation? | Unresolved applicability |
| Satisfaction | Does valid evidence satisfy every applicable requirement? | Unsatisfied or unresolved control |
| Conflict | Can applicable rules be reconciled under authoritative precedence? | Unresolved rule conflict |

NIST SP 800-162 distinguishes policies, contextual information, policy decision, and supporting information. It also notes the role of metapolicy in identifying policy sets and deconfliction information. This supports separation of source administration, contextual inputs, and final decisions without prescribing a CADP implementation. See [NIST SP 800-162](https://csrc.nist.gov/pubs/sp/800/162/upd2/final).

## 13. Missing Rules and Conflicting Rules

Missing-source conditions and rule conflicts must not be collapsed.

| Condition | Discovery closure | Conflict status | Architectural consequence |
| --- | --- | --- | --- |
| Required source declaration unavailable | Incomplete | Not yet determinable | No successful applicability evaluation |
| Required source identity ambiguous | Incomplete | Possible discovery conflict | No successful applicability evaluation |
| Every source found; two applicable rules conflict | Complete may still be possible | Unresolved rule conflict | Policy Decision remains non-success, normally `Indeterminate` under existing CADP semantics |
| Source graph conflict changes which sources belong | Incomplete | Discovery conflict | Closure fails before rule conflict resolution |
| Rules differ but explicit precedence resolves them | Complete may be possible | Resolved | Preserve both rules and the controlling precedence evidence |
| No discovered rule applies after complete discovery | Complete | No unresolved conflict | Aggregate `Not Applicable` remains a Policy Decision question, not a closure result |

This distinction improves auditability:

- “Incomplete” explains that the evaluator cannot establish the full source set.
- “Conflict” explains that the source set is known but governing meaning remains unresolved.

Both can coexist, but one must not stand in for the other.

## 14. Temporal Rule Validity

Rule discovery is evaluated at a declared time against exact source revisions and effective intervals.

The evidence must distinguish:

- artifact creation time;
- approval decision time;
- effectiveness interval;
- adoption interval;
- supersession boundary;
- deprecation or withdrawal boundary;
- source-discovery time;
- operation evaluation time; and
- decision issuance time.

A later rule revision does not rewrite an earlier Rule Universe. A later discovery may reveal that historical evidence was incomplete, but the derived assessment remains separate from the historical decision record.

### 14.1 Rule Changes During an Open Evaluation

An open evaluation uses a fixed source-of-sources revision and fixed source snapshots. A rule or source-boundary change creates a new prospective evidence state. It may trigger reevaluation but cannot silently replace the evidence basis of the open evaluation.

### 14.2 Supersession and Transition

Superseded material may remain relevant where an explicit transition or legacy binding preserves effectiveness. Discovery must therefore evaluate supersession together with scope and time rather than automatically discarding every predecessor.

## 15. Cross-Repository Rule Composition

A cross-repository Governed Operation requires composition of independently governed source boundaries.

The researched architecture would bind:

- one common Governed Operation identity;
- every participating repository identity and immutable revision;
- the platform source boundary;
- each applicable Product Binding;
- repository and component source declarations;
- shared and repository-specific authority sources;
- external-obligation incorporation relationships;
- one declared evaluation time;
- every relevant effective interval;
- cross-scope inheritance and precedence;
- the combined source-of-sources traversal; and
- all discovery and rule conflicts.

### 15.1 Composition Rule

Each repository’s complete local universe is necessary but may not be sufficient. The combined universe also includes shared platform rules, cross-repository controls, coordinating authority rules, and external obligations incorporated at the combined scope.

The combined universe is Complete only when:

1. every participating local boundary is complete;
2. every shared boundary is complete;
3. every cross-scope relationship is resolved; and
4. no unresolved discovery gap could change the combined source membership.

One repository’s completeness cannot repair another repository’s missing source.

### 15.2 Snapshot Coherence

Snapshot coherence does not require one physical repository or storage system. It requires a reproducible evidence relationship among exact revisions and a common evaluation-time model.

If participating sources cannot establish compatible revisions or effective intervals, the combined universe remains Incomplete or temporally unresolved.

## 16. Auditability and Historical Reproducibility

Rule-discovery evidence serves two different audit questions:

1. **Contemporaneous question:** Was the Closure Claim justified by the authoritative boundary and evidence available at the decision time?
2. **Current question:** Would the same operation receive the same discovery result under current governance and current source revisions?

The answers may differ without rewriting history.

A reproducible historical record retains:

- the original source-of-sources revision;
- every traversed declaration and source revision;
- exact scope and time;
- eligibility and confidentiality handling;
- negative declarations;
- exclusions and rationale;
- unresolved conditions;
- discovery and conflict classifications;
- evaluator identity and version; and
- provenance and integrity evidence.

Indexes, caches, knowledge graphs, and generated bundles may assist retrieval. They remain derived representations unless CADP separately governs a source-of-truth transition.

## 17. Architectural Risks

| Risk | Architectural effect | Research response |
| --- | --- | --- |
| Source-of-sources is stale | Newly governed source is silently omitted | Version and govern the boundary; treat unresolved freshness as incomplete |
| Source-of-sources self-authorizes | Discovery mechanism creates authority | Require independent authority, lifecycle, and canonical validation |
| Federation cycle | Traversal becomes ambiguous or non-terminating | Require acyclic or explicitly bounded source relationships |
| False negative declaration | Local authority hides a valid source | Bind declaration to accountable authority, scope, time, and audit evidence |
| External obligation omitted | Applicable legal or contractual rule is absent | Govern incorporation responsibility and treat unresolved obligation claims as incomplete |
| External universe becomes unbounded | Evaluation can never close | Close over authoritative incorporation relationships, not the entire external world |
| Restricted source cannot be disclosed | Source is silently dropped | Count the source through an eligible evaluation path and preserve non-disclosing evidence |
| Rule conflict classified as missing | Audit cannot distinguish cause | Separate discovery closure from rule-conflict status |
| Dynamic source mutates open decision | Decision is not reproducible | Fix source snapshots and treat source changes prospectively |
| Registry mistaken for authority | Entry gains unintended normative effect | Registry and declarations reference authority; they do not create it |
| Cross-repository time mismatch | Combined result is historically incoherent | Require one time model and compatible effective intervals |
| Derived index becomes canonical | Search output silently replaces governed sources | Retain canonical-source and projection boundaries |
| Closure proof becomes implementation-specific | Governance depends on one vendor | Define evidence semantics independently of storage, query, or policy technology |

## 18. Migration Considerations

Migration to the researched architecture would be a future governance activity. This report authorizes none of it.

Architecturally, migration should preserve these boundaries:

1. inventory current candidate rule sources without declaring the inventory complete;
2. distinguish normative-capable sources from research, reviews, history, and generated evidence;
3. identify existing platform, product, repository, component, and external-incorporation relationships;
4. preserve exact current and historical revisions;
5. identify missing ownership, ambiguous scope, and unversioned inheritance;
6. establish a prospective source-boundary baseline only through separately authorized governance;
7. assess legacy decisions under their contemporaneous evidence;
8. avoid retroactively fabricating closure evidence; and
9. require independent review before relying on the new closure model.

Legacy records that lack a modern closure record remain historical evidence. A current assessment may classify their discovery basis as sufficient, insufficient, or Indeterminate under an authorized future model, but it does not rewrite the earlier record.

## 19. Future Normative Ownership Recommendations

The following ownership allocation is a research recommendation, not a current assignment.

| Governance source | Recommended future ownership |
| --- | --- |
| Foundation Architecture | Recognize the bounded-closure invariant, source authority separation, fail-closed boundary, and one shared discovery owner |
| Future Governance Applicability Contract or equivalent | Own common discovery-boundary semantics, source-of-sources composition, closure classifications, closure evidence requirements, and separation from applicability and conflict |
| Canonical Artifact Contract | Retain canonical identity, immutable revision, lineage, and integrity meanings |
| Metadata Registry Contract | Govern registered source classes and controlled metadata only after separately authorized values exist |
| Authority and Delegation Contract | Retain authority-source, delegation, revocation, scope, and eligibility semantics |
| Governance Lifecycle Contract | Retain approval, effectiveness, adoption, disposition, archival, retirement, and temporal applicability semantics |
| Product Binding governance | Own the explicit relationship connecting platform governance to product scope and versions |
| Domain contracts | Retain the meaning and evidence requirements of their rules and controls |
| Policy Decision Contract | Retain final provider-neutral outcomes and consume discovery, applicability, authority, lifecycle, conflict, and satisfaction results |
| Review artifacts | Evaluate evidence without creating authority or closure |

No rule-source registry should become an authority tier. No discovery owner should absorb approval, lifecycle, authority, domain-rule meaning, or final Policy Decision ownership.

## 20. Open Questions

1. What exact artifact class should govern the authoritative source-of-sources?
2. Which higher authority is eligible to establish and revise the global source boundary?
3. Is one global source root sufficient, or are independently governed roots required for confidentiality-separated domains?
4. What evidence makes a negative source declaration trustworthy?
5. Which source relationships must be acyclic, and which bounded reference cycles are harmless?
6. How is closure demonstrated when a restricted source can be evaluated but not disclosed to the requester?
7. Which external-obligation incorporation decisions require legal or specialist review?
8. How are jurisdiction, customer, contract, and tenant boundaries expressed without creating product-specific universal rules?
9. What temporal rule determines whether a newly discovered historical obligation triggers current reevaluation?
10. How are aliases, mirrors, translations, and derived rule representations reconciled to one canonical source?
11. What conflict evidence belongs to discovery and what belongs to applicability or final Policy Decision evaluation?
12. Which exact scope relationships are permitted among platform, product, repository, component, and cross-repository boundaries?
13. What minimum evidence is required for a source catalog to claim local completeness?
14. Can a source authority issue its own negative declaration, or is independent verification required for protected scopes?
15. How does emergency governance introduce a bounded source without mutating the active operation’s snapshot?
16. Which changes invalidate a cached Closure Claim?
17. How should a current assessment describe a legacy decision for which no contemporaneous source boundary can be reconstructed?
18. Which human decisions are fundamental and non-delegable when establishing or changing discovery boundaries?

## 21. Research Question Coverage

| Research question | Principal sections |
| --- | --- |
| Closed World vs Open World assumptions | 5, 9 |
| Authoritative Rule Registry | 4.5, 7.2, 7.3 |
| Authoritative Source-of-Sources | 4.6, 9 |
| Rule Discovery Boundary | 4.7, 10 |
| Rule Universe Closure Proof | 11 |
| Repository-local rules | 6.3 |
| Platform rules | 6.1 |
| Product Binding rules | 6.2 |
| External obligations | 6.6 |
| Inherited governance | 6.5 |
| Dynamic rule incorporation | 6.7, 9.4 |
| Temporal rule validity | 14 |
| Cross-repository rule composition | 15 |
| Conflict between discovered rules | 12, 13 |
| Conflict between missing and conflicting rules | 13 |
| Discovery evidence | 11.2 |
| Closure evidence | 11 |
| Auditability | 16 |
| Historical reproducibility | 14, 16, 18 |
| Future normative ownership | 19 |

## 22. External Research References

The following sources informed the comparison of architectural concepts. They are research references only and do not govern CADP:

1. [W3C OWL 2 Web Ontology Language Primer](https://www.w3.org/TR/owl2-primer/) — open-world and closed-world distinction.
2. [W3C Shapes Constraint Language](https://www.w3.org/TR/shacl/) — explicit bounded closure through declared shapes.
3. [W3C PROV Overview](https://www.w3.org/TR/prov-overview/) — provenance concepts for entities, activities, agents, derivation, attribution, and reproducibility.
4. [NIST SP 800-162, Guide to Attribute Based Access Control](https://csrc.nist.gov/pubs/sp/800/162/upd2/final) — separation of policies, contextual information, metapolicy, decision, and enforcement concerns.
5. [Open Policy Agent Discovery documentation](https://www.openpolicyagent.org/docs/management-discovery) — comparative example of a bootstrapped source that discovers subordinate policy configuration. CADP does not adopt OPA or its implementation model through this reference.

The sources demonstrate recurring architectural patterns: an explicit root for discovery, separation of policy administration from decisions, immutable or attributable evidence, and the need to distinguish absence from a bounded closed-world conclusion.

## 23. Research Recommendation

Further CADP architecture work should use the Governed Bounded-Closed Federation as the primary candidate for resolving Applicable Rule Universe completeness.

The candidate is preferred because it:

- provides an authoritative closure root;
- supports platform, product, repository, component, external, and cross-repository composition;
- preserves existing semantic ownership;
- distinguishes missing sources from conflicting discovered rules;
- binds evaluation to exact revisions, scope, and time;
- permits governed extension without mutating completed decisions;
- supports confidentiality-separated sources;
- preserves audit and historical reconstruction; and
- remains independent of policy engines, databases, repositories, model providers, and workflow products.

This recommendation is not an architecture decision. Separate proposal, independent review, human decision, lifecycle, and effectiveness steps would be required before any part of this research could become normative CADP architecture.
