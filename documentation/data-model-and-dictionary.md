# GRC Data Model and Dictionary

## 1. Purpose

This document defines the logical data model, controlled vocabularies, entity relationships, and data integrity requirements for the Enterprise Banking GRC Assessment.

The model supports evidence-based assessment of the simulated `banking.lab` environment.

It establishes a consistent structure for recording:

- Assets
- Existing controls
- Supporting evidence
- Framework assessments
- Consolidated findings
- Security risks
- Risk treatments

The model is designed for relational implementation in Notion and controlled publication through GitHub.

## 2. Architectural Principles

The GRC information architecture follows these principles:

1. Maintain one authoritative working record per entity.
2. Assign stable, unique identifiers to all records.
3. Preserve relationships between assessments and evidence.
4. Distinguish implemented controls from proposed controls.
5. Maintain framework-specific assessment ratings.
6. Separate factual findings from risk scenarios.
7. Avoid duplicating findings across multiple frameworks.
8. Preserve historical evidence and assessment context.
9. Use controlled vocabularies where appropriate.
10. Publish approved assessment snapshots to GitHub.

Notion is the live working assessment environment.

GitHub contains the approved, version-controlled assessment records and published deliverables.

The two environments must be reconciled before formal assessment publication and project closure.

## 3. Entity Architecture

### 3.1 Core Entities

| Prefix | Entity | Primary Purpose |
| --- | --- | --- |
| AST | Asset | Define assessed technology and information assets |
| CTL | Control | Document existing security controls |
| EVD | Evidence | Record verifiable supporting evidence |
| FND | Finding | Document factual assessment observations |
| RSK | Risk | Evaluate credible security risk scenarios |
| TRT | Treatment | Document risk treatment recommendations |

### 3.2 Framework Assessment Entity

| Prefix | Entity | Primary Purpose |
| --- | --- | --- |
| FAS | Framework Assessment | Record framework-specific evaluations |

Framework Assessment records represent applicable assessment units within the adopted framework baseline.

Examples include:

- APRA CPS 234 requirement assessments
- ASD Essentials action-domain assessments
- ISO/IEC 27001:2022 supporting alignment assessments

The same framework record must not be duplicated merely because it relates to several controls or assets.

## 4. Identifier Convention

Each entity uses a unique, persistent identifier.

| Entity | Example |
| --- | --- |
| Asset | AST-001 |
| Control | CTL-001 |
| Evidence | EVD-001 |
| Framework Assessment | FAS-001 |
| Finding | FND-001 |
| Risk | RSK-001 |
| Treatment | TRT-001 |

Identifiers must not be reused after records are retired, superseded, or deleted.

Identifiers must remain consistent between Notion and published GitHub assessment snapshots.

Official framework identifiers are recorded separately from internal FAS identifiers.

## 5. Asset Register

### 5.1 Purpose

The Asset Register identifies the technology, identity, information, and service assets within the approved assessment boundary.

### 5.2 Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Asset ID | Text | Unique AST identifier |
| Asset Name | Title | Recognisable asset name |
| Asset Type | Select | Controlled asset category |
| Description | Text | Technical or business function |
| Assessment Domain | Multi-select | Internal DOM-01 to DOM-10 |
| Owner Role | Text | Proposed or evidenced accountable role |
| Custodian Role | Text | Technical operating responsibility |
| Confidentiality | Select | CIA confidentiality classification |
| Integrity | Select | CIA integrity classification |
| Availability | Select | CIA availability classification |
| Criticality | Select | Overall asset criticality |
| Depends On | Relation | Assets on which this asset depends |
| Depended On By | Relation | Assets dependent on this asset |
| Controls | Relation | Related CTL records |
| Evidence | Relation | Related EVD records |
| Framework Assessments | Relation | Related FAS records |
| Scope Status | Select | Assessment boundary status |
| Classification Rationale | Text | Supporting classification reasoning |
| Evidence Limitations | Text | Material assurance limitations |

### 5.3 Asset Categories

Use the following categories where applicable:

- Infrastructure
- Operating System
- Application
- Identity
- Credential
- Data
- Technology Service

Categories should support the ASD Essentials enterprise IT asset-scoping methodology.

Logical assets may be recorded separately from physical or virtual systems where justified.

Unimplemented applications, services, or infrastructure must not be represented as existing assets.

## 6. Control Register

### 6.1 Purpose

The Control Register documents security controls implemented or evidenced within the assessment scope.

