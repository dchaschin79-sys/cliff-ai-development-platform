# Rule Source Catalog Contract Proposal

## 1. Document Control

| Field | Value |
| --- | --- |
| Contract identity | `CADP-CONTRACT-RULE-SOURCE-CATALOG` |
| Title | Rule Source Catalog Contract |
| Document type | Contract Proposal |
| Version | 0.2.1 |
| Previous version | 0.2.0 |
| Revision classification | Pre-acceptance Patch Maintenance Revision |
| Revision basis | Canonical Contract System Consistency Verification — bounded dependency-graph reconciliation |
| Status | Draft Contract Proposal |
| Review state | Graph reconciled — Pending bounded Independent Verification |
| Date | 2026-07-24 |
| Architecture domain | Governance Rule Discovery |
| Contract domain | Rule Source Catalog |
| Primary responsibility | Canonical source identity, description, catalog participation, and catalog relationship semantics |
| Proposed canonical semantic owner | This contract |
| Repository | `dchaschin79-sys/cliff-ai-development-platform` |
| Source baseline | `caf90dde13189cbd27278ae5ac3bd895677a714c` |
| Acceptance | Not created |
| Effectiveness | Not created |
| Normative effect | None |
| Implementation authority | None |
| Supersedes | None — initial proposal |

This document is the first Draft Contract Proposal under the CADP Contract Governance Framework.

It is not accepted, not Effective, not implementation-authorizing, and not a Design Freeze. Its existence, authorship, review, Git history, or publication does not create contract acceptance or normative authority.

## 2. Authoritative Source Bindings

| Authoritative input | Bound revision | Use |
| --- | --- | --- |
| [Foundation Architecture](../FOUNDATION_ARCHITECTURE.md) | Version 0.2.0; Git object `005f1e0a9fca7d4c75b69a013f0d24710348a866` | Canonical ownership, authority, lifecycle, confidentiality, product independence, provider neutrality, and fail-closed boundaries |
| [Governance Rule Discovery Architecture Decision Proposal](../architecture/GOVERNANCE_RULE_DISCOVERY_ARCHITECTURE_DECISION_PROPOSAL.md) | Version 0.1.1; Git object `5fc17613f5ef78fb5f546f17bdeded75465da9c0` | Accepted source-catalog architecture and separation of concerns |
| [Governance Rule Discovery Architecture Acceptance Record](../architecture/GOVERNANCE_RULE_DISCOVERY_ARCHITECTURE_ACCEPTANCE_RECORD.md) | Record `CADP-AAR-GRD-0001`, Version 1.0.0; Git object `19995bca6768b1de01c3db2055bc618404dbc9ec` | Authorization for architecture-based contract design and contract review |
| [CADP Contract Governance Framework](../governance/CONTRACT_GOVERNANCE_FRAMEWORK.md) | Version 0.1.0 Draft; Git object `ff975ac805b03d7e86aa47d4870b47497a31b7a2` | Contract ownership, lifecycle, review, versioning, change, and traceability methodology |
| [Governance Rule Discovery Contract Decomposition Plan](GOVERNANCE_RULE_DISCOVERY_CONTRACT_DECOMPOSITION_PLAN.md) | Version 0.2.0; Git object `c4c1fb6c459d72227b0f3342d6af388ba954a5cd`; commit `f26e52f63a9118991f8620cbe733bb6b80722664` | Rule Source Catalog responsibility, seven-contract decomposition, direct dependency graph, exclusions, review order, and Category B impact |

No other source is used to define this proposal. If a later authoritative revision conflicts with this Draft, the conflict must be resolved through contract governance rather than inferred or silently merged.

## 3. Purpose

The Rule Source Catalog Contract establishes the canonical semantics by which governed rule sources are identified, described, classified, categorized, related to a catalog scope, associated with independently owned eligibility and lifecycle references, and kept attributable to their canonical metadata owners.

The contract exists so downstream Governance Rule Discovery contracts can refer to sources consistently without:

- transferring source ownership to a catalog;
- making registration authoritative;
- treating repository location as participation;
- duplicating canonical source identity;
- redefining upstream eligibility or lifecycle meanings; or
- allowing downstream mechanisms to invent source semantics.

This contract owns source-catalog semantics only.

## 4. Canonical Responsibility and Scope

### 4.1 Owned Semantic Concepts

This proposal defines the canonical meaning of:

1. Rule Source Catalog;
2. Catalog Identity;
3. Catalog Revision;
4. Catalog Scope;
5. Rule Source;
6. Source Identity;
7. Exact Source Revision Binding;
8. Source Classification;
9. Source Descriptor;
10. Descriptor Identity;
11. Descriptor Revision;
12. Source Category;
13. Source Reference;
14. Source Declaration;
15. Source Participation;
16. Source Eligibility References;
17. Source Metadata Ownership;
18. Canonical Logical Source Identity; and
19. Source Lifecycle References.

### 4.2 Explicit Ownership Boundary

This contract owns the meaning of a governed source declaration and its catalog relationships.

It does not own:

- the content semantics of the referenced source;
- source or actor authority;
- source authorization or confidentiality policy;
- eligibility decisions;
- lifecycle decisions;
- Federation Root or root-set semantics;
- discovery-boundary membership;
- traversal;
- source resolution activity;
- discovery manifests;
- closure relevance or closure evidence;
- provenance records;
- Complete Rule Universe Snapshots;
- Incomplete Discovery Results;
- validation;
- rule applicability;
- Policy Decision outcomes; or
- implementation.

### 4.3 Catalog Meaning

