# Architecture Research Closure Decision Methodology

| Field | Value |
| --- | --- |
| Document type | Architecture Governance Methodology |
| Version | 0.2.0 |
| Lifecycle state | Draft |
| Current normative effect | None |
| Current governance authority | None |
| Approval effect | None |
| Implementation authority | None |
| Scope | Determining readiness to move from architectural research into Architecture Decision Proposal development |
| Applicability | Reusable across CADP architecture research efforts |

## 1. Authority and Scope Boundary

This document defines a proposed, repeatable methodology for deciding whether an architectural research effort is sufficiently complete to begin Architecture Decision Proposal development.

This Draft does not:

- approve an architecture;
- select an architectural alternative;
- approve or make Effective a contract;
- approve governance;
- approve implementation, execution, deployment, or tooling;
- create a Design Freeze;
- create a Product Binding;
- create an approval record;
- create an authority class, role, delegation, registry value, or schema;
- amend the Foundation Architecture or an existing contract; or
- make its own methodology normative merely by existing, being committed, or being published.

If this methodology later becomes independently Approved and Effective through separately valid governance, its effect is limited to the transition from research into architectural decision making. A research-closure outcome authorizes only the preparation of an ADP. It does not approve the resulting ADP or any architecture described by it.

The [Governance Document Model](../GOVERNANCE_DOCUMENT_MODEL.md) remains controlling for document-class and authority separation. The [Foundation Architecture](../FOUNDATION_ARCHITECTURE.md) remains controlling for architectural precedence, human approval boundaries, immutable history, lifecycle separation, and fail-closed behavior.

This revision applies prospectively. It does not retroactively reclassify, replace, invalidate, or silently rewrite a closure decision made under an earlier revision. The [Governance Rule Discovery Research Closure](GOVERNANCE_RULE_DISCOVERY_RESEARCH_CLOSURE.md) remains historically valid as the record produced under the methodology then in use. Reassessment under this revision requires a new, explicit decision record that preserves lineage to the earlier record.

## 2. Purpose

Architecture research can fail in two opposite ways:

1. it can stop before the evidence needed for a sound architectural decision exists; or
2. it can expand indefinitely because every unresolved question is treated as a blocker.

This methodology establishes a bounded closure discipline between those extremes.

Research is sufficiently complete when the architectural decision boundary is understood, alternatives capable of materially changing the decision have been investigated, critical assumptions are justified, remaining uncertainty is classified and bounded, and no unresolved issue would invalidate or fundamentally alter the architecture to be proposed.

Research closure does not mean that:

- every related question has been answered;
- no uncertainty remains;
- the preferred alternative has been approved;
- later evidence cannot justify reopening research;
- implementation details are known; or
- future research has no value.

Closure means that the remaining uncertainty can be carried safely into decision development without misrepresenting architectural correctness.

## 3. Motivation and Reusable Context

The [Governance Rule Discovery Architecture Research Report](../research/GOVERNANCE_RULE_DISCOVERY_ARCHITECTURE_RESEARCH_REPORT.md) illustrates the need for this methodology.

That research examines open-world and bounded closed-world assumptions, authoritative rule registries, an authoritative source-of-sources, closure evidence, inherited governance, external obligations, dynamic incorporation, temporal validity, cross-repository composition, auditability, and future ownership.

Some unresolved questions could fundamentally affect the validity of a later architecture—for example, whether an authoritative source-of-sources can obtain non-circular authority or whether externally binding obligations can be represented without false closure. Other questions may affect decomposition, assurance strength, migration detail, or future extension without invalidating the architectural direction.

This methodology does not classify or close that research. The example demonstrates why unresolved topics require explicit impact classification rather than being treated uniformly.

The methodology is generic. It applies to future CADP research regardless of subject, product, repository, technology, provider, or architectural domain.

## 4. Core Definitions

### 4.1 Research Question

A bounded question whose answer is needed to understand an architectural problem, alternative, assumption, dependency, risk, or decision consequence.

A Research Question identifies:

- the architectural subject;
- why the answer may matter;
- the evidence or reasoning needed;
- the decision boundary affected; and
- the condition under which the question can be considered sufficiently investigated.

### 4.2 Open Question

A Research Question for which no final or sufficiently supported answer has been established.

An Open Question is not automatically a blocker. Its category depends on the architectural effect of remaining unresolved, not on the fact that it is open.

### 4.3 Research Gap

A material absence in the research record, such as:

- an unexamined architectural mechanism;
- a missing alternative capable of changing the recommendation;
- an unsupported critical assumption;
- missing evidence for a consequential claim;
- an unresolved conflict among authoritative sources;
- an unexamined failure mode;
- a missing authority, lifecycle, confidentiality, temporal, or migration boundary; or
- inadequate treatment of affected scopes.

A Research Gap is classified according to its architectural impact.

