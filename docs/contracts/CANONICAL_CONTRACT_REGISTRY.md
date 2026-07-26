# Governance Rule Discovery Canonical Contract Registry

| Attribute | Value |
|---|---|
| Document type | Canonical Contract Registry |
| Domain | Governance Rule Discovery |
| Classification | Descriptive, non-normative index |
| Repository baseline | `f3c913626d0da24ea2ff4652a3265235f255b290` |
| Registry scope | Canonical contracts C1 through C7 |
| Normative effect | None |
| Governance authority | None |
| Lifecycle effect | None |

This registry describes the canonical contract set at the identified repository baseline. It does not define, accept, publish, make Effective, supersede, or authorize any contract. Each referenced proposal, Acceptance Record, governance artifact, and architecture artifact remains authoritative for the information it owns.

## 1. Registry Purpose

The purpose of this registry is to provide one navigational index for the seven canonical contracts in the Governance Rule Discovery domain. It records their current proposal revisions, associated Acceptance Records, current documented statuses, indexed primary responsibilities, and direct dependency relationships.

The registry is a descriptive projection of existing artifacts. It does not become a source of contract semantics merely by repeating information from those artifacts.

## 2. Registry Scope

The registry covers:

- the seven canonical contract positions C1 through C7 defined by the [Governance Rule Discovery Contract Decomposition Plan v0.2.0](GOVERNANCE_RULE_DISCOVERY_CONTRACT_DECOMPOSITION_PLAN.md);
- the current proposal revision for each position at the repository baseline;
- the Acceptance Record associated with each contract;
- each contract's current documented proposal and attestation status; and
- direct, intra-domain dependencies defined by the accepted decomposition graph.

The identifiers C1 through C7 are decomposition and registry references. They do not replace the canonical artifact identities declared by the contracts.

An Acceptance Record reference is revision-specific. Where an Acceptance Record binds a predecessor proposal revision, the registry states that limitation explicitly; it does not extend the record to a later proposal revision.

## 3. Canonical Contract Index

The responsibility entries below are index summaries only. The linked proposal remains the sole source for the complete semantic boundary of each contract.