A **Rule Source Catalog** is the canonical semantic boundary within which governed Rule Source declarations and their catalog participation relationships are expressed.

A catalog:

- references sources without acquiring their canonical ownership;
- preserves the identity and ownership of each source;
- makes source declarations addressable to downstream governed consumers;
- does not establish a Federation Root;
- does not determine which sources participate in a specific discovery context;
- does not prove completeness;
- does not grant authority, approval, effectiveness, adoption, or applicability; and
- does not prescribe a physical registry, repository layout, service, database, file, or implementation.

This proposal defines catalog meaning, not catalog representation.

Catalog ownership, Catalog Identity, Catalog Revision, and Catalog Scope are separate semantic dimensions:

- **catalog ownership** is the externally governed canonical responsibility for the catalog and its accepted revisions;
- **Catalog Identity** distinguishes the same logical catalog across revisions;
- **Catalog Revision** identifies one exact semantic state of that catalog; and
- **Catalog Scope** bounds the meaning of catalog-owned assertions at that revision.

Technical custody, authorship, repository ownership, file location, or implementation control MUST NOT create catalog ownership or collapse these dimensions.

### 4.4 Catalog Identity

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish one logical Rule Source Catalog from every other catalog across revisions and representations. |
| Canonical definition | Catalog Identity is the stable logical identity of a Rule Source Catalog. It identifies the same catalog across its Catalog Revisions without identifying any one revision. |
| Semantically required invariants | One logical catalog MUST have one Catalog Identity within its governed identity boundary. A change of location, representation, custodian, or Catalog Revision MUST NOT create a new Catalog Identity. Two catalogs MUST NOT be treated as identical because they contain equivalent Source References or refer to the same Rule Source. |
| Relationships | Catalog Identity is the subject of Catalog Revision and Catalog Scope. Source Participation is always interpreted relative to one identified Catalog Identity through an exact Catalog Revision and Catalog Scope. |
| Ownership boundary | This contract owns Catalog Identity semantics. Independently governed authority determines the eligible canonical owner of a particular Catalog Identity. |
| Explicit non-goals | This concept does not define identifier syntax, namespaces, registry keys, repository locations, catalog topology, or identity-resolution algorithms. |

### 4.5 Catalog Revision

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish one exact semantic state of a Rule Source Catalog from its earlier and later states. |
| Canonical definition | Catalog Revision is the immutable semantic state of one Catalog Identity at an exact revision boundary. It does not replace or change the logical Catalog Identity. |
| Semantically required invariants | A Catalog Revision MUST belong to exactly one Catalog Identity. A later Catalog Revision MUST NOT mutate the meaning or assertions of an earlier revision. Equivalent catalog contents MUST NOT be assumed to be the same Catalog Revision without canonical revision evidence. |
| Relationships | Catalog Revision binds Catalog Scope and every catalog-owned Source Declaration and Source Participation assertion evaluated at that revision. |
| Ownership boundary | This contract owns the distinction between logical catalog identity and exact catalog revision. Canonical artifact governance owns revision identity, integrity, and source-of-truth evidence. |
| Explicit non-goals | This concept does not define version numbering, hashes, revision formats, publication mechanisms, storage, synchronization, or change procedures. |

### 4.6 Catalog Scope

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Establish the semantic boundary within which catalog-owned assertions are interpreted. |
| Canonical definition | Catalog Scope is the governed semantic boundary that qualifies the meaning of Source Declarations and Source Participation within one Catalog Identity and Catalog Revision. |
| Semantically required invariants | Catalog Scope MUST be attributable, explicit, and revision-bound. Two assertions about the same Rule Source MUST NOT be assumed to concern the same Catalog Scope. Catalog Scope MUST NOT be inferred from repository location, organization name, product name, technical tenancy, or physical catalog placement. |
| Relationships | Catalog Scope is bound to Catalog Identity and Catalog Revision and qualifies Source Declaration, Source Participation, Source Category, and catalog-owned Source Metadata Ownership assertions. |
| Ownership boundary | This contract owns the abstract meaning and qualifying role of Catalog Scope. Exact scope values and cross-layer scope relationships remain unresolved under GRD-08 and GRD-12. Federation Boundary owns federation composition and discovery-context scope. |
| Explicit non-goals | This concept does not define scope values, scope taxonomies, product-specific scope, tenant-specific scope, repository topology, federation topology, access boundaries, or admission workflows. |

## 5. Rule Source

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Provide the stable, bounded source concept that a Rule Source Catalog may declare and reference. |
| Canonical definition | A Rule Source is a semantically identifiable governed source of rule-bearing material, or a source of an artifact class later authorized under GRD-01 to carry rule-bearing source relationships. |
| Semantically required invariants | A Rule Source MUST be distinguishable from its location, representation, catalog declaration, owner, revision, authority, eligibility, and downstream use. Its identity and exact revision MUST NOT be inferred from proximity, naming, search ranking, model memory, or implementation behavior. A catalog, root, resolver, registry mechanism, source-of-sources relationship, access path, traversal result, provenance record, or closure evidence MUST NOT become a Rule Source merely because it points to, aggregates, accesses, registers, or processes Rule Sources. |
| Relationships | A Rule Source has a Source Identity, may be bound to an Exact Source Revision, may be represented by a Source Descriptor, may carry Source Classification and Source Category relationships, may have Source Participation in a Catalog Scope, and may reference upstream eligibility and lifecycle evidence. |
| Ownership boundary | This contract owns the source concept as used by a Rule Source Catalog. The source’s content, canonical artifact meaning, authority, eligibility, lifecycle, and applicability remain owned by their respective upstream or downstream governance domains. |
| Explicit non-goals | This concept does not determine the artifact class deferred by GRD-01; whether a source must be discovered, is closure-relevant, can be resolved, contains an applicable rule, or is sufficient for a Policy Decision; or whether any catalog, federation, registry, access, traversal, provenance, or closure mechanism is itself a Rule Source. |

