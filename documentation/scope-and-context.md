# Assessment Scope and Context

## 1. Purpose

This document establishes the organisational context, technical assessment boundary, assumptions, limitations, and evidence sources for the Enterprise Banking GRC Assessment.

It provides the foundation for evaluating existing security controls against APRA CPS 234, ASD Essentials for enterprise IT, and supporting ISO/IEC 27001:2022 control alignment.

The assessment is evidence-based and limited to the implemented environment and verifiable supporting information.

## 2. Assessment Identification

| Attribute | Description |
| --- | --- |
| Project | Enterprise Banking GRC Assessment |
| Repository | `enterprise-banking-grc-assessment` |
| Environment | `banking.lab` |
| Assessment Type | Simulated enterprise information security GRC assessment |
| Geographic Context | Australia |
| Industry Context | Banking and financial services |
| Design Baseline | v2.0 |
| Foundation Commencement | 19 October 2026 |

The assessment is conducted as an independent portfolio exercise using the technical environment established through Projects 1 and 2.

## 3. Organisational Context

### 3.1 Simulated Organisation

The assessment uses a simulated Australian enterprise banking environment to provide a consistent business and regulatory context for evaluating information security risks.

The scenario reflects security considerations associated with enterprise identity infrastructure, administrative access, technology operations, and information security governance.

APRA CPS 234 is used as the primary prudential assessment lens.

The simulated organisation is not an actual APRA-regulated entity.

### 3.2 Organisational Assumptions

The assessment may use role-based organisational assumptions to support risk ownership, control accountability, and treatment recommendations.

Examples include:

- Head of Cyber Security
- Identity and Access Management
- Infrastructure Operations
- Security Operations
- Technology Risk
- Information Asset Owner

These roles represent proposed accountability structures within the simulated enterprise context.

They do not constitute evidence that corresponding positions, governance committees, approval processes, or management arrangements have been implemented.

Organisational assumptions must remain distinguishable from observed technical controls and verified operational evidence.

## 4. Technical Assessment Boundary

### 4.1 Environment Architecture

The assessment covers the existing `banking.lab` environment implemented using UTM/QEMU virtualisation.

The environment operates on an isolated Host-Only network.

| Attribute | Configuration |
| --- | --- |
| Active Directory Domain | `banking.lab` |
| Network | `10.10.10.0/24` |
| Network Mode | UTM Host-Only |
| Addressing | Static IPv4 |
| Default Gateway | None |
| Internal Network Segmentation | Not Implemented |

Host-Only network isolation must not be represented as internal network segmentation.

The environment does not implement multiple security zones, VLAN-based segmentation, or routed inter-subnet controls.

### 4.2 Systems in Scope

| Hostname | IP Address | Platform | Function |
| --- | --- | --- | --- |
| `AU-SYD-DC01` | `10.10.10.10` | Windows Server 2022 | Active Directory Domain Services and DNS |
| `au-syd-siem01` | `10.10.10.20` | Ubuntu Server 24.04 LTS | Monitoring and logging foundation |
| `AU-SYD-W101` | `10.10.10.30` | Windows 11 Pro | Domain-joined corporate workstation |
| `au-syd-secops01` | `10.10.10.40` | Kali Linux | Controlled security-testing workstation |

The underlying UTM/QEMU platform is considered an enabling infrastructure dependency.

Specific host-platform security controls will be assessed only where relevant evidence is available.

## 5. Source Projects

### 5.1 Project 1 — Secure Enterprise Network Lab

**Repository:** `secure-enterprise-network-lab`

**Status:** Completed and Closed

Project 1 provides evidence relating to:

- Virtual infrastructure architecture
- Host-Only network isolation
- Static IP addressing
- System roles and network configuration
- Active Directory and DNS infrastructure foundation
- Windows workstation domain membership
- Internal connectivity validation

The project provides evidence of a functioning isolated enterprise-style technical environment.

It does not establish internal network segmentation, production network resilience, or comprehensive enterprise network security controls.

### 5.2 Project 2 — Enterprise Banking IAM Architecture

**Repository:** `enterprise-banking-iam-architecture`

**Status:** Completed and Closed

Project 2 provides evidence relating to:

- Active Directory organisational unit architecture
- Role-oriented Global Security Group assignments
- Tier 0, Tier 1, and Tier 2 administrative separation
- Privileged, standard, and service identities
- PowerShell identity provisioning
- Domain password and account lockout controls
- LDAP signing enforcement
- Service-account interactive-logon restrictions
- Selected Tier 0 administrative access restrictions
- Group Policy configuration and effective-state validation
- Independent read-only IAM security assurance

The implemented IAM architecture uses Active Directory Global Security Groups for role-based access control.

AGDLP was not implemented.

The assessment must not claim comprehensive resource-level authorisation, Domain Local permission groups, or universal cross-tier access restrictions.

Project 2's final assurance result was:

- 14 PASS
- 0 FAIL
- 2 WARN
- Overall WARN

The residual RDP observation and aggregate assurance warning must be interpreted according to their documented scope.

## 6. Assessment Framework Scope

### 6.1 APRA CPS 234

CPS 234 is the primary prudential framework.

The assessment evaluates relevant information security requirements against the available technical and organisational evidence.

Requirements dependent on unavailable organisational information must be evaluated with appropriate evidence limitations.

The assessment does not constitute a determination of regulatory compliance.

### 6.2 ASD Essentials for Enterprise IT

ASD Essentials for enterprise IT is the primary technical security-outcome assessment framework.