### 4.4 Critical Gap

A Category A Research Gap that satisfies the complete Category A Materiality Test in Section 6.1.1. Its unresolved state prevents safe selection of a specific architecture element because it may materially change an architecture boundary, normative ownership, dependency direction, trust or authority root, mandatory safety invariant, fail-closed behavior, decision outcome semantics, compatibility model, confidentiality or authorization boundary, reproducibility invariant, or adoption or migration validity.

Critical Gap is a research-readiness classification. It is not a lifecycle state, authority class, defect severity registry value, or Policy Decision outcome.

### 4.5 Acceptable Uncertainty

An unresolved matter whose boundaries, assumptions, consequences, and revisit conditions are explicit and whose possible answers cannot invalidate the proposed architectural direction.

Acceptable Uncertainty:

- has a declared scope;
- has known plausible outcomes;
- does not conceal a Critical Gap;
- preserves architectural safety and correctness under each plausible outcome;
- has an explicit owner or future decision forum where ownership is known;
- has a recorded trigger for reconsideration; and
- is not represented as resolved.

### 4.6 Future Research

A separately retained research topic that may improve optimization, extension, understanding, or later architecture but is not required to establish correctness within the current Decision Boundary.

Future Research is not discarded. It is removed from the current closure gate while retaining traceability to its origin and relevance.

### 4.7 Research Closure

An attributable governance determination that the research evidence is sufficient to begin ADP development for an exact research artifact revision and Decision Boundary.

Research Closure:

- is bound to the exact research scope and immutable revision reviewed;
- applies only to readiness for ADP development;
- does not select or approve architecture;
- does not convert research into normative material;
- does not erase open or deferred questions; and
- may be reconsidered only under an explicit reopening condition.

### 4.8 Architecture Readiness

The condition in which an ADP can be developed without relying on an unresolved Category A issue, an unjustified critical assumption, an unbounded uncertainty, or a missing alternative capable of fundamentally changing the architecture.

Architecture Readiness is readiness to conduct architectural decision making. It is not architecture approval, implementation readiness, release readiness, adoption, effectiveness, or Design Freeze eligibility.

### 4.9 Decision Boundary

The exact architectural problem, scope, affected systems, authority domain, time horizon, constraints, and decision consequences that the research is intended to support.

The Decision Boundary distinguishes:

- questions that must be answered for the current architecture;
- questions that can be resolved within ADP development;
- questions belonging to later design or implementation;
- questions belonging to a different architecture effort; and
- questions whose relevance is only exploratory.

A research effort cannot claim closure against an undefined or silently changing Decision Boundary.

The Decision Boundary has been reached when:

- the architectural problem and its exclusions are bounded;
- representative, materially distinct architecture families have been evaluated;
- at least one viable architectural direction can be proposed without inventing an unresearched foundational decision;
- critical assumptions are explicit;
- residual uncertainty can be represented in an ADP without making that ADP internally invalid;
- fail-closed treatment can contain unresolved cases without concealing a missing architecture boundary; and
- further research is more likely to refine, specialize, or extend the proposed core than to replace it.

Reaching the Decision Boundary does not presume that research must close. It establishes the point at which the closure criteria can be evaluated neutrally.

## 5. Research Lifecycle

The research-to-decision lifecycle contains the following stages.

### Stage 1 — Research Initiation

Establish:

- research identity;
- problem statement;
- Decision Boundary;
- current governing constraints;
- initial Research Questions;
- expected evidence;
- known stakeholders and affected scopes; and
- explicit non-goals.

Initiation creates no presumption that the research will produce an ADP.

### Stage 2 — Research Inventory

Build and maintain a traceable inventory of:

- Research Questions;
- investigated alternatives;
- assumptions;
- evidence sources;
- findings;
- Research Gaps;
- conflicts;
- risks;
- open questions;
- external dependencies;
- deferred topics; and
- potential reopening conditions.

The inventory records both investigated and excluded alternatives. An exclusion requires an architectural rationale; omission is not exclusion.

### Stage 3 — Evidence Development

Investigate the architectural mechanisms and failure modes relevant to the Decision Boundary.

Evidence development should establish:

- what alternatives exist at the architectural level;
- what properties each alternative provides;
- what assumptions each alternative depends on;
- how each alternative fails;
- which higher governance boundaries constrain the alternatives;
- what remains unknown; and
- whether additional evidence could materially change the conclusion.

Implementation prototypes are not required unless a separate research question demonstrates that feasibility cannot be evaluated conceptually.

### Stage 4 — Closure Candidate

Bind a candidate closure assessment to an exact research artifact revision and inventory snapshot.

At this stage:

- every unresolved item receives a proposed Category A, B, or C classification;
- remaining assumptions and uncertainty are recorded;
- the architectural effect of each unresolved item is stated;
- a research outcome is recommended; and
- the evidence is made available for independent review.