A pointing relationship, access path, aggregation mechanism, infrastructure component, registration-governance mechanism, or federation boundary does not acquire Rule Source meaning from its proximity to rule-bearing material.

A Rule Source may be repository-local, platform-related, product-bound, tenant-bound where separately governed, externally referenced, inherited, legacy-related, or shared. This statement recognizes architecture-supported source domains; it does not define Source Category values, decide their scope rules, or resolve GRD-01.

## 6. Source Identity

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish one Rule Source logically from every other Rule Source across representations and revisions. |
| Canonical definition | Source Identity is the stable logical identity by which a Rule Source is addressed within governed catalog relationships, independent of storage location, file path, alias, mirror, copy, translation, derived representation, or current revision. |
| Semantically required invariants | One logical Rule Source cannot have two conflicting Source Identities for the same governed identity boundary. Reuse of a label or location does not establish identity equivalence. A new revision does not by itself create a new Source Identity; a different semantic source cannot inherit an existing identity merely through similarity. |
| Relationships | Source Identity identifies the subject described by a Source Descriptor and linked to a Canonical Logical Source Identity. Exact Source Revision Binding identifies one immutable revision without changing that logical identity. Source Identity is used by Source Declaration, Source Participation, and Source Metadata Ownership relationships. |
| Ownership boundary | This contract owns the source-catalog meaning of Source Identity. Canonical artifact identity, external authority over identity, and identity-provider mechanisms remain outside this contract. |
| Explicit non-goals | This concept does not define an identifier syntax, namespace format, registry key, URI, file name, database key, or identity-resolution algorithm. |

When identity evidence conflicts or cannot distinguish sources deterministically, the catalog relationship must preserve the unresolved condition. It must not select an identity by convenience or model inference.

### 6.1 Exact Source Revision Binding

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Bind a source-catalog assertion to one exact immutable revision of its Canonical Logical Source Identity. |
| Canonical definition | Exact Source Revision Binding is the attributable relationship that identifies the precise revision of a logical Rule Source to which a Source Declaration, Source Descriptor, or Source Participation assertion applies. It is not a second logical source identity. |
| Semantically required invariants | An exact binding MUST resolve to one immutable source revision under its canonical revision evidence. It MUST NOT float to a later revision, be inferred from the current repository state, or be treated as the Canonical Logical Source Identity itself. Source Identity and Canonical Logical Source Identity MUST NOT be treated as exact revision bindings. |
| Relationships | Exact Source Revision Binding qualifies Source Descriptor, Source Declaration, Source Participation, Source Classification, Source Category, Source Eligibility References, and Source Lifecycle References where those assertions concern a particular source revision. |
| Ownership boundary | This contract owns the source-catalog distinction between logical source identity and exact source revision binding. Canonical artifact governance or independently governed external-source governance owns the revision identity, integrity, and evidence. |
| Explicit non-goals | This concept does not define revision syntax, version numbering, hashes, mutable aliases, lookup behavior, retrieval, storage, integrity mechanisms, or binding algorithms. |

## 7. Source Classification

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Associate a Rule Source with independently governed classification meanings needed to interpret the source declaration correctly. |
| Canonical definition | Source Classification is the governed relationship between a Rule Source and one or more externally owned classification meanings applicable to that source. |
| Semantically required invariants | A classification MUST retain its originating semantic owner, exact governing revision, and applicable scope. Classification does not create authority, eligibility, lifecycle state, participation, category, or applicability. Independent classification dimensions MUST NOT be collapsed into one ranking. No equivalence between Source Classification and Source Category may be inferred from similar labels or values. |
| Relationships | Source Classification may reference artifact type, confidentiality, authority class, memory class, or another independently governed classification where applicable. It may coexist with Source Category but does not define, substitute for, override, or determine Source Category or Source Participation. |
| Ownership boundary | This contract owns only the meaning of associating a Rule Source with an upstream classification. The classification vocabulary and its values remain owned by their originating governance domains. |
| Explicit non-goals | This concept does not define classification values, Source Category values, a registry, hierarchy, precedence order, cross-dimension equivalence, inference rule, or validation algorithm. |

A missing or conflicting required classification cannot be silently replaced by a catalog-local label.

## 8. Source Descriptor

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Provide the coherent semantic description through which a Rule Source is represented to governed catalog consumers. |
| Canonical definition | A Source Descriptor is the catalog-governed semantic representation that coherently brings together references to a Rule Source and its governed source-catalog assertions without becoming the source, owning its content, or becoming a second canonical owner of any referenced meaning. |
| Semantically required invariants | A Source Descriptor MUST have one canonical Descriptor Identity owner and one canonical Descriptor Revision owner. One Descriptor Identity and Descriptor Revision MUST NOT have competing canonical descriptors. A descriptor refers to exactly one Source Identity within its declared Catalog Scope and Exact Source Revision Binding where required. Every contained assertion MUST remain attributable to its own canonical semantic owner. A descriptor MUST NOT contradict Canonical Logical Source Identity, transfer source-content ownership, create eligibility, or make an assertion authoritative by containment. Changing any descriptor-owned semantic assertion requires a new immutable Descriptor Revision; externally owned assertions remain bound to their external revisions and are not mutated by a descriptor revision. |
| Relationships | A Source Descriptor relates Descriptor Identity and Descriptor Revision to Source Identity, Exact Source Revision Binding, Canonical Logical Source Identity, Source Classification, Source Category, Source Declaration, Source Participation, Source Eligibility References, Source Metadata Ownership, and Source Lifecycle References. |
| Ownership boundary | This contract owns Source Descriptor, Descriptor Identity, and Descriptor Revision semantics within the Rule Source Catalog domain. The eligible catalog semantic owner owns canonical Descriptor Identity and Descriptor Revision assertions. The Rule Source content owner retains source-content semantics. Each classification, eligibility result, lifecycle state, authority fact, canonical logical identity, and exact source revision retains its external owner. |
| Explicit non-goals | This concept does not define descriptor fields, required keys, optional properties, document shape, serialization, storage, schema, API, or rendering. |

