# Engineering Project Standard

**Version:** 0.1
**Status:** Draft
**Last updated:** 2026-09-05

## Purpose

This standard defines the minimum engineering and documentation requirements for technical projects included in the portfolio.

The objective is to ensure that projects demonstrate more than successful implementation.

A portfolio project should show a structured engineering process:

**Problem → Requirements → Architecture → Design → Implementation → Verification → Results → Lessons Learned**

The standard shall be applied proportionally.

Small technical laboratories may use a simplified version, while flagship projects should apply the full structure.

---

# 1. Core Principles

All portfolio projects should follow these principles.

## 1.1 Engineering before software

Projects shall begin with a technical problem, not with a software package.

Avoid:

> Build something in TIA Portal.

Prefer:

> Develop a machine-control architecture capable of managing operating states, faults and recovery predictably.

The engineering problem determines the tools.

---

## 1.2 Requirements before implementation

Important project behaviour should be defined before implementation begins.

Not every detail must be known initially, but the project should have sufficient requirements to establish:

* intended behaviour,
* scope,
* constraints,
* success criteria.

---

## 1.3 Evidence over claims

The portfolio should demonstrate competence through artefacts such as:

* source code,
* schematics,
* calculations,
* CAD,
* diagrams,
* test results,
* simulations,
* measurements,
* design decisions.

Software screenshots alone should not normally constitute strong evidence.

---

## 1.4 Verification is part of development

A system working once is not sufficient proof.

Projects shall include deliberate verification against defined expectations.

Where appropriate, abnormal and failure conditions should also be tested.

---

## 1.5 Limitations shall be explicit

Every project shall distinguish between:

* conceptual design,
* software simulation,
* virtual commissioning,
* prototype implementation,
* physical testing,
* production deployment.

No project shall imply a level of implementation or validation that did not occur.

---

## 1.6 Documentation should support technical review

A technically competent reviewer should be able to understand:

* the problem,
* the proposed solution,
* key engineering decisions,
* implementation,
* verification,
* and limitations

without requiring verbal explanation from the author.

---

# 2. Project Classification

Every project shall be classified as one of the following.

## LAB

Focused technical engineering laboratory.

Primary purpose:

* develop competence,
* test a technical concept,
* create reusable engineering evidence.

Expected documentation level:

**Moderate**

---

## CASE

Engineering case study.

Primary purpose:

* formalize existing professional knowledge,
* analyse a technical problem,
* demonstrate engineering judgement.

Expected documentation level:

**Moderate**

---

## FLAGSHIP

Major multidisciplinary engineering project.

Primary purpose:

* demonstrate integrated engineering capability,
* combine multiple disciplines,
* create high-value portfolio evidence.

Expected documentation level:

**High**

---

# 3. Project Identification

Each project shall receive a unique identifier.

Examples:

```text
LAB-001
LAB-002
CASE-001
FLAGSHIP-001
```

The project identifier should remain unchanged throughout the project lifecycle.

Recommended repository naming:

```text
lab-001-industrial-machine-control
lab-002-hmi-alarm-architecture
case-001-manufacturing-dfm
flagship-001-automated-cnc-cell
```

Use lowercase letters and hyphens in repository names.

---

# 4. Recommended Repository Structure

Standard project structure:

```text
project-name/
│
├── README.md
│
├── docs/
│   ├── 01-problem-definition.md
│   ├── 02-requirements.md
│   ├── 03-system-architecture.md
│   ├── 04-functional-description.md
│   ├── 05-design-decisions.md
│   ├── 06-verification-plan.md
│   ├── 07-test-results.md
│   └── 08-lessons-learned.md
│
├── src/
│
├── diagrams/
│
├── tests/
│
├── media/
│
└── references/
```

Project-specific folders may replace or supplement `src/`.

Examples:

```text
plc/
hmi/
mechanical/
electrical/
robot/
pneumatics/
python/
pcb/
networking/
```

Unused folders should not be created merely to satisfy the template.

---

# 5. README Standard

Every public project shall contain a `README.md`.

The README is the project's primary entry point.

It should provide enough information for a reviewer to understand the project within a few minutes.

## Required sections

### Project Title

Include:

* project ID,
* descriptive title.

Example:

```text
# LAB-001 — Industrial Machine Control Core
```

---

