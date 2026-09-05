# Engineering Project Backlog

**Version:** 0.1\
**Status:** Draft\
**Date Created:** 2026-09-04\
**Last updated:** 2026-09-05

## Purpose

This document defines the initial engineering project roadmap for the portfolio.

Projects are selected based on:

* identified competency gaps,
* required portfolio evidence,
* relevance to target engineering roles,
* integration potential,
* available software and simulation tools,
* and reuse of work in larger multidisciplinary projects.

Projects shall not primarily be selected because a software package is available.

The preferred development logic is:

**Competency Gap → Required Evidence → Engineering Problem → Project → Verification → Portfolio Evidence**

---

# 1. Project Categories

The portfolio shall initially use three project categories.

## LAB — Technical Engineering Laboratory

Focused projects intended to develop and verify one or several technical competencies.

Typical characteristics:

* limited scope,
* strong technical focus,
* requirements-driven,
* independently verifiable,
* reusable in future projects.

Examples:

* PLC architecture,
* HMI,
* pneumatics,
* industrial communication.

---

## FLAGSHIP — Multidisciplinary Engineering Project

Large projects integrating multiple disciplines and previously developed technical labs.

Typical characteristics:

* realistic industrial problem,
* multidisciplinary system architecture,
* significant integration,
* extensive documentation,
* comprehensive verification.

Flagship projects should represent the strongest portfolio evidence.

---

## CASE — Engineering Case Study

A project or documented technical analysis primarily demonstrating existing professional competence.

Possible topics:

* machining strategy,
* production optimization,
* DFM,
* root-cause analysis,
* tolerance strategy,
* fixture design.

Case studies are particularly useful for converting existing industrial experience into publicly reviewable engineering evidence.

---

# 2. Portfolio Development Phases

## Phase 1 — Control Engineering Foundation

Primary objective:

Establish strong evidence in structured automation engineering.

Projects:

* LAB-001 — Industrial Machine Control Core
* LAB-002 — HMI & Alarm Architecture
* LAB-003 — Electro-Pneumatic Machine Module

---

## Phase 2 — Connectivity & Integration

Primary objective:

Demonstrate integration between control systems, robots and higher-level industrial systems.

Projects:

* LAB-004 — Industrial Communication & SCADA
* LAB-005 — Robot Integration Interface

---

## Phase 3 — Manufacturing Integration

Primary objective:

Combine established manufacturing competence with newly demonstrated automation and systems competence.

Projects:

* CASE-001 — Manufacturing & DFM Engineering Case
* FLAGSHIP-001 — Automated CNC Manufacturing Cell

---

## Phase 4 — Advanced Mechatronics

Primary objective:

Expand into electronics, embedded systems, advanced sensing and multidisciplinary mechatronics.

Potential projects:

* LAB-006 — Industrial Sensor Interface
* LAB-007 — Condition Monitoring System
* LAB-008 — PCB / Embedded Sensor Node
* LAB-009 — Machine Vision Inspection
* FLAGSHIP-002 — Integrated Mechatronic Production System

Projects in this phase remain provisional and should be reviewed as the formal mechatronics programme progresses.

---

# 3. Active Project

## LAB-001 — Industrial Machine Control Core

**Status:** Next\
**Priority:** P0\
**Project type:** Technical Engineering Laboratory\
**Primary tools:** Siemens TIA Portal V20, S7-PLCSIM V20\
**Secondary tools:** CODESYS, Git, GitHub, Obsidian

### Engineering Problem

Industrial machine-control software must handle operating states, commands, faults and transitions predictably.

A poorly structured PLC application can become difficult to:

* understand,
* modify,
* troubleshoot,
* test,
* and integrate with other systems.

The project shall investigate how a generic industrial machine-control core can be designed using a structured, state-based architecture.

### Initial Problem Statement

> How can a reusable industrial machine-control architecture be designed so that machine states, operating modes, permissives, interlocks, faults and recovery are handled in a predictable, maintainable and verifiable manner?

### Primary Competency Evidence

* PLC architecture
* IEC 61131-3 programming
* state machines
* operating modes
* function blocks
* permissives
* interlocks
* fault handling
* software diagnostics
* requirements engineering
* verification
* technical documentation
* Git workflow