The adopted initial publication baseline is 15 October 2026.

The adopted OSCAL release identifier is:

`E4EIT v2026.10.15`

The assessment considers the applicable ASD principles, actions, and domains.

The eight official ASD domains are distinct from the Project 3 internal assessment domains.

Assessment scope and action applicability will be determined using the relevant ASD guidance.

### 6.3 ISO/IEC 27001:2022

ISO/IEC 27001:2022 provides supporting governance and information security control alignment.

The assessment does not represent:

- An ISO certification audit
- A complete ISMS implementation assessment
- An independent certification opinion
- A formal Statement of Applicability approved by management

ISO control references are used to support analysis of relevant implemented controls, findings, and risks.

## 7. Assessment Domains

Project 3 maintains ten internal information security assessment domains.

These domains organise assets, controls, evidence, findings, risks, and treatment recommendations.

ASD Essentials uses its own eight-domain structure.

Relationships between the two domain models will be documented through framework-specific assessment mappings.

A Project 3 assessment domain must not be treated as equivalent to an ASD domain without explicit mapping.

## 8. Business Impact and Dependency Context

The assessment identifies the technical services provided by in-scope assets and their operational dependencies.

Confidentiality, integrity, availability, and asset criticality assessments must include documented rationale.

Where actual banking business-impact data is unavailable, impact assessments may use explicitly identified scenario-based assumptions.

The assessment must not fabricate:

- Financial loss estimates
- Customer transaction volumes
- Board-approved risk appetite
- Business continuity tolerances
- Recovery Time Objectives
- Recovery Point Objectives

Such values may only be included where supported by legitimate evidence or clearly labelled scenario assumptions.

## 9. Third-Party and AI Considerations

### 9.1 Third-Party Dependencies

The assessment includes a proportionate review of technology dependencies and applicable supplier security considerations.

Third-party information security requirements will be assessed where the defined environment and supporting evidence permit meaningful conclusions.

External service providers, contracts, and supplier assurance processes must not be invented.

### 9.2 Artificial Intelligence

ASD Essentials includes security outcomes relevant to AI-enabled systems and organisational AI governance.

No dedicated AI workload or autonomous agent implementation has been established within the current `banking.lab` baseline.

Relevant AI governance requirements will be considered according to assessment scope and available evidence.

The project does not conduct a standalone ISO/IEC 42001 assessment.

## 10. Assessment Exclusions

The following are outside the implemented technical baseline being assessed:

- Production banking transaction systems
- Real customer information and payment processing
- AWS cloud infrastructure planned for Project 4
- Microsoft Sentinel implementation planned for Project 5
- Comprehensive production SOC operations
- Unimplemented enterprise business applications
- Hypothetical vendor contracts or outsourced services
- Dedicated industrial control and operational technology
- AI systems not implemented within the assessed environment

These exclusions do not automatically establish that every associated framework requirement is Not Applicable.

Applicability must be justified using the relevant framework's assessment methodology.

## 11. Evidence Sources and Limitations

### 11.1 Existing Evidence

Projects 1 and 2 are the authoritative historical technical evidence sources.

Evidence may include:

- Configuration records
- PowerShell scripts and validation outputs
- Group Policy evidence
- System and architecture screenshots
- Technical test results
- Project documentation

Documentation describing a control is not automatically sufficient to establish its implementation or effectiveness.

### 11.2 Additional Evidence

Where existing evidence is insufficient, Project 3 may request controlled technical evidence acquisition.

Technical evidence requests will normally be read-only and executed through the designated infrastructure execution workspace.

New technical evidence must record its acquisition date, observed configuration state, and any relevant limitations.

No configuration changes or remediation activities are automatically authorised by an evidence request.

### 11.3 Historical Evidence

Historical evidence must retain its original capture context.

Evidence collected after the assessment baseline date cannot automatically establish the state of an earlier configuration.

Any such conclusion requires appropriate supporting evidence and explicit qualification.

## 12. Assessment Baseline and Reference Date

**Technical assessment reference date:** 19 October 2026.

The reference date corresponds to the commencement of Project 3 and establishes the intended historical assessment point for the existing Projects 1 and 2 environment.

The reference date does not independently establish the configuration state of every system on that date.

Framework publication dates, evidence acquisition dates, and GitHub commit dates are recorded separately.

The assessment distinguishes:

- Historical implementation evidence
- Baseline technical configuration
- Subsequent read-only observations
- Future remediation or treatment implementation

Historical evidence must retain its original capture context.

Later observations cannot automatically establish an earlier configuration state without corroborating evidence.

Later remediation must not silently replace the original assessment findings or residual-risk conclusions.

## 13. Assessment Integrity

The following requirements apply throughout Project 3:

1. Only supported technical implementation claims are made.
2. Organisational assumptions remain explicitly identified.
3. Evidence limitations are documented.
4. Assessment ratings follow their respective frameworks.
5. Findings are distinguished from risk scenarios.
6. Risks use the approved Project 3 methodology.
7. Controls are assessed for actual operation and effectiveness.
8. Existing Projects 1 and 2 remain closed evidence sources.
9. Framework updates are managed through change control.
10. The assessment does not claim production banking deployment or regulatory certification.

## 14. Scope Maintenance

Changes to the assessment boundary must be documented and reviewed for their impact on:

- Asset inventory
- Control assessments
- Evidence sufficiency
- Framework applicability
- Findings and risks
- Executive reporting

Scope changes must not be made solely to improve assessment ratings.

The approved scope and supporting evidence must be reconciled before final Project 3 closure.