A Source Descriptor may be represented in more than one derived form. Equivalent representations MUST preserve the same governed meaning, Descriptor Identity, and Descriptor Revision. Descriptor custody, representation, or publication does not grant ownership of its referenced assertions.

## 9. Source Category

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Distinguish governed source roles or origin domains within Rule Source Catalog semantics without conflating them with authority or lifecycle. |
| Canonical definition | Source Category is an independent, catalog-owned semantic dimension that groups sources by a governed source-role or origin-domain distinction relevant to catalog interpretation. It is not Source Classification. |
| Semantically required invariants | A Source Category assertion MUST be explicit, attributable to the catalog semantic owner, revision-bound, Catalog Scope-bound, and independent from Source Classification, authority, eligibility, lifecycle, confidentiality, applicability, and catalog topology. A category name cannot create participation or make a source universal. Category and classification assertions that appear similar MUST NOT be merged, substituted, overridden, or treated as equivalent without separately governed equivalence evidence. |
| Relationships | Source Category characterizes a Rule Source or Source Descriptor within an identified Catalog Identity, Catalog Revision, and Catalog Scope. It may coexist with multiple independently owned Source Classifications; neither dimension determines the other. |
| Ownership boundary | This contract owns the meaning and constraints of Source Category as a catalog concept. Actual category values and their future governance are deferred to separately governed work. |
| Explicit non-goals | This concept does not define category values, classification values, product-specific categories, tenant-specific values, taxonomy depth, precedence, cross-dimension equivalence, topology, or registry representation. |

Source Category does not determine whether a source belongs to a Federation Root, is closure-relevant, or applies to a Governed Operation.

## 10. Source Reference

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Permit a governed catalog assertion to identify a Rule Source without asserting that the source participates in a Catalog Scope. |
| Canonical definition | Source Reference is an attributable reference to a Source Identity and, where the assertion concerns a precise state, an Exact Source Revision Binding. A Source Reference identifies its subject but does not by itself declare any catalog property or participation. |
| Semantically required invariants | A Source Reference MUST preserve Canonical Logical Source Identity and exact revision evidence where required. Reference existence, repetition, accessibility, catalog location, or inclusion in a Source Descriptor MUST NOT imply Source Declaration, Source Participation, authority, eligibility, lifecycle status, discovery membership, or applicability. |
| Relationships | Source Reference is used by Source Declaration, Source Descriptor, Source Participation, Source Classification, Source Category, Source Eligibility References, and Source Lifecycle References to identify their subject without inheriting their meaning. |
| Ownership boundary | This contract owns Source Reference meaning within source-catalog semantics. Canonical artifact governance or independently governed external-source governance owns the referenced logical identity and exact revision. |
| Explicit non-goals | This concept does not define reference syntax, resolution, retrieval, access paths, links, aliases, locator formats, registration, discovery, or validation. |

## 11. Source Declaration

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Express one attributable semantic assertion about a Rule Source within an identified catalog boundary. |
| Canonical definition | Source Declaration is an assertion made by the authorized canonical semantic owner of that assertion about a Rule Source or its source-catalog relationship, qualified by Catalog Identity, Catalog Revision, Catalog Scope, Source Identity, and Exact Source Revision Binding where required. |
| Semantically required invariants | Every Source Declaration MUST identify one assertion meaning and one canonical semantic owner. Authorship, technical custody, repository ownership, or catalog maintenance MUST NOT establish authority to make the declaration. A declaration about source content, descriptor identity, descriptor revision, classification, category, participation, eligibility reference, or lifecycle reference MUST retain the distinct owner of that assertion. Declaration existence MUST NOT imply Source Participation unless the declaration is explicitly the catalog-owned Source Participation assertion. |
| Relationships | Source Declaration uses Source Reference to identify its subject. Source Descriptor may coherently represent multiple Source Declarations while preserving their separate owners. Source Participation and Source Category are catalog-owned kinds of Source Declaration; externally owned classifications, eligibility references, lifecycle references, canonical identity, exact revision, and source-content assertions retain their external ownership. |
| Ownership boundary | This contract owns the meaning and attribution requirements of Source Declaration. It does not assign a particular person or organization as owner, determine authority eligibility, or transfer the externally governed ownership of the asserted meaning. |
| Explicit non-goals | This concept does not define declaration fields, workflows, commands, submission, admission, acceptance, publication, validation, evidence formats, or implementation. |