The Closure Candidate is not a closure decision.

### Stage 5 — Independent Research Review

An independent reviewer evaluates:

- research completeness within the Decision Boundary;
- adequacy of the alternatives considered;
- correctness of terminology and architectural reasoning;
- unsupported assumptions;
- classification of unresolved items;
- authority, lifecycle, confidentiality, temporal, and historical boundaries;
- unexamined failure modes;
- research neutrality;
- risks of premature closure; and
- risks of indefinite expansion.

The reviewer may agree with, reject, or reclassify the proposed findings. A review verdict is evidence only and does not itself close research.

### Stage 6 — Research Closure Decision

An eligible human decision authority evaluates the candidate, inventory, independent review, classifications, remaining uncertainty, and recommendation.

The human decision selects one permitted outcome:

- `RESEARCH CLOSED`;
- `RESEARCH CLOSED WITH DEFERRED QUESTIONS`; or
- `ADDITIONAL RESEARCH REQUIRED`.

AI may inventory, analyze, classify provisionally, identify inconsistencies, and draft evidence. AI cannot make or impersonate the Research Closure decision.

This methodology does not create the human role or authority eligible to make that decision. Eligibility must be established independently under applicable CADP authority governance.

### Stage 7 — ADP Handoff or Continued Research

If research is closed, the ADP handoff retains:

- exact research sources and revisions;
- the Decision Boundary;
- critical assumptions;
- accepted uncertainties;
- deferred questions;
- rejected and retained alternatives;
- review evidence;
- closure outcome and rationale; and
- reopening conditions.

If additional research is required, the decision identifies the unresolved Category A items or other failed closure criteria. Research resumes only within the resulting bounded scope unless the Decision Boundary is separately revised.

### Stage 8 — Reopening

Closed research is reopened only when a recorded trigger occurs or new evidence shows that a closure criterion was not satisfied.

Reopening does not erase the earlier closure decision. It creates a new research state and preserves the earlier decision, evidence, scope, and rationale as immutable history.

## 6. Unresolved Topic Classification

### 6.1 Category A — Must Be Resolved Before ADP

Category A is reserved for a demonstrated architecture-selection blocker. An unresolved topic qualifies only when leaving it unresolved materially affects at least one of the following:

- an architecture boundary;
- normative ownership;
- dependency direction;
- a trust or authority root;
- a mandatory safety invariant;
- fail-closed behavior;
- decision outcome semantics;
- a compatibility model;
- a confidentiality or authorization boundary;
- a reproducibility invariant; or
- adoption or migration validity.

The effect must be specific enough to show why a safe architectural choice cannot be made. General importance, severity, uncertainty, complexity, or future usefulness is insufficient.

An item is not Category A merely because it:

- is important, high risk, or described as foundational in general terms;
- remains unresolved or could benefit from more research;
- concerns external obligations without showing an architecture-changing consequence;
- requires future normative detail;
- will be difficult to implement;
- would improve completeness;
- was identified by a reviewer; or
- may have consequences that are speculative, unsupported, or outside the Decision Boundary.

All Category A items must be resolved, or the Decision Boundary must be explicitly and validly narrowed so the demonstrated material effect no longer applies. Silent narrowing is prohibited.

#### 6.1.1 Category A Materiality Test

Every proposed Category A item must answer all seven questions:

1. What exact architecture element is unsafe to select while this issue remains unresolved?
2. What materially different architecture alternatives remain possible because of the issue?
3. Which invariant, ownership boundary, dependency direction, or decision semantic would change between those alternatives?
4. Why can the uncertainty not be represented explicitly in the ADP?
5. Why can the issue not be deferred to a contract, domain rule, implementation choice, procedure, future research effort, or residual-risk record?
6. What evidence shows that additional research is likely to resolve the issue sufficiently to change the ADP?
7. What concrete completion criterion would demonstrate that the required research is complete?

An answer that is missing, circular, speculative, or unsupported prevents Category A classification. A reviewer’s severity label is evidence to assess, not a substitute for this test.

#### 6.1.2 Burden of Proof

The party proposing Category A bears the burden of demonstrating the material effect and satisfying the Materiality Test with attributable evidence.

Uncertainty alone is insufficient. The proposer does not need to prove that no further useful research could ever exist; instead, the proposer must show why the specifically requested research is necessary before ADP development and how its concrete completion criterion can be met. Open-ended standards such as “research until complete,” “resolve all risk,” or “investigate further” are invalid.

### 6.2 Category B — May Remain Open During ADP

Category B is controlled deferral. It applies when an unresolved topic remains relevant to ADP development but can be carried safely through one or more of the following:

- an explicit assumption in the ADP;
- fail-closed treatment of unresolved cases;
- an architectural extension point;
- future architectural decomposition;
- a domain-specific rule;
- later contract detail;
- migration sequencing; or
- a later revision that does not invalidate the initial architecture.

