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

**Target competency:** Problem defition\
**Priority:** P0\
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

**Target competency:** Requirements engineering\
**Priority:** P0\
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

**Target competency:** Functional decomposition\
**Priority:** P0\
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

**Target competency:** System architecture\
**Priority:** P0\
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


**Target competency:** Interface design\
**Priority:** P0\
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

**Target competency:** Engineering decision-making\
**Priority:** P0\
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

---

# 5. PLC & Control Software Evidence

## PLC-001 - Structured PLC Architecture

**Priority:** P0\
**Toolchain:** TIA Portal V20 / CODESYS\
**Target:** LAB-001\
**Status:** Planned

### Required Evidence

A structured machine-control application.

### Expert artefacts

* program architecture,
* block hierarchy,
* documented variable structures,
* source code,
* state-machine diagram,
* functional description.

### Required implementation

The application should include:

* initialization,
* operating modes,
* automatic sequence,
* manual functions,
* premissives,
* interlocks,
* fault handling,
* reset logic,
* diagnostics.

### Portfolio Verified when

The application is moduler, understandable and demonstrably more structured than a collection of unrelated ladder networks.

---

## PLC-002 - State Machine

**Priority:** P0\
**Target:** LAB-001\
**Status:** Planned

### Required evidence

Explicit state-based machine behaviour.

Possible states:

> OFF\
> INITIALIZING\
> READY\
> AUTOMATIC\
> PAUSED\
> STOPPING\
> FAULT

### Required artefacts

* state diagram,
* transition table,
* transition conditions,
* implementation,
* test cases.

### Required verification

Test at minimum:

* valid transitions,
* invalid transitions,
* fault transition,
* reset/recovery,
* startup behaviour.

### Portfolio Verified when

The implemented logic is traceable directly to the documented state model.

---

## PLC-003 - Operating Modes

**Priority:** P0\
**Target:** LAB-001 / LAB-002\
**Status:** Planned

### Required evidence

Implementation of appropriate machine operating modes.

At minimum:

* Manual
* Automatic

Potential later modes:

* Setup
* Service
* Maintenance

### Required evidence

* mode transition rules,
* permissions,
* actuator restrictions,
* HMI representation,
* verification.

---

## PLC-004 - Interlocks & Permissives

**Priority:** P0\
**Target:** LAB-001 / LAB-003\
**Status:** Planned

### Required evidence

Actuation and machine transitions shall depend on explicit conditions.

Examples:

* pressure available,
* workpiece present,
* clamp confirmed,
* robot clear,
* machine ready,
* no active blocking fault.

### Portfolio Verified when

Unsafe or logically invalid commands are rejected and this behaviour is tested.

---

## PLC-005 - Fault Handling

**Priority:** P0\
**Target:** LAB-001\
**Status:** Planned

### Required evidence

A structured fault-management philosophy.

### Include

* fault detection,
* fault classification,
* machine response,
* alarm generation,
* reset criteria,
* recovery behaviour.

### Required tests

Examples:

* Actuator timeout,
* sensor disagreement,
* communication loss,
* invalid state,
* missing permissive.

---

## PLC-006 - Reusable Function Blocks

**Priority:** P0\
**Target:** LAB-001 / CODESYS Labs\
**Status:** Planned

### Required evidence

Reusable control objects for common device types.

Possible examples:

* cylinder,
* motor,
* digital sensor,
* valve,
* alarm object.

### Portfolio Verified when

The same blcok can be instantiated for multiple devices without duplicating application logic.

---

# 6. HMI & Operator Interface Evidence 

## HMI-001 - Machine Overview

**Priority:** P1\
**Target:** LAB-002\
**Status:** Planned

### Evidence

HMI shall communicate machine status clearly.

Include:

* current state,
* current mode,
* machine readiness,
* production status,
* active faults.

---

## HMI-002 - Manual Control

**Priority:** P1\
**Target:** LAB-002 / LAB-003\
**Status:** Planned

### Evidence

Manual actuator control shall:

* respect interlocks,
* provide state feedback,
* prevent invalid commands,
* clearly show command and feedback status.

---

## HMI-003 - Alarm Management

**Priority:** P0\
**Target:** LAB-002\
**Status:** Planned

### Required evidence

* alarm identifier,
* description,
* timestamp where supported,
* active/inactive state,
* acknowledgement where relevant,
* reset/recovery instructions.

