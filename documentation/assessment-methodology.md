# Assessment Methodology

## 1. Purpose

This document defines the assessment methodology for the Enterprise Banking GRC Assessment.

It establishes the procedures, rating criteria, evidence requirements, risk evaluation rules, and traceability requirements used throughout the project.

The methodology supports consistent assessment of the existing `banking.lab` environment against:

- APRA CPS 234 Information Security
- ASD Essentials for enterprise IT
- ISO/IEC 27001:2022 supporting control alignment

The assessment is evidence-based and does not constitute a regulatory compliance determination or certification audit.

## 2. Assessment Principles

The assessment follows these principles:

1. Conclusions must be supported by relevant evidence.
2. Implemented controls must be distinguished from proposed controls and control statements.
3. Control implementation and control effectiveness must be assessed separately.
4. Assessment limitations must be explicitly documented.
5. Organisational assumptions must not be presented as verified operational evidence.
6. Findings must remain distinct from risk scenarios.
7. Framework assessments must use their respective rating criteria.
8. Risk evaluation must follow the approved project-defined methodology.
9. Existing evidence must be reviewed before new evidence acquisition is requested.
10. Assessment findings must not trigger automatic remediation.

## 3. Assessment Lifecycle

The assessment follows ten sequential activities:

1. Establish assessment scope and baseline.
2. Identify and classify assets.
3. Catalogue existing security controls.
4. Register and evaluate supporting evidence.
5. Conduct framework-specific assessments.
6. Consolidate assessment findings.
7. Identify and evaluate security risks.
8. Develop risk treatment recommendations.
9. Prepare executive reporting and visualisations.
10. Perform assurance and final traceability validation.

The order supports an evidence-first evaluation of the previously implemented environment.

Risk-driven selection of additional controls occurs during risk treatment, after the current-state assessment.

## 4. Assessment Baseline

### 4.1 Technical Baseline

The technical assessment covers the implemented `banking.lab` environment established through Projects 1 and 2.

**Proposed assessment cut-off:** 19 October 2026.

The technical assessment cut-off must be confirmed through baseline reconciliation before operational assessment records are populated.

Existing historical evidence retains its original capture date and implementation context.

### 4.2 Framework Baseline

Framework references must correspond to the versions documented in:

`documentation/framework-baseline-register.md`

The adopted ASD Essentials for enterprise IT baseline is the initial release dated 15 October 2026.

The adopted OSCAL release identifier is:

`E4EIT v2026.10.15`

Subsequent framework revisions require documented change-impact assessment before adoption.

### 4.3 Assessment Scope

The assessment boundary and exclusions are defined in:

`documentation/scope-and-context.md`

Only applicable assets, controls, and security outcomes within the approved assessment boundary may be assessed.

## 5. Asset Assessment Methodology

### 5.1 Asset Identification

Assets are identified using existing infrastructure documentation, configuration records, identity inventories, and technical evidence.

Each asset receives a unique `AST-###` identifier.

Relevant asset information includes:

- Asset name and category
- Description and technical function
- Assessment domain
- Accountable owner role
- Technical custodian role
- Confidentiality requirement
- Integrity requirement
- Availability requirement
- Asset criticality
- Technical and operational dependencies
- Supporting evidence
- Assumptions and limitations

### 5.2 CIA Classification

Confidentiality, integrity, and availability are assessed using the following qualitative levels:

| Level | Interpretation |
| --- | --- |
| Low | Limited adverse consequence |
| Moderate | Material but manageable consequence |
| High | Significant security or operational consequence |

Each classification must include supporting rationale.

### 5.3 Asset Criticality

Asset criticality uses the following classifications:

- Low
- Moderate
- High
- Critical

Criticality must consider the asset's function, dependencies, and consequences of compromise or failure.

CIA classifications inform criticality but do not automatically determine it.

### 5.4 Business Impact and Dependencies

A proportionate business-impact and dependency review supports asset classification and risk analysis.

The review identifies:

- Services supported by an asset
- Technical dependencies
- Potential confidentiality consequences
- Potential integrity consequences
- Potential availability consequences
- Single points of failure where evidenced
- Assumptions affecting impact assessment

Business-impact conclusions must not rely on fabricated banking operations, financial losses, or recovery targets.

Scenario-based assumptions must be clearly identified.

## 6. Control Assessment Methodology

### 6.1 Control Identification

Existing security controls are identified from implemented Projects 1 and 2 configurations and supporting evidence.

Each control receives a unique `CTL-###` identifier.

A framework requirement or generic control statement does not establish that a control has been implemented.

### 6.2 Implementation Status

Control implementation is classified as:

| Status | Definition |
| --- | --- |
| Implemented | Control exists within the defined scope |
| Partially Implemented | Only part of the intended control is implemented |
| Not Implemented | Applicable control is absent |
| Not Assessed | Available information does not support a conclusion |