### Initial Functional Scope

The controller should include at minimum:

* startup / initialization,
* Ready state,
* Manual mode,
* Automatic mode,
* Stop handling,
* Fault state,
* fault reset,
* basic diagnostics,
* permissive logic,
* interlock logic.

### Proposed Machine States

Initial state model:

```text
OFF
 ↓
INITIALIZING
 ↓
READY
 ↓
AUTOMATIC
 ↕
PAUSED

READY / AUTOMATIC
        ↓
     STOPPING

Any applicable state
        ↓
      FAULT
```

The final architecture shall be derived from requirements rather than this draft alone.

### Major Deliverables

* Project README
* problem definition
* scope
* functional requirements
* state-machine diagram
* transition table
* PLC architecture
* source/project files where appropriate
* test specification
* fault-injection tests
* verification report
* lessons learned

### Exit Criteria

LAB-001 may be considered complete when:

* all defined requirements have a verification result,
* normal machine-state transitions pass,
* invalid transitions are controlled,
* representative faults are injected and handled,
* reset/recovery behaviour is documented,
* and the project can be understood by a technical reviewer without requiring verbal explanation.

### Reuse

LAB-001 shall form the control-software foundation for later projects.

---

# 4. Planned Phase 1 Projects

## LAB-002 — HMI & Alarm Architecture

**Status:** Planned\
**Priority:** P0/P1\
**Dependencies:** LAB-001\
**Primary tools:** TIA Portal V20\
**Project type:** Technical Engineering Laboratory

### Engineering Problem

A machine may function correctly at controller level while remaining difficult for an operator or technician to understand.

The project shall develop an operator interface for the machine-control architecture created in LAB-001.

### Problem Statement

> How can an industrial HMI be structured so that operators and maintenance personnel can understand machine status, operate permitted functions, diagnose faults and recover from abnormal conditions efficiently?

### Primary Evidence

* HMI architecture
* operator interface design
* machine-state visualization
* manual controls
* alarm management
* diagnostics
* PLC ↔ HMI integration
* fault recovery

### Proposed Screens

* Overview
* Automatic Operation
* Manual Operation
* Alarms
* Diagnostics
* I/O
* Maintenance / Service

### Important Design Questions

The project should address:

* What information does an operator require?
* What information does maintenance require?
* Which commands should be unavailable in each mode?
* How should active interlocks be visualized?
* How should faults differ from warnings?
* What information helps diagnose a stopped machine?

### Verification

Representative operator tasks should be tested, including:

* start permitted cycle,
* rejected start,
* fault identification,
* manual operation,
* reset,
* identification of blocking permissive.

### Reuse

LAB-002 shall provide HMI concepts and alarm architecture for future integrated machine projects.

---

## LAB-003 — Electro-Pneumatic Machine Module

**Status:** Planned\
**Priority:** P0/P1\
**Dependencies:** LAB-001\
**Primary tools:** FluidSIM, TIA Portal / CODESYS\
**Electrical documentation:** PCSCHEMATIC Automation

### Engineering Problem

Industrial automation frequently requires interaction between control software and physical actuators.

A simple workpiece-clamping module shall be used to demonstrate this interaction.

### Problem Statement

> How can an automatically controlled pneumatic workholding system detect and respond correctly to normal operation, missing conditions and actuator faults?

### Proposed System

Representative system:

```text
Workpiece
   ↓
Presence Sensor
   ↓
PLC
   ↓
Solenoid Valve
   ↓
Pneumatic Cylinder
   ↓
Extended / Retracted Feedback
```

### Primary Evidence

* pneumatics
* electro-pneumatic integration
* actuator control
* sensor feedback
* PLC sequencing
* interlocks
* timeout handling
* fault diagnostics
* electrical schematic
* verification

### Expected Failure Cases

At minimum:

* workpiece missing,
* cylinder fails to extend,
* cylinder fails to retract,
* contradictory sensors,
* pressure not available,
* operation timeout.

### Engineering Artefacts

* pneumatic schematic
* electrical schematic
* I/O list
* sequence diagram
* component-selection rationale
* PLC integration
* test cases
* verification report

### Reuse