### Project Status

Example:

```text
Status: In Development
Version: v0.3
```

---

### Overview

Brief description of:

* the problem,
* the proposed system,
* why the project is relevant.

Recommended length:

Approximately 100–300 words.

---

### Objectives

List the primary technical objectives.

---

### Engineering Scope

Describe:

* included functionality,
* excluded functionality,
* assumptions.

---

### System Architecture

Provide a simplified architecture diagram or link to detailed documentation.

---

### Technologies

List technologies used only where they are actually relevant.

Example:

* Siemens TIA Portal V20
* S7-PLCSIM V20
* Structured Text
* Git

Avoid presenting software lists as the primary achievement.

---

### Key Engineering Evidence

Highlight major artefacts such as:

* state-machine architecture,
* electrical schematics,
* PLC source code,
* test report,
* CAD assembly.

---

### Verification Summary

Summarize:

* what was tested,
* overall result,
* known limitations.

---

### Documentation

Link to detailed documents.

---

### Project Limitations

Clearly state relevant limitations.

Examples:

* PLC simulated only
* no physical safety hardware used
* network behaviour partially simulated
* component sizing conceptual

---

# 6. Problem Definition Standard

Every technical project shall contain a clear problem definition.

Recommended content:

## Context

What system or technical environment does the problem belong to?

## Problem

What undesirable condition, limitation or engineering need exists?

## Objective

What should the project achieve?

## Stakeholders

Where relevant:

* operator,
* maintenance,
* production,
* engineering,
* higher-level control system.

## Constraints

Examples:

* available software,
* simulation limitations,
* hardware limitations,
* cost,
* interfaces,
* standards.

## Scope

Define what the project includes.

## Out of Scope

Define what the project deliberately does not attempt to solve.

---

# 7. Requirements Standard

Requirements shall be uniquely identifiable.

Recommended prefixes:

```text
FR — Functional Requirement
PR — Performance Requirement
IR — Interface Requirement
DR — Design Requirement
SR — Safety-related Requirement
CON — Constraint
```

Examples:

```text
FR-001
The controller shall provide Manual and Automatic operating modes.
```

```text
IR-001
The PLC shall expose machine-state information to the HMI.
```

```text
CON-001
The initial implementation shall be verified using S7-PLCSIM.
```

---

# 8. Requirement Writing Rules

Requirements should be:

* concise,
* understandable,
* technically meaningful,
* testable where practical,
* implementation-neutral where possible.

Prefer:

> The system shall prevent automatic cycle start unless all required permissives are satisfied.

Avoid:

> The PLC program should probably check all important signals before running.

Use **shall** for mandatory project requirements.

Use **should** only for desirable but non-mandatory behaviour.

---

# 9. Requirement Attributes

For larger projects, requirements may contain additional attributes.

Example:

| Field        | Example                                                                                  |
| ------------ | ---------------------------------------------------------------------------------------- |
| ID           | FR-014                                                                                   |
| Requirement  | The machine shall enter Fault state if cylinder extension exceeds the permitted timeout. |
| Priority     | Must                                                                                     |
| Source       | Project design                                                                           |
| Verification | Fault injection                                                                          |
| Status       | Verified                                                                                 |
| Test         | TC-023                                                                                   |

FLAGSHIP projects should use traceability more extensively than small labs.

---

# 10. Requirements Baseline

Before major implementation begins, create an initial requirements baseline.

Suggested milestone:

```text
v0.1 — Initial Requirements Baseline
```

Requirements may change after this point, but significant changes should be documented.

This demonstrates that the engineering process can evolve without pretending that every requirement was known perfectly from the start.

---

# 11. System Architecture Standard

Projects involving multiple functions or subsystems should contain an architecture description.

Architecture documentation should answer:

* What are the major components?
* What responsibility belongs to each?
* How do they interact?
* Which interfaces exist?
* Where are system boundaries?

Possible diagrams:

* functional block diagrams,
* system context diagrams,
* network diagrams,
* software architecture,
* electrical architecture.

---

# 12. Architecture Before Detail

The architecture should remain understandable without requiring detailed implementation knowledge.

Example:

```text
Operator
   │
   ↓
 HMI
   │
   ↓
 PLC
 ├──── Sensors
 ├──── Actuators
 └──── SCADA
```