### 6.3 Control Effectiveness

Control effectiveness is assessed separately from implementation status.

| Rating | Definition |
| --- | --- |
| Effective | Evidence demonstrates the intended control outcome |
| Partially Effective | Evidence demonstrates some benefit but identifies material limitations |
| Ineffective | The control does not achieve its intended outcome |
| Not Assessed | Effectiveness cannot be established from available evidence |

These are Project 3 control-level assessment categories.

They must not be substituted for ASD Essentials' official action-effectiveness ratings.

### 6.4 Control Assurance

Each material control assessment considers:

1. Intended security outcome
2. Actual implementation
3. Protected assets
4. Supporting evidence
5. Observed effectiveness
6. Coverage and limitations
7. Related risks and findings

Controls must not be classified as effective solely because a script, policy, or configuration document exists.

## 7. Evidence Assessment Methodology

### 7.1 Evidence Registration

Each evidence item receives a unique `EVD-###` identifier.

Evidence records must identify:

- Evidence title and description
- Source project and repository
- Source file or repository path
- Evidence type
- Capture or validation date where known
- Relevant assets and controls
- Supported assessment conclusions
- Evidence limitations

### 7.2 Evidence Sufficiency

Evidence sufficiency uses four categories:

| Rating | Definition |
| --- | --- |
| Strong | Direct, reliable evidence independently supports the relevant conclusion |
| Adequate | Evidence sufficiently supports the conclusion, with limited assurance constraints |
| Limited | Relevant evidence exists but does not fully support the conclusion |
| None | No usable supporting evidence is available |

Evidence sufficiency is evaluated in relation to the specific assessment claim.

A single evidence item may provide strong support for one conclusion but limited support for another.

### 7.3 Evidence Types

Evidence may include:

- Effective configuration outputs
- Independent technical validation results
- PowerShell test outputs
- Group Policy resultant-state evidence
- System configuration screenshots
- Technical test results
- Architecture documentation
- Implementation records

Documentation describing design intent must not be treated as equivalent to independent validation of operating effectiveness.

### 7.4 Evidence Reuse

Existing Projects 1 and 2 evidence is reviewed first.

Additional technical evidence is requested only where necessary to support a defensible assessment conclusion.

Evidence acquired after the assessment cut-off must retain its actual acquisition date.

### 7.5 Technical Evidence Requests

New technical evidence requests use the identifier:

`ER-###`

Requests must specify:

- Assessment objective
- Target system
- Required evidence
- Approved procedure or validation method
- Execution limitations
- Expected output
- Return and documentation requirements

Evidence acquisition is normally read-only.

Configuration changes, remediation, and intrusive testing require separate authorisation.

## 8. APRA CPS 234 Assessment

### 8.1 Assessment Approach

CPS 234 requirements are evaluated against the defined technical and simulated organisational context.

Each assessed requirement records:

- Requirement reference
- Applicability
- Relevant assets
- Existing controls
- Supporting evidence
- Assessment conclusion
- Evidence sufficiency
- Related findings and risks
- Assessment limitations

### 8.2 Assessment Status

| Status | Definition |
| --- | --- |
| Implemented | Sufficient evidence supports implementation within the assessed scope |
| Partially Implemented | Relevant measures exist but do not fully address the assessed requirement |
| Not Implemented | An applicable requirement is demonstrably not addressed |
| Not Assessed | Evidence is insufficient to reach a defensible conclusion |
| Not Applicable | The requirement is demonstrably outside the applicable circumstances |

These are Project 3 assessment classifications, not official APRA compliance determinations.

Not Assessed must not be treated as equivalent to Not Implemented.

Not Applicable requires explicit justification.

### 8.3 Organisational Limitations

Requirements involving governance bodies, executive accountability, organisational processes, third parties, or management approvals must be assessed according to the evidence actually available.

Role-based assumptions do not demonstrate that organisational processes operate.

## 9. ASD Essentials for Enterprise IT

### 9.1 Assessment Structure

ASD Essentials assessments use three official layers:

- Principles
- Actions
- Domains

Actions are evaluated against each applicable domain.

The eight ASD domains remain separate from Project 3's ten internal assessment domains.

### 9.2 ASD Action Ratings

The official action-effectiveness ratings are:

| Rating | Assessment interpretation |
| --- | --- |
| Not Assessed | No assessment completed or insufficient evidence |
| Not Effective | Intended security outcome is not achieved |
| Partially Effective | Outcome is achieved in part, with meaningful gaps |
| Fully Effective | Outcome is demonstrably achieved across the assessed domain |

Partial implementation alone does not establish partial effectiveness.