Category B may also cover optimization, compatible sub-patterns, assurance above the minimum correctness boundary, non-fundamental terminology, or component ownership below the core boundary. Every plausible answer within the recorded bound must preserve core correctness, authority separation, mandatory safety invariants, fail-closed behavior, auditability, reproducibility, and compatibility with higher governance.

Each Category B item retained at closure must record:

1. the explicit assumption under which ADP development may proceed;
2. the current architectural risk created by the uncertainty;
3. the containment mechanism that prevents the uncertainty from producing an invalid or permissive architecture;
4. the future owner or decision forum responsible for resolution; and
5. the objective trigger for reopening or mandatory resolution.

Affected architecture and the latest safe resolution point must also be traceable where applicable. Category B is not risk dismissal and cannot conceal work that satisfies the Category A Materiality Test.

### 6.3 Category C — Future Research

Category C applies when the topic:

- is outside the current Decision Boundary;
- concerns an optional optimization or an alternative implementation;
- concerns an uncommon future condition not required for current architectural validity;
- explores a speculative extension;
- compares frameworks, technologies, providers, or mechanisms without affecting the selected architecture family;
- belongs to another architectural domain; or
- would not change the ADP’s architectural correctness under any presently credible answer.

Category C topics are retained as Future Research. They do not block closure and do not require resolution inside the current ADP.

### 6.4 Classification Decision Test

For each unresolved item:

1. determine whether it is inside the current Decision Boundary;
2. identify the exact architectural claim and materially plausible answers;
3. test whether it affects one of the enumerated Category A architectural elements;
4. if Category A is proposed, apply all seven Materiality Test questions and verify the burden of proof;
5. if the issue can be safely contained while remaining relevant to the ADP, classify it as Category B and record all five controlled-deferral elements; and
6. if it cannot affect the selected architecture family within the current boundary, classify it as Category C.

No classification follows automatically from risk severity, source type, reviewer terminology, or the existence of uncertainty.

### 6.5 Classification Disagreement

A material disagreement about whether an item is Category A cannot be resolved by relabeling it Category B or C.

The disagreement is presented to the eligible human closure authority with:

- each proposed classification;
- supporting evidence;
- architectural consequences;
- affected scope; and
- the independent reviewer’s assessment.

The eligible human closure authority applies the same Materiality Test and burden of proof. If Category A is not demonstrated, the authority evaluates Category B containment or Category C separation; lack of consensus alone does not create Category A. The final classification must be attributable, supported, and preserved with contrary evidence.

## 7. Research Closure Decision Process

### Step 1 — Confirm the Decision Boundary

Verify that the research artifact and closure request identify the same architectural problem, scope, affected systems, constraints, and decision consequences.

Scope additions discovered late in research are evaluated separately. They enter the current boundary only when they could materially affect its correctness. Otherwise they become Category C or a new research effort.

### Step 2 — Verify the Research Inventory

Confirm that the inventory accounts for:

- every initial Research Question;
- every material question discovered during research;
- alternatives considered;
- alternatives excluded with rationale;
- assumptions;
- findings;
- open questions;
- gaps;
- conflicts;
- risks;
- future research; and
- evidence sources.

Completeness of the inventory is bounded by the Decision Boundary. It is not a claim that every related topic in the world has been identified.

### Step 3 — Classify Findings and Gaps

Assign every unresolved item to Category A, B, or C using Section 6.

Resolved findings remain in the inventory with their evidence and resolution. They are not deleted merely because they no longer block closure.

Every proposed Category A item includes complete, evidence-supported answers to the seven-question Materiality Test. Every Category B item includes the five required controlled-deferral elements. Review findings are normalized into research questions before classification; a review severity does not determine a research category.

### Step 4 — Assess Architectural Risk

Evaluate whether unresolved items could affect:

- authority or ownership;
- canonical identity or source precedence;
- security or confidentiality;
- safety;
- deterministic behavior;
- lifecycle separation;
- external obligations;
- temporal validity;
- cross-scope composition;
- auditability;
- historical preservation;
- migration safety; or
- provider neutrality.

An unsupported assertion that a risk is unlikely is insufficient. The assessment identifies the mechanism, consequence, evidence, and boundary.

Risk identification does not by itself establish Category A. A risk blocks ADP development only when the Category A Materiality Test demonstrates the required architecture-changing effect.

### Step 5 — Bound Remaining Uncertainty

For each unresolved item, record:

- known facts;
- unknown facts;
- plausible outcomes;
- affected architecture;
- assumptions;
- safety consequence;
- reason for its category;
- containment mechanism for Category B;
- future owner or decision forum;
- revisit trigger; and
- the point by which it must be resolved, if applicable.