### 6.2 Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Control ID | Text | Unique CTL identifier |
| Control Name | Title | Control description |
| Security Objective | Text | Intended security outcome |
| Control Type | Select | Preventive, Detective, Corrective |
| Implementation Status | Select | Current implementation classification |
| Effectiveness | Select | Assessed control effectiveness |
| Assets | Relation | Protected or affected AST records |
| Evidence | Relation | Supporting EVD records |
| Framework Assessments | Relation | Related FAS records |
| Control Owner Role | Text | Accountable role |
| Technical Limitations | Text | Known gaps and restrictions |
| Assessment Rationale | Text | Basis for effectiveness conclusion |

### 6.3 Control Types

- Preventive
- Detective
- Corrective

Where a control performs multiple functions, the primary function must be identified and additional functions documented.

### 6.4 Implementation Status

- Implemented
- Partially Implemented
- Not Implemented
- Not Assessed

Control records primarily describe actual implemented or partially implemented measures.

Missing expected controls may be documented through framework assessments and findings.

A placeholder control record must not be created for every missing framework requirement.

### 6.5 Control Effectiveness

- Effective
- Partially Effective
- Ineffective
- Not Assessed

Control implementation and effectiveness must remain separate properties.

These categories are internal control-level ratings and are not ASD action ratings.

## 7. Evidence Register

### 7.1 Purpose

The Evidence Register maintains traceability between technical observations, supporting documentation, and assessment conclusions.

### 7.2 Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Evidence ID | Text | Unique EVD identifier |
| Evidence Title | Title | Descriptive evidence title |
| Evidence Type | Select | Evidence classification |
| Source Repository | Text | Authoritative source repository |
| Source Path | Text | Repository-relative file path |
| Source Revision | Text | Git commit or relevant version |
| Capture Date | Date | Actual evidence acquisition date |
| Evidence Description | Text | What the evidence demonstrates |
| Assets | Relation | Related AST records |
| Controls | Relation | Related CTL records |
| Framework Assessments | Relation | Related FAS records |
| Evidence Limitations | Text | Boundaries of the observation |
| Verification Status | Select | Evidence verification state |

### 7.3 Evidence Types

- Configuration Output
- Validation Result
- Screenshot
- Technical Test
- Implementation Record
- Architecture Documentation
- Policy or Procedure
- Other Supporting Document

### 7.4 Evidence Verification Status

- Pending Verification
- Verified
- Limited
- Rejected

Evidence verification describes whether the evidence source and content have been appropriately checked.

It is not interchangeable with the evidence sufficiency rating assigned to an assessment claim.

### 7.5 Evidence Sufficiency

Evidence sufficiency is evaluated against the relevant control or framework claim.

Approved categories are:

- Strong
- Adequate
- Limited
- None

The same evidence item may support different claims with different levels of sufficiency.

Evidence sufficiency must therefore be recorded within the relevant assessment context.

## 8. Framework Assessment Register

### 8.1 Purpose

The Framework Assessment Register maintains framework-specific assessments without duplicating underlying asset, control, or evidence records.

### 8.2 Common Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Assessment ID | Text | Unique FAS identifier |
| Assessment Title | Title | Assessed requirement or action |
| Framework | Select | CPS 234, ASD Essentials, ISO alignment |
| Framework Baseline | Text | Adopted framework release |
| Official Reference | Text | Official requirement or action identifier |
| Assessment Unit | Select | Requirement, Action-Domain, Alignment |
| Applicability | Select | Applicable, Excluded, Pending Review |
| Applicability Rationale | Text | Scope and applicability decision |
| Assets | Relation | Related AST records |
| Controls | Relation | Related CTL records |
| Evidence | Relation | Related EVD records |
| Findings | Relation | Related FND records |
| Evidence Sufficiency | Select | Evidence sufficiency for the conclusion |
| Assessment Rationale | Text | Basis of the assessment conclusion |
| Assessment Limitations | Text | Material uncertainty or exclusions |
| Assessment Date | Date | Date conclusion was reached |
| Baseline As-Of Date | Date | Technical state being evaluated |

Framework-specific ratings are maintained as separate properties.

### 8.3 APRA CPS 234 Assessment Fields

| Field | Data Type | Description |
| --- | --- | --- |
| CPS 234 Status | Select | Project-defined requirement implementation status |
| CPS 234 Reference | Text | Relevant CPS 234 requirement |
| Prudential Context | Text | Relevant organisational or technical context |

