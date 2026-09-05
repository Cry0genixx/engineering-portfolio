# Engineering Evidence Matrix

**Version:** 0.1
**Status:** Draft
**Last Updated:** 2026-09-05

##Purpose

This document defines what constitutes meaningful and verifiable evidence for key engineering competencies within the portfolio.

The Evidence Matrix connets:
> Competency -> Required Evidence -> Engineering Artefacts -> Verification -> Portfolio Project

Its purpose is to prevent vague skill claims and ensure that important competencies are supported by reviewable technical work.

A competency should not be considered Portfolio Verified simply because software was used, a course was completed or a feature was demonstrated once.

Strong evidence should demonstrate:

* technical understanding,
* practical implementation, 
* engineering decision-making, 
* verification,
* documentation,
* and appropriate awareness of limitations.

---

# 1. Evidence Status

| Status | Definition | 
|:---|:---| 
| Not Started | No portfolio evidence exists. |
| Planned | Evidance has been assigned to a future project or lab. |
| In Development | Relevant work is actively being developed. | 
| Implemented | Technical implementation exists, but verification/documentation is incomplete. |
| Verified | Implementation has been tested against defined criteria. |
| Portfolio Verified | Strong technical evidence, verification and documentation are publicly reviewable. |

---

# 2. Evidence Strength

## E0 - No Evidence

No meaningful supporting material exists.

## E1 - Educational / Claimed 

Examples:

* CV entry
* LinkedIn skill
* Course completion
* Certificate
* Educational exposure
* Software familiarity

Useful supporting information, but insufficient as strong portfolio evidence.

## E2 - Demonstrated

The competency has been used in a concrete exercise, work task, simulation or project.

Evidence may include: 

* screenshots,
* code,
* CAD models,
* schematics,
* videos,
* calculations,
* project description.

## E3 - Verified

The competency is demonstrated through an engineeried implementation with defined requirements and verification.

Evidence should normally include:

* objective,
* requirements,
* implementation,
* test criteria,
* results,
* limitations.

## E4 - Portfolio Verified

The competency is supported by a complete and reviewable engineering case.

This normally includes:

* requirements,
* architecture,
* design decisions,
* implementation,
* techincal artefacts,
* verification,
* results,
* lessons learned,
* and sufficient documentation for an external technical reviewer to understand the work.

---

# 3. General Evidence Standard

For a major competency to reach Portfolio Verified, the evidence should answer six questions:

### 1. What problem was being solved?

The technical context and objective shall be clear.

### 2. What requirements applied?

Important functional and technical requirements shall be documented.

### 3. How was the solution designed?

Architecture, interfaces and major design decisions shall be understandable.

### 4. What was actually implemented?

Relevant source code, drawings, models, configurations or simulations shall be available where practical.

### 5. How was it verified?

Defined acceptance criteria shall be tested.

### 6. What were the limitations?

The project shall clearly distinguish between:

* implemented,
* simulated,
* virtually commissioned,
* physically tested,
* and assumed behavior.

---

# 4. Systems Engineering Evidence

## SE-001 - Problem Definition

**Target competency:** Problem defition
**Priority:** P0
**Status:** Planned

### Required evidence

A technical problem shall be translated into a concise engineering problem statement.

### Minimum artefacts

* problem statement,
* context,
* objectives,
* constraints,
* project scope,
* exclusions.

### Portfolio Verified when

An external reviewer can understand:

* what problem exists,
* why it matters,
* what the project intends to solve,
* and what lies outside the project boundary.

### Target projects

* LAB-001
* all major future projects
* FLAGSHIP-001

---

## SE-002 - Requirements Engineering

**Target competency:** Requirements engineering
**Priority:** P0
**Status:** Planned

### Required evidence

Formal functions and technical requirements.

### Minimum artefacts

* uniquely identified requirements,
* functional requirements,
* interface requirements where relevant,
* constraints,
* acceptance criteria.

Example:

> FR-001\
> The system shall provide Manual and Automatic operationg modes.\
> \
> Verification:\
> Functional test.\
> \
> Acceptance criterion:\
> The operator shall be able to select each permitted mode and the controller shall enter the corresponding machine state.

### Portfolio Verified when

Requirements are:

* unambiguous,
* testable where practical,
* traceable to implementation, 
* and linked to verification.

### Target projects

* LAB-001
* FLAGSHIP-001

---

## SE-003 - Functional Decomposition

**Target competency:** Functional decomposition
**Priority:** P0
**Status:** Planned

### Required evidence

A system shall be decomposed into logical functions and subsystems.

### Minimum artefacts

* functional block diagram,
* subsystem definitions,
* responsibility boundaries.

### Portfolio Verified when

The decomposition clearly separates relevant functions such as:

* machine control,
* robot control,
* HMI,
* safety-related functions,
* pneumatics,
* communication,
* data collection,
* diagnostics.

### Target projects

* LAB-001
* FLAGSHIP-001

---

## SE-004 - System Architecture

**Target competency:** System architecture
**Priority:** P0
**Status:** Planned

### Required evidence

A documented architecture showing system components and relationships.

### Minimum artefacts

* architecture diagram,
* subsystem description,
* communication paths,
* major interfaces.

### Portfolio Verified when

A technical reviewer can understand the system without first reading source code.

### Target projects

* LAB-001
* LAB-004
* LAB-005
* FLAGSHIP-001

---

## SE-005 - Interface Definition


**Target competency:** Interface design
**Priority:** P0
**Status:** Planned

### Required evidence

Interfaces between subsystems shall be explicitly defined.

Possible interfaces:

* PLC <-> HMI
* PLC <-> robot
* PLC <-> SCADA
* PLC <-> sensors
* PLC <-> actuators
* robot <-> CNC
* mechanical <-> electrical

### Minimum artefacts

* signal tables,
* data structure definitions,
* handshakes,
* interface diagrams,
* communication parameters.

### Portfolio Verified when

The expected behaviour of both sides of an interface is clearly documented and tested.

### Target projects

* LAB-004
* LAB-005
* FLAGSHIP-001

---

## SE-006 - Engineering Trade-Off Analysis

**Target competency:** Engineering decision-making
**Priority:** P0
**Status:** Planned

### Required evidence

Important technical decisions shall include rationale.

Examples:

* PLC architecture choice,
* sensor selection,
* communication protocol,
* actuator type,
* robot layout,
* material choice,
* manufacturing method.

### Minimum artefacts

* Alternatives considered,
* decision criteria,
* selected solution,
* disadvantages / limitations.

### Portfolio Verified when

The project shows not merely **what** was selected, but **why**.

### Target projects

* all major projects
































