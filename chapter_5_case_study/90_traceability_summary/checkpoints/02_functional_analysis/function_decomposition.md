System name: main_landing_gear
Function source: landing-gear functional analysis material.
This file records the landing-gear functional decomposition stage.

Downstream logical modeling note:
- The activity flow below describes functional/physical response evidence, not external logical events.
- For Step7-Step9 logical modeling, only descent start at 0.0 s and touchdown at 0.23 s are external events.
- Compression, damping, rebound, stroke margin, and acceleration peak evaluation are physical functions or observation/evaluation functions.

# Landing-Gear Case Functional Model Supplement

This document provides the functional decomposition, activity flow, functional inputs and outputs, and requirement-to-function mapping used by the case study.

## Functional Decomposition

| Function ID | Function | Purpose | Related Use Case |
| --- | --- | --- | --- |
| `F-001` | Withstand vertical landing impact | Coordinate the complete drop/landing response scenario | `withstand_vertical_landing_impact` |
| `F-002` | Provide vertical aircraft support | Carry aircraft-side vertical load through the landing gear | `provide_vertical_support` |
| `F-003` | Establish runway contact support | Build tire-ground contact force after impact | `maintain_runway_contact_support` |
| `F-004` | Transfer wheel-end landing load | Transfer tire/wheel load into axle, sliding tube, and oleo path | `transfer_vertical_landing_load` |
| `F-005` | Absorb impact energy by oleo compression | Convert impact motion into shock strut compression | `absorb_vertical_impact_energy` |
| `F-006` | Dissipate impact energy by hydraulic damping | Reduce response peaks through velocity-dependent damping | `dissipate_impact_energy` |
| `F-007` | Control rebound response | Recover from compression through gas elastic response | `control_rebound_response` |
| `F-008` | Recover stable ground support | Reach stable post-impact support state | `recover_stable_support_state` |
| `F-009` | Evaluate acceleration peaks | Extract positive and negative acceleration peaks over the full simulation | case-study MDO objective |
| `F-010` | Evaluate stroke and bottoming margin | Check maximum oleo compression against allowable stroke | performance verification |
| `F-011` | Support inspection and servicing | Represent maintenance access and wear-item servicing needs | `permit_inspection_and_maintenance` |

## Activity Flow

```text
Start drop-test scenario
  -> release equivalent wheel-end load
  -> establish free-fall response
  -> detect tire-ground contact
  -> build tire deflection load
  -> transfer wheel-end load through axle/sliding tube
  -> compress oleo-pneumatic shock strut
  -> dissipate energy through hydraulic damping
  -> rebound through gas spring behavior
  -> recover stable ground support
  -> evaluate acceleration peaks and stroke response
```

## Functional Inputs and Outputs

| Function | Inputs | Outputs | Main Model Evidence |
| --- | --- | --- | --- |
| `F-001` | initial clearance, release force, ground height | landing impact sequence | `LandingImpactCondition`, `DropTestReleaseFixture` |
| `F-002` | oleo force, sprung mass | aircraft-side acceleration/support load | `EquivalentAirframeWheelMassAssembly.a_s`, `aircraft_vertical_support_load` |
| `F-003` | wheel-end displacement, tire radius, ground height | tire deflection, tire force | `MainGearTireWheelAssembly.tire_stiffness` |
| `F-004` | tire contact load, tire deflection load | axle load transfer, oleo piston load introduction | `WheelAxleAndSlidingTubeAssembly` |
| `F-005` | relative displacement `y_s - y_u` | oleo compression, oleo axial length | `ShockStrutSlidingJoint` |
| `F-006` | oleo compression speed | damping force | `HydraulicDampingChannel` |
| `F-007` | air chamber compression | air elastic recovery force | `ShockStrutGasChamber` |
| `F-008` | rebound completion event, response states | stable support state | `UpperCylinderAndMainFittingAssembly` |
| `F-009` | acceleration trajectory `piston_zdd_out(t)` | max positive acceleration, max negative acceleration magnitude | MDO evaluator |
| `F-010` | `oleo_compression(t)`, `max_piston_stroke` | stroke margin, bottoming flag | performance evaluator |
| `F-011` | maintenance actor and wear-sensitive items | inspection and servicing tasks | use-case model |

## Requirement-Function Mapping

| Requirement | Covered Functions |
| --- | --- |
| `MLG-REQ-000` | `F-001`, `F-002`, `F-005`, `F-006`, `F-007`, `F-008` |
| `MLG-REQ-001` | `F-002`, `F-003`, `F-004`, `F-005`, `F-006`, `F-007` |
| `MLG-REQ-002` | `F-002` |
| `MLG-REQ-003` | `F-003` |
| `MLG-REQ-004` | `F-004` |
| `MLG-REQ-005` | `F-005` |
| `MLG-REQ-006` | `F-006` |
| `MLG-REQ-007` | `F-007` |
| `MLG-REQ-009` | `F-009`, `F-010` |
| `MLG-REQ-010` | `F-009` |
| `MLG-REQ-011` | `F-010` |
| `MLG-REQ-012` | `F-010` |
| `MLG-REQ-013` | `F-008` |
| `MLG-REQ-014` | `F-003`, `F-005`, `F-006`, `F-007` |
| `MLG-REQ-015` | `F-003` |
| `MLG-REQ-016` | `F-005`, `F-007` |
| `MLG-REQ-017` | `F-007` |
| `MLG-REQ-018` | `F-006` |
| `MLG-REQ-020` | `F-004` |
| `MLG-REQ-021` | `F-001` |
| `MLG-REQ-025` | `F-011` |