Uncertainty is bounded only when the architecture remains valid under every plausible outcome retained within that bound. Fail-closed treatment may establish boundedness when the ADP can state a conservative invariant, unresolved cases cannot produce permissive success, and future specialization cannot violate the initial architecture. Fail-closed treatment cannot conceal a missing architecture boundary or replace a required architecture choice.

### Step 6 — Assess Architectural Impact

Determine whether the research supports development of an ADP without forcing the ADP author to invent an unresearched foundational decision.

The assessment distinguishes:

- architecture-selection evidence;
- contract-design questions;
- implementation questions;
- migration questions;
- future extensions; and
- unrelated research.

The assessment distinguishes architecture families from variants within a family, implementation choices, operational procedures, and speculative future conditions. Only a materially distinct and plausible architecture family can be treated as a missing alternative capable of supporting Category A.

### Step 7 — Record the Recommendation

The research author recommends one permitted outcome and explains:

- why closure criteria pass or fail;
- which Category A items remain;
- which Category B items are proposed for deferral;
- which Category C items are retained;
- what risks remain; and
- what reopening conditions apply.

The recommendation has no closure authority.

### Step 8 — Apply Research-Closure Approval Criteria

Before an eligible human may declare research closed, the evidence must demonstrate:

1. the research artifact, inventory, and review are bound to exact revisions;
2. the Decision Boundary is explicit and stable for the closure decision;
3. representative, materially distinct architecture families are represented by mechanism and failure mode;
4. critical assumptions have attributable justification;
5. every proposed Category A item has passed the complete Materiality Test and no demonstrated Category A item remains unresolved;
6. every Category B item meets the Acceptable Uncertainty and controlled-deferral criteria;
7. every Category C item is explicitly separated from the current decision;
8. unresolved authority, confidentiality, safety, external-obligation, temporal, or historical issues are either demonstrated Category A items or are explicitly contained as Category B or separated as Category C;
9. the proposed architecture can remain deterministic and auditable under the retained uncertainty;
10. independent review has evaluated the exact closure candidate;
11. disagreements and contrary evidence are preserved;
12. future work and reopening triggers are explicit; and
13. the closure decision-maker’s eligibility is independently established.

These criteria approve only the research-to-ADP transition. They do not approve the research recommendation, architectural alternative, future ADP, contract, governance content, or implementation.

### Step 9 — Record the Outcome

The decision evidence identifies:

- closure decision identity;
- research artifact identity and exact revision;
- inventory and review identities and revisions;
- Decision Boundary;
- decision-maker identity and independently established eligibility reference;
- decision timestamp;
- outcome;
- rationale;
- Category A, B, and C inventory;
- accepted uncertainties;
- deferred-question obligations;
- reopening triggers;
- integrity evidence; and
- historical lineage.

This section defines evidence categories, not a schema or approval record.

## 8. Objective Closure Criteria

Research is complete enough for ADP development when all of the following are true.

### 8.1 Boundary Sufficiency

The problem, scope, affected authority domains, architectural consequences, and non-goals are explicit. Closure does not depend on silent scope exclusion.

### 8.2 Alternative Sufficiency

The research covers representative, materially distinct architecture families and their failure modes.

For this criterion:

- an architecture family differs in boundary, normative ownership, dependency direction, trust or authority root, mandatory invariant, decision semantics, compatibility model, confidentiality or authorization boundary, reproducibility, or adoption or migration validity;
- an architecture variant preserves those core properties while changing decomposition or a compatible sub-pattern;
- an implementation alternative realizes an already evaluated family through a different technology, algorithm, data format, or provider;
- an operational alternative changes procedure, staffing, sequencing, or run-time handling without changing the architecture family; and
- a speculative future alternative depends on a condition that is neither presently applicable nor supported as plausibly material to the current Decision Boundary.

Only omission of a materially distinct and plausible architecture family can support Category A. Variants, implementation choices, operational choices, and speculative futures do not block closure unless evidence demonstrates that they actually change one of the enumerated Category A architectural elements.

### 8.3 Assumption Sufficiency

Every assumption necessary for architectural correctness is:

- explicit;
- traceable to evidence or an authoritative constraint;
- tested against plausible contrary conditions; and
- classified as resolved, bounded Category B, or demonstrated Category A using Section 6.

A preference is not evidence for a critical assumption.

### 8.4 Risk Sufficiency

Material risks have:

- an identified cause;
- an architectural consequence;
- an affected scope;
- a relationship to the alternatives;
- a classification; and
- a disposition for ADP, future research, or further investigation.

### 8.5 Uncertainty Sufficiency

Remaining uncertainty is bounded and classified. Every Category B item records its assumption, current risk, containment, future owner, and reopening trigger. No Category B or C item can produce a plausible outcome that invalidates the architecture within the recorded bound.

