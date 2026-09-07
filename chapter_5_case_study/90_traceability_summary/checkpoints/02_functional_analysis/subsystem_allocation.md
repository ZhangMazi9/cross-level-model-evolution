System name: main_landing_gear
Subsystem analysis source: derived from the landing gear function model and RFLP artifacts.
This file is generated as a compact functional carrier map for Step7.

Purpose:
- Provide Step7 with physical-component and scenario-observation carriers for the landing gear case.
- Keep subsystem roles aligned with the function model without turning physical response phases into extra external logical events.

Functional carriers:
| Subsystem | Meaning | Covered functions | Downstream logic role |
| --- | --- | --- | --- |
| DropTestScenarioTimeline | Scenario timeline and high-level drop-test mode carrier | F-001 | Emits/propagates scenario phase tags for descent and touchdown observation. |
| ReleaseFixtureLogic | Release fixture and descent-start condition carrier | F-001 | Represents whether the drop/release condition is active after t=0.0 s. |
| AirframeEquivalentMassLogic | Aircraft-side equivalent mass/load support carrier | F-002, F-004, F-009 | Represents descent/load-transfer observation states corresponding to the airframe equivalent mass. |
| TireWheelAssemblyLogic | Wheel/tire contact and tire stiffness carrier | F-003, F-004, F-010 | Represents clearance tracking before touchdown and tire contact support after t=0.23 s. |
| GroundContactBoundaryLogic | Ground/runway contact boundary carrier | F-003 | Represents ground boundary monitoring and contact constraint activation. |
| OleoPneumaticStrutLogic | Oleo-pneumatic compression and gas recovery carrier | F-005, F-007, F-010 | Represents strut readiness and contact-response observation, not max-compression event scheduling. |
| HydraulicDampingLogic | Hydraulic damping path carrier | F-006 | Represents damping readiness/activation after touchdown as an observation state. |
| AccelerationObservationLogic | Acceleration/stroke response observation carrier | F-009, F-010 | Represents full-run observation and final evaluation support. |
| ScenarioTimelineSource | External scenario event source | F-001 | Provides exactly two external event markers: descent start at 0.0 s and touchdown at 0.23 s. |
| ScenarioEventMarkerRecorder | Traceability recorder | F-001, F-009 | Records logical event markers in CSV for validation. |

Important boundary:
- The function model includes physical activities such as free-fall response, tire-ground contact, oleo compression, hydraulic damping, rebound, and stable support recovery.
- These activities should inform physical and observation roles, but Step7-Step9 must not create additional external logical events for them.
- The logical model remains a compact scenario-time model with two external events and a 5.0 s observation horizon.

Recommended Step7 logical subsystem set:
- DropTestScenarioTimeline
- ReleaseFixtureLogic
- AirframeEquivalentMassLogic
- TireWheelAssemblyLogic
- GroundContactBoundaryLogic
- OleoPneumaticStrutLogic
- HydraulicDampingLogic
- AccelerationObservationLogic

Support/trace subsystems allowed for simulation implementation:
- ScenarioTimelineSource
- ScenarioEventMarkerRecorder