The module may later become the workholding system in FLAGSHIP-001.

---

# 5. Planned Phase 2 Projects

## LAB-004 — Industrial Communication & SCADA

**Status:** Planned\
**Priority:** P0\
**Dependencies:** LAB-001\
**Primary tools:** TIA Portal, Ignition, Python where useful\
**Supporting tools:** Cisco Packet Tracer

### Engineering Problem

Modern automated machinery often needs to expose operational data beyond the PLC without compromising the controller's primary control responsibilities.

### Problem Statement

> How can machine data be transferred from an industrial controller to a supervisory system in a structured and maintainable manner while maintaining clear separation between machine control and higher-level data functions?

### Proposed Architecture

```text
Machine Simulation
      ↓
     PLC
      ↓
    OPC UA
      ↓
   Ignition
   ↙      ↘
HMI       Historian
            ↓
         Analysis
```

### Primary Evidence

* OPC UA
* industrial networking
* data modelling
* SCADA
* Ignition
* historian
* production dashboards
* IT/OT architecture
* system interfaces
* communication fault handling

### Initial Data Set

Potential tags:

* machine state,
* operating mode,
* production count,
* cycle counter,
* cycle time,
* machine-ready status,
* active fault,
* fault code.

### Possible Extensions

* Python OPC UA client
* database
* automatic reporting
* simulated OEE
* downtime classification

### Verification

Tests should include:

* normal communication,
* incorrect value handling,
* connection loss,
* reconnection,
* tag verification,
* data persistence where applicable.

---

## LAB-005 — PLC ↔ Robot Integration Interface

**Status:** Planned\
**Priority:** P0\
**Dependencies:** LAB-001\
**Primary tools:** TIA Portal, URSim, VMware Workstation\
**Future alternative implementation:** Mitsubishi GX Works3 / RT ToolBox3

### Engineering Problem

PLC-controlled machinery and industrial robots require deterministic and understandable coordination.

Robot motion alone does not demonstrate machine integration.

### Problem Statement

> How can a PLC and industrial robot coordinate machine-cycle execution using a robust handshake that handles startup, normal operation, faults, timeouts and recovery?

### Proposed Interface

PLC → Robot:

* Program Select
* Start
* Reset
* Hold / Stop where applicable

Robot → PLC:

* Robot Ready
* Program Ready
* Busy
* Complete
* Fault

### Primary Evidence

* PLC ↔ robot integration
* interface engineering
* sequence design
* handshake protocols
* timeouts
* robot state management
* fault recovery
* virtual commissioning

### Verification Scenarios

* normal cycle,
* robot unavailable,
* incorrect program selection,
* robot fault before start,
* fault during cycle,
* missing Complete,
* PLC timeout,
* reset and restart.

### Reuse

This interface shall later become one of the central subsystems in FLAGSHIP-001.

---

# 6. Manufacturing Case Study

## CASE-001 — Manufacturing & DFM Engineering Case

**Status:** Planned\
**Priority:** P1\
**Primary tools:** SOLIDWORKS / Inventor / Fusion\
**Project type:** Engineering Case Study

### Purpose

Convert existing machining and manufacturing experience into formal, reviewable engineering evidence.

### Possible Problem Statement

> How can a machined component or fixture be redesigned to improve manufacturability while maintaining its functional and dimensional requirements?

### Potential Evidence

* original design assumptions,
* manufacturing constraints,
* tolerance analysis,
* setup strategy,
* tool accessibility,
* workholding,
* machining sequence,
* revised design,
* CAM simulation,
* inspection strategy.

### Core Objective

The project should demonstrate that manufacturing experience actively influences engineering design decisions.

### Important Constraint

The case should use either:

* a newly created representative component,
* publicly shareable material,
* or fully anonymized professional experience.

No confidential employer information should be published.

---

# 7. First Flagship Project

## FLAGSHIP-001 — Automated CNC Manufacturing Cell

**Status:** Future\
**Priority:** Strategic\
**Dependencies:** LAB-001 through LAB-005 recommended\
**Project type:** Multidisciplinary Flagship Project

### Engineering Context

Automated machining cells combine multiple engineering disciplines:

* manufacturing,
* mechanical design,
* workholding,
* robot handling,
* control systems,
* HMI,
* industrial networking,
* safety concepts,
* production data,
* diagnostics.

This project shall combine the user's established manufacturing experience with newly verified mechatronics and automation competence.

### Initial Problem Statement

> How can a CNC production cell be designed for automated workpiece handling while ensuring predictable machine sequencing, process interlocking, robot-machine coordination, operator diagnostics and production-data visibility?

### Proposed System Architecture

```text
                  ┌──────────────────┐
                  │     IGNITION     │
                  │ SCADA / Historian│
                  └────────▲─────────┘
                           │
                        OPC UA
                           │
                  ┌────────┴─────────┐
                  │       PLC        │
                  └───┬─────────┬────┘
                      │         │
            ┌─────────┘         └─────────┐
            ↓                             ↓
         ROBOT                           HMI
            │
            ↓
      CNC MACHINE
            │
            ↓
      WORKHOLDING
            │
            ↓
        MACHINING
            │
            ↓
       PART OUTPUT
```

### Candidate Functional Sequence

Example:

1. Cell initialization
2. Verify machine availability
3. Verify raw workpiece
4. Robot requests access
5. Machine enters loading-safe condition
6. Robot loads workpiece
7. Workpiece clamped
8. Clamp confirmation
9. Robot exits machine envelope
10. CNC cycle permitted
11. Machining completed
12. Robot unloads part
13. Finished part transferred
14. Production counter updated
15. Cycle data transferred to SCADA

This sequence is preliminary and shall later be converted into formal requirements.

### Primary Evidence Areas

FLAGSHIP-001 should integrate:

* requirements engineering
* systems architecture
* interface engineering
* mechanical design
* DFM
* CNC process knowledge
* workholding
* electrical documentation
* PLC architecture
* state machines
* HMI
* alarms
* pneumatics
* robot integration
* industrial networks
* OPC UA
* SCADA
* production data
* fault handling
* verification
* virtual commissioning
* technical documentation

### Intended Portfolio Role

This project should become the strongest demonstration of the intended multidisciplinary profile:

**Manufacturing + Mechanical Engineering + Mechatronics + Automation + Robotics + IT/OT + Systems Engineering**

---

# 8. Future Technical Labs

The following projects are intentionally not scheduled yet.

They should be activated only when:

* formal studies reach the relevant subject,
* prerequisite competence is sufficient,
* or another portfolio project creates a clear need.

---

## LAB-006 — Motor & Drive Control

Possible evidence:

* motor selection,
* load analysis,
* VFD,
* PLC control,
* speed reference,
* faults,
* electrical documentation.

**Priority:** Future P1

---

## LAB-007 — Condition Monitoring & Data Acquisition

Possible system:

```text
Motor
 ↓
Sensor
 ↓
Data Acquisition
 ↓
Signal Processing
 ↓
Trend / Diagnostics
```

Possible evidence:

* sensors,
* sampling,
* Python,
* signal processing,
* SCADA,
* maintenance engineering.

**Priority:** Future P1

---

## LAB-008 — Industrial Sensor Interface PCB

Primary tools:

* KiCad
* Python / microcontroller development
* CAD for enclosure

Possible evidence:

* electronics,
* PCB,
* sensor interface,
* 24 V considerations,
* protection,
* embedded systems,
* EMC considerations.

**Priority:** Future P1

---

## LAB-009 — Machine Vision Inspection

Possible problem:

Automated inspection of a manufactured component.

Potential evidence:

* vision,
* dimensional/feature inspection,
* pass/fail logic,
* PLC interface,
* production quality,
* traceability.

**Priority:** Future P2/P1

---

## LAB-010 — Cross-Platform PLC Architecture

Potential objective:

Reimplement selected LAB-001 architecture using:

* CODESYS,
* Mitsubishi GX Works3,
* or both.

### Purpose

Demonstrate that control-system understanding is not dependent on one PLC vendor.

**Priority:** Future P2

---

# 9. Suggested Development Order

Initial recommended order:

```text
PORTFOLIO-000
     │
     ↓
LAB-001
Industrial Machine Control Core
     │
     ├─────────────┐
     ↓             ↓
LAB-002         LAB-003
HMI             Pneumatics
     │             │
     └──────┬──────┘
            ↓
         LAB-004
    Communication / SCADA
            │
            ↓
         LAB-005
      Robot Integration
            │
     ┌──────┴──────┐
     ↓             ↓
 CASE-001      Additional Labs
     │
     └──────┬──────┘
            ↓
      FLAGSHIP-001
 Automated CNC Cell
```

This sequence is not intended as a rigid dependency graph.

Some projects may overlap when useful, but the number of simultaneously active technical projects should remain limited.

---

# 10. Work-In-Progress Rule

Recommended initial limit:

Maximum 1 primary technical project + 1 supporting documentation task active at the same time.

Example:

Acceptable:

* LAB-001 implementation
* Portfolio documentation update

Avoid:

* LAB-001
* LAB-002
* LAB-003
* PCB project
* robot cell
* website redesign

all simultaneously.

The objective is completion and verification rather than maximum project initiation.

---

# 11. Project Selection Criteria

Before adding a new project to the active backlog, evaluate it against the following criteria.

| Criterion            | Question                                                            |
| -------------------- | ------------------------------------------------------------------- |
| Competency relevance | Does it address an identified competence gap?                       |
| Evidence value       | Will it create strong technical evidence?                           |
| Career relevance     | Does it support target engineering roles?                           |
| Integration value    | Can it be reused in later projects?                                 |
| Technical depth      | Does it require meaningful engineering decisions?                   |
| Verification         | Can success and failure be tested objectively?                      |
| Feasibility          | Can it be completed with available resources?                       |
| Differentiation      | Does it show something beyond generic tutorial work?                |
| Documentation        | Can the work be presented clearly without confidential information? |

Projects with low evidence value should generally not enter the active portfolio roadmap.

---

# 12. Definition of Ready

A technical project should not move from **Planned** to **Active** until it has:

* defined engineering problem,
* initial scope,
* known primary evidence targets,
* identified toolchain,
* major constraints,
* initial deliverables,
* and at least a draft requirement set.

---

# 13. Definition of Done

A project shall not be considered complete simply because the software or simulation operates.

Minimum completion criteria:

* implementation complete,
* important requirements tested,
* verification results documented,
* known failures or limitations documented,
* major technical artefacts organized,
* README complete,
* lessons learned complete,
* repository structure clean,
* final revision created.

Only then should the project be considered for **Portfolio Verified** status.

---

# 14. Current Backlog Summary

| ID            | Project                              | Type      | Priority  | Status         |
| ------------- | ------------------------------------ | --------- | --------- | -------------- |
| PORTFOLIO-000 | Portfolio Engineering Framework      | Framework | P0        | In Development |
| LAB-001       | Industrial Machine Control Core      | Lab       | P0        | **Next**       |
| LAB-002       | HMI & Alarm Architecture             | Lab       | P0/P1     | Planned        |
| LAB-003       | Electro-Pneumatic Machine Module     | Lab       | P0/P1     | Planned        |
| LAB-004       | Industrial Communication & SCADA     | Lab       | P0        | Planned        |
| LAB-005       | PLC ↔ Robot Integration              | Lab       | P0        | Planned        |
| CASE-001      | Manufacturing & DFM Engineering Case | Case      | P1        | Planned        |
| FLAGSHIP-001  | Automated CNC Manufacturing Cell     | Flagship  | Strategic | Future         |
| LAB-006       | Motor & Drive Control                | Lab       | P1        | Future         |
| LAB-007       | Condition Monitoring                 | Lab       | P1        | Future         |
| LAB-008       | Industrial Sensor Interface PCB      | Lab       | P1        | Future         |
| LAB-009       | Machine Vision Inspection            | Lab       | P1/P2     | Future         |
| LAB-010       | Cross-Platform PLC Architecture      | Lab       | P2        | Future         |

---

# 15. Immediate Next Milestone

The next technical milestone is:

## LAB-001 — Industrial Machine Control Core

Before PLC implementation begins, the following shall be created:

1. Project README
2. Problem definition
3. Scope
4. Assumptions and constraints
5. Functional requirements
6. Initial state model
7. Verification strategy

Only after these artefacts exist should the first control-software implementation begin.