Fail-closed treatment is sufficient only when the uncertainty is bounded, a conservative invariant can be stated in the ADP, unresolved cases cannot produce permissive success, and later specialization can occur without violating the initial architecture. It is insufficient when the missing information defines the architecture boundary itself.

### 8.6 Traceability Sufficiency

Research conclusions, unresolved items, classifications, reviews, and closure evidence are attributable and bound to immutable revisions.

### 8.7 Governance Sufficiency

The research does not depend on:

- self-authorizing sources;
- inferred human approval;
- AI-created authority;
- lifecycle collapse;
- repository location as authority;
- missing evidence as permission;
- an unrecorded exception; or
- a non-normative source overriding applicable governance.

### 8.8 Future-Work Sufficiency

Future work is explicitly identified and separated into:

- questions that must be resolved during ADP development;
- questions that must be resolved before a later contract or architecture stage;
- implementation research;
- migration research; and
- optional future research.

The existence of future work does not block closure when its boundary and latest safe resolution point are explicit.

## 9. Permitted Outcomes

The methodology does not prefer closure or continued research. The outcome follows from the evidence and criteria for the exact Decision Boundary.

### 9.1 RESEARCH CLOSED

Use `RESEARCH CLOSED` when:

- all closure criteria pass;
- no Category A item remains;
- no Category B uncertainty needs to remain open for ADP development; and
- any Category C topics are independently retained as Future Research.

Effect:

- ADP development may begin for the exact Decision Boundary reviewed.

No other approval, authority, lifecycle, or implementation effect is created.

### 9.2 RESEARCH CLOSED WITH DEFERRED QUESTIONS

Use `RESEARCH CLOSED WITH DEFERRED QUESTIONS` when:

- all closure criteria pass;
- no Category A item remains;
- one or more Category B items remain;
- every Category B item satisfies Acceptable Uncertainty requirements;
- each deferred question has a revisit trigger and latest safe resolution point; and
- Category C topics are independently retained.

Effect:

- ADP development may begin, and the deferred-question record becomes a required input to that ADP.

Deferral does not imply resolution, acceptance of risk outside the recorded bound, or permission to omit the question from later decision evidence.

### 9.3 ADDITIONAL RESEARCH REQUIRED

Use `ADDITIONAL RESEARCH REQUIRED` when any of the following is true:

- a Category A item that satisfies the complete Materiality Test remains unresolved;
- the Decision Boundary is materially ambiguous or unstable;
- a materially distinct and plausible architecture family is omitted and passes the Category A Materiality Test;
- a critical assumption lacks sufficient evidence;
- remaining uncertainty is unbounded;
- a Category B classification cannot be justified;
- an authority, confidentiality, safety, external-obligation, temporal, audit, or historical issue has a demonstrated architecture-changing effect that cannot be contained;
- an independent review finding is normalized into a research question and demonstrates a Category A material effect;
- the closure evidence cannot be reproduced; or
- decision-maker eligibility cannot be established.

Effect:

- ADP development is not authorized by this closure process.

The outcome identifies the bounded research required. It does not require investigation of unrelated Category C topics.

## 10. Preventing Perpetual Research Expansion

Architectural rigor does not require unrestricted topic expansion.

### 10.1 New-Topic Admissibility

A newly proposed research topic enters the current closure gate only when:

- it is inside the recorded Decision Boundary, or attributable evidence demonstrates that the boundary is materially incomplete;
- it is stated as a bounded Research Question;
- its proponent identifies the exact architectural claim affected; and
- if Category A is proposed, the complete Materiality Test and burden of proof are satisfied.

An inadmissible topic becomes Category C or a separately scoped research effort. It cannot delay closure merely by being raised.

### 10.2 Duplicate-Question Control

Questions that test the same architectural claim, uncertainty, and plausible alternatives are consolidated under one inventory identity. Restatement with different terminology, source framing, risk label, or reviewer wording does not create a new blocker.

Additional evidence may be attached to the existing question. A separate question is warranted only when it affects a distinct architectural element or presents a materially distinct plausible architecture family.

### 10.3 Domain-Boundary Control

A question belonging primarily to a contract, domain rule, implementation choice, operating procedure, migration plan, or different architecture domain does not enter the current Category A set unless evidence shows that deferral would materially change an enumerated Category A architectural element.

The current research records the handoff, owner or future decision forum, containment, and reopening trigger as Category B, or retains the topic as Category C. Domain separation cannot be used to hide a missing architecture boundary.

### 10.4 Review-Finding Normalization

A review finding is input evidence, not a research category. Before it can affect closure, it is normalized into:

- a bounded Research Question;
- the exact architecture element affected;
- materially plausible alternatives;
- evidence and contrary evidence; and
- a proposed classification under Section 6.

Reviewer severity, repetition, title, or status creates no presumption of Category A.

### 10.5 Evidence Saturation

More research is not required merely because more sources could be consulted. Additional evidence is necessary when it could materially change a Category A resolution, a critical assumption, an alternative comparison, or the boundedness of remaining uncertainty.