## 12. Source Participation

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Express that a Rule Source explicitly participates within one governed Catalog Scope at one Catalog Revision and is available for evaluation by authorized downstream contract domains. |
| Canonical definition | Source Participation is the catalog-owned Source Declaration that a Rule Source participates in one identified Catalog Identity, Catalog Revision, and Catalog Scope under an Exact Source Revision Binding where required. |
| Semantically required invariants | Participation MUST be explicit, attributable to the catalog semantic owner, Catalog Scope-bound, and Catalog Revision-bound. It cannot be inferred from Source Reference, another Source Declaration, repository location, file proximity, code import, hyperlink, search result, naming, conversational mention, prior discovery, or model memory. Participation MUST preserve the Rule Source content owner, Canonical Logical Source Identity, and Exact Source Revision Binding. It does not approve the source, make it Effective, create authority, establish eligibility, establish federation or discovery membership, or establish rule applicability. Participation in one Catalog Scope MUST NOT imply participation in another. |
| Relationships | Source Participation uses Source Reference and relates a Rule Source to an identified Catalog Identity, Catalog Revision, and Catalog Scope. It may reference Source Eligibility and Source Lifecycle evidence needed by downstream governance. Federation Boundary consumers may evaluate Source Participation under their own accepted semantics without converting it into federation membership. |
| Ownership boundary | This contract owns Source Participation meaning, and the eligible catalog semantic owner owns each Source Participation assertion. Rule Source content ownership, Federation Root membership, discovery-boundary membership, closure relevance, resolution, and downstream inclusion remain outside this contract. |
| Explicit non-goals | This concept does not define registration workflows, admission algorithms, discovery behavior, traversal, ordering, priority, retrieval, or removal procedures. |

### 12.1 Terminology Reconciliation

- **Source Registration** is a non-canonical process term outside this contract. It MUST NOT be used as a substitute for Source Declaration or Source Participation and does not create either semantic assertion.
- **Catalog Entry** is a non-canonical representation term. Its existence or representation MUST NOT create Source Reference, Source Declaration, or Source Participation.
- **Catalog Membership** is not a separate semantic concept. Where legacy material uses that phrase as shorthand, it means exactly Source Participation within one identified Catalog Identity, Catalog Revision, and Catalog Scope; it MUST NOT mean Federation Root membership, discovery-boundary membership, or cross-catalog composition.

A derived catalog view does not create new Source Participation.

## 13. Source Eligibility References

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Preserve explicit relationships to independently governed eligibility evidence that may be required before a source or source declaration can be used. |
| Canonical definition | Source Eligibility References are attributable relationships from a Rule Source or Source Participation declaration to eligibility determinations owned outside the Rule Source Catalog domain. |
| Semantically required invariants | A reference does not create, expand, repair, or replace eligibility. It preserves the identity, revision, scope, purpose, provider boundary where applicable, and temporal boundary of the independently governed eligibility evidence it cites. Missing, stale, conflicting, or unverifiable required eligibility evidence cannot default to eligible. |
| Relationships | References may relate to source authorization, confidentiality eligibility, purpose eligibility, provider eligibility where applicable, and other independently governed information-use eligibility required by the accepted architecture. |
| Ownership boundary | This contract owns only the source-catalog relationship to eligibility evidence. Universal Eligibility and every underlying eligibility policy, decision, and result remain externally owned. |
| Explicit non-goals | This concept does not define eligibility criteria, evaluate eligibility, authorize retrieval, disclose protected information, grant authority, or determine a downstream failure result. |

The catalog may preserve that an eligibility reference is absent or unresolved. It does not decide how a downstream discovery attempt processes that condition.

## 14. Source Metadata Ownership

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Keep every source-catalog assertion attributable to one canonical semantic owner and prevent catalog custody from transferring source ownership. |
| Canonical definition | Source Metadata Ownership is the governed assignment of canonical responsibility for each semantic assertion associated with a Rule Source declaration. |
| Semantically required invariants | Each semantic assertion MUST have exactly one canonical semantic owner at an exact governing revision and scope. Rule Source content ownership, Descriptor Identity ownership, Descriptor Revision ownership, and ownership of each represented assertion MUST remain distinguishable. Catalog maintenance, technical custody, authorship, copying, indexing, rendering, synchronization, or repeated use does not transfer ownership. The Rule Source content owner does not automatically own Descriptor Identity, Descriptor Revision, Source Category, or Source Participation. The catalog semantic owner does not own source content or externally governed identity, classification, eligibility, lifecycle, authority, or revision meanings. Conflicting or missing ownership claims MUST remain explicit and MUST NOT be resolved through proximity, custody, or inference. |
| Relationships | Source Metadata Ownership relates the Rule Source content owner; the catalog semantic owner; the Descriptor Identity owner; the Descriptor Revision owner; the owner of each Source Declaration; and the external owners of Canonical Logical Source Identity, Exact Source Revision Binding, Source Classification, Source Eligibility References, Source Lifecycle References, authority meanings, and source-content meanings. The eligible catalog semantic owner owns catalog-specific Source Category and Source Participation assertions. |
| Ownership boundary | This contract owns the attribution model for source-catalog assertions. It does not assign human authority, approve an owner, redefine canonical artifact ownership, or govern implementation custody. |
| Explicit non-goals | This concept does not define access control, repository permissions, maintainer roles, database ownership, file ownership, organizational reporting, or delegation. |

No Source Descriptor may imply that one actor owns every represented semantic dimension merely because the actor owns or maintains the descriptor. Descriptor Identity and Descriptor Revision each have one canonical owner; no competing canonical descriptor may claim the same identity and revision. A new Descriptor Revision may change only descriptor-owned assertions and references. It MUST NOT mutate the historical meaning or ownership of an externally governed assertion.

