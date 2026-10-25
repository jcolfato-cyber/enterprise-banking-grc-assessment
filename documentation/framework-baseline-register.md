# Framework Baseline Register

## 1. Purpose

This register establishes the authoritative regulatory, cybersecurity, and information security framework references used by the Enterprise Banking GRC Assessment.

It documents framework scope, publication versions, assessment roles, source references, and version-control requirements.

The register supports reproducibility, assessment consistency, and traceability when framework guidance changes.

## 2. Assessment Context

**Project:** Enterprise Banking GRC Assessment

**Repository:** enterprise-banking-grc-assessment

**Environment:** banking.lab

**Assessment subject:** Simulated Australian enterprise banking environment.

**Project design baseline:** v2.0

**Foundation commencement:** 19 October 2026

The assessment evaluates the existing technical environment, security controls, and supporting evidence established through Projects 1 and 2 of the Enterprise Banking Cybersecurity Portfolio.

The environment is simulated and non-production.

Framework alignment does not constitute regulatory compliance certification, an independent audit opinion, or evidence of an operational APRA-regulated banking institution.

### Baseline Provenance

- Project design baseline adoption: 19 October 2026
- Technical assessment cut-off: Proposed 19 October 2026; subject to confirmation
- Official framework reference check: 24 October 2026
- ASD Essentials enterprise IT initial release: 15 October 2026
- Adopted ASD OSCAL identifier: E4EIT v2026.10.15

The project design baseline, framework publication dates, technical assessment cut-off, and evidence acquisition dates are separate records.

A framework reference check does not establish that a technical configuration was unchanged on the assessment cut-off date.

## 3. Framework Hierarchy

| Reference ID | Framework | Assessment Role |
| --- | --- | --- |
| FW-001 | APRA CPS 234 | Primary prudential assessment |
| FW-002 | ASD Essentials for enterprise IT | Technical security effectiveness |
| FW-003 | ISO/IEC 27001:2022 | Supporting ISMS/control alignment |
| FW-004 | APRA CPG 234 | Prudential implementation guidance |
| FW-005 | ASD Information Security Manual | Supporting technical guidance |
| FW-006 | Essential Eight Maturity Model | Historical/transition reference |
| FW-007 | APRA CPS 230 | Contextual operational risk reference |

Frameworks have distinct purposes and assessment methodologies.

Their results must not be combined into a single compliance, maturity, or security effectiveness score.

## 4. Authoritative Framework Baselines

### FW-001 — APRA CPS 234

- **Title:** CPS 234 Information Security
- **Publisher:** Australian Prudential Regulation Authority
- **In-force date:** 1 July 2019
- **Assessment role:** Primary prudential framework
- **Baseline status:** Adopted

The assessment considers relevant CPS 234 requirements within the defined simulated banking context.

CPS 234 requirements concerning organisational governance, third-party management, and operational processes must not be treated as technically implemented without supporting evidence.

**Official source:**

<https://www.apra.gov.au/standards/cps-234>

### FW-002 — ASD Essentials for enterprise IT

- **Framework:** ASD Essentials
- **Chapter:** ASD Essentials for enterprise IT
- **Publisher:** Australian Signals Directorate
- **Initial framework release:** 15 October 2026
- **Adopted publication baseline:** 15 October 2026
- **OSCAL release identifier:** E4EIT v2026.10.15
- **Assessment role:** Technical security outcome assessment
- **Baseline status:** Adopted

The adopted OSCAL release is based on the 15 October 2026 Assessment Evidence Guide for Enterprise IT.

The OSCAL release identifier is recorded separately from the publication date to avoid treating them as interchangeable version identifiers.

Assessment results use ASD's official effectiveness ratings:

- Not Assessed
- Not Effective
- Partially Effective
- Fully Effective

The framework is assessed at the applicable action-domain level, with principle and domain reporting derived according to ASD's published assessment methodology.

ASD implementation priority phases must not be interpreted as maturity levels or effectiveness ratings.

**Official sources:**

Framework chapter:

<https://www.cyber.gov.au/publication/essentials-for-enterprise-it>

OSCAL release:

<https://www.cyber.gov.au/e4eit/oscal/v2026.10.15>

Assessment process:

<https://www.cyber.gov.au/publication/assessment-process-guide>

### FW-003 — ISO/IEC 27001:2022