Evidence is saturated for the current question when:

- representative source types within the Decision Boundary have been considered;
- material contrary evidence has been addressed;
- new evidence is more likely to repeat, refine, specialize, or extend the current analysis than to reveal a materially distinct plausible architecture family; and
- no demonstrated Category A completion criterion remains unmet.

The possibility of discovering more information does not defeat saturation.

### 10.6 Reopening Threshold

Closure is evaluated against an exact research revision and inventory snapshot. A closed research effort is reopened only when new attributable evidence:

- invalidates a critical assumption used by the ADP direction;
- identifies an omitted, materially distinct, and plausible architecture family;
- demonstrates that Category B containment cannot preserve a mandatory invariant or fail-closed behavior;
- establishes that the recorded Decision Boundary excluded a presently applicable architectural obligation; or
- otherwise satisfies the complete Category A Materiality Test against the closed boundary.

Preference changes, additional examples, new implementations, new terminology, duplicate review findings, or evidence that only refines the selected family do not meet the reopening threshold.

A material topic outside the closed boundary may receive its own research identity, scope, inventory, review, and closure decision without reopening the earlier research.

## 11. Reopening Conditions

Research previously closed under this methodology may be reopened only when the Section 10.6 threshold is met. Qualifying evidence may show that:

- new evidence invalidates a critical assumption;
- an omitted, materially distinct, and plausible architecture family is shown to be capable of replacing or invalidating the architecture;
- applicable higher governance changes the Decision Boundary;
- an external obligation materially changes or is newly established for the scope and changes an enumerated Category A architectural element;
- a deferred Category B item now satisfies the Category A Materiality Test;
- the ADP reveals that a foundational decision lacks research support;
- source, authority, confidentiality, temporal, or scope evidence used for closure is invalidated in a way that changes architectural validity;
- the closure decision was based on materially incomplete or misrepresented evidence; or
- cross-repository or product expansion changes the architecture rather than merely extending it.

Research is not reopened merely because:

- a new implementation technology appears;
- a different vendor becomes available;
- an optimization is proposed;
- additional examples are found;
- a prior question is restated;
- a new review assigns a different severity without new material evidence;
- a Category C topic becomes interesting; or
- a later reviewer prefers a different architecture without new material evidence.

The party proposing reopening bears the same burden of proof required for Category A. The reopening decision identifies the affected earlier closure evidence and preserves the original record. It does not edit the earlier decision.

## 12. Roles and Separation of Responsibilities

This methodology describes functions, not company roles or authority assignments.

| Function | Responsibility | Authority boundary |
| --- | --- | --- |
| Research author | Defines questions, investigates alternatives, records evidence, classifies provisionally, and recommends an outcome. | Cannot close their own research merely by recommendation or authorship. |
| Independent research reviewer | Tests completeness, neutrality, assumptions, classifications, risks, and readiness. | Review evidence does not close research or approve architecture. |
| Human closure decision authority | Makes the attributable research-closure decision when independently eligible. | May authorize only the transition to ADP development within the reviewed boundary. |
| ADP author | Uses closed research, deferred questions, and evidence to prepare a decision proposal. | Cannot treat research closure as architecture approval. |
| AI system | May draft, analyze, compare, trace, and identify gaps. | Cannot create closure authority, approve research, approve architecture, or infer human consent. |

Where one human performs more than one function, applicable authority, independence, separation-of-duty, and conflict requirements remain independently controlling. This methodology does not permit role composition that applicable governance prohibits.

## 13. Relationship to Other CADP Governance

### 13.1 Foundation Architecture

Foundation retains architectural supremacy, authority hierarchy, confidentiality, canonical-source, lifecycle, immutable-history, and fail-closed boundaries.

This methodology does not amend Foundation or determine that Foundation itself is Approved or Effective.

### 13.2 Governance Document Model

The Governance Document Model retains ownership of document-class relationships. Research, reviews, closure evidence, and future ADPs remain distinct artifacts with distinct authority boundaries.

### 13.3 Canonical Artifact Contract

The [Canonical Artifact Contract](../contracts/CANONICAL_ARTIFACT_CONTRACT.md) retains stable identity, exact revision, canonical source, lineage, and integrity semantics.

This methodology consumes those semantics for research and closure evidence.

### 13.4 Authority and Delegation Contract

The [Authority and Delegation Contract](../contracts/AUTHORITY_AND_DELEGATION_CONTRACT.md) retains human eligibility, authority source, scope, operation, interval, delegation, revocation, and non-delegable-boundary semantics.

This methodology creates no closure role or authority merely by naming a function.

### 13.5 Policy Decision Contract

The [Policy Decision Contract](../contracts/POLICY_DECISION_CONTRACT.md) retains `Allow`, `Deny`, `Indeterminate`, and `Not Applicable`.

