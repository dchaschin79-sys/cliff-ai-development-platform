# CADP Architecture History

The Architecture History subsystem preserves explanatory records of CADP architectural development. It provides historical context and navigation without creating governance authority.

## Navigation

- [Architecture History Index](index.md)
- [CADP Architecture Timeline](ARCHITECTURE_TIMELINE.md)
- [Phase 1 Step 4 Architecture Milestone](milestones/PHASE_1_STEP_4_ARCHITECTURE_MILESTONE.md)

## 1. Purpose

Architecture History preserves:

- architectural evolution;
- milestone context;
- major design rationale;
- exact baseline references where verified;
- review lineage;
- historical scope and boundaries;
- links among milestones, decisions, diagrams, contracts, and reviews.

The subsystem gives future maintainers a concise route to the historical intent behind the architecture while preserving direct links to the evidence on which each account relies.

## 2. Non-Normative Status

Architecture History documents are historical and explanatory. They:

- do not create governance rules;
- do not grant authority;
- do not record approval by themselves;
- do not make an artifact Effective or Adopted;
- do not create a Design Freeze;
- do not supersede contracts;
- do not replace approval records or lifecycle records;
- are not inputs that independently produce a Policy Decision `Allow`.

Where a historical document conflicts with a current applicable normative contract, the normative contract controls. A commit, review verdict, milestone status, diagram, or historical explanation is not human approval and does not establish current lifecycle authority.

## 3. Record Types

### Architecture Timeline

The [Architecture Timeline](ARCHITECTURE_TIMELINE.md) provides chronological navigation across recorded architecture phases and steps. It identifies verified baseline commits, recorded historical status, available milestone records, and known evidence gaps.

### Milestone Records

The [`milestones/`](milestones/) directory contains historical summaries of completed architecture phases or steps. A milestone preserves objectives, design decisions, review lineage, resolved findings, exclusions, and readiness at a recorded baseline. It is not a contract, review verdict, approval record, or lifecycle transition.

### Architecture Decision Records

The `decisions/` directory is reserved for standalone Architecture Decision Records that explain particularly important architectural choices requiring treatment independent of a milestone. An ADR records rationale and historical decision context; it does not acquire normative authority merely from its location or record type.

### Architecture Diagrams

The `diagrams/` directory is reserved for historical architecture diagrams. Diagrams are explanatory views of architecture at a cited scope or baseline. They remain non-normative and cannot replace their cited contracts or evidence.

## 4. Evidence Discipline

History maintainers must:

- cite exact commit SHAs when they are known and verified;
- distinguish verified repository facts from explanatory interpretation;
- avoid guessing dates, lifecycle states, versions, approvals, or decisions;
- use `Unknown`, `Not yet reconstructed`, or an equivalent explicit statement when evidence is unavailable;
- preserve superseded historical explanations rather than silently rewriting their prior meaning;
- link to normative sources and review evidence where practical;
- describe corrections transparently and identify their source or attributable change.

Repository chronology must not be presented as lifecycle chronology unless the governing evidence establishes that relationship. A baseline commit identifies repository content; it does not establish approval, effectiveness, adoption, or protection.

## 5. Maintenance Model

- The Architecture Timeline is updated when a verified milestone baseline is recorded.
- Milestone documents summarize completed architecture phases or steps and cite their verified baselines.
- Standalone ADRs are created only when an important architectural decision merits independent historical treatment.
- Diagrams are added only as explanatory views with a defined scope and evidence basis.
- Historical corrections are made transparently and attributably.
- Missing historical facts remain explicitly unresolved until repository or governance evidence supports reconstruction.

Historical records may gain new explanatory revisions. Corrections preserve the prior account through repository history and do not silently alter the meaning of the cited normative sources.

## 6. Directory Map

| Path | Purpose |
| --- | --- |
| [`ARCHITECTURE_TIMELINE.md`](ARCHITECTURE_TIMELINE.md) | Chronological architecture milestone navigation and verified baseline references. |
| [`milestones/`](milestones/) | Historical records for completed architecture milestones. |
| `decisions/` | Standalone Architecture Decision Records when valid records are later created. |
| `diagrams/` | Historical explanatory diagrams when valid diagrams are later created. |
| [`index.md`](index.md) | Concise navigation across history records and principal normative sources. |