Detailed tags, addresses and program blocks belong in lower-level documentation.

---

# 13. Functional Description Standard

Automated systems should include a functional description.

Recommended sections:

## Startup

What occurs when the system is initialized?

## Ready Condition

What conditions are necessary before operation?

## Manual Operation

What can the operator control manually?

## Automatic Operation

Describe the normal operating sequence.

## Stop

How is normal stopping handled?

## Fault

What happens when abnormal conditions are detected?

## Reset

Which conditions allow faults to be reset?

## Recovery

How does the system return to a known state?

## Shutdown

Where relevant, describe controlled shutdown.

---

# 14. State-Based Systems

Where state machines are used, provide:

* state diagram,
* state descriptions,
* transition conditions,
* invalid-transition behaviour.

Example table:

| Current State        | Condition               | Next State |
| -------------------- | ----------------------- | ---------- |
| INITIALIZING         | Initialization complete | READY      |
| READY                | Auto start accepted     | AUTOMATIC  |
| AUTOMATIC            | Stop requested          | STOPPING   |
| Any applicable state | Critical process fault  | FAULT      |

The implementation should be traceable to the state model.

---

# 15. Design Decision Standard

Important engineering decisions should be documented when alternatives reasonably exist.

Examples:

* state-machine structure,
* control philosophy,
* PLC programming language,
* sensor type,
* pneumatic architecture,
* network protocol,
* mechanical material,
* workholding method.

Recommended format:

```text
ADR-001 — State Machine Architecture

Context
What decision was required?

Options Considered
1. ...
2. ...
3. ...

Decision
Which option was selected?

Rationale
Why was it selected?

Consequences
What benefits and disadvantages result?
```

ADR means:

**Architecture / Engineering Decision Record**

The terminology may later be standardized further.

---

# 16. Source Code Standard

Source code should prioritize:

* readability,
* predictable structure,
* descriptive naming,
* modularity,
* maintainability.

Avoid unnecessary complexity intended primarily to appear sophisticated.

Comments should explain:

* intent,
* unusual behaviour,
* assumptions,
* important constraints.

Comments should not merely repeat obvious code.

---

# 17. PLC Naming Convention

A detailed PLC naming convention may later receive its own document.

Until then, use names that describe engineering meaning.

Prefer:

```text
xWorkpiecePresent
xClampExtended
xAutoStartRequest
eMachineState
tClampTimeout
```

Avoid:

```text
M1
Bit34
Temp3
FlagX
```

unless required by a specific platform or interface.

Naming conventions should remain consistent within each project.

---

# 18. Engineering Units

Quantities shall include engineering units where relevant.

Examples:

```text
Pressure: 6 bar
Timeout: 2.5 s
Speed: 1500 rpm
Voltage: 24 VDC
Distance: 125 mm
```

Avoid undocumented numerical constants.

Prefer named parameters.

Example:

```text
ClampTimeout = 2.5 s
```

rather than an unexplained literal timer value.

---

# 19. Interface Documentation Standard

Interfaces shall be documented where subsystem coordination is important.

Example PLC ↔ Robot interface:

| Signal        | Direction   | Meaning                        |
| ------------- | ----------- | ------------------------------ |
| RobotReady    | Robot → PLC | Robot available for production |
| StartCycle    | PLC → Robot | Request robot cycle            |
| RobotBusy     | Robot → PLC | Robot sequence active          |
| CycleComplete | Robot → PLC | Requested sequence complete    |
| RobotFault    | Robot → PLC | Robot unable to continue       |

Also document:

* expected sequence,
* timing assumptions,
* timeout behaviour,
* startup behaviour,
* reset logic.

---

# 20. Electrical Documentation Standard

Where electrical design is relevant, documentation should include appropriate subsets of:

* power architecture,
* control voltage,
* protection,
* PLC I/O,
* sensors,
* actuators,
* terminal connections,
* wire identification,
* component references,
* cable information.

A conceptual or simulated design shall be labelled accordingly.

Electrical documentation should not imply compliance certification unless such assessment has actually occurred.

---

# 21. Mechanical Documentation Standard

Mechanical projects should include relevant subsets of:

* CAD models,
* assemblies,
* drawings,
* dimensions,
* tolerances,
* materials,
* manufacturing method,
* surface requirements,
* DFM considerations,
* calculations,
* analysis.