Not Applicable is not an additional ASD action rating.

Scope exclusions and applicability decisions must be recorded separately.

### 9.3 Assessment Dimensions

Each applicable action is evaluated considering:

#### Coverage

Whether the action applies to all relevant assets
within the domain.

#### Consistency

Whether the action operates consistently across those assets.

#### Currency

Whether the evidence remains representative of the assessed implementation.

#### Evidence Quality

Whether the evidence reliably supports the intended security outcome.

### 9.4 Indicators of Good Practice

Official ASD Indicators of Good Practice support assessment of action effectiveness.

Indicators are interpreted in the context of the applicable domain, assets, and expected outcomes.

They are not a substitute for assessor judgement.

Material departures from an indicated rating must include documented justification and evidence.

### 9.5 Principle Aggregation

Action ratings are aggregated to principle ratings within each applicable domain.

The official ASD weakest-link methodology applies.

A principle is:

- Not Effective when at least one applicable action is rated Not Effective.
- Partially Effective when all applicable actions have been assessed, none are Not Effective, and at least one is Partially Effective.
- Fully Effective when all applicable actions are Fully Effective.

Where the applicable actions have not been sufficiently assessed to determine a principle rating, the principle is recorded as Not Assessed.

Principles are assessed separately within each domain.

### 9.6 Domain Reporting

Domain reports must distinguish:

- Fully Effective principles
- Partially Effective principles
- Not Effective principles
- Not Assessed principles

Any domain effectiveness calculation must follow the official ASD Assessment Process Guide.

Unassessed principles must remain visible.

No overall Essential Eight maturity level is assigned.

ASD implementation priority phases are not effectiveness ratings or maturity levels.

### 9.7 Assessment Limitations

ASD assessments must consider the actual scope and characteristics of `banking.lab`.

The absence of an internet-facing environment, cloud workload, production banking application, or operational AI system must not automatically be interpreted as effective security.

Applicability and evidence limitations must be assessed individually.

## 10. ISO/IEC 27001:2022 Supporting Alignment

ISO/IEC 27001:2022 provides supporting alignment for governance observations and security controls.

Relevant mappings may record:

- ISO reference
- Relevant implemented control
- Related asset
- Supporting evidence
- Related finding
- Alignment rationale

### 10.1 Alignment Categories

| Category | Definition |
| --- | --- |
| Aligned | Evidence supports the relevant control-alignment observation |
| Partially Aligned | Some relevant alignment exists but material gaps remain |
| Gap | Evidence establishes a relevant control-alignment deficiency |
| Not Assessed | Insufficient evidence to determine alignment |

These categories are internal mapping conventions.

They are not ISO certification outcomes.

### 10.2 Risk-Driven Control Selection

Existing controls are assessed against their actual implementation and evidence.

Subsequently, risk treatment may identify additional controls necessary to address assessed risks.

Applicable ISO reference controls are used to support and cross-check those treatment decisions.

Project 3 does not claim a complete, management-approved ISO Statement of Applicability.

## 11. Finding Identification

Each material assessment finding receives a unique:

`FND-###`

Findings describe factual security observations.

A finding may identify:

- Control deficiency
- Incomplete implementation
- Ineffective security outcome
- Evidence limitation
- Other material assurance concern

Findings must reference relevant assets, controls, evidence, and framework requirements.

### 11.1 Cross-Framework Consolidation

One underlying security condition may relate to multiple framework requirements.

The same factual condition must not automatically produce separate findings for CPS 234, ASD Essentials, and ISO/IEC 27001.

Existing findings must be reviewed before creating additional finding records.

### 11.2 Findings and Risks

A finding is not automatically a risk.

A risk requires a credible scenario involving:

- Threat or adverse event
- Vulnerability or enabling condition
- Affected asset or objective
- Potential consequence

Findings without credible risk scenarios may remain findings without separate Risk Register entries.

## 12. Risk Assessment Methodology

### 12.1 Risk Identification

Each risk receives a unique identifier:

`RSK-###`

Risk statements should use the structure:

"There is a risk that [threat/event] exploits [vulnerability/condition], resulting in [consequence] to [asset or security objective]."

### 12.2 Likelihood Scale

| Score | Likelihood | Description |
| --- | --- | --- |
| 1 | Rare | Exceptional circumstances required |
| 2 | Unlikely | Could occur but is not expected |
| 3 | Possible | Could reasonably occur |
| 4 | Likely | Expected under plausible conditions |
| 5 | Almost Certain | Expected frequently or under normal threat conditions |

### 12.3 Impact Scale

| Score | Impact | Description |
| --- | --- | --- |
| 1 | Insignificant | Minimal security or operational consequence |
| 2 | Minor | Limited disruption or exposure |
| 3 | Moderate | Material but manageable consequence |
| 4 | Major | Significant operational, financial, or security consequence |
| 5 | Severe | Critical enterprise impact or severe compromise |