Approved CPS 234 status categories:

- Implemented
- Partially Implemented
- Not Implemented
- Not Assessed
- Not Applicable

These classifications do not constitute an APRA regulatory compliance determination.

### 8.4 ASD Essentials Assessment Fields

| Field | Data Type | Description |
| --- | --- | --- |
| ASD Domain | Select | Official ASD enterprise IT domain |
| ASD Priority Phase | Select | All, Phase 1, Phase 2, Phase 3 |
| ASD Principle Reference | Text | Official principle identifier |
| ASD Action Reference | Text | Official action identifier |
| ASD Effectiveness | Select | Official ASD action rating |
| Coverage | Text | Application across relevant assets |
| Consistency | Text | Consistency of security outcome |
| Currency | Text | Currency of assessment evidence |
| Evidence Quality | Text | Reliability of supporting evidence |
| IGP Rationale | Text | Indicator-based assessment reasoning |

Each applicable ASD action-domain combination is assessed independently.

Official action and principle identifiers must be obtained from the adopted ASD publication or corresponding versioned OSCAL catalogue.

The assessment must not invent official identifiers.

### 8.5 ASD Effectiveness Ratings

- Not Assessed
- Not Effective
- Partially Effective
- Fully Effective

Not Applicable is not an ASD effectiveness rating.

Applicability and scope exclusions are managed through separate assessment fields.

### 8.6 ASD Aggregation

Action ratings support principle-level effectiveness assessments.

Principle results are determined using the official ASD Assessment Process Guide.

Domain reporting is derived from the relevant principle-level results.

Derived principle and domain results must not be treated as independent action assessments.

Reporting must preserve unassessed counts and the underlying assessment detail.

### 8.7 ISO/IEC 27001:2022 Alignment Fields

| Field | Data Type | Description |
| --- | --- | --- |
| ISO Reference | Text | Relevant ISO requirement or Annex A control |
| ISO Alignment | Select | Supporting alignment classification |
| Alignment Rationale | Text | Basis for the mapped observation |

Approved ISO alignment categories:

- Aligned
- Partially Aligned
- Gap
- Not Assessed

ISO alignment is supporting analysis.

It is not a certification audit result or a formal Statement of Applicability.

## 9. Finding Register

### 9.1 Purpose

The Finding Register records consolidated, factual security and assurance observations.

### 9.2 Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Finding ID | Text | Unique FND identifier |
| Finding Title | Title | Concise factual description |
| Observation | Text | Actual observed condition |
| Expected Outcome | Text | Relevant security expectation |
| Assets | Relation | Related AST records |
| Controls | Relation | Related CTL records |
| Evidence | Relation | Supporting EVD records |
| Framework Assessments | Relation | Related FAS records |
| Risks | Relation | Related RSK records |
| Finding Type | Select | Controlled finding classification |
| Finding Status | Select | Current finding lifecycle state |
| Assessment Rationale | Text | Why the finding is supported |

### 9.3 Finding Types

- Control Deficiency
- Implementation Gap
- Effectiveness Gap
- Evidence Limitation
- Governance Gap
- Other Assurance Observation

### 9.4 Finding Status

- Open
- Under Review
- Addressed
- Closed

Finding closure requires supporting verification.

A proposed treatment does not automatically close a finding.

## 10. Risk Register

### 10.1 Purpose

The Risk Register evaluates credible security risk scenarios arising from the assessed environment.

### 10.2 Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Risk ID | Text | Unique RSK identifier |
| Risk Title | Title | Concise risk description |
| Risk Scenario | Text | Threat, condition, and consequence |
| Assets | Relation | Related AST records |
| Findings | Relation | Supporting FND records |
| Existing Controls | Relation | Relevant CTL records |
| Risk Owner Role | Text | Proposed accountable role |
| Inherent Likelihood | Number | Likelihood before controls |
| Inherent Impact | Number | Impact before controls |
| Inherent Score | Formula | Likelihood multiplied by impact |
| Inherent Rating | Formula | Derived risk category |
| Residual Likelihood | Number | Likelihood after existing controls |
| Residual Impact | Number | Impact after existing controls |
| Residual Score | Formula | Residual likelihood multiplied by impact |
| Residual Rating | Formula | Derived residual risk category |
| Assessment Rationale | Text | Scoring justification |
| Treatments | Relation | Related TRT records |
| Risk Status | Select | Current risk lifecycle status |