| Canonical ID | Contract Name | Current Proposal Version | Acceptance Record | Current Status | Primary Responsibility | Direct Upstream Dependencies | Direct Downstream Dependencies |
|---|---|---:|---|---|---|---|---|
| C1 | [Rule Source Catalog](RULE_SOURCE_CATALOG_CONTRACT_PROPOSAL.md) | 0.2.1 | [Rule Source Catalog Contract Acceptance Record v0.1.0](RULE_SOURCE_CATALOG_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal. The Acceptance Record is not acceptance and does not bind current proposal v0.2.1. | Canonical source identity, description, catalog participation, and catalog relationship semantics. | None within the canonical contract set. | C2 Federation Boundary; C3 Discovery Operation Evidence; C4 Discovery Evidence Provenance; C5 Discovery Closure Evidence; C7 Discovery Validation. |
| C2 | [Federation Boundary](FEDERATION_BOUNDARY_CONTRACT_PROPOSAL.md) | 0.2.2 | [Federation Boundary Contract Acceptance Record v0.1.0](FEDERATION_BOUNDARY_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal. The Acceptance Record is not acceptance and does not bind current proposal v0.2.2. | Canonical semantics for root or root-set discovery topology and cross-boundary composition. | C1 Rule Source Catalog. | C3 Discovery Operation Evidence; C4 Discovery Evidence Provenance; C5 Discovery Closure Evidence; C7 Discovery Validation. |
| C3 | [Discovery Operation Evidence](DISCOVERY_OPERATION_EVIDENCE_CONTRACT_PROPOSAL.md) | 0.2.1 | [Discovery Operation Evidence Contract Acceptance Record v0.1.0](DISCOVERY_OPERATION_EVIDENCE_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal. The Acceptance Record is not acceptance and does not bind current proposal v0.2.1. | Canonical semantics of one attributed Discovery Operation and the evidence describing what discovery attempted, under which Federation Boundary, within one exact Decision Context. | C1 Rule Source Catalog; C2 Federation Boundary. | C4 Discovery Evidence Provenance; C5 Discovery Closure Evidence; C6 Rule Universe Result; C7 Discovery Validation. |
| C4 | [Discovery Evidence Provenance](DISCOVERY_EVIDENCE_PROVENANCE_CONTRACT_PROPOSAL.md) | 0.2.0 | [Discovery Evidence Provenance Contract Acceptance Record v0.1.0](DISCOVERY_EVIDENCE_PROVENANCE_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal; independently verified. The Acceptance Record remains Pending Human Attestation and does not constitute acceptance. | Canonical semantics of attributable lineage and identity, revision, and temporal continuity across discovery evidence. | C1 Rule Source Catalog; C2 Federation Boundary; C3 Discovery Operation Evidence. | C5 Discovery Closure Evidence; C6 Rule Universe Result; C7 Discovery Validation. |
| C5 | [Discovery Closure Evidence](DISCOVERY_CLOSURE_EVIDENCE_CONTRACT_PROPOSAL.md) | 0.2.0 | [Discovery Closure Evidence Contract Acceptance Record v0.1.0](DISCOVERY_CLOSURE_EVIDENCE_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal; independently verified. The Acceptance Record remains Pending Human Attestation and does not constitute acceptance. | Canonical semantics of the evidence basis supporting a bounded discovery-closure determination. | C1 Rule Source Catalog; C2 Federation Boundary; C3 Discovery Operation Evidence; C4 Discovery Evidence Provenance. | C6 Rule Universe Result; C7 Discovery Validation. |
| C6 | [Rule Universe Result](RULE_UNIVERSE_RESULT_CONTRACT_PROPOSAL.md) | 0.2.0 | [Rule Universe Result Contract Acceptance Record v0.1.0](RULE_UNIVERSE_RESULT_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal; independently verified. The Acceptance Record remains Pending Human Attestation and does not constitute acceptance. | Canonical semantics of one Complete-versus-Incomplete Rule Universe Result for one exact externally governed result-production point. | C3 Discovery Operation Evidence; C4 Discovery Evidence Provenance; C5 Discovery Closure Evidence. | C7 Discovery Validation. |
| C7 | [Discovery Validation](DISCOVERY_VALIDATION_CONTRACT_PROPOSAL.md) | 0.2.0 | [Discovery Validation Contract Acceptance Record v0.1.0](DISCOVERY_VALIDATION_CONTRACT_ACCEPTANCE_RECORD.md), Pending Human Attestation for proposal v0.2.0 | Draft Contract Proposal; independently verified. The Acceptance Record remains Pending Human Attestation and does not constitute acceptance. | Canonical semantics of independent conformance evaluation for one exact Governance Rule Discovery artifact set. | C1 Rule Source Catalog; C2 Federation Boundary; C3 Discovery Operation Evidence; C4 Discovery Evidence Provenance; C5 Discovery Closure Evidence; C6 Rule Universe Result. | None within the canonical contract set. |

## 4. Relationship to the Contract Governance Framework

The [Contract Governance Framework v0.3.0](../governance/CONTRACT_GOVERNANCE_FRAMEWORK.md) governs contract lifecycle, authority, review, verification, human attestation, acceptance, publication, and effectiveness. This registry does not perform or alter any of those functions.

In particular:

- a proposal remains proposal evidence;
- an Acceptance Record with status Pending Human Attestation remains unsigned governance evidence;
- an Acceptance Record does not become acceptance without eligible, attributable human attestation;
- acceptance does not arise from inclusion in this registry; and
- publication and effectiveness do not arise from inclusion in this registry.

The registry records exact proposal-to-Acceptance-Record bindings. It does not cause consumers to float from an attested revision to a later revision.

## 5. Relationship to the Contract Decomposition Plan

The [Governance Rule Discovery Contract Decomposition Plan v0.2.0](GOVERNANCE_RULE_DISCOVERY_CONTRACT_DECOMPOSITION_PLAN.md) remains the source for:

- the C1 through C7 decomposition;
- primary responsibility allocation;
- direct dependency direction;
- sequencing; and
- separation of Discovery Evidence Provenance from Discovery Closure Evidence.

The dependency columns in this registry reproduce only direct edges from that plan. They do not define runtime invocation, implementation coupling, governance authority, lifecycle precedence, or transitive dependency requirements.

If this registry and the decomposition plan differ, the registry is stale; the registry cannot amend or reinterpret the decomposition plan.

## 6. Non-Goals

This registry does not:

- redefine any contract or any term owned by a contract;
- introduce, transfer, or duplicate semantic ownership;
- introduce authority, eligibility, delegation, or approval;
- introduce lifecycle states or lifecycle transitions;
- introduce governance rules or governance behavior;
- resolve Category B items;
- alter a Decision Boundary;
- create acceptance, publication, effectiveness, implementation authorization, deployment authorization, or Design Freeze;
- define implementation, APIs, schemas, runtime behavior, storage, or provider-specific behavior; or
- replace a proposal, Acceptance Record, the Contract Governance Framework, or the Contract Decomposition Plan.

## 7. Registry Integrity

The registry is valid only as a snapshot of its cited repository baseline. A later proposal revision, Acceptance Record, or decomposition revision may make an entry stale. A discrepancy must be resolved by consulting the source artifacts; the registry itself supplies no authority for resolving the discrepancy.

## 8. Quality Gate Record

| Check | Result |
|---|---|
| Every canonical contract C1 through C7 appears exactly once | PASS |
| Current proposal versions match the repository baseline | PASS |
| Every Acceptance Record is referenced with its exact proposal-version binding | PASS |
| Direct dependencies match Contract Decomposition Plan v0.2.0 | PASS |
| The dependency graph is acyclic | PASS |
| Primary responsibilities are indexed without transferring or duplicating ownership | PASS |
| No obsolete combined Closure and Provenance contract is represented | PASS |
| No semantic behavior is introduced | PASS |
| No authority, lifecycle, or governance behavior is introduced | PASS |