Rendering quality is secondary to engineering clarity.

---

# 22. Simulation Standard

Simulation shall be treated as an engineering tool, not proof of physical performance by itself.

Simulation documentation should state:

* what is simulated,
* what model assumptions exist,
* which real-world effects are excluded,
* what behaviour is being verified.

Examples:

```text
Simulation verifies PLC state transitions but does not validate
physical actuator response time.
```

or:

```text
FEA results assume linear elastic material behaviour and idealized
fixture constraints.
```

---

# 23. Verification Standard

Every major requirement should have an appropriate verification method.

Possible methods:

* inspection,
* analysis,
* simulation,
* functional test,
* fault injection,
* calculation,
* physical measurement.

Verification answers:

> Did the implementation satisfy the requirement?

Validation answers:

> Does the resulting system solve the intended engineering problem?

These should not automatically be treated as identical.

---

# 24. Test Case Standard

Recommended test-case structure:

```text
Test ID:
TC-001

Requirement:
FR-001

Objective:
Verify Manual and Automatic mode selection.

Initial Conditions:
System initialized and no active fault.

Procedure:
1. Select Manual.
2. Verify machine reports Manual mode.
3. Select Automatic.
4. Verify machine reports Automatic mode.

Expected Result:
Both permitted modes shall be entered correctly.

Actual Result:
...

Result:
PASS / FAIL

Notes:
...
```

---

# 25. Negative Testing

Projects should deliberately test failure conditions where technically meaningful.

Examples:

* sensor never activates,
* contradictory sensors,
* communication loss,
* actuator timeout,
* robot unavailable,
* incorrect sequence,
* invalid mode request.

A robust system should demonstrate controlled behaviour when things go wrong.

---

# 26. Test Results

Tests shall not be altered retrospectively to make the project appear successful.

Failed tests are useful engineering evidence.

If a test fails:

1. Record the failure.
2. Investigate the cause.
3. Implement a correction if appropriate.
4. Repeat the test.
5. Preserve the development history through Git or project notes.

This is generally stronger evidence than presenting only flawless final results.

---

# 27. Verification Summary

At project completion, summarize verification status.

Example:

| Status             | Count |
| ------------------ | ----: |
| Passed             |    24 |
| Failed             |     0 |
| Partially Verified |     2 |
| Not Verified       |     1 |

Unverified requirements shall be explained.

---

# 28. Lessons Learned Standard

Every completed LAB, CASE and FLAGSHIP project shall contain a retrospective.

Minimum questions:

## What worked well?

Which technical choices were successful?

## What did not work?

Which approaches failed or caused unnecessary complexity?

## What was learned?

What new technical understanding was gained?

## What remains uncertain?

Where is additional testing or knowledge required?

## What would change in Revision 2?

How would the solution be improved if redesigned?

---

# 29. Research & References

Technical claims based on external material should reference appropriate sources.

Potential sources:

* manufacturer manuals,
* datasheets,
* standards,
* textbooks,
* technical papers,
* vendor documentation.

Zotero may be used as the research library.

Avoid using low-quality secondary sources when authoritative documentation is available.

---

# 30. Confidentiality & Professional Information

No portfolio project shall publish:

* proprietary employer code,
* confidential drawings,
* internal production data,
* customer information,
* restricted technical documentation,
* trade secrets.

Professional experience may be converted into portfolio evidence through:

* anonymization,
* recreated examples,
* synthetic data,
* generic representative systems,
* new designs based on the underlying engineering principle.

The project must not falsely imply that a recreated example is the original industrial implementation.

---

# 31. Project Status Model

Recommended project lifecycle:

```text
IDEA
 ↓
PLANNED
 ↓
ACTIVE
 ↓
IMPLEMENTED
 ↓
VERIFICATION
 ↓
VERIFIED
 ↓
PORTFOLIO VERIFIED
 ↓
PUBLIC
```

Definitions:

## IDEA

Potential project only.

## PLANNED

Problem and intended evidence are identified.

## ACTIVE

Engineering work has begun.

## IMPLEMENTED

Primary technical functionality exists.

## VERIFICATION

Formal testing is underway.

## VERIFIED

Defined technical verification has been completed.

## PORTFOLIO VERIFIED

Documentation and evidence meet portfolio quality standards.