### 10.3 Likelihood Scale

| Score | Likelihood |
| --- | --- |
| 1 | Rare |
| 2 | Unlikely |
| 3 | Possible |
| 4 | Likely |
| 5 | Almost Certain |

### 10.4 Impact Scale

| Score | Impact |
| --- | --- |
| 1 | Insignificant |
| 2 | Minor |
| 3 | Moderate |
| 4 | Major |
| 5 | Severe |

### 10.5 Risk Bands

| Score | Rating |
| --- | --- |
| 1–4 | Low |
| 5–9 | Moderate |
| 10–16 | High |
| 17–25 | Critical |

The risk matrix is project-defined.

It is not an official APRA, ASD, or ISO rating scale.

### 10.6 Risk Status

- Open
- Under Review
- Treatment Proposed
- Treatment In Progress
- Accepted
- Closed

Formal risk acceptance requires an identifiable, authorised decision.

A simulated recommendation for acceptance must not be represented as actual executive approval.

### 10.7 Risk Scoring Integrity

Inherent risk excludes the benefit of existing security controls.

Residual risk considers only controls with defensible implementation and effectiveness evidence.

Proposed controls do not reduce current residual risk.

An anticipated post-treatment rating may be recorded separately as a forecast, subject to later validation.

## 11. Treatment Register

### 11.1 Purpose

The Treatment Register documents recommended responses to assessed security risks.

### 11.2 Required Fields

| Field | Data Type | Description |
| --- | --- | --- |
| Treatment ID | Text | Unique TRT identifier |
| Treatment Title | Title | Recommended treatment |
| Treatment Description | Text | Proposed action |
| Risks | Relation | Related RSK records |
| Findings | Relation | Related FND records |
| Treatment Type | Select | Risk treatment strategy |
| Priority | Select | Treatment priority |
| Owner Role | Text | Proposed accountable role |
| Target Date | Date | Proposed completion date |
| Expected Outcome | Text | Intended security improvement |
| Expected Residual Risk | Text | Forecast risk effect and assumptions |
| Validation Requirements | Text | Evidence needed to verify success |
| Treatment Status | Select | Treatment lifecycle status |

### 11.3 Treatment Types

- Mitigate
- Avoid
- Transfer
- Accept

### 11.4 Treatment Priorities

- P1 — Immediate
- P2 — High
- P3 — Medium
- P4 — Low

Treatment priority and residual risk are distinct classifications.

### 11.5 Treatment Status

- Proposed
- Under Review
- Approved
- In Progress
- Implemented
- Verified
- Deferred
- Rejected

Approval and implementation must not be claimed without supporting evidence.

## 12. Internal Assessment Domains

Project 3 uses ten internal GRC assessment domains.

| ID | Internal Assessment Domain |
| --- | --- |
| DOM-01 | Governance & Information Security Management |
| DOM-02 | Asset Management & Classification |
| DOM-03 | Identity & Access Management |
| DOM-04 | Privileged Access & Administrative Tiering |
| DOM-05 | Infrastructure & Network Security |
| DOM-06 | Endpoint & System Hardening |
| DOM-07 | Vulnerability, Patch & Configuration Management |
| DOM-08 | Logging, Monitoring & Detection |
| DOM-09 | Backup, Recovery & Resilience |
| DOM-10 | Incident Response & Security Assurance |

These are internal assessment classifications.

They must not be represented as official ASD Essentials domains.

Mappings may be many-to-many.

## 13. ASD Essentials Domain Structure

The official enterprise IT framework contains eight domains.

### 13.1 Capability Domains

The following apply across all priority phases:

- Governance and culture
- Visibility and response

### 13.2 Priority Phase 1

- Boundary services
- Identity services

### 13.3 Priority Phase 2

- Critical processes and services
- Privileged environments

### 13.4 Priority Phase 3

- Business systems
- User devices

Priority phases represent recommended implementation sequencing.

They do not represent maturity levels, effectiveness ratings, or compliance status.

## 14. Relationship Requirements

### 14.1 Asset Relationships

An asset may relate to multiple controls, evidence items, framework assessments, findings, and risks.

Assets may also depend on other assets.

### 14.2 Control Relationships

A control may protect several assets and support multiple framework assessments.

Controls may have multiple supporting evidence records.

### 14.3 Evidence Relationships

An evidence record may support several controls, assets, and assessment conclusions.

Evidence limitations must remain visible.

