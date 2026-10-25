# Enterprise Banking GRC Assessment

## Project Overview

An evidence-based governance, risk and compliance (GRC) assessment of a simulated Australian enterprise banking environment.

This project evaluates the security architecture, implemented controls, and supporting evidence established through the preceding Secure Enterprise Network Lab and Enterprise Banking IAM Architecture projects.

The assessment focuses on identifying security strengths, control deficiencies, technology risks, and appropriate risk treatment recommendations.

## Assessment Frameworks

| Framework | Assessment Role |
| --- | --- |
| APRA CPS 234 | Primary prudential information security assessment |
| ASD Essentials for enterprise IT | Technical security outcome and control effectiveness assessment |
| ISO/IEC 27001:2022 | Supporting governance and ISMS control alignment |
| APRA CPG 234 | Supporting prudential guidance |
| ASD Information Security Manual | Supporting technical security guidance |

### ASD Essentials Framework Baseline

- **Publisher:** Australian Signals Directorate
- **Framework:** ASD Essentials for enterprise IT
- **Initial release date:** 15 October 2026
- **OSCAL release:** v2026.10.15
- **Assessment methodology:** ASD Essentials Assessment Process Guide

Framework references and updates are governed through the Project 3 Framework Baseline Register.

## Assessment Environment

The assessment covers the existing `banking.lab` environment.

| System | Function |
| --- | --- |
| AU-SYD-DC01 | Active Directory Domain Services and DNS |
| au-syd-siem01 | Linux monitoring and logging foundation |
| AU-SYD-W101 | Domain-joined Windows workstation |
| au-syd-secops01 | Controlled security-testing workstation |

The environment operates on an isolated UTM Host-Only network using the `10.10.10.0/24` subnet.

The environment is isolated but does not implement internal network segmentation.

## Assessment Methodology

The project follows an evidence-first assessment approach:

1. Establish assessment scope and baseline.
2. Identify and classify information and technology assets.
3. Catalogue existing security controls.
4. Register and evaluate supporting evidence.
5. Perform framework-specific assessments.
6. Consolidate findings and identify security risks.
7. Evaluate inherent and residual risk.
8. Develop risk treatment recommendations.
9. Prepare executive reporting and dashboard visualisations.
10. Perform final assurance and project closure.

The assessment maintains traceability between assets, controls, evidence, findings, risks, treatments, and applicable framework requirements.

## Project Scope and Limitations

This project assesses a simulated, non-production environment.

It does not represent an operational APRA-regulated financial institution, a regulatory compliance determination, or an ISO certification audit.

Projects 1 and 2 are treated as completed technical evidence sources.

Existing configurations will not be modified solely to improve assessment outcomes.

## Project Status

### Implementation Progress

| Stage | Description | Status |
| --- | --- | --- |
| 1 | Foundation | In Progress |
| 2 | Asset, Control and Evidence Baseline | Planned |
| 3 | Framework Assessment | Planned |
| 4 | Findings and Risk Assessment | Planned |
| 5 | Treatment and Executive Reporting | Planned |
| 6 | Assurance and Closure | Planned |

## Repository Documentation

### Foundation Documents

- [Assessment Scope and Context](documentation/scope-and-context.md)
- [Framework Baseline Register](documentation/framework-baseline-register.md)
- [Assessment Methodology](documentation/assessment-methodology.md)
- [GRC Data Model and Dictionary](documentation/data-model-and-dictionary.md)

### Architecture Diagrams

- [Notion Relationship Inventory](diagrams/grc-notion-architecture-01-relation-inventory.png)
- [Register Semantics and Assessment Boundaries](diagrams/grc-notion-architecture-02-register-boundaries.png)
- [Editable Draw.io Architecture](diagrams/enterprise-banking-grc-notion-relational-architecture.drawio)

### Notion Foundation Verification

The initial Notion architecture contains seven relational registers and 16 bidirectional relationship pairs.

Relational integrity testing was completed on 22 October 2026:

- Test identifier: S1-05B
- Result: 16/16 PASS
- Temporary QA records: Removed
- Assessment records: Not yet populated

The relational verification result applies to database architecture, not framework compliance, assessment accuracy, or operational control effectiveness.

### Publication Model

Notion maintains the live operational GRC assessment records.

GitHub contains version-controlled methodology, architecture, and approved assessment deliverables.

Published assessment snapshots must be reconciled with the approved Notion records before release.