## PUBLIC

Repository or project presentation has been intentionally published.

---

# 32. Definition of Ready

A project should enter **ACTIVE** status only when the following exist:

* project ID,
* title,
* problem statement,
* scope,
* initial requirements,
* primary competency targets,
* toolchain,
* intended deliverables,
* known major constraints.

For small technical labs this may be concise.

---

# 33. Definition of Done

A project reaches **VERIFIED** when:

* planned implementation is complete,
* important requirements have been tested,
* verification results are recorded,
* failures and deviations are documented,
* major technical limitations are known.

A project reaches **PORTFOLIO VERIFIED** when additionally:

* README is complete,
* project structure is clean,
* documentation is understandable,
* key artefacts are available,
* lessons learned are documented,
* sensitive information has been removed,
* claims accurately reflect what was actually implemented.

---

# 34. Versioning Standard

Recommended semantic-style maturity versions:

```text
v0.1 — Problem / Requirements
v0.2 — Architecture
v0.3 — Initial Implementation
v0.4 — Functional Implementation
v0.5 — Integration
v0.6 — Verification
v0.9 — Portfolio Review
v1.0 — Portfolio Verified Release
```

Intermediate versions may be used as required.

A version number represents project maturity, not merely elapsed time.

---

# 35. Git Commit Standard

Commits should describe meaningful changes.

Prefer:

```text
Add machine state transition requirements
Implement automatic mode state logic
Add clamp extension timeout handling
Document robot handshake interface
Fix reset behaviour after actuator timeout
Add verification results for FR-001 through FR-008
```

Avoid:

```text
stuff
update
test
changes
final
final2
final_final
```

Commits should generally be small enough that their purpose is understandable.

---

# 36. Branching

Complex branching is not required initially.

For early projects, a simple workflow is sufficient:

```text
main
```

with frequent meaningful commits.

Later projects may introduce:

```text
main
develop
feature/...
```

only when this genuinely improves workflow.

Portfolio engineering quality is more important than demonstrating unnecessarily complicated Git practices.

---

# 37. Release Standard

A `v1.0` project release should include:

* verified project state,
* final documentation,
* major technical artefacts,
* known limitations,
* release notes where useful.

Later improvements may use:

```text
v1.1
v1.2
v2.0
```

A major redesign should generally justify a major-version change.

---

# 38. Public Portfolio Quality Gate

Before making a project public, review the following.

## Technical

* Does the project function as claimed?
* Are major requirements verified?
* Are assumptions technically reasonable?
* Are limitations clear?

## Documentation

* Can a reviewer understand the project quickly?
* Are diagrams readable?
* Are file and folder names logical?
* Are important artefacts easy to find?

## Professional

* Is confidential information absent?
* Are claims accurate?
* Is terminology appropriate?
* Are references provided where useful?

## Presentation

* Does the README communicate the main result?
* Are screenshots/videos meaningful rather than decorative?
* Is unfinished work clearly labelled?

Only projects passing this review should be intentionally promoted as portfolio evidence.

---

# 39. Proportional Documentation Rule

The standard shall not be interpreted as requiring identical documentation volume for all projects.

### Small LAB

May use:

* README,
* requirements,
* architecture,
* test results,
* lessons learned.

### Larger LAB

May additionally use:

* functional description,
* design decisions,
* detailed test plan.

### FLAGSHIP

Should normally include:

* problem definition,
* requirements specification,
* system architecture,
* subsystem documentation,
* interface documentation,
* design decisions,
* technical drawings,
* software,
* verification plan,
* test reports,
* risk analysis where relevant,
* lessons learned.

The objective is engineering clarity, not documentation volume.

---

# 40. Portfolio-Wide Rule

A project should ideally demonstrate at least one of the following:

* new competency,
* stronger evidence for an existing competency,
* integration between disciplines,
* meaningful engineering decision-making,
* verification methodology.

If it demonstrates none of these, it probably does not need to become a portfolio project.

---

# 41. Standard Review

This standard is expected to evolve.

It should be reviewed after:

* LAB-001,
* the first fully completed technical lab,
* the first multidisciplinary project,
* FLAGSHIP-001.

Changes should simplify the workflow where possible without reducing evidence quality.

The portfolio should gradually develop its own engineering methodology based on practical experience.