### 12.4 Risk Calculation

Risk Score = Likelihood × Impact

The project uses these risk bands:

| Score | Rating |
| --- | --- |
| 1–4 | Low |
| 5–9 | Moderate |
| 10–16 | High |
| 17–25 | Critical |

These are Project 3-defined qualitative risk criteria.

They must not be attributed to APRA, ASD, or ISO.

### 12.5 Inherent Risk

Inherent risk is evaluated before considering the effectiveness of existing controls.

The assessment records:

- Inherent likelihood
- Inherent impact
- Inherent risk score
- Inherent risk rating
- Supporting rationale

### 12.6 Residual Risk

Residual risk is evaluated after considering existing security controls and their effectiveness.

The assessment records:

- Applicable existing controls
- Control effectiveness
- Residual likelihood
- Residual impact
- Residual risk score
- Residual risk rating
- Supporting rationale

Control effectiveness must be supported by evidence.

Residual risk must not be reduced merely because a control is documented or proposed.

Where evidence is insufficient, uncertainty must be explicitly documented rather than assuming a control provides effective risk reduction.

### 12.7 Risk Assessment Integrity

Risk ratings must not be modified to produce preferred dashboard results or predetermined conclusions.

Impact assumptions must be defensible and consistent with available technical and business context.

## 13. Risk Treatment Methodology

Each treatment receives a unique identifier:

`TRT-###`

### 13.1 Treatment Types

| Treatment | Description |
| --- | --- |
| Mitigate | Reduce likelihood, impact, or both |
| Avoid | Eliminate the activity or exposure |
| Transfer | Allocate or share consequences through suitable arrangements |
| Accept | Retain the risk through an informed decision |

These categories represent treatment options.

Proposed risk acceptance must not be represented as formally approved by an actual executive.

### 13.2 Treatment Priorities

| Priority | Description |
| --- | --- |
| P1 | Immediate |
| P2 | High |
| P3 | Medium |
| P4 | Low |

Treatment priority is separate from risk rating.

Prioritisation may consider:

- Residual risk
- Regulatory significance
- Control dependencies
- Exposure
- Compensating controls
- Implementation feasibility

### 13.3 Treatment Requirements

Treatment records must contain:

- Related risks and findings
- Recommended action
- Treatment type
- Priority
- Accountable owner role
- Target security state
- Framework relationships
- Expected residual risk where defensible
- Validation requirements
- Treatment status

A recommended treatment is not an implemented control.

Future implementation must be supported by new evidence before effectiveness or residual-risk conclusions are revised.

## 14. Assessment Data and Traceability

The six core GRC entities are:

| Identifier | Entity |
| --- | --- |
| AST | Asset |
| CTL | Control |
| EVD | Evidence |
| FND | Finding |
| RSK | Risk |
| TRT | Treatment |

Framework assessments maintain relationships to these entities without creating unnecessary duplicate records.

An ASD action assessment may reference several controls, assets, evidence items, findings, and risks.

Many-to-many relationships are supported where appropriate.

Material assessment conclusions must be traceable to supporting evidence or explicit evidence limitations.

## 15. Executive Reporting

Project 3 uses Notion as the live GRC assessment workspace.

GitHub maintains approved, version-controlled assessment records and executive reporting artefacts.

Reporting will include:

- Assessment scope and coverage
- CPS 234 requirement status
- ASD Essentials effectiveness results
- ISO 27001 supporting alignment
- Control effectiveness
- Evidence sufficiency
- Inherent and residual risk
- Findings and treatment priorities

ASD domain summaries must retain access to supporting principle and action-level details.

Visualisations must not conceal incomplete assessments or material security findings.

## 16. Assessment Assurance

Before formal project closure, the assessment must undergo consistency and traceability validation.

The assurance review verifies:

1. Assessment scope is documented.
2. Framework versions are identifiable.
3. Evidence sources are traceable.
4. Unsupported control claims are excluded.
5. Framework ratings use the correct methodology.
6. Duplicate findings are consolidated.
7. Risk calculations are consistent.
8. Residual-risk conclusions consider control effectiveness.
9. Treatments map to supported findings and risks.
10. Dashboard results reconcile with underlying records.
11. Historical evidence remains distinguishable from subsequent observations.
12. Published GitHub records reconcile with the approved assessment state.

## 17. Methodology Maintenance

Changes to this methodology require assessment of their impact on existing records and conclusions.

Framework changes are governed through:

`documentation/framework-baseline-register.md`

Assessment scope changes are governed through:

`documentation/scope-and-context.md`

Methodology revisions must be documented and must not silently overwrite completed assessment conclusions.