## 15. Canonical Logical Source Identity

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Bind the catalog’s Source Identity to the independently governed stable logical source without allowing the catalog to manufacture canonical status or conflate identity with revision. |
| Canonical definition | Canonical Logical Source Identity is the externally governed stable identity that establishes which logical source artifact or independently eligible external source is canonical across revisions. It does not identify any one exact source revision. |
| Semantically required invariants | A catalog MUST NOT make a source canonical through Source Registration, Source Declaration, Source Participation, naming, popularity, technical accessibility, or repeated use. One Source Identity MUST NOT resolve to conflicting Canonical Logical Source Identities within the same governed identity boundary. Aliases, mirrors, copies, translations, and derived representations remain distinguishable from the canonical logical source unless governed equivalence and lineage are established externally. Canonical Logical Source Identity MUST remain distinct from Exact Source Revision Binding. |
| Relationships | Canonical Logical Source Identity is referenced by Source Identity and Source Descriptor and preserved through Source Declaration and Source Participation. Exact Source Revision Binding selects one immutable revision of that logical identity when an assertion requires revision precision. Both relationships remain attributable through Source Metadata Ownership. |
| Ownership boundary | This contract owns the requirement that a catalog assertion preserve the distinction between canonical logical source identity and exact source revision binding. Canonical artifact governance and independently eligible external-source governance own the canonical logical identity and revision evidence themselves. |
| Explicit non-goals | This concept does not define canonicalization algorithms, alias reconciliation, translation equivalence, source-of-truth migration, integrity mechanisms, or conflict resolution. |

Unresolved Canonical Logical Source Identity or Exact Source Revision Binding cannot be repaired by Source Category, Source Classification, Source Participation, or a downstream consumer.

## 16. Source Lifecycle References

| Semantic aspect | Definition |
| --- | --- |
| Purpose | Preserve relationships to independently governed lifecycle evidence relevant to a Rule Source declaration. |
| Canonical definition | Source Lifecycle References are attributable relationships from a Rule Source or Source Participation declaration to externally owned lifecycle evidence for the exact source revision and applicable scope. |
| Semantically required invariants | A reference preserves the lifecycle source, exact revision, scope, temporal boundary, and historical lineage it cites. A catalog cannot create, modify, infer, or collapse lifecycle states. A later lifecycle change does not silently mutate the lifecycle evidence associated with an earlier catalog or discovery revision. |
| Relationships | Source Lifecycle References may be consumed with Source Eligibility References, Canonical Logical Source Identity, Exact Source Revision Binding, and Source Participation by authorized downstream contracts. |
| Ownership boundary | This contract owns only the source-catalog relationship to lifecycle evidence. Approval, acceptance, effectiveness, adoption, deprecation, withdrawal, supersession, archival, retirement, and Design Freeze meanings remain externally owned. |
| Explicit non-goals | This concept does not define lifecycle states, transitions, effective intervals, adoption, approval, Design Freeze, reevaluation rules, or transition workflows. |

A lifecycle reference does not make a source Effective or Adopted and does not establish participation in a particular discovery context.

## 17. Cross-Concept Relationships

The semantic relationship among the owned concepts is:

```text
Rule Source Catalog
    ├── distinguished across revisions by Catalog Identity
    ├── fixed to one semantic state by Catalog Revision
    └── qualifies catalog-owned assertions through Catalog Scope
            └── Source Participation asserts participation of a Rule Source

Rule Source
    ├── identified logically by Source Identity
    ├── related to Canonical Logical Source Identity
    ├── fixed when required by Exact Source Revision Binding
    ├── identified without participation by Source Reference
    ├── represented semantically by Source Descriptor
    │       ├── distinguished by Descriptor Identity
    │       └── fixed by Descriptor Revision
    ├── described through attributable Source Declarations
    ├── associated independently with Source Classification
    ├── associated independently with Source Category
    ├── linked to Source Eligibility References
    ├── linked to Source Lifecycle References
    └── kept attributable through Source Metadata Ownership
```

This is a semantic relationship map. It is not a data model, schema, object model, storage design, API, or serialization format.

The relationships do not form an authority hierarchy. None can repair a missing or conflicting canonical owner in another semantic domain.

## 18. Contract Invariants

If later Accepted and made Effective, the Rule Source Catalog Contract would require these semantic invariants:

1. **Catalog identity stability:** one Catalog Identity distinguishes one logical Rule Source Catalog across Catalog Revisions and representations.
2. **Catalog revision immutability:** one Catalog Revision identifies one immutable semantic state and does not mutate earlier or later revisions.
3. **Catalog scope qualification:** every catalog-owned assertion is explicitly qualified by Catalog Identity, Catalog Revision, and Catalog Scope.
4. **Source identity uniqueness:** one governed Source Identity distinguishes one logical Rule Source within its applicable identity boundary.
5. **Logical identity preservation:** every catalog assertion preserves its relationship to an independently governed Canonical Logical Source Identity.
6. **Exact revision separation:** Exact Source Revision Binding identifies one immutable revision without becoming or changing Canonical Logical Source Identity.
7. **Reference separation:** Source Reference identifies a Rule Source but does not establish Source Declaration or Source Participation.
8. **Declaration attribution:** every Source Declaration identifies one assertion meaning and one canonical semantic owner.
9. **Terminology determinism:** Source Registration and Catalog Entry create no catalog semantics; Catalog Membership, when encountered as legacy shorthand, means only Source Participation within one identified Catalog Scope.
10. **Ownership consistency:** every catalog assertion remains attributable to exactly one canonical semantic owner.
11. **No ownership transfer:** Source Declaration, Source Participation, descriptor maintenance, and catalog custody do not transfer Rule Source content ownership or externally owned semantics.
12. **Descriptor ownership:** Descriptor Identity and Descriptor Revision each have one canonical owner, and no competing canonical descriptor represents the same identity and revision.
13. **Descriptor coherence:** one Source Descriptor does not combine conflicting Source Identities, conflate revisions, or silently overwrite externally owned meanings.
14. **No semantic duplication:** derived descriptors, catalogs, and projections do not become competing semantic owners.
15. **Classification consistency:** Source Classification preserves the meaning and owner of every referenced upstream classification.
16. **Category independence:** Source Category remains catalog-owned and independent from Source Classification, authority, eligibility, lifecycle, confidentiality, applicability, and topology.
17. **No classification-category substitution:** Source Classification and Source Category may coexist but do not substitute for, override, or imply one another.
18. **Explicit participation:** Source Participation is attributable to the catalog semantic owner, Catalog Scope-bound, Catalog Revision-bound, and never inferred from Source Reference or technical or conversational proximity.
19. **Eligibility-reference separation:** Source Eligibility References do not create or evaluate eligibility.
20. **Lifecycle-reference separation:** Source Lifecycle References do not create or change lifecycle state.
21. **Canonical conflict visibility:** conflicting or unresolved canonical logical identity or exact revision remains explicit and cannot be repaired by a catalog-local assertion.
22. **Historical immutability:** a later catalog, source, descriptor, category, classification, ownership, participation, eligibility-reference, or lifecycle-reference change does not rewrite an earlier revision.
23. **Provider neutrality:** no model, registry product, database, repository host, storage system, schema language, or implementation owns Rule Source Catalog semantics.
24. **No downstream semantic capture:** Federation Boundary, Discovery Operation Evidence, Discovery Evidence Provenance, Discovery Closure Evidence, Rule Universe Result, Discovery Validation, Governance Applicability, and Policy Decision consumers cannot redefine Rule Source Catalog meanings.
25. **No self-authorization:** a Rule Source, Source Descriptor, catalog, category, classification, declaration, or participation assertion cannot establish its own authority, eligibility, acceptance, effectiveness, or applicability.

These invariants define meaning, not validation algorithms or implementation requirements.

## 19. Upstream Dependencies

The contract depends semantically on:

| Upstream domain | Dependency boundary |
| --- | --- |
| Foundation | Canonical ownership, authority hierarchy, confidentiality, product independence, provider neutrality, lifecycle separation, and immutable history |
| Accepted Governance Rule Discovery architecture | Source-catalog responsibility and separation from federation, discovery, closure, provenance, results, validation, applicability, and Policy Decision |
| Architecture Acceptance | Authorization to design and review this contract candidate within the accepted Decision Boundary |
| Contract Governance | Contract identity, ownership, lifecycle, review, versioning, acceptance, effectiveness, change, supersession, and traceability |
| Canonical artifact governance | Canonical artifact identity, exact revision, lineage, derived-representation, and source-of-truth ownership |
| Universal Eligibility | Source authorization, confidentiality, purpose, provider, and other information-use eligibility meanings |
| Governance Authority | Authority, ownership authority, approval eligibility, delegation, and non-delegable boundaries |
| Governance lifecycle | Approval, effectiveness, adoption, disposition, supersession, archival, retirement, and temporal lifecycle meanings |
| Product Binding where separately governed | Product adoption and product-bound source relationships |

This proposal consumes those meanings by reference. It does not redefine them or require an implementation dependency.

## 20. Downstream Consumers

The direct planned downstream contract consumers are:

1. **Federation Boundary Contract candidate** — consumes Rule Source, Source Identity, Source Descriptor, Source Participation, ownership, and reference meanings without redefining them.
2. **Discovery Operation Evidence Contract candidate** — consumes exact source and catalog-declaration meanings when recording discovery activity without acquiring source-catalog ownership.
3. **Discovery Evidence Provenance Contract candidate** — consumes exact source, catalog, identity, revision, declaration, participation, ownership, eligibility-reference, and lifecycle-reference meanings when preserving discovery evidence lineage without acquiring source-catalog ownership.
4. **Discovery Closure Evidence Contract candidate** — consumes exact source, catalog, identity, revision, declaration, participation, relationship, ownership, eligibility-reference, and lifecycle-reference meanings when composing closure-supporting evidence without redefining source-catalog semantics.
5. **Discovery Validation Contract candidate** — consumes exact Rule Source Catalog meanings when evaluating cross-contract conformance without acquiring source-catalog ownership.

Later indirect consumers may include Rule Universe Result, Governance Applicability, Policy Decision, audit, and historical reconstruction. An indirect consumer receives Rule Source Catalog meaning through accepted dependency relationships and may not redefine it.

This section defines semantic dependency direction only. It does not define software dependencies, services, APIs, calls, packages, deployment, or runtime sequencing.

## 21. Category B Open Questions

The following accepted Category B items affect this contract proposal. They remain unresolved.

| Category B item | Effect on this proposal | Preserved boundary |
| --- | --- | --- |
| GRD-01 — Artifact class governing the source-of-sources | The final artifact class carrying a catalog or source-of-sources relationship is undecided. | This proposal defines source-catalog meaning only and selects no artifact class. |
| GRD-04 — Trust evidence for negative source declarations | The assurance required for a declaration that a source or relationship is absent remains undecided. | This proposal does not define negative-declaration evidence or closure sufficiency. |
| GRD-05 — Acyclic relationships and harmless bounded cycles | The permitted cycle policy for source relationships remains undecided. | This proposal prohibits cyclic semantic ownership but defines no traversal, graph, or bounded-cycle rule. |
| GRD-07 — External-incorporation decisions requiring legal or specialist review | Responsibility for specialist eligibility remains undecided. | This proposal may reference externally governed classifications or eligibility evidence but assigns no specialist authority. |
| GRD-08 — Jurisdiction, customer, contract, and tenant scope expression | Exact external and tenant scope semantics remain undecided. | This proposal requires attributable bounded relationships but defines no scope vocabulary or product-specific value. |
| GRD-10 — Alias, mirror, translation, and derived-source reconciliation | Exact equivalence and reconciliation treatment remains undecided. | This proposal preserves canonical identity and conflict visibility but defines no reconciliation mechanism. |
| GRD-12 — Exact scope relationships across governance layers | The final relationship vocabulary among platform, product, repository, component, tenant, and external scopes remains undecided. | This proposal does not define relationship values or cross-layer composition. |
| GRD-19 — Registry topology and granularity | Central, federated, hybrid, and derived catalog representation choices remain undecided. | This proposal defines one semantic owner and no physical or logical topology. |