### 14.4 Framework Relationships

A framework assessment may reference multiple assets, controls, and evidence items.

Several framework assessments may relate to the same consolidated finding.

### 14.5 Finding Relationships

A finding may support one or more risks.

A finding does not require a separate risk record unless a credible risk scenario has been established.

### 14.6 Risk Relationships

A risk may arise from several findings.

A risk may be affected by several existing controls.

### 14.7 Treatment Relationships

A treatment may address several related risks or findings.

A recommended control remains a proposal until implementation is independently evidenced.

## 15. Notion Workspace Architecture

The Enterprise Banking GRC Assessment operates as a dedicated project page within the personal Notion workspace.

### 15.1 Implemented Page Structure

- Enterprise Banking GRC Assessment
  - Assessment Overview
  - GRC Registers
  - Framework Assessments
  - Executive Dashboard
  - Assessment Administration
  - Quality Assurance & Validation

The workspace contains seven relational databases:

1. Asset Register
2. Control Register
3. Evidence Register
4. Framework Assessment Register
5. Finding Register
6. Risk Register
7. Treatment Register

The Framework Assessment Register is maintained as one authoritative database, not three separate framework datasets.

### 15.2 Verified Relational Architecture

The implemented schema contains 16 bidirectional relation pairs across the seven databases, including the Asset Register's self-referential dependency relationship.

Relational verification identifier:
S1-05B — Notion Relational Integrity QA

Verification date: 22 October 2026

Verification result: 16/16 PASS

Validation method:
Manual relationship testing using temporary synthetic QA-TEMP records, including reciprocal-property verification.

Cleanup:
All temporary QA-TEMP records were removed after validation.

The complete relationship inventory is documented in:

- diagrams/grc-notion-architecture-01-relation-inventory.png
- diagrams/grc-notion-architecture-02-register-boundaries.png

The editable architecture source is:

- diagrams/enterprise-banking-grc-notion-relational-architecture.drawio

This validation establishes relational schema integrity only. It does not verify future framework ratings, risk calculations, operational control effectiveness, or compliance conclusions.

### 15.3 Implemented Framework Assessment Views

The Framework Assessment Register contains four views:

- Master Assessment Register — no framework filter
- APRA CPS 234 Assessment — framework-specific filter
- ASD Essentials — Enterprise IT — framework-specific filter
- ISO/IEC 27001:2022 Alignment — framework-specific filter

All four views reference the same underlying database.

Additional domain, assessment-status, or evidence-sufficiency views may be configured as required during later stages.

### 15.4 Executive Reporting

The original Project 3 Executive Dashboard has been structurally configured and internally reviewed.

It contains linked reporting views referencing the authoritative Framework Assessment, Finding, Risk, and Treatment Registers.

The dashboard currently provides assessment governance, reporting definitions, and controlled access to the operational reporting sources. Operational framework assessments, findings, risks, and treatments have not yet been populated.

The Risk Register's unfiltered dashboard view has undergone supplementary data-propagation testing. Other end-to-end reporting checks remain subject to their applicable future quality gates.

Executive indicators, distributions, rankings, and visualisations must be derived from validated assessment records. No assessment metric may be populated from fabricated or unassessed data.

## 16. GitHub Publication Model

GitHub contains approved, version-controlled assessment snapshots and documentation.

The six core GRC registers may be published as CSV exports.

The ASD action assessment records may be published through a dedicated version-controlled CSV export.

CPS 234 and ISO alignment results may be published through framework-specific assessment documents.

All published outputs must remain reconcilable with the approved Notion data.

GitHub publication must identify the assessment baseline and export date.

## 17. Data Integrity Rules

The following rules are mandatory:

1. Each record must have a unique identifier.
2. Identifiers must not be reassigned.
3. Framework-specific ratings must remain separate.
4. Evidence sources must be traceable.
5. Material relationships must be documented.
6. Risk formulas must follow the approved matrix.
7. Proposed controls must not count as implemented.
8. Framework gaps must not automatically create risks.
9. Duplicate findings must be consolidated.
10. Missing evidence must not imply effectiveness.
11. Historical evidence must retain its context.
12. Published results must reconcile with source records.

## 18. Data Model Maintenance

Changes to database structures, relationships, and controlled vocabularies require assessment of their impact on existing records, formulas, and reporting.

Schema changes must not silently modify completed assessment conclusions.

The data model must be validated before Stage 2 register population begins.