- **Title:** Information security management systems — Requirements
- **Publisher:** ISO/IEC
- **Edition:** Third edition
- **Publication:** October 2022
- **Amendment:** ISO/IEC 27001:2022/Amd 1:2024
- **Assessment role:** Supporting governance and ISMS alignment
- **Baseline status:** Adopted

ISO/IEC 27001:2022 provides supporting alignment for relevant information security controls and governance observations.

Project 3 does not conduct an ISO certification audit.

Alignment findings must not be represented as formal certification decisions or comprehensive ISMS conformity claims.

**Official sources:**

<https://www.iso.org/standard/27001>

<https://www.iso.org/standard/88435.html>

### FW-004 — APRA CPG 234

- **Title:** CPG 234 Information Security
- **Publisher:** Australian Prudential Regulation Authority
- **Edition:** June 2019
- **Assessment role:** Supporting CPS 234 interpretation
- **Baseline status:** Adopted

CPG 234 provides APRA's guidance on sound information security practices.

It does not independently create enforceable prudential requirements.

**Official source:**

<https://www.apra.gov.au/practice-guides/cpg-234>

### FW-005 — ASD Information Security Manual

- **Title:** Australian Government Information Security Manual
- **Publisher:** Australian Signals Directorate
- **Assessment role:** Supporting technical control guidance
- **Baseline status:** Reference framework
- **Specific edition:** To be recorded when first applied

The ISM provides technical security principles and controls that may support ASD Essentials assessment conclusions.

The precise ISM release must be identified when referenced in a formal assessment.

**Official source:**

<https://www.cyber.gov.au/resources-business-and-government/essential-cyber-security/ism>

### FW-006 — Essential Eight Maturity Model

- **Publisher:** Australian Signals Directorate
- **Assessment role:** Historical and transition reference
- **Baseline status:** Supporting reference only
- **Specific edition:** To be recorded if formally referenced

The Essential Eight Maturity Model is not the primary technical assessment framework for Project 3.

Historical maturity levels must not be converted directly into ASD Essentials effectiveness ratings.

**Official source:**

<https://www.cyber.gov.au/resources-business-and-government/essential-cyber-security/essential-eight>

### FW-007 — APRA CPS 230

- **Title:** CPS 230 Operational Risk Management
- **Publisher:** Australian Prudential Regulation Authority
- **In-force date:** 1 July 2026
- **Assessment role:** Contextual operational risk reference
- **Baseline status:** Contextual only

CPS 230 may inform discussion of operational resilience, material service providers, and third-party dependencies.

Project 3 does not conduct a comprehensive CPS 230 assessment.

**Official source:**

<https://www.apra.gov.au/standards/cps-230>

## 5. Framework Version-Control Policy

Each assessment must identify the framework baseline against which its conclusions were developed.

The following information must be maintained:

- Framework name and issuing authority
- Official publication or effective date
- Edition, version, or release identifier
- Authoritative source reference
- Project adoption date
- Assessment baseline date
- Relevant amendments or revisions
- Change impact and reassessment decision

### 5.1 Change Detection

Framework updates must be identified through official publisher sources.

News articles, secondary summaries, and social media posts may inform monitoring but do not replace authoritative releases.

### 5.2 Change Classification

#### Editorial change

A clarification or correction that does not materially change assessment requirements or expected outcomes.

#### Methodological change

A revision affecting assessment processes, ratings, evidence requirements, or reporting rules.

#### Substantive change

A revision affecting applicable requirements, principles, actions, domains, or expected security outcomes.

### 5.3 Change Impact Assessment

When a framework revision is identified:

1. Record the new publication and version.
2. Compare it against the adopted baseline.
3. Identify affected requirements and assessments.
4. Evaluate the impact on existing evidence and conclusions.
5. Determine whether reassessment is necessary.
6. Document the adoption or deferral decision.
7. Preserve the historical assessment baseline.

Framework updates must not silently overwrite completed assessment conclusions.

## 6. Assessment Integrity

Framework assessments must maintain the following principles:

1. Evidence supports conclusions, not the reverse.
2. Implemented controls are distinguished from control statements.
3. Assessment limitations are explicitly documented.
4. Unavailable evidence is not treated as proof of implementation.
5. Project-specific risk scoring remains separate from official framework assessment ratings.
6. The simulated environment is not represented as a production banking institution.
7. Framework changes require documented impact assessment.

## 7. Register Maintenance

This register is maintained under Git version control.

Changes to adopted framework baselines must be reviewed for their impact on assessment methodology, existing findings, risk ratings, and executive reporting.

The register must be reconciled with the assessment methodology before final project closure.