No Category B classification, assumption, containment boundary, future owner, or reopening trigger is changed by this proposal.

Questions assigned to Federation Boundary, Discovery Operation Evidence, Discovery Evidence Provenance, Discovery Closure Evidence, Rule Universe Result, or Discovery Validation remain with those contract candidates and are not imported into this contract.

## 22. Explicit Non-Goals

This contract proposal does not define:

- Federation Root or root-set semantics;
- federation topology;
- discovery boundaries;
- traversal;
- recursion;
- cycle algorithms;
- source resolution;
- retrieval;
- discovery manifests;
- closure relevance;
- closure evidence;
- provenance records;
- temporal closure;
- Complete Rule Universe Snapshots;
- Incomplete Discovery Results;
- discovery failure handling;
- validation;
- validation algorithms;
- rule applicability;
- conflict precedence;
- Policy Decision outcomes;
- approval;
- effectiveness;
- adoption;
- Design Freeze;
- database;
- API;
- wire format;
- runtime;
- storage;
- serialization;
- protocol;
- schema;
- fields;
- JSON;
- implementation;
- source code;
- service topology;
- deployment;
- synchronization;
- transaction design;
- registry technology;
- product-specific rules;
- Product Bindings; or
- operational policy.

## 23. Revision History and Review Resolution

### 23.1 Revision History

| Version | Classification | Summary |
| --- | --- | --- |
| 0.1.0 | Initial Draft Contract Proposal | Established the initial Rule Source Catalog semantic candidate under the Contract Governance Framework. |
| 0.2.0 | Pre-acceptance Major Maintenance Revision | Resolves three Major and three Minor findings from the independent Contract Review. This revision does not change the accepted architecture, Decision Boundary, contract decomposition, Category B classifications, contract identity, semantic owner, Draft status, or non-normative effect. |
| 0.2.1 | Pre-acceptance Patch Maintenance Revision | Reconciles the proposal’s Contract Decomposition Plan binding and direct downstream dependency declarations with Version 0.2.0 of the plan. Replaces the former combined downstream label with the separate Discovery Evidence Provenance and Discovery Closure Evidence contracts and records Discovery Validation as a direct consumer. No semantic ownership, primary responsibility, Decision Boundary, fail-closed behavior, Category B mapping, provider-neutrality, or implementation-independence meaning changes. |

### 23.2 Review Resolution Mapping

| Finding | Resolution | Affected sections |
| --- | --- | --- |
| MAJOR-01 — Catalog Identity and Catalog Scope undefined | **Resolved.** Catalog Identity, Catalog Revision, and Catalog Scope are defined as separate semantic dimensions from catalog ownership and from one another. Source Participation is bound to all three. | 4.3–4.6, 12, 17, 18 |
| MAJOR-02 — Declaration, reference, registration, and participation not reconciled | **Resolved.** Source Reference, Source Declaration, and Source Participation have separate canonical meanings. Source Registration and Catalog Entry are non-canonical terms; legacy Catalog Membership is constrained to exact Source Participation meaning and excluded from federation meaning. | 10–12, 17, 18 |
| MAJOR-03 — Descriptor ownership not deterministic | **Resolved.** Rule Source content ownership, Descriptor Identity ownership, Descriptor Revision ownership, each represented assertion owner, and catalog-owned assertion ownership are explicitly separated, with one canonical owner per semantic assertion. | 8, 11, 14, 17, 18 |
| MINOR-01 — Classification and category overlap | **Resolved.** Source Classification is externally owned; Source Category is an independent catalog-owned dimension. Neither substitutes for, overrides, or implies the other. | 7, 9, 18 |
| MINOR-02 — Canonical identity and revision conflated | **Resolved.** Canonical Logical Source Identity is stable across revisions and Exact Source Revision Binding identifies one immutable revision without creating a second identity. | 6, 6.1, 15–18 |
| MINOR-03 — Rule Source definition too broad | **Resolved.** Rule Source is limited to a semantically identifiable source of rule-bearing material or an artifact class later authorized under GRD-01; catalog, registry, federation, access, traversal, provenance, and closure mechanisms are excluded by proximity alone. | 5, 18, 21 |

These resolution statements record the scope of this maintenance revision. They are not an independent verification, review approval, contract acceptance, operational effectiveness, or implementation authorization.

## 24. Contract Lifecycle and Next Governance Action

This proposal is at the `Proposal` stage of the Contract Governance lifecycle.

| Lifecycle dimension | Current result |
| --- | --- |
| Contract status | Draft Contract Proposal |
| Independent Review | Completed — `REQUIRES MAJOR REVISION` |
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

Verification may confirm exact graph conformance, identify a regression, request another bounded maintenance revision, or determine that architecture or decomposition work must resume. Verification does not make this proposal Accepted, Published, or Effective.
