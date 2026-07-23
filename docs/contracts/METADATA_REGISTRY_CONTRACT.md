# Metadata Registry Contract

| Field | Value |
| --- | --- |
| Document ID | CADP-CONTRACT-METADATA-REGISTRY |
| Version | 0.1.1 |
| Lifecycle state | Draft |
| Scope | CADP controlled metadata registries and registered extensions |
| Authority class | Foundation contract candidate |
| Approval requirement | Requires explicit human approval |
| Source baseline reference | CADP-ARCH-FOUNDATION v0.2.0 at Git revision `84052beb7e7d270e2aeba797c039e5f3a0b3ccc4` |
| Related Draft contract | CADP-CONTRACT-CANONICAL-ARTIFACT v0.1.0 |
| Revision note | Version 0.1.1 introduces the non-circular registry bootstrap mechanism required by the independent Step 2 review. |

## 1. Purpose and Scope

This contract defines how CADP controls the vocabularies used by canonical artifact envelopes. A metadata registry assigns stable meaning, ownership, compatibility, and lifecycle to values that must be interpreted consistently across products, repositories, models, validators, and adapters.

A registry entry is itself a governed artifact and follows the Canonical Artifact Contract. Registration recognizes a value; it does not approve an artifact instance, grant a user permission, create a product scope, or make a policy Effective.

This contract establishes registry behavior without defining the initial registry values, a final schema, or a storage implementation.

## 2. Registry Families

CADP maintains controlled registry families for at least:

| Registry family | Purpose | Boundary |
| --- | --- | --- |
| Artifact types | Identifies semantic artifact categories and the metadata categories applicable to each. | An artifact type does not determine authority, folder, lifecycle, or confidentiality. |
| Authority classes | Identifies recognized authority-eligibility and precedence classes. | Registration does not make an artifact authoritative; approval, applicability, scope, source, and eligibility remain required. |
| Confidentiality classes | Identifies recognized information-handling classifications and references their handling policies. | The registry identifies a class; detailed access, provider, regional, egress, and retention policy remains separately governed. |
| Writer classes | Identifies categories of human or system actors eligible to propose or modify artifacts. | A writer class does not grant identity-specific access or approval authority. |
| Scope types | Identifies supported scope shapes and the identifiers required to resolve them. | A scope type does not create a scope instance or establish product adoption. |
| Namespaces | Identifies controlled naming boundaries for global and extension values. | Namespace registration delegates naming space only; it does not delegate governance authority beyond the approved registration. |

Additional registry families require an approved extension to this contract or another applicable governance contract. A new family cannot redefine an existing family's meaning.

## 3. Registry Ownership

Each registry family has:

- an accountable human governance owner;
- authorized writer classes that may propose changes;
- required reviewer roles appropriate to the registry's risk;
- an approval route bound to an immutable entry revision;
- a canonical Git source and controlled namespace;
- an audit and compatibility obligation.

Registry custodians may maintain entries and execute approved administrative procedures. Custodians do not acquire authority to approve their own proposals unless a separate higher-authority policy explicitly permits that role combination.

AI systems may draft entries, identify collisions, compare definitions, and recommend compatibility outcomes. They may not approve registry entries, reserve authority for themselves, or redefine global values.

## 4. Registry Entry Contract

Every registry entry is a canonical artifact and must identify categories for:

- stable namespace-qualified registry key;
- registry family;
- human-readable name and definition;
- semantic version and immutable source revision;
- accountable owner and allowed writer classes;
- review workflow, applicability or disposition, and effective interval;
- compatibility and replacement relationships;
- aliases, if permitted by later policy;
- approval, rationale, audit, and integrity evidence;
- affected registry entries and artifact classes;
- confidentiality classification of the registry record itself.

The definition must be sufficiently precise for two independent validators to classify the same valid artifact consistently. The exact field syntax and conditional requirements remain deferred.

## 5. Registration Workflow

After Registry Bootstrap is complete, registration reuses the Foundation Architecture's orthogonal state and approval model; it does not create a separate authority system. Before bootstrap completion, only the bounded seed process in the Registry Bootstrap section may establish registry entries.

1. **Proposal:** an authorized writer submits a Draft entry under an existing registered namespace.
2. **Identity and collision check:** the registry resolves namespace ownership, stable-key uniqueness, reserved terms, aliases, and semantic overlap.
3. **Impact and compatibility review:** reviewers identify affected artifacts, validators, products, projections, and migration obligations.
4. **Formal Review:** an immutable candidate revision enters Review with named reviewers and evidence.
5. **Human disposition:** the authorized human decision records approval or rejection against the exact revision.
6. **Applicability:** an Approved entry becomes Effective only for its declared scope and interval. Approval alone does not make it effective.
7. **Publication and validation:** indexes and adapters may publish derived representations that cite the canonical entry revision.

Rejected proposals remain evidence and never acquire normative effect. Missing or invalid approval evidence prevents activation.

## Registry Bootstrap

### Exceptional and temporary purpose