### Portfolio Verified when

Faults generated by the PLC can be diagnosed meaningfully through the HMI.

---

## HMI-004 - Diagnostics

**Priority:** P1\
**Target:** LAB-002\
**Status:** Planned

### Evidence

Diagnostics should expose useful troubleshooting data.

Examples:

* I/O states,
* Permissives,
* interlocks,
* communication status,
* sequence step,
* device status.

---

# 7. Industrial Electrical Evidence

## ELEC-001 - Instrial Control Schematic

**Priority:** P0\
**Toolchain:** PCSCHEMATIC Automation\
**Status:** Planned

### Required evidence

A complete electrical documentation package for a representative machine module.

### Expected artefacts

* power distribution,
* 24 VDC control system,
* PLC I/O,
* sensors,
* actuators,
* relays/contactors where relevant,
* device references,
* wire identification.

### Portfolio Verified when

The documentation is internally consistent and a technically competent person could understand how the system is intended to be wired.

---

## ELEC-002 - Component Selection

**Priority:** P1\
**Status:** Planned

### Required evidence

At least one project shall include documented selection of components such as:

* power supply,
* sensor,
* valve,
* relay,
* contactor,
* drive,
* motor,
* protective device.

### Evidence should include

* relevant requirements,
* selected specifications,
* alternatives,
* engineering rationale.

---

## ELEC-003 - Electrical Protection

**Priortiy:** P0\
**Status:** Planned

### Required evidence

A project shall demonstrate awareness of appropriate electrical protectiong and design constraints.

Where applicable:

* overcurrent protection,
* short-curcuit considerations,
* conductor sizing,
* power supply loading,
* grounding/PE concepts,
* separation of power and control.

Any portfolio project involving electrical design shall clearly state which aspects are conceptual/simulated and which, if any, were physically implemented.

---

# 8. Pneumatics Evidence

## PNEU-001 - Electro-Pneumatic Actuator Module

**Priority:** P0\
**Toolchain:** FluidSIM + TIA/CODESYS\
**Target:** LAB-003\
**Status:** Planned

### Example system

Automated workpiece clamp.

### Required evidence

* pneumatic schematic,
* cylinder selection,
* valve configuration,
* position sensors,
* PLC control,
* interlocks,
* timeout monitoring,
* fault recovery.

### Required fault tests

* failed extension,
* failed retraction,
* contradictory sensor states,
* missing pressure,
* sequence timeout.

### Portfolio Verified when

The pneumatic process and PLC logic behave as on integrated system.

---

# 9. Robotics Evidence

## ROB-001 - Robot Programming

**Priority:** P1\
**Toolchain:** URSim\
**Target:** LAB-005 / FLAGSHIP-001\
**Status:** Planned

### Required evidence

A simulated industrial robot application including:

* TCP,
* coordinate frames,
* motion paths,
* process sequence,
* logical I/O.

The objective is not merely robot motion, but integration into a production process.

---

## ROB-002 - PLC <-> Robot Handshake

**Priority:** P0\
**Toolchain:** TIA Portal + URSim\
**Target:** LAB-005\
**Status:** Planned

### Example interface

> PLC -> Robot\
> Start\
> Reset\
> Program_Select\
> \
> Robot -> PLC\
> Ready\
> Busy\
> Complete\
> Fault\

### Required evidence

* signal definition,
* sequence diagram,
* timeout strategy,
* abnormal-state behaviour,
* reset/recovery logic.

### Required verification

Tests shall include:

* normal cycle,
* robot not ready,
* robot fault during cycle,
* lost completion cycle,
* timeout,
* restart.

---

## ROB-003 - Robot Cell Architecture

**Priority:** P0\
**Target:** FLAGSHIP-001\
**Status:** Planned

### Evidence

A complete robot-cell concept including:

* robot,
* machine,
* workholding,
* part flow,
* control interface,
* operating sequence,
* relevant safety boundaries,
* recovery philosophy.

---

# 10. Industrial Networking Evidence

## NET-001 - OT Network Architecture

**Priority:** P0\
**Toolchain:** Packet Tracer + TIA + project documentation\
**Status:** Planned

### Required evidence

Documented industrial network architecture.

### Include

* network topology,
* device roles,
* addressing,
* protocols,
* communication paths,
* logical separation.

### Portfolio Verified when

The design demonstrates understanding of why industrial devices are connected in the chosen architecture.

---



