The three research-closure outcomes are methodology outcomes, not Policy Decision outcomes. They do not replace or reinterpret policy evaluation.

### 13.6 Governance Lifecycle and Approval

The [Governance Lifecycle Contract](../contracts/GOVERNANCE_LIFECYCLE_CONTRACT.md) and [Approval Record Contract](../contracts/APPROVAL_RECORD_CONTRACT.md) retain lifecycle and approval semantics.

Research Closure is not Approved, Effective, Adopted, Superseded, Archived, Retired, or Design Frozen. A future closure record may provide evidence for one bounded research-to-ADP transition, but it does not create artifact approval.

### 13.7 Design Freeze

The [Design Freeze Contract](../contracts/DESIGN_FREEZE_CONTRACT.md) retains all freeze semantics.

Research Closure does not create, imply, expand, renew, lift, or supersede a Design Freeze.

## 14. Minimum Closure Evidence

A reusable Research Closure evidence set includes:

- research identity and exact revision;
- Decision Boundary;
- research inventory;
- alternatives and exclusions;
- assumptions and supporting evidence;
- findings and risks;
- Category A, B, and C classifications with their supporting evidence;
- complete answers to the seven-question Materiality Test for every proposed Category A item;
- the assumption, current risk, containment mechanism, future owner or decision forum, and reopening trigger for every Category B item;
- remaining uncertainty assessment;
- architectural-impact assessment;
- representative-architecture-family assessment;
- evidence-saturation assessment;
- independent review identity and revision;
- research-author recommendation;
- human closure decision identity and independently valid authority reference;
- decision timestamp and rationale;
- permitted outcome;
- deferred questions and latest safe resolution points;
- Future Research references;
- reopening conditions;
- integrity evidence; and
- lineage to later ADPs.

Missing required evidence prevents a valid closure determination. It does not default to `RESEARCH CLOSED` or `RESEARCH CLOSED WITH DEFERRED QUESTIONS`.

This list defines methodology evidence categories only. It does not create a schema, registry, workflow, approval record, or implementation format.

## 15. Methodology Invariants

1. Research Closure is not architecture approval.
2. Research Closure is not implementation approval.
3. Research Closure is bound to an exact Decision Boundary and research revision.
4. Category A exists only when the complete Materiality Test and burden of proof are satisfied.
5. No unresolved, demonstrated Category A item may pass into ADP development as a deferred question.
6. Importance, uncertainty, risk severity, reviewer identification, or the possibility of more research does not independently create Category A.
7. Category B is controlled deferral and cannot conceal a question capable of invalidating the architecture.
8. Every Category B item records an assumption, current risk, containment mechanism, future owner or decision forum, and reopening trigger.
9. Category C cannot block closure merely because it remains interesting.
10. Research scope cannot expand without demonstrated architectural relevance to the Decision Boundary.
11. Only omission of a materially distinct and plausible architecture family can support Category A on alternative-coverage grounds.
12. A review verdict or severity does not close research or determine a research classification.
13. AI cannot make the closure decision.
14. A Git commit, merge, tag, branch, or publication does not close research.
15. Research Closure creates no approval, lifecycle state, authority tier, Product Binding, or Design Freeze.
16. Missing evidence cannot default to closure.
17. Fail-closed containment cannot conceal a missing architecture boundary.
18. Closure and reopening preserve immutable history.
19. Methodology revisions do not silently rewrite earlier closure records.
20. Future ADP, contract, implementation, adoption, effectiveness, and freeze decisions remain independently governed.

## 16. Methodology Outcome

This document establishes no current Research Closure outcome for any CADP research effort.

In particular, this revision does not close, approve, reject, or reclassify the Governance Rule Discovery research. The existing [Governance Rule Discovery Research Closure](GOVERNANCE_RULE_DISCOVERY_RESEARCH_CLOSURE.md) remains an immutable historical decision made under the earlier methodology. It is neither converted into a decision under Version 0.2.0 nor invalidated by this correction.

Any reassessment of that research under Version 0.2.0 requires a new, attributable closure process and a new decision record that references rather than rewrites the earlier record.

The creation and commit of this Draft methodology are document-existence events only. They do not make the methodology Approved, Effective, Adopted, or Design Frozen.

## 17. Revision History

| Version | Revision purpose | Governance effect |
| --- | --- | --- |
| 0.1.0 | Established the initial research-closure categories, process, outcomes, and evidence expectations. | Draft methodology only; no approval or closure outcome created by the methodology document. |
| 0.2.0 | Corrected overly broad Category A behavior observed during the first application by introducing a falsifiable materiality threshold, burden of proof, controlled Category B deferral, representative-alternative distinctions, evidence saturation, and anti-expansion controls. | Prospective methodology correction only; no existing research is reclassified and no earlier closure record is changed. |