Registry Bootstrap exists only to establish the minimum seed entries required for the normal registration workflow to operate. It is exceptional, temporary, and cannot become a permanent parallel authority system, standing exception, or reusable approval route.

Bootstrap does not create a registry family, alter the Foundation Architecture authority hierarchy, permit AI approval, authorize product-specific seed values, or make Draft artifacts normative.

### Human-ratified seed registry and authority source

The initial entries must be established through a human-ratified seed registry bound to:

- the exact Approved Foundation Architecture revision;
- the exact Approved Canonical Artifact Contract revision;
- the exact Approved Metadata Registry Contract revision;
- an immutable Git revision containing the reviewed seed content;
- explicit, external human approval evidence;
- a defined bootstrap scope;
- a defined completion condition.

Before normal registry entries exist, the seed registry derives legitimacy directly and only from explicit human approval of those foundational revisions and the seed's immutable revision. It does not derive legitimacy from a pre-existing registry entry. This is the only permitted non-circular bootstrap path.

Bootstrap becomes usable only after the referenced foundation documents are explicitly Approved. Their Draft versions have no normative effect and cannot authorize seed activation.

### Minimum seed scope

The seed registry may contain only the minimum entries required to operate normal registry governance, including at most:

- the artifact type required for registry entries;
- the authority class required for foundation and registry governance artifacts;
- the writer classes required to propose and maintain registry entries;
- the scope types required to identify global CADP registry scope;
- the confidentiality class required for public or internal governance records;
- the namespaces required for core CADP registry values.

This contract does not define the names, identifiers, definitions, or values of those entries. Product-specific seed entries are prohibited.

### External approval and bootstrap record

The seed registry cannot approve itself. Approval must be external, attributable, human, and bound to the exact immutable seed revision. Text inside a seed artifact claiming approval is not approval evidence.

A separate bootstrap record must identify:

- stable bootstrap identity;
- foundational document identities, versions, and exact source revisions;
- seed registry artifact identities, versions, and exact source revisions;
- approving human identities and roles;
- approval evidence and rationale;
- authorized scope and effective time;
- completion criteria;
- transition plan to normal registry governance;
- rollback or recovery reference;
- integrity evidence.

The bootstrap record is a governed audit artifact. This section defines required categories, not a final schema.

### Completion and closure

Bootstrap is complete only when:

- every required seed entry is Approved and Effective;
- normal registry validation can evaluate registry artifacts without bootstrap exceptions;
- the bootstrap record is closed with attributable human evidence;
- no future registry entry depends on bootstrap authority.

After closure, every new or changed registry entry follows Section 5. Bootstrap authority cannot be reused, extended, or treated as an authority tier. The closed bootstrap record remains permanent audit evidence.

### Failure behavior

The following conditions produce Indeterminate and fail closed for protected operations:

- missing, invalid, or revision-mismatched bootstrap approval evidence;
- ambiguous or unapproved foundational revision;
- seed entries outside the authorized minimum scope;
- self-approved bootstrap artifacts or AI approval;
- incomplete transition to normal registry governance;
- attempted bootstrap reuse after closure;
- conflicting bootstrap records;
- changed seed content after approval without a new reviewed and approved revision.

Bootstrap cannot override ordinary authority, confidentiality, integrity, lineage, or policy-decision controls. A failed bootstrap cannot be converted into a standing exception.

### Deferred bootstrap decisions

Later work will define the exact seed values, seed registry file layout, bootstrap-record serialization, approval-attestation format, signing mechanism, and validation implementation. Deferral does not permit activation without the approved foundation revisions, bounded seed scope, external approval, closure controls, and evidence required above.

## 6. Versioning

Registry entries use semantic versions independently from immutable Git revisions.

- A **compatible revision** clarifies meaning without changing the valid classifications or obligations of existing consumers.
- An **additive revision** introduces meaning that existing consumers may ignore safely when the family contract permits extension.
- A **breaking revision** changes classification, precedence, required metadata, handling, or scope semantics and requires impact analysis and migration.
- An **immutable source revision** identifies the exact content evaluated and approved; it is not a substitute for semantic compatibility.

Draft edits may share a candidate semantic version across Git revisions. Approved entry meaning cannot change under the same semantic version. Compatibility must be assessed against declared consumers and cannot be inferred only from a version-number pattern.

## 7. Deprecation and Supersession

Deprecation and supersession preserve stable keys and history.

An entry marked Deprecated must identify:

- the reason;
- the transition interval;
- affected consumers;
- the replacement when one exists;
- permitted legacy scopes;
- migration and rollback or recovery references.

An entry marked Superseded must identify the successor and the effective boundary. Its key cannot be reassigned to a different meaning. Superseded or Expired entries have no normative effect except within an explicit preserved legacy binding. Rejected and Archived entries never have normative effect.

Derived registry indexes must expose disposition and replacement relationships rather than silently omitting old entries.

## 8. Compatibility

Compatibility evaluation determines whether a registry change preserves the interpretation of existing artifacts and consumers. It covers:

- meaning and classification behavior;
- authority and precedence effects;
- confidentiality and handling effects;
- writer and approval eligibility;
- scope resolution;
- required metadata and validation behavior;
- adapter and derived-index interpretation;
- migration and rollback requirements.

A compatibility result binds to the compared entry versions, source revisions, evaluator identity/version, scope, evidence, rationale, and timestamp. Unknown or conflicting compatibility is Indeterminate and fails closed for activation that could alter authority, confidentiality, approval, or protected operations.

## 9. Collision Handling

A collision exists when entries claim the same namespace-qualified key, reuse a retired identity, define incompatible meanings through aliases, or create indistinguishable classifications in a scope where deterministic evaluation is required.

Collision handling follows these rules:

1. The registry does not resolve collisions by file order, publication time alone, popularity, or retrieval score.
2. An existing stable key is never reassigned to a different meaning.
3. Equivalent proposals are consolidated through explicit lineage rather than duplicated.
4. Conflicting proposals remain non-effective until human review selects a canonical definition or assigns distinct identities.
5. Unresolved collisions return Indeterminate and fail closed for protected operations.

Cross-registry semantic overlap is also reviewed. For example, an artifact type cannot be used to recreate an authority class under another name.

## 10. Reserved Namespaces

The namespace model reserves categories for:

- global CADP values;
- registered product extensions;
- internal system values;
- experimental values with no normative effect;
- provider or adapter-specific values that cannot redefine core semantics.

Global CADP namespaces are controlled by CADP governance. The first core namespaces may be established only through the bounded Registry Bootstrap; later namespace entries follow the normal workflow in Section 5. Internal and experimental namespaces are isolated from normative evaluation unless a governed promotion registers their values appropriately. Provider namespaces translate or extend adapter concerns only.

Exact namespace syntax, reserved prefixes, normalization, character rules, and case sensitivity remain Phase 1 schema decisions. Until defined, a proposed namespace cannot become Effective.

## 11. Product Extensions

A product extension requires explicit namespace registration before any contained value can be recognized. The registration must identify:

- stable product namespace identity;
- accountable owner;
- permitted registry families;
- allowed writer classes;
- product and component scope boundaries;
- compatibility obligations;
- conflict and retirement handling;
- source and audit requirements.

A product extension may narrow or add product-scoped classification where higher authority permits. It cannot redefine, shadow, weaken, or reuse a global value; alter global precedence; bypass confidentiality; or make a product-local artifact globally authoritative.

Namespace registration does not create a Product Binding, product rule, or adoption state. Those remain outside Phase 1 Step 2.

## 12. Validation and Policy Outcomes

Registry validation covers at least:

- registry-family and namespace resolution;
- stable-key uniqueness and non-reuse;
- required metadata presence;
- canonical source and immutable revision;
- owner, writer, reviewer, and approval eligibility;
- valid workflow, applicability, and effective interval;
- definition completeness and deterministic interpretation;
- collision and alias detection;
- compatibility evidence;
- deprecation, supersession, and migration lineage;
- product-extension boundary compliance;
- bootstrap-record validity, minimum-scope compliance, and closure status when evaluating seed entries;
- confidentiality eligibility and integrity evidence.

Validation uses provider-neutral outcomes:

- **Allow:** the evaluated registration or use is permitted for the declared scope and inputs.
- **Deny:** an applicable rule prohibits the registration or use.
- **Indeterminate:** CADP cannot establish a safe, deterministic result.
- **Not Applicable:** the evaluated rule does not govern the declared entry or use.

Missing registration, unresolved collision, invalid namespace ownership, stale source revision, invalid approval, unknown compatibility, conflicting definitions, or an invalid bootstrap record produce Indeterminate where the value is required. Seed entries additionally require the Registry Bootstrap controls. Indeterminate fails closed for protected operations.

## 13. Audit Evidence

Every registry change retains:

- proposer, owner, reviewers, and approver identities;
- exact entry semantic version and immutable source revision;
- change request and rationale;
- collision and compatibility analysis;
- affected entries and artifact classes;
- approval or rejection evidence;
- effective interval;
- predecessor, successor, deprecation, and supersession references;
- migration and rollback or recovery references;
- integrity evidence;
- bootstrap approval, transition, and closure evidence when the change concerns a seed entry;
- publication and derived-index invalidation evidence when applicable.

History must allow reconstruction of which registry definition a validator used for an artifact, scope, and point in time. Deletion of a derived index cannot delete the canonical registration or its required audit evidence.

## 14. Deferred Decisions

Later Phase 1 work will define:

- exact initial values and seed registry contents;
- exact namespace and key syntax;
- field types, cardinality, and conditional validation;
- compatibility versioning rules by registry family;
- alias policy;
- signing and approval-attestation mechanisms;
- seed registry file layout and bootstrap-record serialization;
- canonical storage layout and generated-index formats;
- migration tooling and CI/CD adapters.

These deferrals do not permit unregistered values to gain normative effect or allow product extensions to redefine global values.
