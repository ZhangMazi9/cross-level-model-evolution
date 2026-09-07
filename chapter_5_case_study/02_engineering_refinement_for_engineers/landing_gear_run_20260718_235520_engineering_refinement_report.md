# Engineering Artifacts for Model Refinement

## 1. Summary

- Atomic refinement items: 182
- Engineering model objects: 19
- Interface couplings: 18
- Parameters: 28
- Scenarios/conditions: 91
- Human check issues: 644
- Consistency errors / warnings / auto-fixes: 0 / 307 / 213

## 2. Decomposition Candidates

| Decomposition ID | Source item | Needed | Strategy | Candidates | Reason | Need check |
|---|---|---|---|---|---|---|
| DEC-0001 | ScenarioTimelineSource | True | llm_realization_mapping | DEC-0001-C01 (physical_scenario_clock), DEC-0001-C02 (outgoing_signal_interface_group) | LLM refined one-to-many realization candidates from source evidence. | physical realization candidates are only placeholders until LLM/human review confirms implementable entities |
| DEC-0002 | DropTestScenarioTimeline | True | llm_realization_mapping | DEC-0002-C01 (physical_scenario_phase_tracker), DEC-0002-C02 (incoming_signal_interface_group) | LLM refined one-to-many realization candidates from source evidence. | physical realization candidates are only placeholders until LLM/human review confirms implementable entities |
| DEC-0003 | ReleaseFixtureLogic | True | llm_realization_mapping | DEC-0003-C01 (release_fixture_actuator), DEC-0003-C02 (incoming_signal_interface_group) | LLM refined one-to-many realization candidates from source evidence. | physical realization candidates are only placeholders until LLM/human review confirms implementable entities |
| DEC-0004 | AirframeEquivalentMassLogic | True | llm_realization_mapping | DEC-0004-C01 (airframe_mass_dynamics), DEC-0004-C02 (incoming_signal_interface_group) | LLM refined one-to-many realization candidates from source evidence. | physical realization candidates are only placeholders until LLM/human review confirms implementable entities |
| DEC-0005 | TireWheelAssemblyLogic | True | llm_realization_mapping | DEC-0005-C01 (tire_and_wheel_assembly), DEC-0005-C02 (descent_and_touchdown_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0006 | GroundContactBoundaryLogic | True | llm_realization_mapping | DEC-0006-C01 (ground_plane_test_fixture), DEC-0006-C02 (descent_and_touchdown_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0007 | OleoPneumaticStrutLogic | True | llm_realization_mapping | DEC-0007-C01 (oleo_pneumatic_strut_assembly), DEC-0007-C02 (descent_and_touchdown_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0008 | HydraulicDampingLogic | True | llm_realization_mapping | DEC-0008-C01 (hydraulic_damper_assembly), DEC-0008-C02 (descent_and_touchdown_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0009 | AccelerationObservationLogic | True | llm_realization_mapping | DEC-0009-C01 (accelerometer_and_telemetry_unit), DEC-0009-C02 (descent_and_touchdown_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0010 | ScenarioEventMarkerRecorder | True | llm_realization_mapping | DEC-0010-C01 (scenario_event_marker_recorder_controller), DEC-0010-C02 (event_marker_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0011 | PhysicalScenarioClock | False | llm_realization_mapping | DEC-0011-C01 (physical_scenario_clock_controller) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0012 | PhysicalScenarioPhaseTracker | False | llm_realization_mapping | DEC-0012-C01 (physical_scenario_phase_tracker_controller) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0013 | ReleaseFixtureActuator | False | llm_realization_mapping | DEC-0013-C01 (release_fixture_actuator) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0014 | GroundConstraintEnforcer | False | llm_realization_mapping | DEC-0014-C01 (ground_constraint_enforcer_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0015 | AirframeMassDynamics | False | llm_realization_mapping | DEC-0015-C01 (airframe_equivalent_mass) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0016 | TireContactDynamics | True | llm_realization_mapping | DEC-0016-C01 (tire_and_wheel_assembly), DEC-0016-C02 (tire_ground_contact_patch) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0017 | OleoGasSpringDynamics | False | llm_realization_mapping | DEC-0017-C01 (oleo_gas_spring_chamber) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0018 | HydraulicDamperDynamics | False | llm_realization_mapping | DEC-0018-C01 (hydraulic_damper_metering_system) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0019 | SensorAndTelemetrySystem | True | llm_realization_mapping | DEC-0019-C01 (telemetry_sensor_suite), DEC-0019-C02 (data_acquisition_unit) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0020 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> DropTestScenarioTimeline.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0020-C01 (descent_start_signal_connection) | LLM refined one-to-many realization candidates from source evidence. | concept relation to physical interface decomposition requires LLM/human review |
| DEC-0021 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> DropTestScenarioTimeline.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0021-C01 (signal_interface_for_touchdown_event_to_drop_test) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0022 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> ReleaseFixtureLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0022-C01 (signal_interface_for_descent_start_event_to_release_fixture) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0023 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> ReleaseFixtureLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0023-C01 (signal_interface_for_touchdown_event_to_release_fixture) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0024 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> AirframeEquivalentMassLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0024-C01 (signal_interface_for_descent_start_event_to_airframe_mass) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0025 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> AirframeEquivalentMassLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0025-C01 (signal_interface_for_touchdown_event_to_airframe_mass) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0026 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> TireWheelAssemblyLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0026-C01 (signal_interface_for_descent_start_event_to_tire_wheel_assembly) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0027 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> TireWheelAssemblyLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0027-C01 (signal_interface_for_touchdown_event_to_tire_wheel_assembly) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0028 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> GroundContactBoundaryLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0028-C01 (signal_interface_for_descent_start_event_to_ground_contact_boundary) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0029 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> GroundContactBoundaryLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0029-C01 (signal_interface_for_touchdown_event_to_ground_contact_boundary) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0030 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> OleoPneumaticStrutLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0030-C01 (signal_interface_for_descent_start_event_to_oleo_strut) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0031 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> OleoPneumaticStrutLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0031-C01 (scenariotimelinesource_to_oleopneumaticstrutlogic_touchdown_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0032 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> HydraulicDampingLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0032-C01 (scenariotimelinesource_to_hydraulicdampinglogic_descent_start_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0033 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> HydraulicDampingLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0033-C01 (scenariotimelinesource_to_hydraulicdampinglogic_touchdown_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0034 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> AccelerationObservationLogic.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0034-C01 (scenariotimelinesource_to_accelerationobservationlogic_descent_start_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0035 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> AccelerationObservationLogic.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0035-C01 (scenariotimelinesource_to_accelerationobservationlogic_touchdown_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0036 | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> ScenarioEventMarkerRecorder.LOGIC_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0036-C01 (descent_start_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0037 | ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> ScenarioEventMarkerRecorder.LOGIC_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0037-C01 (touchdown_event_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0038 | clock_inst.simulation_time -> scenario_clock_inst.simulation_time | False | llm_realization_mapping | DEC-0038-C01 (simulation_time_clock_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0039 | clock_inst.PHYS_EVT_DESCENT_START -> scenario_clock_inst.in_PHYS_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0039-C01 (physical_descent_start_trigger_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0040 | clock_inst.PHYS_EVT_TOUCHDOWN -> scenario_clock_inst.in_PHYS_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0040-C01 (physical_touchdown_trigger_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0041 | scenario_clock_inst.PHYS_EVT_DESCENT_START -> release_fixture_inst.PHYS_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0041-C01 (scenario_clock_to_release_fixture_descent_start_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0042 | scenario_clock_inst.PHYS_EVT_TOUCHDOWN -> ground_constraint_inst.PHYS_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0042-C01 (scenario_clock_to_ground_constraint_touchdown_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0043 | release_fixture_inst.release_force -> airframe_mass_inst.release_force | False | llm_realization_mapping | DEC-0043-C01 (release_fixture_to_airframe_release_force_load_path) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0044 | ground_constraint_inst.ground_height -> tire_contact_inst.ground_height | False | llm_realization_mapping | DEC-0044-C01 (ground_constraint_to_tire_contact_ground_height_contact_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0045 | airframe_mass_inst.y_s -> tire_contact_inst.y_s | False | llm_realization_mapping | DEC-0045-C01 (airframe_mass_to_tire_contact_position_kinematic_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0046 | airframe_mass_inst.y_s -> oleo_strut_inst.y_s | False | llm_realization_mapping | DEC-0046-C01 (airframe_to_oleo_strut_mounting_joint) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0047 | airframe_mass_inst.v_s -> oleo_strut_inst.v_s | False | llm_realization_mapping | DEC-0047-C01 (airframe_to_oleo_strut_kinematic_velocity_constraint) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0048 | tire_contact_inst.y_u -> oleo_strut_inst.y_u | False | llm_realization_mapping | DEC-0048-C01 (oleo_strut_to_tire_axle_joint) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0049 | tire_contact_inst.v_u -> oleo_strut_inst.v_u | False | llm_realization_mapping | DEC-0049-C01 (oleo_strut_to_tire_kinematic_velocity_constraint) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0050 | oleo_strut_inst.oleo_compression_speed -> hydraulic_damper_inst.oleo_compression_speed | False | llm_realization_mapping | DEC-0050-C01 (oleo_piston_cylinder_sliding_joint) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0051 | hydraulic_damper_inst.damping_force -> oleo_strut_inst.damping_force | False | llm_realization_mapping | DEC-0051-C01 (hydraulic_damper_to_oleo_strut_internal_load_path) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0052 | oleo_strut_inst.strut_force -> airframe_mass_inst.strut_force | False | llm_realization_mapping | DEC-0052-C01 (oleo_strut_to_airframe_upper_mounting_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0053 | oleo_strut_inst.strut_force -> tire_contact_inst.strut_force | False | llm_realization_mapping | DEC-0053-C01 (oleo_strut_to_tire_lower_axle_joint) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0054 | airframe_mass_inst.y_s -> telemetry_inst.y_s | True | llm_realization_mapping | DEC-0054-C01 (airframe_position_sensor_package), DEC-0054-C02 (airframe_sensor_to_telemetry_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0055 | tire_contact_inst.y_u -> telemetry_inst.y_u | True | llm_realization_mapping | DEC-0055-C01 (tire_position_sensor_package), DEC-0055-C02 (tire_sensor_to_telemetry_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0056 | airframe_mass_inst.v_s -> telemetry_inst.v_s | False | llm_realization_mapping | DEC-0056-C01 (airframe_mass_inst_v_s_to_telemetry_inst_v_s_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0057 | tire_contact_inst.v_u -> telemetry_inst.v_u | False | llm_realization_mapping | DEC-0057-C01 (tire_contact_inst_v_u_to_telemetry_inst_v_u_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0058 | airframe_mass_inst.piston_zdd_out -> telemetry_inst.piston_zdd_out | False | llm_realization_mapping | DEC-0058-C01 (airframe_mass_inst_piston_zdd_out_to_telemetry_inst_piston_zdd_out_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0059 | tire_contact_inst.tire_deflection -> telemetry_inst.tire_deflection | False | llm_realization_mapping | DEC-0059-C01 (tire_contact_inst_tire_deflection_to_telemetry_inst_tire_deflection_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0060 | oleo_strut_inst.oleo_compression -> telemetry_inst.oleo_compression | False | llm_realization_mapping | DEC-0060-C01 (oleo_strut_inst_oleo_compression_to_telemetry_inst_oleo_compression_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0061 | hydraulic_damper_inst.damping_force -> telemetry_inst.damping_force | False | llm_realization_mapping | DEC-0061-C01 (hydraulic_damper_damping_force_telemetry_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0062 | scenario_clock_inst.PHYS_EVT_DESCENT_START -> telemetry_inst.PHYS_EVT_DESCENT_START | False | llm_realization_mapping | DEC-0062-C01 (scenario_clock_descent_start_event_telemetry_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |
| DEC-0063 | scenario_clock_inst.PHYS_EVT_TOUCHDOWN -> telemetry_inst.PHYS_EVT_TOUCHDOWN | False | llm_realization_mapping | DEC-0063-C01 (scenario_clock_touchdown_event_telemetry_signal_interface) | LLM refined one-to-many realization candidates from source evidence. |  |

## 3. Model Object Cards

| ID | Name | Model role | Implementation method | Purpose | Inputs | Outputs | Key parameters | Priority | Need check | Source refs |
|---|---|---|---|---|---|---|---|---|---|---|
| MO-001 | MO-001 (ScenarioTimelineSource) | dynamic_response_model | 1D_physical_model, MBD | Generates time-based events (LOGIC_EVT_DESCENT_START, LOGIC_EVT_TOUCHDOWN) to drive and synchronize the drop test scenario timeline. |  | AccelerationObservationLogic.LOGIC_EVT_DESCENT_START, AccelerationObservationLogic.LOGIC_EVT_TOUCHDOWN, AirframeEquivalentMassLogic.LOGIC_EVT_DESCENT_START, AirframeEquivalentMassLogic.LOGIC_EVT_TOUCHDOWN, DropTestScenarioTimeline.LOGIC_EVT_DESCENT_START, DropTestScenarioTimeline.LOGIC_EVT_TOUCHDOWN, GroundContactBoundaryLogic.LOGIC_EVT_DESCENT_START, GroundContactBoundaryLogic.LOGIC_EVT_TOUCHDOWN, HydraulicDampingLogic.LOGIC_EVT_DESCENT_START, HydraulicDampingLogic.LOGIC_EVT_TOUCHDOWN, OleoPneumaticStrutLogic.LOGIC_EVT_DESCENT_START, OleoPneumaticStrutLogic.LOGIC_EVT_TOUCHDOWN, ReleaseFixtureLogic.LOGIC_EVT_DESCENT_START, ReleaseFixtureLogic.LOGIC_EVT_TOUCHDOWN, ScenarioEventMarkerRecorder.LOGIC_EVT_DESCENT_START, ScenarioEventMarkerRecorder.LOGIC_EVT_TOUCHDOWN, TireWheelAssemblyLogic.LOGIC_EVT_DESCENT_START, TireWheelAssemblyLogic.LOGIC_EVT_TOUCHDOWN |  | high | False | OBJ-0001, REL-0001, REL-0002, REL-0003, REL-0004, REL-0005, REL-0006, REL-0007, REL-0008, REL-0009, REL-0010, REL-0011, REL-0012, REL-0013, REL-0014, REL-0015, REL-0016, REL-0017, REL-0018, SCN-0001, SCN-0002, SCN-0003 |
| MO-002 | MO-002 (DropTestScenarioTimeline) | dynamic_response_model | 1D_physical_model, MBD | Receives timeline events and transitions through scenario states (PreScenario, DescentScenarioActive, TouchdownScenarioActive), acting as a central scenario manager. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN |  |  | high | True | OBJ-0002, REL-0001, REL-0002, SCN-0004, SCN-0005, SCN-0006, SCN-0007, SCN-0046, SCN-0047, SCN-0048, SCN-0049 |
| MO-003 | MO-003 (ReleaseFixtureLogic) | dynamic_response_model | 1D_physical_model, MBD, control_block_model | Models the release fixture behavior, transitioning through HoldingAircraft, Released, and InactiveAfterRelease states based on scenario events. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN |  |  | high | True | OBJ-0003, REL-0003, REL-0004, SCN-0008, SCN-0009, SCN-0010, SCN-0011, SCN-0050, SCN-0051, SCN-0052, SCN-0053 |
| MO-004 | MO-004 (AirframeEquivalentMassLogic) | dynamic_response_model | 1D_physical_model, MBD | Represents the airframe equivalent mass, managing states from initial support through descent to impact load transfer. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN |  | PA-001 (impact_load_transfer_active) | high | True | OBJ-0004, PAR-0001, REL-0005, REL-0006, SCN-0012, SCN-0013, SCN-0014, SCN-0015, SCN-0054, SCN-0055, SCN-0056, SCN-0057 |
| MO-005 | MO-005 (TireWheelAssemblyLogic) | geometry_definition_model | parametric_CAD | Represents the tire and wheel assembly, managing states from airborne through clearance tracking to contact establishment. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN |  |  | high | True | OBJ-0005, REL-0007, REL-0008, SCN-0016, SCN-0017, SCN-0018, SCN-0019, SCN-0058, SCN-0059, SCN-0060, SCN-0061 |
| MO-006 | MO-006 (GroundContactBoundaryLogic) | control_model | control_block_model | Logical component managing ground contact boundary states, transitioning from ground reference definition to clearance monitoring and active contact constraints upon descent and touchdown events. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN | contact_constraint_active |  | high | True | OBJ-0006, REL-0009, REL-0010, SCN-0020, SCN-0021, SCN-0022, SCN-0023, SCN-0062, SCN-0063, SCN-0064, SCN-0065 |
| MO-007 | MO-007 (OleoPneumaticStrutLogic) | control_model | control_block_model | Logical component representing the oleo-pneumatic strut behavior, tracking stroke availability and compression states during descent and touchdown. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN | compression_stroke_active, stroke_available |  | high | True | OBJ-0007, REL-0011, REL-0012, SCN-0024, SCN-0025, SCN-0026, SCN-0027, SCN-0066, SCN-0067, SCN-0068, SCN-0069 |
| MO-008 | MO-008 (HydraulicDampingLogic) | control_model | control_block_model | Logical component controlling hydraulic damping activation, transitioning from standby to relative motion monitoring and finally to activated damping upon touchdown. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN | damping_activated, relative_motion_monitoring | PA-002 (damping_activated) | high | True | OBJ-0008, PAR-0002, REL-0013, REL-0014, SCN-0028, SCN-0029, SCN-0030, SCN-0031, SCN-0070, SCN-0071, SCN-0072, SCN-0073 |
| MO-009 | MO-009 (AccelerationObservationLogic) | control_model | control_block_model | Logical component responsible for observing and recording acceleration baselines during descent and monitoring impact accelerations upon touchdown. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN |  |  | high | True | OBJ-0009, REL-0015, REL-0016, SCN-0032, SCN-0033, SCN-0034, SCN-0035, SCN-0074, SCN-0075, SCN-0076, SCN-0077 |
| MO-010 | MO-010 (ScenarioEventMarkerRecorder) | control_model | control_block_model | Logical component that continuously monitors and records scenario event markers throughout the simulation timeline. | ScenarioTimelineSource.LOGIC_EVT_DESCENT_START, ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN |  |  | high | True | OBJ-0010, REL-0017, REL-0018, SCN-0036 |
| MO-011 | MO-011 (PhysicalScenarioClock) | control_model | control_block_model | Master physical timing controller that broadcasts physical scenario time triggers. |  | physical_event_marker_clock | PA-017 (physical_event_marker_clock) | high | True | OBJ-0011, PAR-0022 |
| MO-012 | MO-012 (PhysicalScenarioPhaseTracker) | dynamic_response_model | 1D_physical_model, MBD | Tracks and broadcasts scenario phase events to domain subsystems. |  | scenario_phase_events |  | high | False | OBJ-0012 |
| MO-013 | MO-013 (ReleaseFixtureActuator) | dynamic_response_model | 1D_physical_model, MBD | Physical driver that drops the release force to zero to initiate free-fall. |  | release_force | PA-003 (initial_support_force) | high | True | OBJ-0013, PAR-0003 |
| MO-014 | MO-014 (GroundConstraintEnforcer) | dynamic_response_model | 1D_physical_model, MBD | Boundary actuator that activates the ground height constraint at touchdown. |  | ground_height_constraint | PA-004 (runway_elevation) | high | True | OBJ-0014, PAR-0004, SCN-0088 |
| MO-015 | MO-015 (AirframeMassDynamics) | dynamic_response_model | 1D_physical_model, MBD | Models the vertical inertial response of the supported airframe mass. | piston_force | piston_zdd_out, v_s_state, y_s_state | PA-005 (piston_zdd_out), PA-006 (M_s), PA-007 (g), PA-018 (v_s_state), PA-019 (y_s_state) | high | True | OBJ-0015, PAR-0005, PAR-0006, PAR-0007, PAR-0023, PAR-0024, SCN-0087 |
| MO-016 | MO-016 (TireContactDynamics) | dynamic_response_model | 1D_physical_model, MBD | Models the unsprung mass dynamics and pneumatic tire deflection upon ground contact. | penetration | v_u, y_u | PA-007 (g), PA-008 (M_u), PA-009 (K_t), PA-020 (penetration), PA-021 (v_u_state), PA-022 (y_u_state) | high | True | OBJ-0016, PAR-0008, PAR-0009, PAR-0010, PAR-0025, PAR-0026, PAR-0027, SCN-0089 |
| MO-017 | MO-017 (OleoGasSpringDynamics) | dynamic_response_model | 1D_physical_model, MBD | Models the pneumatic spring force and relative stroke of the shock strut. | damping_force | oleo_compression, oleo_compression_speed | PA-010 (damping_force), PA-011 (oleo_compression_speed), PA-012 (K_s), PA-023 (oleo_compression_state) | high | True | OBJ-0017, PAR-0011, PAR-0012, PAR-0013, PAR-0028, SCN-0090 |
| MO-018 | MO-018 (HydraulicDamperDynamics) | dynamic_response_model | 1D_physical_model, MBD | Models the hydraulic energy dissipation during strut compression and rebound. | oleo_compression_speed | damping_force | PA-010 (damping_force), PA-011 (oleo_compression_speed), PA-013 (C_v), PA-014 (C_v2) | high | True | OBJ-0018, PAR-0014, PAR-0015, PAR-0016, PAR-0017, SCN-0090 |
| MO-019 | MO-019 (SensorAndTelemetrySystem) | dynamic_response_model | 1D_physical_model, MBD | Captures and streams physical state variables for continuous monitoring and data logging. | damping_force, piston_zdd_out | measured_damping_force, measured_piston_zdd_out | PA-005 (piston_zdd_out), PA-010 (damping_force), PA-015 (measured_piston_zdd_out), PA-016 (measured_damping_force) | high | True | OBJ-0019, PAR-0018, PAR-0019, PAR-0020, PAR-0021, SCN-0091 |

## 4. Interface and Coupling Matrix

| From | To | Coupling type | Transferred variable | Modeling implication | Need check | Source refs |
|---|---|---|---|---|---|---|
| MO-001 (ScenarioTimelineSource) | MO-002 (DropTestScenarioTimeline) | signal_command | unknown | The source item represents an explicit logical producer-consumer relation for the descent start event between ScenarioTimelineSource and DropTestScenarioTimeline. | True | REL-0001 |
| MO-001 (ScenarioTimelineSource) | MO-002 (DropTestScenarioTimeline) | signal_command | unknown | The source item represents an explicit logical producer-consumer relation for the touchdown event between ScenarioTimelineSource and DropTestScenarioTimeline. | True | REL-0002 |
| MO-001 (ScenarioTimelineSource) | MO-003 (ReleaseFixtureLogic) | signal_command | unknown | The source item represents an explicit logical producer-consumer relation for the descent start event between ScenarioTimelineSource and ReleaseFixtureLogic. | True | REL-0003 |
| MO-001 (ScenarioTimelineSource) | MO-003 (ReleaseFixtureLogic) | signal_command | unknown | The source item represents an explicit logical producer-consumer relation for the touchdown event between ScenarioTimelineSource and ReleaseFixtureLogic. | True | REL-0004 |
| MO-001 (ScenarioTimelineSource) | MO-004 (AirframeEquivalentMassLogic) | signal_command | unknown | The source item represents an explicit logical producer-consumer relation for the descent start event between ScenarioTimelineSource and AirframeEquivalentMassLogic. | True | REL-0005 |
| MO-001 (ScenarioTimelineSource) | MO-004 (AirframeEquivalentMassLogic) | signal_command | unknown | The source item represents an explicit logical event signal (LOGIC_EVT_TOUCHDOWN) from the ScenarioTimelineSource to the AirframeEquivalentMassLogic, establishing a clear producer-consumer coupling for touchdown timing. | True | REL-0006 |
| MO-001 (ScenarioTimelineSource) | MO-005 (TireWheelAssemblyLogic) | signal_command | unknown | The source item represents an explicit logical event signal (LOGIC_EVT_DESCENT_START) from the ScenarioTimelineSource to the TireWheelAssemblyLogic, establishing a clear producer-consumer coupling for descent initiation. | True | REL-0007 |
| MO-001 (ScenarioTimelineSource) | MO-005 (TireWheelAssemblyLogic) | signal_command | unknown | The source item represents an explicit logical event signal (LOGIC_EVT_TOUCHDOWN) from the ScenarioTimelineSource to the TireWheelAssemblyLogic, establishing a clear producer-consumer coupling for touchdown timing. | True | REL-0008 |
| MO-001 (ScenarioTimelineSource) | MO-006 (GroundContactBoundaryLogic) | signal_command | unknown | The source item represents an explicit logical event signal (LOGIC_EVT_DESCENT_START) from the ScenarioTimelineSource to the GroundContactBoundaryLogic, establishing a clear producer-consumer coupling for descent initiation. | True | REL-0009 |
| MO-001 (ScenarioTimelineSource) | MO-006 (GroundContactBoundaryLogic) | signal_command | unknown | The source item represents an explicit logical event signal (LOGIC_EVT_TOUCHDOWN) from the ScenarioTimelineSource to the GroundContactBoundaryLogic, establishing a clear producer-consumer coupling for touchdown timing. | True | REL-0010 |
| MO-001 (ScenarioTimelineSource) | MO-007 (OleoPneumaticStrutLogic) | signal_command | unknown | The source item explicitly defines a logical producer-consumer relation where the ScenarioTimelineSource emits a logical event signal to trigger the OleoPneumaticStrutLogic. | True | REL-0011 |
| MO-001 (ScenarioTimelineSource) | MO-007 (OleoPneumaticStrutLogic) | signal_command | unknown | The source item explicitly defines a logical producer-consumer relation where the ScenarioTimelineSource emits a logical event signal to trigger the OleoPneumaticStrutLogic. | True | REL-0012 |
| MO-001 (ScenarioTimelineSource) | MO-008 (HydraulicDampingLogic) | signal_command | unknown | The source item explicitly defines a logical producer-consumer relation where the ScenarioTimelineSource emits a logical event signal to trigger the HydraulicDampingLogic. | True | REL-0013 |
| MO-001 (ScenarioTimelineSource) | MO-008 (HydraulicDampingLogic) | signal_command | unknown | The source item explicitly defines a logical producer-consumer relation where the ScenarioTimelineSource emits a logical event signal to trigger the HydraulicDampingLogic. | True | REL-0014 |
| MO-001 (ScenarioTimelineSource) | MO-009 (AccelerationObservationLogic) | signal_command | unknown | The source item explicitly defines a logical producer-consumer relation where the ScenarioTimelineSource emits a logical event signal to trigger the AccelerationObservationLogic. | True | REL-0015 |
| MO-001 (ScenarioTimelineSource) | MO-009 (AccelerationObservationLogic) | signal_command | unknown | Explicit logical producer-consumer relation for the touchdown event. | True | REL-0016 |
| MO-001 (ScenarioTimelineSource) | MO-010 (ScenarioEventMarkerRecorder) | signal_command | unknown | Explicit logical producer-consumer relation for the descent start event. | True | REL-0017 |
| MO-001 (ScenarioTimelineSource) | MO-010 (ScenarioEventMarkerRecorder) | signal_command | unknown | Explicit logical producer-consumer relation for the touchdown event marker. | True | REL-0018 |

## 5. Parameter Dictionary

| Name | Meaning | Unit | Initial value | Range | Used in | Parameter role | Need check | Source refs |
|---|---|---|---|---|---|---|---|---|
| PA-001 (impact_load_transfer_active) | Logical output parameter indicating if impact load transfer is active | dimensionless | unknown | unknown | MO-004 (AirframeEquivalentMassLogic) | performance_metric | True | PAR-0001 |
| PA-002 (damping_activated) | Logical output parameter indicating if hydraulic damping is activated | dimensionless | unknown | unknown | MO-008 (HydraulicDampingLogic) | performance_metric | True | PAR-0002 |
| PA-003 (initial_support_force) | Force required to hold the equivalent airframe mass in static equilibrium | N | 9810.0 | unknown | MO-013 (ReleaseFixtureActuator) | fixed_parameter | True | PAR-0003 |
| PA-004 (runway_elevation) | Vertical position of the runway surface | m | 0.0 | unknown | MO-014 (GroundConstraintEnforcer) | fixed_parameter | True | PAR-0004 |
| PA-005 (piston_zdd_out) | Vertical acceleration of the equivalent airframe mass | m/s2 | unknown | unknown | MO-015 (AirframeMassDynamics) | performance_metric | True | PAR-0005 |
| PA-006 (M_s) | Equivalent airframe mass | kg | 1000.0 | >0 | MO-015 (AirframeMassDynamics) | design_variable | True | PAR-0006 |
| PA-007 (g) | Gravitational acceleration | m/s^2 | 9.81 | >0 | MO-015 (AirframeMassDynamics) | fixed_parameter | True | PAR-0007 |
| PA-008 (M_u) | Unsprung wheel mass | kg | 300.0 | >0 | MO-016 (TireContactDynamics) | design_variable | True | PAR-0008 |
| PA-009 (K_t) | Tire stiffness approximation | N/m | 1700000.0 | >0 | MO-016 (TireContactDynamics) | design_variable | True | PAR-0009 |
| PA-007 (g) | Gravitational acceleration | m/s^2 | 9.81 | >0 | MO-016 (TireContactDynamics) | fixed_parameter | True | PAR-0010 |
| PA-010 (damping_force) | Hydraulic damping force input to the OleoGasSpringDynamics component. | unknown | unknown | unknown | MO-017 (OleoGasSpringDynamics) | design_variable | True | PAR-0011 |
| PA-011 (oleo_compression_speed) | Relative velocity of the shock strut sliding joint, output from the OleoGasSpringDynamics component. | unknown | unknown | unknown | MO-017 (OleoGasSpringDynamics) | design_variable | True | PAR-0012 |
| PA-012 (K_s) | Gas spring stiffness coefficient. | unknown | 100000.0 | unknown | MO-017 (OleoGasSpringDynamics) | design_variable | True | PAR-0013 |
| PA-011 (oleo_compression_speed) | Relative velocity of the shock strut, input to the HydraulicDamperDynamics component. | unknown | unknown | unknown | MO-018 (HydraulicDamperDynamics) | design_variable | True | PAR-0014 |
| PA-010 (damping_force) | Force generated by hydraulic fluid displacement, output from the HydraulicDamperDynamics component. | unknown | unknown | unknown | MO-018 (HydraulicDamperDynamics) | design_variable | True | PAR-0015 |
| PA-013 (C_v) | Linear oleo damping coefficient | N/(m/s) | 153475.1727204978 | engineering range to be confirmed | MO-018 (HydraulicDamperDynamics) | calibration_parameter | True | PAR-0016 |
| PA-014 (C_v2) | Quadratic oleo damping coefficient | N/(m/s)^2 | 1.9602485837391784 | engineering range to be confirmed | MO-018 (HydraulicDamperDynamics) | calibration_parameter | True | PAR-0017 |
| PA-005 (piston_zdd_out) | Airframe vertical acceleration | unknown | unknown | unknown | MO-019 (SensorAndTelemetrySystem) | fixed_parameter | True | PAR-0018 |
| PA-010 (damping_force) | Damping force | unknown | unknown | unknown | MO-019 (SensorAndTelemetrySystem) | fixed_parameter | True | PAR-0019 |
| PA-015 (measured_piston_zdd_out) | Measured airframe acceleration | unknown | unknown | unknown | MO-019 (SensorAndTelemetrySystem) | performance_metric | True | PAR-0020 |
| PA-016 (measured_damping_force) | Measured damping force output from the SensorAndTelemetrySystem. | N | unknown | unknown | MO-019 (SensorAndTelemetrySystem) | performance_metric | True | PAR-0021 |
| PA-017 (physical_event_marker_clock) | Continuous time state for the PhysicalScenarioClock. | s | 0.0 | unknown | MO-011 (PhysicalScenarioClock) | fixed_parameter | True | PAR-0022 |
| PA-018 (v_s_state) | Auto-injected internal dynamic state for the v_s output port in AirframeMassDynamics. | m/s | 0.0 | unknown | MO-015 (AirframeMassDynamics) | uncertain_parameter | True | PAR-0023 |
| PA-019 (y_s_state) | Auto-injected internal dynamic state for the y_s output port in AirframeMassDynamics. | m | 0.0 | unknown | MO-015 (AirframeMassDynamics) | uncertain_parameter | True | PAR-0024 |
| PA-020 (penetration) | Intermediate variable for ground penetration in TireContactDynamics. | m | 0.0 | unknown | MO-016 (TireContactDynamics) | uncertain_parameter | True | PAR-0025 |
| PA-021 (v_u_state) | Auto-injected internal dynamic state for output port v_u. | unknown | 0.0 | unknown | MO-016 (TireContactDynamics) | uncertain_parameter | True | PAR-0026 |
| PA-022 (y_u_state) | Auto-injected internal dynamic state for output port y_u. | unknown | 0.0 | unknown | MO-016 (TireContactDynamics) | uncertain_parameter | True | PAR-0027 |
| PA-023 (oleo_compression_state) | Auto-injected internal dynamic state for output port oleo_compression. | unknown | 0.0 | unknown | MO-017 (OleoGasSpringDynamics) | uncertain_parameter | True | PAR-0028 |

## 6. Simulation Scenario Matrix

| Name | Purpose | Inputs | Conditions | Metrics | Related models | Priority | Need check | Source refs |
|---|---|---|---|---|---|---|---|---|
| SC-001 (BeforeSchedule to EvtDescentStart Transition Scenario) | Transition from BeforeSchedule to EvtDescentStart triggered by timeover, emitting LOGIC_EVT_DESCENT_START. |  | timeover |  | MO-001 (ScenarioTimelineSource) | high | True | SCN-0001 |
| SC-002 (EvtDescentStart to EvtTouchdown Transition Scenario) | Transition from EvtDescentStart to EvtTouchdown triggered by timeover, emitting LOGIC_EVT_TOUCHDOWN. |  | timeover |  | MO-001 (ScenarioTimelineSource) | high | True | SCN-0002 |
| SC-003 (EvtTouchdown End State Transition Scenario) | Transition from EvtTouchdown to EvtTouchdown triggered by timeover, clearing LOGIC_EVT_TOUCHDOWN. |  | timeover |  | MO-001 (ScenarioTimelineSource) | high | True | SCN-0003 |
| SC-004 (PreScenario to DescentScenarioActive Transition Scenario) | Transition from PreScenario to DescentScenarioActive triggered by receiving LOGIC_EVT_DESCENT_START, activating descent_scenario_active. |  | receive LOGIC_EVT_DESCENT_START |  | MO-002 (DropTestScenarioTimeline) | high | True | SCN-0004 |
| SC-005 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition Scenario) | Transition from DescentScenarioActive to TouchdownScenarioActiveEntry triggered by receiving LOGIC_EVT_TOUCHDOWN, activating touchdown_scenario_active. |  | receive LOGIC_EVT_TOUCHDOWN |  | MO-002 (DropTestScenarioTimeline) | high | True | SCN-0005 |
| SC-006 (Touchdown Scenario Active Entry Phase) | Time-based transition from TouchdownScenarioActiveEntry to TouchdownScenarioActive, activating the touchdown scenario. |  | DropTestScenarioTimeline.TouchdownScenarioActiveEntry.transition[0] |  | MO-002 (DropTestScenarioTimeline) | high | True | SCN-0006 |
| SC-007 (Touchdown Scenario Active Phase) | Continuous time-based trigger in the TouchdownScenarioActive state, maintaining the touchdown scenario active output. |  | DropTestScenarioTimeline.TouchdownScenarioActive.transition[0] |  | MO-002 (DropTestScenarioTimeline) | high | True | SCN-0007 |
| SC-008 (Aircraft Holding and Release Phase) | Event-driven transition from HoldingAircraft to Released upon receiving LOGIC_EVT_DESCENT_START, triggering the release fixture. |  | ReleaseFixtureLogic.HoldingAircraft.transition[0] |  | MO-003 (ReleaseFixtureLogic) | high | True | SCN-0008 |
| SC-009 (Post-Release Touchdown Phase) | Event-driven transition from Released to InactiveAfterRelease upon receiving LOGIC_EVT_TOUCHDOWN, deactivating the release fixture. |  | ReleaseFixtureLogic.Released.transition[0] |  | MO-003 (ReleaseFixtureLogic) | high | True | SCN-0009 |
| SC-010 (Release Fixture Inactive Transition Phase) | Time-based transition from InactiveAfterRelease to TouchdownScenarioActive, maintaining the release fixture inactive state. |  | ReleaseFixtureLogic.InactiveAfterRelease.transition[0] |  | MO-003 (ReleaseFixtureLogic) | high | True | SCN-0010 |
| SC-011 (Release Fixture Logic - Touchdown Scenario Active) | Maintains the release fixture in an inactive state during the touchdown scenario via a time-over trigger. |  | ReleaseFixtureLogic.TouchdownScenarioActive.transition[0] |  | MO-003 (ReleaseFixtureLogic) | high | True | SCN-0011 |
| SC-012 (Airframe Equivalent Mass Logic - Supported Initial Condition to Released Descent) | Transitions from supported initial condition to released descent upon receiving the descent start event, activating airframe descent. | descent start event | AirframeEquivalentMassLogic.SupportedInitialCondition.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | high | True | SCN-0012 |
| SC-013 (Airframe Equivalent Mass Logic - Released Descent to Impact Load Transfer) | Transitions from released descent to impact load transfer upon receiving the touchdown event. | touchdown event | AirframeEquivalentMassLogic.ReleasedDescent.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | high | True | SCN-0013 |
| SC-014 (Airframe Equivalent Mass Logic - Impact Load Transfer to Touchdown Scenario Active) | Transitions from impact load transfer to touchdown scenario active after a time-over condition. |  | AirframeEquivalentMassLogic.ImpactLoadTransfer.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | high | True | SCN-0014 |
| SC-015 (Airframe Equivalent Mass Logic - Touchdown Scenario Active) | Maintains the touchdown scenario active state after a time-over condition. |  | AirframeEquivalentMassLogic.TouchdownScenarioActive.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | high | True | SCN-0015 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | Transition from AirborneNoContact to ClearanceTracking triggered by LOGIC_EVT_DESCENT_START | LOGIC_EVT_DESCENT_START | state == AirborneNoContact, trigger == receive |  | MO-005 (TireWheelAssemblyLogic) | high | True | SCN-0016 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | Transition from ClearanceTracking to ContactEstablished triggered by LOGIC_EVT_TOUCHDOWN | LOGIC_EVT_TOUCHDOWN | state == ClearanceTracking, trigger == receive |  | MO-005 (TireWheelAssemblyLogic) | high | True | SCN-0017 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | Transition from ContactEstablished to TouchdownScenarioActive triggered by a timeover condition |  | state == ContactEstablished, trigger == timeover |  | MO-005 (TireWheelAssemblyLogic) | high | True | SCN-0018 |
| SC-019 (TouchdownScenarioActive Self-Transition) | Self-transition of TouchdownScenarioActive state triggered by a timeover condition |  | state == TouchdownScenarioActive, trigger == timeover |  | MO-005 (TireWheelAssemblyLogic) | high | True | SCN-0019 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | Transition from GroundReferenceDefined to ClearanceBoundaryMonitoring triggered by LOGIC_EVT_DESCENT_START | LOGIC_EVT_DESCENT_START | state == GroundReferenceDefined, trigger == receive |  | MO-006 (GroundContactBoundaryLogic) | high | True | SCN-0020 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | Transition from ClearanceBoundaryMonitoring to ContactConstraintActive triggered by LOGIC_EVT_TOUCHDOWN. | LOGIC_EVT_TOUCHDOWN | GroundContactBoundaryLogic.ClearanceBoundaryMonitoring.transition[0] | contact_constraint_active=1 | MO-006 (GroundContactBoundaryLogic) | high | True | SCN-0021 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | Transition from ContactConstraintActive to TouchdownScenarioActive triggered by a timeover event. |  | GroundContactBoundaryLogic.ContactConstraintActive.transition[0] | contact_constraint_active=1 | MO-006 (GroundContactBoundaryLogic) | high | True | SCN-0022 |
| SC-019 (TouchdownScenarioActive Self-Transition) | Self-transition in TouchdownScenarioActive state triggered by a timeover event, maintaining contact constraint active. |  | GroundContactBoundaryLogic.TouchdownScenarioActive.transition[0] | contact_constraint_active=1 | MO-006 (GroundContactBoundaryLogic) | high | True | SCN-0023 |
| SC-023 (ExtendedStroke to StrokeAvailable Transition) | Transition from ExtendedStroke to StrokeAvailable triggered by LOGIC_EVT_DESCENT_START, indicating stroke availability. | LOGIC_EVT_DESCENT_START | OleoPneumaticStrutLogic.ExtendedStroke.transition[0] | stroke_available=1 | MO-007 (OleoPneumaticStrutLogic) | high | True | SCN-0024 |
| SC-024 (StrokeAvailable to CompressionStroke Transition) | Transition from StrokeAvailable to CompressionStroke triggered by LOGIC_EVT_TOUCHDOWN, initiating the compression stroke. | LOGIC_EVT_TOUCHDOWN | OleoPneumaticStrutLogic.StrokeAvailable.transition[0] | compression_stroke_active=1 | MO-007 (OleoPneumaticStrutLogic) | high | True | SCN-0025 |
| SC-025 (OleoPneumaticStrutLogic.CompressionStroke) | Transition from CompressionStroke to TouchdownScenarioActive triggered by timeover, setting compression_stroke_active to 1. |  | true |  | MO-007 (OleoPneumaticStrutLogic) | high | True | SCN-0026 |
| SC-026 (OleoPneumaticStrutLogic.TouchdownScenarioActive) | Self-loop transition in TouchdownScenarioActive triggered by timeover, maintaining compression_stroke_active at 1. |  | true |  | MO-007 (OleoPneumaticStrutLogic) | high | True | SCN-0027 |
| SC-027 (HydraulicDampingLogic.DampingStandby) | Transition from DampingStandby to RelativeMotionMonitoring triggered by receiving LOGIC_EVT_DESCENT_START, activating relative_motion_monitoring. | LOGIC_EVT_DESCENT_START | true |  | MO-008 (HydraulicDampingLogic) | high | True | SCN-0028 |
| SC-028 (HydraulicDampingLogic.RelativeMotionMonitoring) | Transition from RelativeMotionMonitoring to DampingActivated triggered by receiving LOGIC_EVT_TOUCHDOWN, activating damping. | LOGIC_EVT_TOUCHDOWN | true |  | MO-008 (HydraulicDampingLogic) | high | True | SCN-0029 |
| SC-029 (HydraulicDampingLogic.DampingActivated) | Transition from DampingActivated to TouchdownScenarioActive triggered by timeover, maintaining damping_activated. |  | true |  | MO-008 (HydraulicDampingLogic) | high | True | SCN-0030 |
| SC-030 (HydraulicDampingLogic.TouchdownScenarioActive) | Timeover self-loop transition within TouchdownScenarioActive state of HydraulicDampingLogic, maintaining state and activating damping output. | simulation_time | timeover | damping_output_activation | MO-008 (HydraulicDampingLogic) | high | True | SCN-0031 |
| SC-031 (AccelerationObservationLogic.ObservationIdle) | Transition from ObservationIdle to BaselineAccelerationRecording triggered by LOGIC_EVT_DESCENT_START, initiating baseline acceleration recording. | LOGIC_EVT_DESCENT_START | receive LOGIC_EVT_DESCENT_START | baseline_acceleration_recording_initiation | MO-009 (AccelerationObservationLogic) | high | True | SCN-0032 |
| SC-032 (AccelerationObservationLogic.BaselineAccelerationRecording) | Transition from BaselineAccelerationRecording to ImpactAccelerationMonitoring triggered by LOGIC_EVT_TOUCHDOWN, initiating impact monitoring. | LOGIC_EVT_TOUCHDOWN | receive LOGIC_EVT_TOUCHDOWN | impact_monitoring_initiation | MO-009 (AccelerationObservationLogic) | high | True | SCN-0033 |
| SC-033 (AccelerationObservationLogic.ImpactAccelerationMonitoring) | Timeover transition from ImpactAccelerationMonitoring to TouchdownScenarioActive, maintaining impact monitoring output. | simulation_time | timeover | impact_monitoring_output_maintenance | MO-009 (AccelerationObservationLogic) | high | True | SCN-0034 |
| SC-034 (AccelerationObservationLogic.TouchdownScenarioActive) | Timeover self-loop transition within TouchdownScenarioActive state, maintaining impact acceleration monitoring output. | simulation_time | timeover | impact_acceleration_monitoring_output | MO-009 (AccelerationObservationLogic) | high | True | SCN-0035 |
| SC-035 (Monitoring State Timeover Event) | Timeover transition within the ScenarioEventMarkerRecorder Monitoring state, triggered by descent start or touchdown events. |  | ScenarioEventMarkerRecorder.Monitoring.transition[0] |  | MO-010 (ScenarioEventMarkerRecorder) | medium | True | SCN-0036 |
| SC-036 (MainLandingGearDropTest Simulation) | Physical model simulation run for the main landing gear drop test with a stop time of 5.23 seconds. |  | stop_time = 5.23s |  |  | high | True | SCN-0037 |
| SC-037 (MainLandingGearDropTest Physical Context) | Vertical landing impact drop-test scenario for main landing gear, evaluating shock absorption, damping, and rebound over a 5.0s horizon. |  | simulation_horizon = 5.0s | damping, rebound, shock absorption |  | high | True | SCN-0038 |
| SC-038 (Vertical Landing Impact Condition) | Specified vertical landing impact and drop-test conditions under which the main landing gear shall provide safe vertical support and shock absorption. |  | req0 | safe vertical support, shock absorption |  | high | True | SCN-0039 |
| SC-039 (Runway Contact Condition) | Specified runway contact condition under which the wheel and tire assembly shall maintain stable contact support with the runway surface. |  | req23 | stable contact support |  | high | True | SCN-0040 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | Evaluate structural members, tire, wheel assembly, and shock strut under repeated vertical load-cycle conditions to ensure no loss of capability. |  | req24 | loss of capability |  | high | True | SCN-0041 |
| SC-041 (PreScenario) | Define the initial state of the system with no physical motion before descent. |  | scenario_states[0] |  |  | high | True | SCN-0042 |
| SC-042 (DescentStart) | Simulate the aircraft release and the beginning of free-fall descent with strut extended and tire airborne. |  | scenario_states[1] |  |  | high | True | SCN-0043 |
| SC-043 (Touchdown) | Simulate the touchdown event where the tire contacts the ground, oleo compresses, and damping activates to observe acceleration peaks. |  | scenario_states[2] | acceleration peaks |  | high | True | SCN-0044 |
| SC-044 (Allowed Degradation Condition) | Evaluate the system's performance when key buffering components experience allowed performance deviation, wear, or degradation. |  | req28 |  |  | high | True | SCN-0045 |
| SC-045 (PreScenario to DescentScenarioActive Transition) | Trigger the start of the descent scenario via LOGIC_EVT_DESCENT_START. | LOGIC_EVT_DESCENT_START | DropTestScenarioTimeline.PreScenario.transition[0] | Descent scenario active state reached | MO-002 (DropTestScenarioTimeline) | medium | True | SCN-0046 |
| SC-046 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition) | Trigger the start of the touchdown scenario via LOGIC_EVT_TOUCHDOWN. | LOGIC_EVT_TOUCHDOWN | DropTestScenarioTimeline.DescentScenarioActive.transition[0] | Touchdown scenario entry state reached | MO-002 (DropTestScenarioTimeline) | medium | True | SCN-0047 |
| SC-047 (TouchdownScenarioActiveEntry to TouchdownScenarioActive Transition) | Transition from TouchdownScenarioActiveEntry to TouchdownScenarioActive based on time. |  | DropTestScenarioTimeline.TouchdownScenarioActiveEntry.transition[0] | Touchdown scenario active state reached | MO-002 (DropTestScenarioTimeline) | medium | True | SCN-0048 |
| SC-019 (TouchdownScenarioActive Self-Transition) | Maintain or update the TouchdownScenarioActive state via a time-based self-transition. |  | DropTestScenarioTimeline.TouchdownScenarioActive.transition[0] | Touchdown scenario active state maintained | MO-002 (DropTestScenarioTimeline) | medium | True | SCN-0049 |
| SC-048 (HoldingAircraft to Released Transition) | Trigger the release of the aircraft fixture via LOGIC_EVT_DESCENT_START. | LOGIC_EVT_DESCENT_START | ReleaseFixtureLogic.HoldingAircraft.transition[0] | Aircraft fixture released | MO-003 (ReleaseFixtureLogic) | medium | True | SCN-0050 |
| SC-049 (ReleaseFixtureLogic.Released to InactiveAfterRelease on LOGIC_EVT_TOUCHDOWN) | Logical transition from Released to InactiveAfterRelease triggered by receiving LOGIC_EVT_TOUCHDOWN. | LOGIC_EVT_TOUCHDOWN | ReleaseFixtureLogic.Released.transition[0] |  | MO-003 (ReleaseFixtureLogic) | medium | True | SCN-0051 |
| SC-050 (ReleaseFixtureLogic.InactiveAfterRelease to TouchdownScenarioActive on timeover) | Logical transition from InactiveAfterRelease to TouchdownScenarioActive triggered by a timeover event. | timeover | ReleaseFixtureLogic.InactiveAfterRelease.transition[0] |  | MO-003 (ReleaseFixtureLogic) | medium | True | SCN-0052 |
| SC-051 (ReleaseFixtureLogic.TouchdownScenarioActive self-transition on timeover) | Logical self-transition in TouchdownScenarioActive state triggered by a timeover event. | timeover | ReleaseFixtureLogic.TouchdownScenarioActive.transition[0] |  | MO-003 (ReleaseFixtureLogic) | medium | True | SCN-0053 |
| SC-052 (AirframeEquivalentMassLogic.SupportedInitialCondition to ReleasedDescent on LOGIC_EVT_DESCENT_START) | Logical transition from SupportedInitialCondition to ReleasedDescent triggered by receiving LOGIC_EVT_DESCENT_START. | LOGIC_EVT_DESCENT_START | AirframeEquivalentMassLogic.SupportedInitialCondition.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | medium | True | SCN-0054 |
| SC-053 (AirframeEquivalentMassLogic.ReleasedDescent to ImpactLoadTransfer on LOGIC_EVT_TOUCHDOWN) | Logical transition from ReleasedDescent to ImpactLoadTransfer triggered by receiving LOGIC_EVT_TOUCHDOWN. | LOGIC_EVT_TOUCHDOWN | AirframeEquivalentMassLogic.ReleasedDescent.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | medium | True | SCN-0055 |
| SC-054 (ImpactLoadTransfer to TouchdownScenarioActive Transition) | Time-based transition from ImpactLoadTransfer to TouchdownScenarioActive state. |  | AirframeEquivalentMassLogic.ImpactLoadTransfer.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | medium | True | SCN-0056 |
| SC-019 (TouchdownScenarioActive Self-Transition) | Time-based self-transition maintaining the TouchdownScenarioActive state. |  | AirframeEquivalentMassLogic.TouchdownScenarioActive.transition[0] |  | MO-004 (AirframeEquivalentMassLogic) | medium | True | SCN-0057 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | Event-triggered transition from AirborneNoContact to ClearanceTracking upon descent start. |  | TireWheelAssemblyLogic.AirborneNoContact.transition[0] |  | MO-005 (TireWheelAssemblyLogic) | medium | True | SCN-0058 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | Event-triggered transition from ClearanceTracking to ContactEstablished upon touchdown. |  | TireWheelAssemblyLogic.ClearanceTracking.transition[0] |  | MO-005 (TireWheelAssemblyLogic) | medium | True | SCN-0059 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | Time-based transition from ContactEstablished to TouchdownScenarioActive state. |  | TireWheelAssemblyLogic.ContactEstablished.transition[0] |  | MO-005 (TireWheelAssemblyLogic) | medium | True | SCN-0060 |
| SC-055 (TouchdownScenarioActive timeover transition) | Default timeover transition within TouchdownScenarioActive state of TireWheelAssemblyLogic. |  | TireWheelAssemblyLogic.TouchdownScenarioActive.transition[0] |  | MO-005 (TireWheelAssemblyLogic) | medium | True | SCN-0061 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | Transition triggered by LOGIC_EVT_DESCENT_START from GroundReferenceDefined to ClearanceBoundaryMonitoring in GroundContactBoundaryLogic. |  | GroundContactBoundaryLogic.GroundReferenceDefined.transition[0] |  | MO-006 (GroundContactBoundaryLogic) | medium | True | SCN-0062 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | Transition triggered by LOGIC_EVT_TOUCHDOWN from ClearanceBoundaryMonitoring to ContactConstraintActive in GroundContactBoundaryLogic. |  | GroundContactBoundaryLogic.ClearanceBoundaryMonitoring.transition[0] |  | MO-006 (GroundContactBoundaryLogic) | medium | True | SCN-0063 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | Default timeover transition from ContactConstraintActive to TouchdownScenarioActive in GroundContactBoundaryLogic. |  | GroundContactBoundaryLogic.ContactConstraintActive.transition[0] |  | MO-006 (GroundContactBoundaryLogic) | medium | True | SCN-0064 |
| SC-055 (TouchdownScenarioActive timeover transition) | Default timeover transition within TouchdownScenarioActive state of GroundContactBoundaryLogic. |  | GroundContactBoundaryLogic.TouchdownScenarioActive.transition[0] |  | MO-006 (GroundContactBoundaryLogic) | medium | True | SCN-0065 |
| SC-056 (OleoPneumaticStrutLogic ExtendedStroke to StrokeAvailable Transition) | Define the scenario phase for the transition from ExtendedStroke to StrokeAvailable in OleoPneumaticStrutLogic, triggered by the descent start event. | LOGIC_EVT_DESCENT_START | OleoPneumaticStrutLogic.ExtendedStroke.transition[0], trigger == LOGIC_EVT_DESCENT_START |  | MO-007 (OleoPneumaticStrutLogic) | medium | True | SCN-0066 |
| SC-057 (OleoPneumaticStrutLogic StrokeAvailable to CompressionStroke Transition) | Define the scenario phase for the transition from StrokeAvailable to CompressionStroke in OleoPneumaticStrutLogic, triggered by the touchdown event. | LOGIC_EVT_TOUCHDOWN | OleoPneumaticStrutLogic.StrokeAvailable.transition[0], trigger == LOGIC_EVT_TOUCHDOWN |  | MO-007 (OleoPneumaticStrutLogic) | medium | True | SCN-0067 |
| SC-058 (OleoPneumaticStrutLogic CompressionStroke to TouchdownScenarioActive Transition) | Define the scenario phase for the time-based transition from CompressionStroke to TouchdownScenarioActive in OleoPneumaticStrutLogic. | timeover | OleoPneumaticStrutLogic.CompressionStroke.transition[0], trigger == timeover |  | MO-007 (OleoPneumaticStrutLogic) | medium | True | SCN-0068 |
| SC-059 (OleoPneumaticStrutLogic TouchdownScenarioActive Self-Transition) | Define the scenario phase for the time-based self-transition maintaining the TouchdownScenarioActive state in OleoPneumaticStrutLogic. | timeover | OleoPneumaticStrutLogic.TouchdownScenarioActive.transition[0], trigger == timeover |  | MO-007 (OleoPneumaticStrutLogic) | medium | True | SCN-0069 |
| SC-060 (HydraulicDampingLogic DampingStandby to RelativeMotionMonitoring Transition) | Define the scenario phase for the transition from DampingStandby to RelativeMotionMonitoring in HydraulicDampingLogic, triggered by the descent start event. | LOGIC_EVT_DESCENT_START | HydraulicDampingLogic.DampingStandby.transition[0], trigger == LOGIC_EVT_DESCENT_START |  | MO-008 (HydraulicDampingLogic) | medium | True | SCN-0070 |
| SC-061 (Touchdown event triggers DampingActivated state) | Unconditional transition from RelativeMotionMonitoring to DampingActivated upon receiving LOGIC_EVT_TOUCHDOWN. | LOGIC_EVT_TOUCHDOWN | HydraulicDampingLogic.RelativeMotionMonitoring.transition[0] |  | MO-008 (HydraulicDampingLogic) | medium | True | SCN-0071 |
| SC-062 (Timeover triggers TouchdownScenarioActive state) | Unconditional time-based transition from DampingActivated to TouchdownScenarioActive. |  | HydraulicDampingLogic.DampingActivated.transition[0] |  | MO-008 (HydraulicDampingLogic) | medium | True | SCN-0072 |
| SC-063 (Timeover maintains TouchdownScenarioActive state) | Unconditional time-based self-transition within TouchdownScenarioActive state. |  | HydraulicDampingLogic.TouchdownScenarioActive.transition[0] |  | MO-008 (HydraulicDampingLogic) | medium | True | SCN-0073 |
| SC-064 (Descent start event triggers BaselineAccelerationRecording state) | Unconditional transition from ObservationIdle to BaselineAccelerationRecording upon receiving LOGIC_EVT_DESCENT_START. | LOGIC_EVT_DESCENT_START | AccelerationObservationLogic.ObservationIdle.transition[0] |  | MO-009 (AccelerationObservationLogic) | medium | True | SCN-0074 |
| SC-065 (Touchdown event triggers ImpactAccelerationMonitoring state) | Unconditional transition from BaselineAccelerationRecording to ImpactAccelerationMonitoring upon receiving LOGIC_EVT_TOUCHDOWN. | LOGIC_EVT_TOUCHDOWN | AccelerationObservationLogic.BaselineAccelerationRecording.transition[0] |  | MO-009 (AccelerationObservationLogic) | medium | True | SCN-0075 |
| SC-066 (ImpactAccelerationMonitoring to TouchdownScenarioActive Transition) | Transition from ImpactAccelerationMonitoring to TouchdownScenarioActive state triggered by timeover with condition true. |  | AccelerationObservationLogic.ImpactAccelerationMonitoring.transition[0] |  | MO-009 (AccelerationObservationLogic) | medium | True | SCN-0076 |
| SC-019 (TouchdownScenarioActive Self-Transition) | Self-transition in the TouchdownScenarioActive state triggered by timeover with condition true. |  | AccelerationObservationLogic.TouchdownScenarioActive.transition[0] |  | MO-009 (AccelerationObservationLogic) | medium | True | SCN-0077 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | The main landing gear shall limit the peak vertical shock acceleration transmitted to the supported aircraft structure within the specified limit. |  | req10 | peak vertical shock acceleration |  | high | True | SCN-0078 |
| SC-068 (Maximum Compression Stroke Limit) | The shock strut shall limit maximum compression stroke within the specified limit during vertical landing impact. |  | req11 | maximum compression stroke |  | high | True | SCN-0079 |
| SC-069 (Hard Bottoming Prevention) | The shock strut shall prevent hard bottoming under specified vertical landing impact conditions. |  | req12 | hard bottoming prevention |  | high | True | SCN-0080 |
| SC-070 (Tire Vertical Stiffness Range) | Evaluate tire vertical stiffness characteristics to ensure they meet the allowed range required for landing impact buffering. | Tire vertical stiffness parameters | req15 | Landing impact buffering performance, Tire vertical stiffness |  | medium | True | SCN-0081 |
| SC-071 (Hydraulic Damping Characteristics Range) | Evaluate hydraulic damping characteristics of the shock strut to ensure they meet the allowed range for impact energy dissipation and rebound control. | Hydraulic damping parameters | req18 | Hydraulic damping characteristics, Impact energy dissipation, Rebound control |  | medium | True | SCN-0082 |
| SC-072 (Sealing Integrity) | Verify oil and gas sealing integrity of the shock strut to ensure adequate oleo-pneumatic load support, energy absorption, and elastic recovery. | Oil and gas pressure, Sealing parameters | req19 | Oleo-pneumatic load support, Seal leakage rate |  | medium | True | SCN-0083 |
| SC-073 (Load Path Integrity) | Assess the integrity and alignment of the vertical load path from tire contact through the shock strut to the aircraft attachment structure. | Load path geometry, Structural stiffness | req20 | Load path alignment, Structural integrity |  | medium | True | SCN-0084 |
| SC-044 (Allowed Degradation Condition) | Evaluate landing gear performance when key buffering components experience performance deviation, wear, or degradation within the allowed range. | Component degradation parameters, Wear profiles | req28 | Buffering performance under degradation |  | medium | True | SCN-0085 |
| SC-074 (Physical Simulation Time Alignment) | Ensure physical simulation time strictly follows physical_scenario_time for event triggers (0.0s and 0.23s), avoiding logical entry_hold_time or statehold values. |  | scenario_alignment_rules |  |  | high | True | SCN-0086 |
| SC-075 (1D Vertical Translation Constraint) | Constrain the airframe mass as a rigid body to 1D vertical translation under constant, uniform gravity. |  | AirframeMassDynamics.assumptions |  | MO-015 (AirframeMassDynamics) | medium | True | SCN-0087 |
| SC-076 (Rigid Runway Surface) | Define the runway surface as perfectly rigid, flat, and horizontal, with ground constraint activating instantaneously at physical scenario time. |  | GroundConstraintEnforcer.assumptions |  | MO-014 (GroundConstraintEnforcer) | medium | True | SCN-0088 |
| SC-077 (Linear Tire Spring Assumption) | Model the tire carcass as a linear spring with no internal damping, assuming a perfectly rigid and non-deforming ground surface. |  | TireContactDynamics.assumptions |  | MO-016 (TireContactDynamics) | medium | True | SCN-0089 |
| SC-078 (No Fluid Aeration or Cavitation) | Assume no internal gas leakage, fluid aeration, or cavitation, treating hydraulic fluid as incompressible and flowing through fixed orifices. |  | OleoGasSpringDynamics.assumptions / HydraulicDamperDynamics.assumptions |  | MO-017 (OleoGasSpringDynamics), MO-018 (HydraulicDamperDynamics) | medium | True | SCN-0090 |
| SC-079 (Ideal Sensor Assumption) | To define the operational boundary condition for the physical behavior model assuming ideal sensors with no latency, bandwidth limitations, or noise, and continuous sampling at the simulation step rate. |  | SensorAndTelemetrySystem.assumptions | sampling rate, sensor latency, sensor noise | MO-019 (SensorAndTelemetrySystem) | medium | True | SCN-0091 |

## 7. Human Check List

| Item | Issue type | Reason | Suggestion | Source refs |
|---|---|---|---|---|
| CP-019 (Simulation Time Transfer) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0019 |
| CP-020 (Physical Descent Start Event Transfer) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0020 |
| CP-021 (PHYS_EVT_TOUCHDOWN coupling from clock_inst to scenario_clock_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0021 |
| CP-022 (PHYS_EVT_DESCENT_START coupling from scenario_clock_inst to release_fixture_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0022 |
| CP-023 (PHYS_EVT_TOUCHDOWN coupling from scenario_clock_inst to ground_constraint_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0023 |
| CP-024 (release_force coupling from release_fixture_inst to airframe_mass_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0024 |
| CP-025 (ground_height coupling from ground_constraint_inst to tire_contact_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0025 |
| CP-026 (airframe_mass_inst.y_s -> tire_contact_inst.y_s) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0026 |
| CP-027 (airframe_mass_inst.y_s -> oleo_strut_inst.y_s) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0027 |
| CP-028 (airframe_mass_inst.v_s -> oleo_strut_inst.v_s) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0028 |
| CP-029 (tire_contact_inst.y_u -> oleo_strut_inst.y_u) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0029 |
| CP-030 (tire_contact_inst.v_u -> oleo_strut_inst.v_u) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0030 |
| CP-031 (oleo_compression_speed coupling from oleo_strut_inst to hydraulic_damper_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0031 |
| CP-032 (damping_force coupling from hydraulic_damper_inst to oleo_strut_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0032 |
| CP-033 (strut_force coupling from oleo_strut_inst to airframe_mass_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0033 |
| CP-034 (strut_force coupling from oleo_strut_inst to tire_contact_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0034 |
| CP-035 (y_s coupling from airframe_mass_inst to telemetry_inst) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0035 |
| CP-036 (tire_contact_inst.y_u -> telemetry_inst.y_u) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0036 |
| CP-037 (airframe_mass_inst.v_s -> telemetry_inst.v_s) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0037 |
| CP-038 (tire_contact_inst.v_u -> telemetry_inst.v_u) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0038 |
| CP-039 (airframe_mass_inst.piston_zdd_out -> telemetry_inst.piston_zdd_out) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0039 |
| CP-040 (tire_contact_inst.tire_deflection -> telemetry_inst.tire_deflection) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0040 |
| CP-041 (oleo_strut_inst.oleo_compression -> telemetry_inst.oleo_compression) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0041 |
| CP-042 (hydraulic_damper_inst.damping_force -> telemetry_inst.damping_force) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0042 |
| CP-043 (scenario_clock_inst.PHYS_EVT_DESCENT_START -> telemetry_inst.PHYS_EVT_DESCENT_START) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0043 |
| CP-044 (scenario_clock_inst.PHYS_EVT_TOUCHDOWN -> telemetry_inst.PHYS_EVT_TOUCHDOWN) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | REL-0044 |
| SC-036 (MainLandingGearDropTest Simulation) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0037 |
| SC-037 (MainLandingGearDropTest Physical Context) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0038 |
| SC-038 (Vertical Landing Impact Condition) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0039 |
| SC-039 (Runway Contact Condition) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0040 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0041 |
| SC-041 (PreScenario) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0042 |
| SC-042 (DescentStart) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0043 |
| SC-043 (Touchdown) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0044 |
| SC-044 (Allowed Degradation Condition) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0045 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0078 |
| SC-068 (Maximum Compression Stroke Limit) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0079 |
| SC-069 (Hard Bottoming Prevention) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0080 |
| SC-070 (Tire Vertical Stiffness Range) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0081 |
| SC-071 (Hydraulic Damping Characteristics Range) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0082 |
| SC-072 (Sealing Integrity) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0083 |
| SC-073 (Load Path Integrity) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0084 |
| SC-044 (Allowed Degradation Condition) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0085 |
| SC-074 (Physical Simulation Time Alignment) | unassigned_atomic_item | atomic refinement item could not be reliably assigned to an engineering model object | review whether this item belongs to an existing model object or should create a new confirmed object | SCN-0086 |
| CP-019 (Simulation Time Transfer) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0019 |
| CP-020 (Physical Descent Start Event Transfer) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0020 |
| CP-021 (PHYS_EVT_TOUCHDOWN coupling from clock_inst to scenario_clock_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0021 |
| CP-022 (PHYS_EVT_DESCENT_START coupling from scenario_clock_inst to release_fixture_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0022 |
| CP-023 (PHYS_EVT_TOUCHDOWN coupling from scenario_clock_inst to ground_constraint_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0023 |
| CP-024 (release_force coupling from release_fixture_inst to airframe_mass_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0024 |
| CP-025 (ground_height coupling from ground_constraint_inst to tire_contact_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0025 |
| CP-026 (airframe_mass_inst.y_s -> tire_contact_inst.y_s) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0026 |
| CP-027 (airframe_mass_inst.y_s -> oleo_strut_inst.y_s) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0027 |
| CP-028 (airframe_mass_inst.v_s -> oleo_strut_inst.v_s) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0028 |
| CP-029 (tire_contact_inst.y_u -> oleo_strut_inst.y_u) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0029 |
| CP-030 (tire_contact_inst.v_u -> oleo_strut_inst.v_u) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0030 |
| CP-031 (oleo_compression_speed coupling from oleo_strut_inst to hydraulic_damper_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0031 |
| CP-032 (damping_force coupling from hydraulic_damper_inst to oleo_strut_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0032 |
| CP-033 (strut_force coupling from oleo_strut_inst to airframe_mass_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0033 |
| CP-034 (strut_force coupling from oleo_strut_inst to tire_contact_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0034 |
| CP-035 (y_s coupling from airframe_mass_inst to telemetry_inst) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0035 |
| CP-036 (tire_contact_inst.y_u -> telemetry_inst.y_u) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0036 |
| CP-037 (airframe_mass_inst.v_s -> telemetry_inst.v_s) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0037 |
| CP-038 (tire_contact_inst.v_u -> telemetry_inst.v_u) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0038 |
| CP-039 (airframe_mass_inst.piston_zdd_out -> telemetry_inst.piston_zdd_out) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0039 |
| CP-040 (tire_contact_inst.tire_deflection -> telemetry_inst.tire_deflection) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0040 |
| CP-041 (oleo_strut_inst.oleo_compression -> telemetry_inst.oleo_compression) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0041 |
| CP-042 (hydraulic_damper_inst.damping_force -> telemetry_inst.damping_force) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0042 |
| CP-043 (scenario_clock_inst.PHYS_EVT_DESCENT_START -> telemetry_inst.PHYS_EVT_DESCENT_START) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0043 |
| CP-044 (scenario_clock_inst.PHYS_EVT_TOUCHDOWN -> telemetry_inst.PHYS_EVT_TOUCHDOWN) | unassigned_atomic_item | relation endpoints could not be mapped to model_object_cards | review relation endpoint names and model object allocation | REL-0044 |
| PA-001 (impact_load_transfer_active) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0001 |
| PA-001 (impact_load_transfer_active) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0001 |
| PA-001 (impact_load_transfer_active) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0001 |
| PA-002 (damping_activated) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0002 |
| PA-002 (damping_activated) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0002 |
| PA-002 (damping_activated) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0002 |
| PA-003 (initial_support_force) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0003 |
| PA-003 (initial_support_force) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0003 |
| PA-004 (runway_elevation) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0004 |
| PA-004 (runway_elevation) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0004 |
| PA-005 (piston_zdd_out) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0005 |
| PA-005 (piston_zdd_out) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0005 |
| PA-005 (piston_zdd_out) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0005 |
| PA-006 (M_s) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0006 |
| PA-006 (M_s) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0006 |
| PA-007 (g) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0007 |
| PA-007 (g) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0007 |
| PA-008 (M_u) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0008 |
| PA-009 (K_t) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0009 |
| PA-007 (g) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0010 |
| PA-007 (g) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0010 |
| PA-010 (damping_force) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0011 |
| PA-010 (damping_force) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0011 |
| PA-010 (damping_force) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0011 |
| PA-011 (oleo_compression_speed) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0012 |
| PA-011 (oleo_compression_speed) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0012 |
| PA-011 (oleo_compression_speed) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0012 |
| PA-012 (K_s) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0013 |
| PA-012 (K_s) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0013 |
| PA-011 (oleo_compression_speed) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0014 |
| PA-011 (oleo_compression_speed) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0014 |
| PA-011 (oleo_compression_speed) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0014 |
| PA-010 (damping_force) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0015 |
| PA-010 (damping_force) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0015 |
| PA-010 (damping_force) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0015 |
| PA-013 (C_v) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0016 |
| PA-013 (C_v) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0016 |
| PA-014 (C_v2) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0017 |
| PA-014 (C_v2) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0017 |
| PA-005 (piston_zdd_out) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0018 |
| PA-005 (piston_zdd_out) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0018 |
| PA-005 (piston_zdd_out) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0018 |
| PA-010 (damping_force) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0019 |
| PA-010 (damping_force) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0019 |
| PA-010 (damping_force) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0019 |
| PA-015 (measured_piston_zdd_out) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0020 |
| PA-015 (measured_piston_zdd_out) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0020 |
| PA-015 (measured_piston_zdd_out) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0020 |
| PA-016 (measured_damping_force) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0021 |
| PA-016 (measured_damping_force) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0021 |
| PA-016 (measured_damping_force) | missing_initial_value | initial value is unknown | confirm nominal or initial value before simulation | PAR-0021 |
| PA-017 (physical_event_marker_clock) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0022 |
| PA-017 (physical_event_marker_clock) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0022 |
| PA-017 (physical_event_marker_clock) | unclear_parameter_role | parameter role is uncertain | classify as fixed parameter, design variable, optimization candidate, constraint, metric, uncertainty, or calibration parameter | PAR-0022 |
| PA-018 (v_s_state) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0023 |
| PA-018 (v_s_state) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0023 |
| PA-019 (y_s_state) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0024 |
| PA-019 (y_s_state) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0024 |
| PA-020 (penetration) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0025 |
| PA-020 (penetration) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0025 |
| PA-020 (penetration) | unclear_parameter_role | parameter role is uncertain | classify as fixed parameter, design variable, optimization candidate, constraint, metric, uncertainty, or calibration parameter | PAR-0025 |
| PA-021 (v_u_state) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0026 |
| PA-021 (v_u_state) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0026 |
| PA-022 (y_u_state) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0027 |
| PA-022 (y_u_state) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0027 |
| PA-023 (oleo_compression_state) | missing_unit | unit is unknown | confirm the unit before using this parameter in professional analysis | PAR-0028 |
| PA-023 (oleo_compression_state) | missing_range | range is unknown | define engineering lower/upper bounds before optimization or verification | PAR-0028 |
| SC-001 (BeforeSchedule to EvtDescentStart Transition Scenario) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0001 |
| SC-001 (BeforeSchedule to EvtDescentStart Transition Scenario) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0001 |
| SC-002 (EvtDescentStart to EvtTouchdown Transition Scenario) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0002 |
| SC-002 (EvtDescentStart to EvtTouchdown Transition Scenario) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0002 |
| SC-003 (EvtTouchdown End State Transition Scenario) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0003 |
| SC-003 (EvtTouchdown End State Transition Scenario) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0003 |
| SC-004 (PreScenario to DescentScenarioActive Transition Scenario) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0004 |
| SC-004 (PreScenario to DescentScenarioActive Transition Scenario) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0004 |
| SC-005 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition Scenario) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0005 |
| SC-005 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition Scenario) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0005 |
| SC-006 (Touchdown Scenario Active Entry Phase) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0006 |
| SC-006 (Touchdown Scenario Active Entry Phase) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0006 |
| SC-007 (Touchdown Scenario Active Phase) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0007 |
| SC-007 (Touchdown Scenario Active Phase) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0007 |
| SC-008 (Aircraft Holding and Release Phase) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0008 |
| SC-008 (Aircraft Holding and Release Phase) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0008 |
| SC-009 (Post-Release Touchdown Phase) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0009 |
| SC-009 (Post-Release Touchdown Phase) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0009 |
| SC-010 (Release Fixture Inactive Transition Phase) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0010 |
| SC-010 (Release Fixture Inactive Transition Phase) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0010 |
| SC-011 (Release Fixture Logic - Touchdown Scenario Active) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0011 |
| SC-011 (Release Fixture Logic - Touchdown Scenario Active) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0011 |
| SC-012 (Airframe Equivalent Mass Logic - Supported Initial Condition to Released Descent) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0012 |
| SC-012 (Airframe Equivalent Mass Logic - Supported Initial Condition to Released Descent) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0012 |
| SC-013 (Airframe Equivalent Mass Logic - Released Descent to Impact Load Transfer) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0013 |
| SC-013 (Airframe Equivalent Mass Logic - Released Descent to Impact Load Transfer) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0013 |
| SC-014 (Airframe Equivalent Mass Logic - Impact Load Transfer to Touchdown Scenario Active) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0014 |
| SC-014 (Airframe Equivalent Mass Logic - Impact Load Transfer to Touchdown Scenario Active) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0014 |
| SC-015 (Airframe Equivalent Mass Logic - Touchdown Scenario Active) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0015 |
| SC-015 (Airframe Equivalent Mass Logic - Touchdown Scenario Active) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0015 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0016 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0016 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0017 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0017 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0018 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0018 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0019 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0019 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0020 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0020 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0021 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0021 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0022 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0022 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0023 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0023 |
| SC-023 (ExtendedStroke to StrokeAvailable Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0024 |
| SC-023 (ExtendedStroke to StrokeAvailable Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0024 |
| SC-024 (StrokeAvailable to CompressionStroke Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0025 |
| SC-024 (StrokeAvailable to CompressionStroke Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0025 |
| SC-025 (OleoPneumaticStrutLogic.CompressionStroke) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0026 |
| SC-025 (OleoPneumaticStrutLogic.CompressionStroke) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0026 |
| SC-026 (OleoPneumaticStrutLogic.TouchdownScenarioActive) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0027 |
| SC-026 (OleoPneumaticStrutLogic.TouchdownScenarioActive) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0027 |
| SC-027 (HydraulicDampingLogic.DampingStandby) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0028 |
| SC-027 (HydraulicDampingLogic.DampingStandby) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0028 |
| SC-028 (HydraulicDampingLogic.RelativeMotionMonitoring) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0029 |
| SC-028 (HydraulicDampingLogic.RelativeMotionMonitoring) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0029 |
| SC-029 (HydraulicDampingLogic.DampingActivated) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0030 |
| SC-029 (HydraulicDampingLogic.DampingActivated) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0030 |
| SC-030 (HydraulicDampingLogic.TouchdownScenarioActive) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0031 |
| SC-030 (HydraulicDampingLogic.TouchdownScenarioActive) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0031 |
| SC-031 (AccelerationObservationLogic.ObservationIdle) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0032 |
| SC-031 (AccelerationObservationLogic.ObservationIdle) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0032 |
| SC-032 (AccelerationObservationLogic.BaselineAccelerationRecording) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0033 |
| SC-032 (AccelerationObservationLogic.BaselineAccelerationRecording) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0033 |
| SC-033 (AccelerationObservationLogic.ImpactAccelerationMonitoring) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0034 |
| SC-033 (AccelerationObservationLogic.ImpactAccelerationMonitoring) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0034 |
| SC-034 (AccelerationObservationLogic.TouchdownScenarioActive) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0035 |
| SC-034 (AccelerationObservationLogic.TouchdownScenarioActive) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0035 |
| SC-035 (Monitoring State Timeover Event) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0036 |
| SC-035 (Monitoring State Timeover Event) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0036 |
| SC-036 (MainLandingGearDropTest Simulation) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0037 |
| SC-036 (MainLandingGearDropTest Simulation) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0037 |
| SC-036 (MainLandingGearDropTest Simulation) | missing_conditions | scenario conditions are not explicit | define boundary, initial, trigger, environmental, or constraint conditions | SCN-0037 |
| SC-036 (MainLandingGearDropTest Simulation) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0037 |
| SC-037 (MainLandingGearDropTest Physical Context) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0038 |
| SC-037 (MainLandingGearDropTest Physical Context) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0038 |
| SC-037 (MainLandingGearDropTest Physical Context) | missing_conditions | scenario conditions are not explicit | define boundary, initial, trigger, environmental, or constraint conditions | SCN-0038 |
| SC-037 (MainLandingGearDropTest Physical Context) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0038 |
| SC-038 (Vertical Landing Impact Condition) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0039 |
| SC-038 (Vertical Landing Impact Condition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0039 |
| SC-038 (Vertical Landing Impact Condition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0039 |
| SC-039 (Runway Contact Condition) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0040 |
| SC-039 (Runway Contact Condition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0040 |
| SC-039 (Runway Contact Condition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0040 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0041 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0041 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0041 |
| SC-041 (PreScenario) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0042 |
| SC-041 (PreScenario) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0042 |
| SC-041 (PreScenario) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0042 |
| SC-042 (DescentStart) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0043 |
| SC-042 (DescentStart) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0043 |
| SC-042 (DescentStart) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0043 |
| SC-043 (Touchdown) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0044 |
| SC-043 (Touchdown) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0044 |
| SC-043 (Touchdown) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0044 |
| SC-044 (Allowed Degradation Condition) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0045 |
| SC-044 (Allowed Degradation Condition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0045 |
| SC-044 (Allowed Degradation Condition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0045 |
| SC-045 (PreScenario to DescentScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0046 |
| SC-045 (PreScenario to DescentScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0046 |
| SC-046 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0047 |
| SC-046 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0047 |
| SC-047 (TouchdownScenarioActiveEntry to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0048 |
| SC-047 (TouchdownScenarioActiveEntry to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0048 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0049 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0049 |
| SC-048 (HoldingAircraft to Released Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0050 |
| SC-048 (HoldingAircraft to Released Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0050 |
| SC-049 (ReleaseFixtureLogic.Released to InactiveAfterRelease on LOGIC_EVT_TOUCHDOWN) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0051 |
| SC-049 (ReleaseFixtureLogic.Released to InactiveAfterRelease on LOGIC_EVT_TOUCHDOWN) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0051 |
| SC-050 (ReleaseFixtureLogic.InactiveAfterRelease to TouchdownScenarioActive on timeover) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0052 |
| SC-050 (ReleaseFixtureLogic.InactiveAfterRelease to TouchdownScenarioActive on timeover) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0052 |
| SC-051 (ReleaseFixtureLogic.TouchdownScenarioActive self-transition on timeover) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0053 |
| SC-051 (ReleaseFixtureLogic.TouchdownScenarioActive self-transition on timeover) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0053 |
| SC-052 (AirframeEquivalentMassLogic.SupportedInitialCondition to ReleasedDescent on LOGIC_EVT_DESCENT_START) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0054 |
| SC-052 (AirframeEquivalentMassLogic.SupportedInitialCondition to ReleasedDescent on LOGIC_EVT_DESCENT_START) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0054 |
| SC-053 (AirframeEquivalentMassLogic.ReleasedDescent to ImpactLoadTransfer on LOGIC_EVT_TOUCHDOWN) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0055 |
| SC-053 (AirframeEquivalentMassLogic.ReleasedDescent to ImpactLoadTransfer on LOGIC_EVT_TOUCHDOWN) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0055 |
| SC-054 (ImpactLoadTransfer to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0056 |
| SC-054 (ImpactLoadTransfer to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0056 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0057 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0057 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0058 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0058 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0059 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0059 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0060 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0060 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0061 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0061 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0062 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0062 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0063 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0063 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0064 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0064 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0065 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0065 |
| SC-056 (OleoPneumaticStrutLogic ExtendedStroke to StrokeAvailable Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0066 |
| SC-056 (OleoPneumaticStrutLogic ExtendedStroke to StrokeAvailable Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0066 |
| SC-057 (OleoPneumaticStrutLogic StrokeAvailable to CompressionStroke Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0067 |
| SC-057 (OleoPneumaticStrutLogic StrokeAvailable to CompressionStroke Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0067 |
| SC-058 (OleoPneumaticStrutLogic CompressionStroke to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0068 |
| SC-058 (OleoPneumaticStrutLogic CompressionStroke to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0068 |
| SC-059 (OleoPneumaticStrutLogic TouchdownScenarioActive Self-Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0069 |
| SC-059 (OleoPneumaticStrutLogic TouchdownScenarioActive Self-Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0069 |
| SC-060 (HydraulicDampingLogic DampingStandby to RelativeMotionMonitoring Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0070 |
| SC-060 (HydraulicDampingLogic DampingStandby to RelativeMotionMonitoring Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0070 |
| SC-061 (Touchdown event triggers DampingActivated state) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0071 |
| SC-061 (Touchdown event triggers DampingActivated state) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0071 |
| SC-062 (Timeover triggers TouchdownScenarioActive state) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0072 |
| SC-062 (Timeover triggers TouchdownScenarioActive state) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0072 |
| SC-063 (Timeover maintains TouchdownScenarioActive state) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0073 |
| SC-063 (Timeover maintains TouchdownScenarioActive state) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0073 |
| SC-064 (Descent start event triggers BaselineAccelerationRecording state) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0074 |
| SC-064 (Descent start event triggers BaselineAccelerationRecording state) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0074 |
| SC-065 (Touchdown event triggers ImpactAccelerationMonitoring state) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0075 |
| SC-065 (Touchdown event triggers ImpactAccelerationMonitoring state) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0075 |
| SC-066 (ImpactAccelerationMonitoring to TouchdownScenarioActive Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0076 |
| SC-066 (ImpactAccelerationMonitoring to TouchdownScenarioActive Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0076 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0077 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0077 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0078 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0078 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0078 |
| SC-068 (Maximum Compression Stroke Limit) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0079 |
| SC-068 (Maximum Compression Stroke Limit) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0079 |
| SC-068 (Maximum Compression Stroke Limit) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0079 |
| SC-069 (Hard Bottoming Prevention) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0080 |
| SC-069 (Hard Bottoming Prevention) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0080 |
| SC-069 (Hard Bottoming Prevention) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0080 |
| SC-070 (Tire Vertical Stiffness Range) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0081 |
| SC-070 (Tire Vertical Stiffness Range) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0081 |
| SC-070 (Tire Vertical Stiffness Range) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0081 |
| SC-071 (Hydraulic Damping Characteristics Range) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0082 |
| SC-071 (Hydraulic Damping Characteristics Range) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0082 |
| SC-071 (Hydraulic Damping Characteristics Range) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0082 |
| SC-072 (Sealing Integrity) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0083 |
| SC-072 (Sealing Integrity) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0083 |
| SC-072 (Sealing Integrity) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0083 |
| SC-073 (Load Path Integrity) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0084 |
| SC-073 (Load Path Integrity) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0084 |
| SC-073 (Load Path Integrity) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0084 |
| SC-044 (Allowed Degradation Condition) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0085 |
| SC-044 (Allowed Degradation Condition) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0085 |
| SC-044 (Allowed Degradation Condition) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0085 |
| SC-074 (Physical Simulation Time Alignment) | unassigned_atomic_item | scenario could not be mapped to a model object | review scenario applicability to engineering model objects | SCN-0086 |
| SC-074 (Physical Simulation Time Alignment) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0086 |
| SC-074 (Physical Simulation Time Alignment) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0086 |
| SC-075 (1D Vertical Translation Constraint) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0087 |
| SC-075 (1D Vertical Translation Constraint) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0087 |
| SC-076 (Rigid Runway Surface) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0088 |
| SC-076 (Rigid Runway Surface) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0088 |
| SC-077 (Linear Tire Spring Assumption) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0089 |
| SC-077 (Linear Tire Spring Assumption) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0089 |
| SC-078 (No Fluid Aeration or Cavitation) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0090 |
| SC-078 (No Fluid Aeration or Cavitation) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0090 |
| SC-079 (Ideal Sensor Assumption) | missing_inputs | scenario inputs are not explicit | define loads, commands, environmental inputs, or initial state inputs | SCN-0091 |
| SC-079 (Ideal Sensor Assumption) | missing_metrics | scenario metrics are not explicit | define engineering evaluation metrics or acceptance criteria | SCN-0091 |
| Verify state transitions and time-based triggers for DropTestScenarioTimeline | requires_human_confirmation | Logical state transitions triggered by events or timeover require human confirmation to ensure correct scenario sequencing. | Review the transition conditions and triggers in the logical model. | SCN-0046, SCN-0047, SCN-0048, SCN-0049 |
| Verify state transitions for ReleaseFixtureLogic | requires_human_confirmation | Logical state transitions triggered by events or timeover require human confirmation. | Review the transition conditions and triggers in the logical model. | SCN-0050, SCN-0051, SCN-0052, SCN-0053 |
| Verify state transitions for AirframeEquivalentMassLogic and the impact_load_transfer_active parameter | requires_human_confirmation | Logical state transitions and parameter definitions (missing initial value, unit, range) require human confirmation. | Review the transition conditions and provide missing parameter attributes. | PAR-0001, SCN-0054, SCN-0055, SCN-0056, SCN-0057 |
| Verify state transitions for TireWheelAssemblyLogic | requires_human_confirmation | Logical state transitions triggered by events or timeover require human confirmation. | Review the transition conditions and triggers in the logical model. | SCN-0058, SCN-0059, SCN-0060, SCN-0061 |
| Verify model_role and implementation_method for logical state machines | classification | The components MO-006 to MO-010 are described as logical components with state transitions. They have been updated to control_model and control_block_model, but originally were dynamic_response_model with 1D_physical_model/MBD. | Confirm if these logical state machines should be modeled as control_block_model or if they represent physical dynamic responses. | OBJ-0006, OBJ-0007, OBJ-0008, OBJ-0009, OBJ-0010 |
| Confirm output ports for state machines | missing_data | Outputs for MO-006, MO-007, and MO-008 were inferred from state transition outputs. Outputs for MO-009 and MO-010 are not explicitly defined in the evidence. | Verify the exact output port names and ensure all logical outputs are captured. | OBJ-0009, OBJ-0010, SCN-0021, SCN-0024, SCN-0025, SCN-0028, SCN-0029 |
| Review scenario transitions requiring human confirmation | validation | Multiple scenario transitions (SCN-0062 to SCN-0077) were flagged as requiring human confirmation during the refinement process. | Review the state transition logic and conditions for these scenarios to ensure they correctly represent the intended system behavior. | SCN-0062, SCN-0063, SCN-0064, SCN-0065, SCN-0066, SCN-0067, SCN-0068, SCN-0069, SCN-0070, SCN-0071, SCN-0072, SCN-0073, SCN-0074, SCN-0075, SCN-0076, SCN-0077 |
| Confirm unit and range for physical_event_marker_clock | missing_data | Parameter physical_event_marker_clock is missing unit and range. | Provide unit (e.g., s) and valid range. | PAR-0022 |
| Confirm unit and range for initial_support_force | missing_data | Parameter initial_support_force is missing unit and range. | Provide unit (e.g., N) and valid range. | PAR-0003 |
| Confirm unit and range for runway_elevation | missing_data | Parameter runway_elevation is missing unit and range. | Provide unit (e.g., m) and valid range. | PAR-0004 |
| Confirm Rigid Runway Surface assumption | assumption_validation | Scenario assumption requires human confirmation. | Verify if the runway surface can be assumed perfectly rigid, flat, and horizontal. | SCN-0088 |
| Confirm initial value, unit, and range for piston_zdd_out | missing_data | Parameter piston_zdd_out is missing initial value, unit, and range. | Provide initial value, unit (e.g., m/s2), and valid range. | PAR-0005 |
| Confirm unit and range for M_s | missing_data | Parameter M_s is missing unit and range. | Provide unit (e.g., kg) and valid range. | PAR-0006 |
| Confirm unit and range for g | missing_data | Parameter g is missing unit and range. | Provide unit (e.g., m/s2) and valid range. | PAR-0007 |
| Confirm unit and range for v_s_state | missing_data | Parameter v_s_state is missing unit and range. | Provide unit (e.g., m/s) and valid range. | PAR-0023 |
| Confirm unit and range for y_s_state | missing_data | Parameter y_s_state is missing unit and range. | Provide unit (e.g., m) and valid range. | PAR-0024 |
| Confirm 1D Vertical Translation Constraint assumption | assumption_validation | Scenario assumption requires human confirmation. | Verify if the airframe mass can be assumed as a rigid body constrained to 1D vertical translation with constant gravity. | SCN-0087 |
| Confirm units and valid ranges for TireContactDynamics parameters (M_u, K_t, g, penetration, v_u_state, y_u_state). | missing_data | Parameters lack physical units and expected operational ranges. | Provide physical units (e.g., kg, N/m, m/s^2) and valid ranges for all tire dynamics parameters. | PAR-0008, PAR-0009, PAR-0010, PAR-0025, PAR-0026, PAR-0027 |
| Confirm initial values, units, and ranges for OleoGasSpringDynamics parameters (damping_force, oleo_compression_speed, oleo_compression_state). | missing_data | Parameters lack initial values, physical units, and valid ranges. | Define initial conditions and physical bounds for the gas spring dynamics to ensure proper simulation initialization. | PAR-0011, PAR-0012, PAR-0028 |
| Confirm units and ranges for HydraulicDamperDynamics parameters (oleo_compression_speed, damping_force, C_v, C_v2). | missing_data | Parameters lack physical units and valid operational ranges. | Specify units (e.g., N/(m/s) for C_v, N/(m/s)^2 for C_v2) and operational ranges for damping coefficients. | PAR-0014, PAR-0015, PAR-0016, PAR-0017 |
| Confirm initial values, units, and ranges for SensorAndTelemetrySystem parameters (piston_zdd_out, damping_force, measured_piston_zdd_out, measured_damping_force). | missing_data | Sensor inputs and outputs lack initial values, physical units, and signal ranges. | Define sensor measurement units, expected signal ranges, and initial states for telemetry blocks. | PAR-0018, PAR-0019, PAR-0020, PAR-0021 |
| Validate the 'Linear Tire Spring Assumption' (no internal damping, rigid ground) for the drop test scenario. | assumption_validation | Assumes perfectly rigid ground and linear tire spring, which may not reflect real-world drop test conditions. | Review if nonlinear tire stiffness or ground compliance should be included for higher fidelity drop test simulations. | SCN-0089 |
| Validate the 'No Fluid Aeration or Cavitation' assumption for the oleo-pneumatic strut. | assumption_validation | Assumes incompressible fluid and no aeration/cavitation, which might be violated during high-impact drop tests. | Consider fluid compressibility and aeration models if high-pressure drops or rapid strut extensions are expected. | SCN-0090 |
| Validate the 'Ideal Sensor Assumption' (no latency, noise, or bandwidth limits). | assumption_validation | Assumes perfect sensors, ignoring real-world telemetry limitations and signal processing delays. | Assess if sensor dynamics (e.g., low-pass filtering, noise, latency) need to be modeled for control or telemetry analysis. | SCN-0091 |
| Verify the transferred variable for the logical event signals (e.g., LOGIC_EVT_DESCENT_START, LOGIC_EVT_TOUCHDOWN) between ScenarioTimelineSource and other logic models. | missing_information | The transferred variable names are logical events rather than standard parameter IDs, and the allowed values restrict it to 'PA-007' or 'unknown'. | Confirm if a specific parameter ID should be assigned to these logical event signals or if 'unknown' is acceptable for logical event couplings. | REL-0001, REL-0002, REL-0003, REL-0004, REL-0005 |
| Verify the exact signal names and mapping for logical events (e.g., LOGIC_EVT_DESCENT_START, LOGIC_EVT_TOUCHDOWN) between ScenarioTimelineSource and the logic models. | missing_information | The transferred variables are logical events rather than standard physical parameters, and their exact implementation in the simulation environment needs confirmation. | Confirm the signal names and ensure the simulation tool supports logical event triggers for these logic blocks. | REL-0011, REL-0012, REL-0013, REL-0014, REL-0015 |
| Verify unit, initial value, and range for impact_load_transfer_active | missing_information | Initial value and range are missing; unit is inferred as dimensionless for a logical boolean output. | Confirm if this is a boolean/dimensionless parameter and provide expected initial value and range. | PAR-0001 |
| Verify unit, initial value, and range for damping_activated | missing_information | Initial value and range are missing; unit is inferred as dimensionless for a logical boolean output. | Confirm if this is a boolean/dimensionless parameter and provide expected initial value and range. | PAR-0002 |
| Verify unit and range for initial_support_force | missing_information | Range is missing; unit is inferred as Newtons (N) based on the description of force and initial value of 9810.0. | Confirm the unit is N and provide the valid operating range for the support force. | PAR-0003 |
| Verify unit and range for runway_elevation | missing_information | Range is missing; unit is inferred as meters (m) based on the description of vertical position. | Confirm the unit is m and provide the valid range for runway elevation. | PAR-0004 |
| Verify unit, initial value, and range for piston_zdd_out | missing_information | Initial value and range are missing; unit is inferred as m/s2 based on the description of vertical acceleration. | Confirm the unit is m/s2 and provide expected initial value and range. | PAR-0005 |
| Confirm the unit for M_s is kg and verify the valid range. | missing_unit | The source unit is unknown, inferred as kg based on domain knowledge for mass. | Verify the unit and range for equivalent airframe mass. | PAR-0006 |
| Confirm the unit for g is m/s^2 and parameter role is fixed_parameter. | missing_unit | The source unit is unknown, inferred as m/s^2. Gravity is typically a fixed parameter rather than a design variable. | Verify the unit and parameter role for gravitational acceleration. | PAR-0007 |
| Verify the valid range for M_u. | missing_range | The unit is kg and the initial value is provided by the RFLP concept physical model. | Verify the valid design range for unsprung wheel mass. | PAR-0008 |
| Verify the valid range for K_t. | missing_range | The unit is N/m and the initial value is provided by the RFLP concept physical model. | Verify the valid design range for tire stiffness approximation. | PAR-0009 |
| Confirm the unit for g is m/s^2 and parameter role is fixed_parameter. | missing_unit | The source unit is unknown, inferred as m/s^2. Gravity is typically a fixed parameter rather than a design variable. | Verify the unit and parameter role for gravitational acceleration. | PAR-0010 |
| Verify physical units, initial values, and operational ranges for damping_force, oleo_compression_speed, and K_s parameters. | missing_data | Units, initial values, and ranges are missing or unknown for multiple parameters in the OleoGasSpringDynamics and HydraulicDamperDynamics components. | Provide physical units (e.g., N, m/s, N/m), typical initial values, and operational ranges based on landing gear design specifications and drop test requirements. | PAR-0011, PAR-0012, PAR-0013, PAR-0014, PAR-0015 |
| Confirm unit and range for C_v | missing_data | Unit and range are unknown for the linear oleo damping coefficient. | Provide the physical unit (e.g., N/(m/s)) and valid operating range. | PAR-0016 |
| Confirm unit and range for C_v2 | missing_data | Unit and range are unknown for the quadratic oleo damping coefficient. | Provide the physical unit (e.g., N/(m/s)^2) and valid operating range. | PAR-0017 |
| Confirm initial value, unit, and range for piston_zdd_out | missing_data | Initial value, unit, and range are unknown for airframe vertical acceleration input. | Define the expected unit (e.g., m/s^2), initial value, and range. | PAR-0018 |
| Confirm initial value, unit, and range for damping_force | missing_data | Initial value, unit, and range are unknown for damping force input. | Define the expected unit (e.g., N), initial value, and range. | PAR-0019 |
| Confirm initial value, unit, and range for measured_piston_zdd_out | missing_data | Initial value, unit, and range are unknown for measured airframe acceleration output. | Define the expected unit (e.g., m/s^2), initial value, and range. | PAR-0020 |
| Confirm unit and range for measured_damping_force | missing_information | Unit and range are missing in the source data. Inferred unit as N (Newtons) based on domain knowledge of damping force. | Verify if the unit should be N or lbf, and provide the expected operational range. | PAR-0021 |
| Confirm unit and range for physical_event_marker_clock | missing_information | Unit and range are missing. Inferred unit as s (seconds) for a time clock. | Verify the time unit and the maximum simulation time or clock range. | PAR-0022 |
| Confirm unit and range for v_s_state | missing_information | Unit and range are missing. Inferred unit as m/s for velocity state. | Verify the velocity unit and expected range for the airframe vertical velocity. | PAR-0023 |
| Confirm unit and range for y_s_state | missing_information | Unit and range are missing. Inferred unit as m for position state. | Verify the position unit and expected range for the airframe vertical displacement. | PAR-0024 |
| Confirm unit and range for penetration | missing_information | Unit and range are missing. Inferred unit as m for ground penetration depth. | Verify the penetration unit and maximum expected penetration depth. | PAR-0025 |
| Confirm the physical unit and valid range for the initial state v_u_state. | missing_information | The unit and range are currently unknown for this dynamic state. | Determine the unit (e.g., m/s) and expected range for the vertical velocity state. | PAR-0026 |
| Confirm the physical unit and valid range for the initial state y_u_state. | missing_information | The unit and range are currently unknown for this dynamic state. | Determine the unit (e.g., m) and expected range for the vertical displacement state. | PAR-0027 |
| Confirm the physical unit and valid range for the initial state oleo_compression_state. | missing_information | The unit and range are currently unknown for this dynamic state. | Determine the unit (e.g., m) and expected range for the oleo compression state. | PAR-0028 |
| Verify if a state machine transition should be classified as a distinct scenario or merely an event within a scenario. | classification | The source item represents a state machine transition triggered by a timeover condition during the monitoring phase. | Confirm if 'Monitoring State Timeover Event' should remain as a distinct scenario in the simulation scenario matrix. | SCN-0036 |
| Confirm the exact trigger condition and timing for LOGIC_EVT_DESCENT_START in the descent scenario transition. | missing_detail | The transition relies on LOGIC_EVT_DESCENT_START, but the exact timing and condition details need human confirmation. | Verify the event trigger logic and timing in the system architecture. | SCN-0046 |
| Confirm the exact trigger condition and timing for LOGIC_EVT_TOUCHDOWN in the touchdown scenario transition. | missing_detail | The transition relies on LOGIC_EVT_TOUCHDOWN, but the exact timing and condition details need human confirmation. | Verify the event trigger logic and timing in the system architecture. | SCN-0047 |
| Confirm the time duration or condition for the transition from TouchdownScenarioActiveEntry to TouchdownScenarioActive. | missing_detail | The time-based transition parameters are not fully specified. | Verify the time delay or condition for this state transition. | SCN-0048 |
| Confirm the time step or condition for the self-transition within the TouchdownScenarioActive state. | missing_detail | The time-based self-transition parameters are not fully specified. | Verify the time step or condition for this self-transition. | SCN-0049 |
| Confirm the exact trigger condition and timing for LOGIC_EVT_DESCENT_START in the aircraft fixture release transition. | missing_detail | The transition relies on LOGIC_EVT_DESCENT_START, but the exact timing and condition details need human confirmation. | Verify the event trigger logic and timing in the system architecture. | SCN-0050 |
| Verify logical state transitions and event triggers for ReleaseFixtureLogic and AirframeEquivalentMassLogic. | requires_human_confirmation | The state transitions and event triggers (LOGIC_EVT_TOUCHDOWN, timeover, LOGIC_EVT_DESCENT_START) require human confirmation to ensure correct logical sequencing in the drop test simulation. | Review the state machine definitions and event timing to confirm the transitions accurately reflect the physical drop test sequence. | SCN-0051, SCN-0052, SCN-0053, SCN-0054, SCN-0055 |
| Verify the time-based transition logic from ImpactLoadTransfer to TouchdownScenarioActive state. | requires_human_confirmation | The transition is time-based and requires confirmation of the timing parameters and state logic. | Review the time threshold for the transition in the AirframeEquivalentMassLogic component. | SCN-0056 |
| Verify the time-based self-transition logic maintaining the TouchdownScenarioActive state. | requires_human_confirmation | The self-transition is time-based and requires confirmation of the timing parameters. | Review the time threshold for the self-transition in the AirframeEquivalentMassLogic component. | SCN-0057 |
| Verify the event-triggered transition from AirborneNoContact to ClearanceTracking upon descent start. | requires_human_confirmation | The transition is event-triggered and requires confirmation of the descent start event definition. | Review the descent start event trigger in the TireWheelAssemblyLogic component. | SCN-0058 |
| Verify the event-triggered transition from ClearanceTracking to ContactEstablished upon touchdown. | requires_human_confirmation | The transition is event-triggered and requires confirmation of the touchdown event definition. | Review the touchdown event trigger in the TireWheelAssemblyLogic component. | SCN-0059 |
| Verify the time-based transition logic from ContactEstablished to TouchdownScenarioActive state. | requires_human_confirmation | The transition is time-based and requires confirmation of the timing parameters and state logic. | Review the time threshold for the transition in the TireWheelAssemblyLogic component. | SCN-0060 |
| Confirm state transition logic for TouchdownScenarioActive timeover transition in TireWheelAssemblyLogic. | requires_human_confirmation | The source item is a state transition with an always-true condition, representing a default or time-triggered state change in the logical model. | Verify if this timeover transition is correctly capturing the intended default behavior or if specific conditions should be added. | SCN-0061 |
| Confirm state transition logic for GroundReferenceDefined to ClearanceBoundaryMonitoring transition. | requires_human_confirmation | The source item is a state transition triggered by a descent start event, representing a logical state change in the ground contact boundary logic. | Verify if LOGIC_EVT_DESCENT_START is the correct and only trigger for this transition. | SCN-0062 |
| Confirm state transition logic for ClearanceBoundaryMonitoring to ContactConstraintActive transition. | requires_human_confirmation | The source item is a state transition triggered by a touchdown event, representing the activation of contact constraints in the logical model. | Verify if LOGIC_EVT_TOUCHDOWN is the correct and only trigger for this transition. | SCN-0063 |
| Confirm state transition logic for ContactConstraintActive to TouchdownScenarioActive transition. | requires_human_confirmation | The source item is a state transition with an always-true condition, representing a default or time-triggered state change in the logical model. | Verify if this timeover transition is correctly capturing the intended default behavior or if specific conditions should be added. | SCN-0064 |
| Confirm state transition logic for TouchdownScenarioActive timeover transition in GroundContactBoundaryLogic. | requires_human_confirmation | The source item is a state transition with an always-true condition, representing a default or time-triggered state change in the logical model. | Verify if this timeover transition is correctly capturing the intended default behavior or if specific conditions should be added. | SCN-0065 |
| Confirm the trigger events and transition conditions for OleoPneumaticStrutLogic and HydraulicDampingLogic state machines. | missing_information | The state transitions rely on specific logical events (LOGIC_EVT_DESCENT_START, LOGIC_EVT_TOUCHDOWN, timeover) which require human confirmation to ensure they match the system-level requirements. | Verify the logical events and time-based triggers with the system architect. | SCN-0066, SCN-0067, SCN-0068, SCN-0069, SCN-0070 |
| Confirm the unconditional state machine transitions and event triggers (LOGIC_EVT_TOUCHDOWN, LOGIC_EVT_DESCENT_START) for HydraulicDampingLogic and AccelerationObservationLogic. | requires_human_confirmation | The source items are deterministic logic flows derived from logical model state transitions, requiring human confirmation of the event names and transition conditions. | Verify the event names and transition logic in the system architecture model. | SCN-0071, SCN-0072, SCN-0073, SCN-0074, SCN-0075 |
| SC-066 (ImpactAccelerationMonitoring to TouchdownScenarioActive Transition) | missing_information | Requires human confirmation of the logical state transition conditions. | Verify the timeover and condition true triggers for the transition. | SCN-0076 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_information | Requires human confirmation of the self-transition conditions. | Verify the timeover and condition true triggers for the self-transition. | SCN-0077 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | missing_information | The specific numerical limit for peak vertical shock acceleration is not defined in the text. | Provide the exact numerical value for the peak vertical shock acceleration limit. | SCN-0078 |
| SC-068 (Maximum Compression Stroke Limit) | missing_information | The specific numerical limit for maximum compression stroke is not defined in the text. | Provide the exact numerical value for the maximum compression stroke limit. | SCN-0079 |
| SC-069 (Hard Bottoming Prevention) | missing_information | Requires human confirmation of the specified vertical landing impact conditions. | Define the specific vertical landing impact conditions for hard bottoming prevention. | SCN-0080 |
| Define the specific allowed range for tire vertical stiffness. | missing_information | The specific allowed range for tire vertical stiffness is not defined in the source text. | Provide the numerical bounds or tolerance for tire vertical stiffness. | SCN-0081 |
| Define the specific allowed range for hydraulic damping characteristics. | missing_information | The specific allowed range for hydraulic damping characteristics is not defined in the source text. | Provide the numerical bounds or tolerance for hydraulic damping. | SCN-0082 |
| Confirm the specific criteria and metrics for sealing integrity. | missing_information | The exact leakage limits or pressure retention metrics for sealing integrity are not specified. | Define acceptable leakage rates or pressure decay limits. | SCN-0083 |
| Confirm the specific alignment tolerances for the vertical load path. | missing_information | The exact alignment tolerances and structural integrity metrics for the load path are not specified. | Provide allowable misalignment angles or load distribution limits. | SCN-0084 |
| Define the allowed degradation range for key buffering components. | missing_information | The specific performance deviation or wear limits for buffering components are not defined. | Specify the maximum allowable degradation percentages or wear depths. | SCN-0085 |
| Verify physical simulation time alignment rules for event triggers at 0.0s and 0.23s. | requirement_clarity | Requires human confirmation to ensure logical hold times are not mistakenly used as physical process durations. | Confirm that physical_scenario_time is strictly used for event triggers. | SCN-0086 |
| Verify 1D vertical translation constraint for airframe mass. | modeling_assumption | Requires human confirmation of the rigid body and constant gravity assumptions. | Confirm that 1D vertical translation and uniform gravity are sufficient for the drop test analysis. | SCN-0087 |
| Verify rigid runway surface assumption. | modeling_assumption | Requires human confirmation that the runway is perfectly rigid, flat, and horizontal. | Confirm that instantaneous ground constraint activation and rigid surface are acceptable. | SCN-0088 |
| Verify linear tire spring assumption. | modeling_assumption | Requires human confirmation of the linear spring model with no internal damping. | Confirm that ignoring tire internal damping and ground deformation is acceptable for this test. | SCN-0089 |
| Verify no fluid aeration or cavitation assumption. | modeling_assumption | Requires human confirmation that hydraulic fluid is incompressible with no aeration or cavitation. | Confirm that fixed orifices and incompressible fluid assumptions are valid for the oleo and damper dynamics. | SCN-0090 |
| Verify the assumption of ideal sensors with no latency, bandwidth limitations, or noise, and continuous sampling at the simulation step rate. | assumption_validation | The scenario assumes ideal sensors, which may not reflect real-world physical behavior and requires human confirmation. | Confirm if ideal sensor assumptions are acceptable for the current simulation fidelity or if sensor dynamics should be modeled. | SCN-0091 |
| PA-001 (impact_load_transfer_active) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0001 |
| PA-001 (impact_load_transfer_active) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0001 |
| PA-002 (damping_activated) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0002 |
| PA-002 (damping_activated) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0002 |
| PA-003 (initial_support_force) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0003 |
| PA-004 (runway_elevation) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0004 |
| PA-005 (piston_zdd_out) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0005 |
| PA-005 (piston_zdd_out) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0005 |
| PA-010 (damping_force) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0011 |
| PA-010 (damping_force) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0011 |
| PA-010 (damping_force) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0011 |
| PA-011 (oleo_compression_speed) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0012 |
| PA-011 (oleo_compression_speed) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0012 |
| PA-011 (oleo_compression_speed) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0012 |
| PA-012 (K_s) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0013 |
| PA-012 (K_s) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0013 |
| PA-011 (oleo_compression_speed) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0014 |
| PA-011 (oleo_compression_speed) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0014 |
| PA-011 (oleo_compression_speed) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0014 |
| PA-010 (damping_force) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0015 |
| PA-010 (damping_force) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0015 |
| PA-010 (damping_force) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0015 |
| PA-013 (C_v) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0016 |
| PA-013 (C_v) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0016 |
| PA-014 (C_v2) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0017 |
| PA-014 (C_v2) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0017 |
| PA-005 (piston_zdd_out) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0018 |
| PA-005 (piston_zdd_out) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0018 |
| PA-005 (piston_zdd_out) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0018 |
| PA-010 (damping_force) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0019 |
| PA-010 (damping_force) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0019 |
| PA-010 (damping_force) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0019 |
| PA-015 (measured_piston_zdd_out) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0020 |
| PA-015 (measured_piston_zdd_out) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0020 |
| PA-015 (measured_piston_zdd_out) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0020 |
| PA-016 (measured_damping_force) | missing_initial_value | initial_value is missing or unknown | confirm initial_value before engineering use | PAR-0021 |
| PA-016 (measured_damping_force) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0021 |
| PA-017 (physical_event_marker_clock) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0022 |
| PA-018 (v_s_state) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0023 |
| PA-019 (y_s_state) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0024 |
| PA-020 (penetration) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0025 |
| PA-021 (v_u_state) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0026 |
| PA-021 (v_u_state) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0026 |
| PA-022 (y_u_state) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0027 |
| PA-022 (y_u_state) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0027 |
| PA-023 (oleo_compression_state) | missing_unit | unit is missing or unknown | confirm unit before engineering use | PAR-0028 |
| PA-023 (oleo_compression_state) | missing_range | range is missing or unknown | confirm range before engineering use | PAR-0028 |
| SC-001 (BeforeSchedule to EvtDescentStart Transition Scenario) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0001 |
| SC-001 (BeforeSchedule to EvtDescentStart Transition Scenario) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0001 |
| SC-002 (EvtDescentStart to EvtTouchdown Transition Scenario) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0002 |
| SC-002 (EvtDescentStart to EvtTouchdown Transition Scenario) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0002 |
| SC-003 (EvtTouchdown End State Transition Scenario) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0003 |
| SC-003 (EvtTouchdown End State Transition Scenario) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0003 |
| SC-004 (PreScenario to DescentScenarioActive Transition Scenario) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0004 |
| SC-004 (PreScenario to DescentScenarioActive Transition Scenario) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0004 |
| SC-005 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition Scenario) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0005 |
| SC-005 (DescentScenarioActive to TouchdownScenarioActiveEntry Transition Scenario) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0005 |
| SC-006 (Touchdown Scenario Active Entry Phase) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0006 |
| SC-006 (Touchdown Scenario Active Entry Phase) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0006 |
| SC-007 (Touchdown Scenario Active Phase) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0007 |
| SC-007 (Touchdown Scenario Active Phase) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0007 |
| SC-008 (Aircraft Holding and Release Phase) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0008 |
| SC-008 (Aircraft Holding and Release Phase) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0008 |
| SC-009 (Post-Release Touchdown Phase) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0009 |
| SC-009 (Post-Release Touchdown Phase) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0009 |
| SC-010 (Release Fixture Inactive Transition Phase) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0010 |
| SC-010 (Release Fixture Inactive Transition Phase) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0010 |
| SC-011 (Release Fixture Logic - Touchdown Scenario Active) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0011 |
| SC-011 (Release Fixture Logic - Touchdown Scenario Active) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0011 |
| SC-012 (Airframe Equivalent Mass Logic - Supported Initial Condition to Released Descent) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0012 |
| SC-013 (Airframe Equivalent Mass Logic - Released Descent to Impact Load Transfer) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0013 |
| SC-014 (Airframe Equivalent Mass Logic - Impact Load Transfer to Touchdown Scenario Active) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0014 |
| SC-014 (Airframe Equivalent Mass Logic - Impact Load Transfer to Touchdown Scenario Active) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0014 |
| SC-015 (Airframe Equivalent Mass Logic - Touchdown Scenario Active) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0015 |
| SC-015 (Airframe Equivalent Mass Logic - Touchdown Scenario Active) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0015 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0016 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0017 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0018 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0018 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0019 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0019 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0020 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0022 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0023 |
| SC-025 (OleoPneumaticStrutLogic.CompressionStroke) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0026 |
| SC-025 (OleoPneumaticStrutLogic.CompressionStroke) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0026 |
| SC-026 (OleoPneumaticStrutLogic.TouchdownScenarioActive) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0027 |
| SC-026 (OleoPneumaticStrutLogic.TouchdownScenarioActive) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0027 |
| SC-027 (HydraulicDampingLogic.DampingStandby) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0028 |
| SC-028 (HydraulicDampingLogic.RelativeMotionMonitoring) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0029 |
| SC-029 (HydraulicDampingLogic.DampingActivated) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0030 |
| SC-029 (HydraulicDampingLogic.DampingActivated) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0030 |
| SC-035 (Monitoring State Timeover Event) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0036 |
| SC-035 (Monitoring State Timeover Event) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0036 |
| SC-036 (MainLandingGearDropTest Simulation) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0037 |
| SC-036 (MainLandingGearDropTest Simulation) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0037 |
| SC-036 (MainLandingGearDropTest Simulation) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0037 |
| SC-037 (MainLandingGearDropTest Physical Context) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0038 |
| SC-037 (MainLandingGearDropTest Physical Context) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0038 |
| SC-038 (Vertical Landing Impact Condition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0039 |
| SC-038 (Vertical Landing Impact Condition) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0039 |
| SC-039 (Runway Contact Condition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0040 |
| SC-039 (Runway Contact Condition) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0040 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0041 |
| SC-040 (Repeated Vertical Load-Cycle Condition) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0041 |
| SC-041 (PreScenario) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0042 |
| SC-041 (PreScenario) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0042 |
| SC-041 (PreScenario) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0042 |
| SC-042 (DescentStart) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0043 |
| SC-042 (DescentStart) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0043 |
| SC-042 (DescentStart) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0043 |
| SC-043 (Touchdown) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0044 |
| SC-043 (Touchdown) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0044 |
| SC-044 (Allowed Degradation Condition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0045 |
| SC-044 (Allowed Degradation Condition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0045 |
| SC-044 (Allowed Degradation Condition) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0045 |
| SC-047 (TouchdownScenarioActiveEntry to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0048 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0049 |
| SC-049 (ReleaseFixtureLogic.Released to InactiveAfterRelease on LOGIC_EVT_TOUCHDOWN) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0051 |
| SC-050 (ReleaseFixtureLogic.InactiveAfterRelease to TouchdownScenarioActive on timeover) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0052 |
| SC-051 (ReleaseFixtureLogic.TouchdownScenarioActive self-transition on timeover) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0053 |
| SC-052 (AirframeEquivalentMassLogic.SupportedInitialCondition to ReleasedDescent on LOGIC_EVT_DESCENT_START) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0054 |
| SC-053 (AirframeEquivalentMassLogic.ReleasedDescent to ImpactLoadTransfer on LOGIC_EVT_TOUCHDOWN) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0055 |
| SC-054 (ImpactLoadTransfer to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0056 |
| SC-054 (ImpactLoadTransfer to TouchdownScenarioActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0056 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0057 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0057 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0058 |
| SC-016 (AirborneNoContact to ClearanceTracking Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0058 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0059 |
| SC-017 (ClearanceTracking to ContactEstablished Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0059 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0060 |
| SC-018 (ContactEstablished to TouchdownScenarioActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0060 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0061 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0061 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0062 |
| SC-020 (GroundReferenceDefined to ClearanceBoundaryMonitoring Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0062 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0063 |
| SC-021 (ClearanceBoundaryMonitoring to ContactConstraintActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0063 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0064 |
| SC-022 (ContactConstraintActive to TouchdownScenarioActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0064 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0065 |
| SC-055 (TouchdownScenarioActive timeover transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0065 |
| SC-056 (OleoPneumaticStrutLogic ExtendedStroke to StrokeAvailable Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0066 |
| SC-057 (OleoPneumaticStrutLogic StrokeAvailable to CompressionStroke Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0067 |
| SC-058 (OleoPneumaticStrutLogic CompressionStroke to TouchdownScenarioActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0068 |
| SC-059 (OleoPneumaticStrutLogic TouchdownScenarioActive Self-Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0069 |
| SC-060 (HydraulicDampingLogic DampingStandby to RelativeMotionMonitoring Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0070 |
| SC-061 (Touchdown event triggers DampingActivated state) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0071 |
| SC-062 (Timeover triggers TouchdownScenarioActive state) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0072 |
| SC-062 (Timeover triggers TouchdownScenarioActive state) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0072 |
| SC-063 (Timeover maintains TouchdownScenarioActive state) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0073 |
| SC-063 (Timeover maintains TouchdownScenarioActive state) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0073 |
| SC-064 (Descent start event triggers BaselineAccelerationRecording state) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0074 |
| SC-065 (Touchdown event triggers ImpactAccelerationMonitoring state) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0075 |
| SC-066 (ImpactAccelerationMonitoring to TouchdownScenarioActive Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0076 |
| SC-066 (ImpactAccelerationMonitoring to TouchdownScenarioActive Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0076 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0077 |
| SC-019 (TouchdownScenarioActive Self-Transition) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0077 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0078 |
| SC-067 (Peak Vertical Shock Acceleration Limit) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0078 |
| SC-068 (Maximum Compression Stroke Limit) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0079 |
| SC-068 (Maximum Compression Stroke Limit) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0079 |
| SC-069 (Hard Bottoming Prevention) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0080 |
| SC-069 (Hard Bottoming Prevention) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0080 |
| SC-070 (Tire Vertical Stiffness Range) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0081 |
| SC-071 (Hydraulic Damping Characteristics Range) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0082 |
| SC-072 (Sealing Integrity) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0083 |
| SC-073 (Load Path Integrity) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0084 |
| SC-044 (Allowed Degradation Condition) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0085 |
| SC-074 (Physical Simulation Time Alignment) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0086 |
| SC-074 (Physical Simulation Time Alignment) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0086 |
| SC-074 (Physical Simulation Time Alignment) | unassigned_atomic_item | related_models is missing or unknown | confirm related_models before engineering use | SCN-0086 |
| SC-075 (1D Vertical Translation Constraint) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0087 |
| SC-075 (1D Vertical Translation Constraint) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0087 |
| SC-076 (Rigid Runway Surface) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0088 |
| SC-076 (Rigid Runway Surface) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0088 |
| SC-077 (Linear Tire Spring Assumption) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0089 |
| SC-077 (Linear Tire Spring Assumption) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0089 |
| SC-078 (No Fluid Aeration or Cavitation) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0090 |
| SC-078 (No Fluid Aeration or Cavitation) | missing_metrics | metrics is missing or unknown | confirm metrics before engineering use | SCN-0090 |
| SC-079 (Ideal Sensor Assumption) | missing_inputs | inputs is missing or unknown | confirm inputs before engineering use | SCN-0091 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0001 |
| CP-001 (LOGIC_EVT_DESCENT_START coupling from ScenarioTimelineSource to DropTestScenarioTimeline) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0001 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0002 |
| CP-002 (LOGIC_EVT_TOUCHDOWN coupling from ScenarioTimelineSource to DropTestScenarioTimeline) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0002 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0003 |
| CP-003 (LOGIC_EVT_DESCENT_START coupling from ScenarioTimelineSource to ReleaseFixtureLogic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0003 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0004 |
| CP-004 (LOGIC_EVT_TOUCHDOWN coupling from ScenarioTimelineSource to ReleaseFixtureLogic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0004 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0005 |
| CP-005 (LOGIC_EVT_DESCENT_START coupling from ScenarioTimelineSource to AirframeEquivalentMassLogic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0005 |
| LOGIC_EVT_TOUCHDOWN | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0006 |
| CP-006 (Touchdown Event Signal to Airframe Equivalent Mass Logic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0006 |
| LOGIC_EVT_DESCENT_START | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0007 |
| CP-007 (Descent Start Event Signal to Tire Wheel Assembly Logic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0007 |
| LOGIC_EVT_TOUCHDOWN | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0008 |
| CP-008 (Touchdown Event Signal to Tire Wheel Assembly Logic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0008 |
| LOGIC_EVT_DESCENT_START | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0009 |
| CP-009 (Descent Start Event Signal to Ground Contact Boundary Logic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0009 |
| LOGIC_EVT_TOUCHDOWN | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0010 |
| CP-010 (Touchdown Event Signal to Ground Contact Boundary Logic) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0010 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0011 |
| CP-011 (ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> OleoPneumaticStrutLogic.LOGIC_EVT_DESCENT_START) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0011 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0012 |
| CP-012 (ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> OleoPneumaticStrutLogic.LOGIC_EVT_TOUCHDOWN) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0012 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0013 |
| CP-013 (ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> HydraulicDampingLogic.LOGIC_EVT_DESCENT_START) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0013 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0014 |
| CP-014 (ScenarioTimelineSource.LOGIC_EVT_TOUCHDOWN -> HydraulicDampingLogic.LOGIC_EVT_TOUCHDOWN) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0014 |
| unknown | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0015 |
| CP-015 (ScenarioTimelineSource.LOGIC_EVT_DESCENT_START -> AccelerationObservationLogic.LOGIC_EVT_DESCENT_START) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0015 |
| LOGIC_EVT_TOUCHDOWN | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0016 |
| CP-016 (Touchdown Event Signal) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0016 |
| LOGIC_EVT_DESCENT_START | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0017 |
| CP-017 (Descent Start Event Signal) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0017 |
| LOGIC_EVT_TOUCHDOWN | unassigned_atomic_item | transferred variable is not registered as a parameter | confirm transferred variable or add parameter entry | REL-0018 |
| CP-018 (Touchdown Event Marker Signal) | unassigned_atomic_item | transferred_variable is missing or unknown | confirm transferred_variable before engineering use | REL-0018 |

## 8. Consistency Report

### Errors

None.

### Warnings

| Code | Item | Message |
|---|---|---|
| coupling_type_pending | REL-0001 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0001 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0002 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0002 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0003 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0003 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0004 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0004 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0005 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0005 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0006 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0006 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0007 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0007 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0008 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0008 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0009 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0009 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0010 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0010 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0011 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0011 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0012 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0012 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0013 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0013 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0014 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0014 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0015 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0015 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0016 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0016 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0017 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0017 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0018 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_transferred_variable | REL-0018 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0019 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0019 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0019 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0020 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0020 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0020 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0021 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0021 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0021 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0022 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0022 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0022 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0023 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0023 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0023 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0024 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0024 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0024 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0025 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0025 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0025 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0026 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0026 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0026 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0027 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0027 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0027 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0028 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0028 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0028 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0029 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0029 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0029 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0030 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0030 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0030 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0031 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0031 | coupling endpoint could not be resolved to a registered model object |
| coupling_type_pending | REL-0032 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0032 | coupling endpoint could not be resolved to a registered model object |
| coupling_type_pending | REL-0033 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0033 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0033 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0034 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0034 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0034 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0035 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0035 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0035 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0036 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0036 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0036 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0037 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0037 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0037 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0038 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0038 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0038 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0039 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0039 | coupling endpoint could not be resolved to a registered model object |
| coupling_type_pending | REL-0040 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0040 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0040 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0041 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0041 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0041 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0042 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0042 | coupling endpoint could not be resolved to a registered model object |
| coupling_type_pending | REL-0043 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0043 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0043 | transferred variable could not be resolved to a registered parameter |
| coupling_type_pending | REL-0044 | coupling_type is left unknown in entity_registry and must be confirmed by engineering_artifacts or human review |
| unresolved_coupling_endpoint | REL-0044 | coupling endpoint could not be resolved to a registered model object |
| unresolved_transferred_variable | REL-0044 | transferred variable could not be resolved to a registered parameter |
| incomplete_information | MO-001 | model_object_card.inputs is incomplete |
| incomplete_information | MO-002 | model_object_card.outputs is incomplete |
| incomplete_information | MO-003 | model_object_card.outputs is incomplete |
| incomplete_information | MO-004 | model_object_card.outputs is incomplete |
| incomplete_information | MO-005 | model_object_card.outputs is incomplete |
| incomplete_information | MO-009 | model_object_card.outputs is incomplete |
| incomplete_information | MO-010 | model_object_card.outputs is incomplete |
| incomplete_information | MO-011 | model_object_card.inputs is incomplete |
| incomplete_information | MO-012 | model_object_card.inputs is incomplete |
| incomplete_information | MO-013 | model_object_card.inputs is incomplete |
| incomplete_information | MO-014 | model_object_card.inputs is incomplete |
| unknown_value | CP-001 | transferred_variable is unknown |
| unknown_value | CP-002 | transferred_variable is unknown |
| unknown_value | CP-003 | transferred_variable is unknown |
| unknown_value | CP-004 | transferred_variable is unknown |
| unknown_value | CP-005 | transferred_variable is unknown |
| unknown_value | CP-006 | transferred_variable is unknown |
| unknown_value | CP-007 | transferred_variable is unknown |
| unknown_value | CP-008 | transferred_variable is unknown |
| unknown_value | CP-009 | transferred_variable is unknown |
| unknown_value | CP-010 | transferred_variable is unknown |
| unknown_value | CP-011 | transferred_variable is unknown |
| unknown_value | CP-012 | transferred_variable is unknown |
| unknown_value | CP-013 | transferred_variable is unknown |
| unknown_value | CP-014 | transferred_variable is unknown |
| unknown_value | CP-015 | transferred_variable is unknown |
| unknown_value | CP-016 | transferred_variable is unknown |
| unknown_value | CP-017 | transferred_variable is unknown |
| unknown_value | CP-018 | transferred_variable is unknown |
| incomplete_information | PA-001 | parameter.initial_value is incomplete |
| incomplete_information | PA-001 | parameter.range is incomplete |
| incomplete_information | PA-002 | parameter.initial_value is incomplete |
| incomplete_information | PA-002 | parameter.range is incomplete |
| incomplete_information | PA-003 | parameter.range is incomplete |
| incomplete_information | PA-004 | parameter.range is incomplete |
| incomplete_information | PA-005 | parameter.initial_value is incomplete |
| incomplete_information | PA-005 | parameter.range is incomplete |
| incomplete_information | PA-010 | parameter.unit is incomplete |
| incomplete_information | PA-010 | parameter.initial_value is incomplete |
| incomplete_information | PA-010 | parameter.range is incomplete |
| incomplete_information | PA-011 | parameter.unit is incomplete |
| incomplete_information | PA-011 | parameter.initial_value is incomplete |
| incomplete_information | PA-011 | parameter.range is incomplete |
| incomplete_information | PA-012 | parameter.unit is incomplete |
| incomplete_information | PA-012 | parameter.range is incomplete |
| incomplete_information | PA-013 | parameter.unit is incomplete |
| incomplete_information | PA-013 | parameter.range is incomplete |
| incomplete_information | PA-014 | parameter.unit is incomplete |
| incomplete_information | PA-014 | parameter.range is incomplete |
| incomplete_information | PA-005 | parameter.unit is incomplete |
| incomplete_information | PA-015 | parameter.unit is incomplete |
| incomplete_information | PA-015 | parameter.initial_value is incomplete |
| incomplete_information | PA-015 | parameter.range is incomplete |
| incomplete_information | PA-016 | parameter.initial_value is incomplete |
| incomplete_information | PA-016 | parameter.range is incomplete |
| incomplete_information | PA-017 | parameter.range is incomplete |
| incomplete_information | PA-018 | parameter.range is incomplete |
| incomplete_information | PA-019 | parameter.range is incomplete |
| incomplete_information | PA-020 | parameter.range is incomplete |
| incomplete_information | PA-021 | parameter.unit is incomplete |
| incomplete_information | PA-021 | parameter.range is incomplete |
| incomplete_information | PA-022 | parameter.unit is incomplete |
| incomplete_information | PA-022 | parameter.range is incomplete |
| incomplete_information | PA-023 | parameter.unit is incomplete |
| incomplete_information | PA-023 | parameter.range is incomplete |
| incomplete_information | SC-001 | scenario.inputs is incomplete |
| incomplete_information | SC-001 | scenario.metrics is incomplete |
| incomplete_information | SC-002 | scenario.inputs is incomplete |
| incomplete_information | SC-002 | scenario.metrics is incomplete |
| incomplete_information | SC-003 | scenario.inputs is incomplete |
| incomplete_information | SC-003 | scenario.metrics is incomplete |
| incomplete_information | SC-004 | scenario.inputs is incomplete |
| incomplete_information | SC-004 | scenario.metrics is incomplete |
| incomplete_information | SC-005 | scenario.inputs is incomplete |
| incomplete_information | SC-005 | scenario.metrics is incomplete |
| incomplete_information | SC-006 | scenario.inputs is incomplete |
| incomplete_information | SC-006 | scenario.metrics is incomplete |
| incomplete_information | SC-007 | scenario.inputs is incomplete |
| incomplete_information | SC-007 | scenario.metrics is incomplete |
| incomplete_information | SC-008 | scenario.inputs is incomplete |
| incomplete_information | SC-008 | scenario.metrics is incomplete |
| incomplete_information | SC-009 | scenario.inputs is incomplete |
| incomplete_information | SC-009 | scenario.metrics is incomplete |
| incomplete_information | SC-010 | scenario.inputs is incomplete |
| incomplete_information | SC-010 | scenario.metrics is incomplete |
| incomplete_information | SC-011 | scenario.inputs is incomplete |
| incomplete_information | SC-011 | scenario.metrics is incomplete |
| incomplete_information | SC-012 | scenario.metrics is incomplete |
| incomplete_information | SC-013 | scenario.metrics is incomplete |
| incomplete_information | SC-014 | scenario.inputs is incomplete |
| incomplete_information | SC-014 | scenario.metrics is incomplete |
| incomplete_information | SC-015 | scenario.inputs is incomplete |
| incomplete_information | SC-015 | scenario.metrics is incomplete |
| incomplete_information | SC-016 | scenario.metrics is incomplete |
| incomplete_information | SC-017 | scenario.metrics is incomplete |
| incomplete_information | SC-018 | scenario.inputs is incomplete |
| incomplete_information | SC-018 | scenario.metrics is incomplete |
| incomplete_information | SC-019 | scenario.inputs is incomplete |
| incomplete_information | SC-019 | scenario.metrics is incomplete |
| incomplete_information | SC-020 | scenario.metrics is incomplete |
| incomplete_information | SC-022 | scenario.inputs is incomplete |
| incomplete_information | SC-025 | scenario.inputs is incomplete |
| incomplete_information | SC-025 | scenario.metrics is incomplete |
| incomplete_information | SC-026 | scenario.inputs is incomplete |
| incomplete_information | SC-026 | scenario.metrics is incomplete |
| incomplete_information | SC-027 | scenario.metrics is incomplete |
| incomplete_information | SC-028 | scenario.metrics is incomplete |
| incomplete_information | SC-029 | scenario.inputs is incomplete |
| incomplete_information | SC-029 | scenario.metrics is incomplete |
| incomplete_information | SC-035 | scenario.inputs is incomplete |
| incomplete_information | SC-035 | scenario.metrics is incomplete |
| incomplete_information | SC-036 | scenario.inputs is incomplete |
| incomplete_information | SC-036 | scenario.metrics is incomplete |
| incomplete_information | SC-036 | scenario.related_models is incomplete |
| incomplete_information | SC-037 | scenario.inputs is incomplete |
| incomplete_information | SC-037 | scenario.related_models is incomplete |
| incomplete_information | SC-038 | scenario.inputs is incomplete |
| incomplete_information | SC-038 | scenario.related_models is incomplete |
| incomplete_information | SC-039 | scenario.inputs is incomplete |
| incomplete_information | SC-039 | scenario.related_models is incomplete |
| incomplete_information | SC-040 | scenario.inputs is incomplete |
| incomplete_information | SC-040 | scenario.related_models is incomplete |
| incomplete_information | SC-041 | scenario.inputs is incomplete |
| incomplete_information | SC-041 | scenario.metrics is incomplete |
| incomplete_information | SC-041 | scenario.related_models is incomplete |
| incomplete_information | SC-042 | scenario.inputs is incomplete |
| incomplete_information | SC-042 | scenario.metrics is incomplete |
| incomplete_information | SC-042 | scenario.related_models is incomplete |
| incomplete_information | SC-043 | scenario.inputs is incomplete |
| incomplete_information | SC-043 | scenario.related_models is incomplete |
| incomplete_information | SC-044 | scenario.inputs is incomplete |
| incomplete_information | SC-044 | scenario.metrics is incomplete |
| incomplete_information | SC-044 | scenario.related_models is incomplete |
| incomplete_information | SC-047 | scenario.inputs is incomplete |
| incomplete_information | SC-049 | scenario.metrics is incomplete |
| incomplete_information | SC-050 | scenario.metrics is incomplete |
| incomplete_information | SC-051 | scenario.metrics is incomplete |
| incomplete_information | SC-052 | scenario.metrics is incomplete |
| incomplete_information | SC-053 | scenario.metrics is incomplete |
| incomplete_information | SC-054 | scenario.inputs is incomplete |
| incomplete_information | SC-054 | scenario.metrics is incomplete |
| incomplete_information | SC-016 | scenario.inputs is incomplete |
| incomplete_information | SC-017 | scenario.inputs is incomplete |
| incomplete_information | SC-055 | scenario.inputs is incomplete |
| incomplete_information | SC-055 | scenario.metrics is incomplete |
| incomplete_information | SC-020 | scenario.inputs is incomplete |
| incomplete_information | SC-021 | scenario.inputs is incomplete |
| incomplete_information | SC-021 | scenario.metrics is incomplete |
| incomplete_information | SC-022 | scenario.metrics is incomplete |
| incomplete_information | SC-056 | scenario.metrics is incomplete |
| incomplete_information | SC-057 | scenario.metrics is incomplete |
| incomplete_information | SC-058 | scenario.metrics is incomplete |
| incomplete_information | SC-059 | scenario.metrics is incomplete |
| incomplete_information | SC-060 | scenario.metrics is incomplete |
| incomplete_information | SC-061 | scenario.metrics is incomplete |
| incomplete_information | SC-062 | scenario.inputs is incomplete |
| incomplete_information | SC-062 | scenario.metrics is incomplete |
| incomplete_information | SC-063 | scenario.inputs is incomplete |
| incomplete_information | SC-063 | scenario.metrics is incomplete |
| incomplete_information | SC-064 | scenario.metrics is incomplete |
| incomplete_information | SC-065 | scenario.metrics is incomplete |
| incomplete_information | SC-066 | scenario.inputs is incomplete |
| incomplete_information | SC-066 | scenario.metrics is incomplete |
| incomplete_information | SC-067 | scenario.inputs is incomplete |
| incomplete_information | SC-067 | scenario.related_models is incomplete |
| incomplete_information | SC-068 | scenario.inputs is incomplete |
| incomplete_information | SC-068 | scenario.related_models is incomplete |
| incomplete_information | SC-069 | scenario.inputs is incomplete |
| incomplete_information | SC-069 | scenario.related_models is incomplete |
| incomplete_information | SC-070 | scenario.related_models is incomplete |
| incomplete_information | SC-071 | scenario.related_models is incomplete |
| incomplete_information | SC-072 | scenario.related_models is incomplete |
| incomplete_information | SC-073 | scenario.related_models is incomplete |
| incomplete_information | SC-074 | scenario.inputs is incomplete |
| incomplete_information | SC-074 | scenario.metrics is incomplete |
| incomplete_information | SC-074 | scenario.related_models is incomplete |
| incomplete_information | SC-075 | scenario.inputs is incomplete |
| incomplete_information | SC-075 | scenario.metrics is incomplete |
| incomplete_information | SC-076 | scenario.inputs is incomplete |
| incomplete_information | SC-076 | scenario.metrics is incomplete |
| incomplete_information | SC-077 | scenario.inputs is incomplete |
| incomplete_information | SC-077 | scenario.metrics is incomplete |
| incomplete_information | SC-078 | scenario.inputs is incomplete |
| incomplete_information | SC-078 | scenario.metrics is incomplete |
| incomplete_information | SC-079 | scenario.inputs is incomplete |
| missing_human_check | OBJ-0002 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0003 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0004 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0005 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0011 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0013 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0014 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0015 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0016 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0017 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0018 | need_check=true item is not represented in human_check_list |
| missing_human_check | OBJ-0019 | need_check=true item is not represented in human_check_list |

### Auto-fixes

| Code | Item | Message |
|---|---|---|
| alias_merge | g | merged parameter alias into PA-007 |
| alias_merge | oleo_compression_speed | merged parameter alias into PA-011 |
| alias_merge | damping_force | merged parameter alias into PA-010 |
| alias_merge | piston_zdd_out | merged parameter alias into PA-005 |
| alias_merge | TouchdownScenarioActive Self-Transition | merged scenario alias into SC-019 |
| alias_merge | AirborneNoContact to ClearanceTracking Transition | merged scenario alias into SC-016 |
| alias_merge | ClearanceTracking to ContactEstablished Transition | merged scenario alias into SC-017 |
| alias_merge | ContactEstablished to TouchdownScenarioActive Transition | merged scenario alias into SC-018 |
| alias_merge | GroundReferenceDefined to ClearanceBoundaryMonitoring transition | merged scenario alias into SC-020 |
| alias_merge | ClearanceBoundaryMonitoring to ContactConstraintActive transition | merged scenario alias into SC-021 |
| alias_merge | ContactConstraintActive to TouchdownScenarioActive transition | merged scenario alias into SC-022 |
| alias_merge | TouchdownScenarioActive timeover transition | merged scenario alias into SC-055 |
| alias_merge | Allowed Degradation Condition | merged scenario alias into SC-044 |
| id_replace | impact_load_transfer_active | replaced key parameter with PA-001 |
| id_replace | damping_activated | replaced key parameter with PA-002 |
| id_replace | physical_event_marker_clock | replaced key parameter with PA-017 |
| id_replace | initial_support_force | replaced key parameter with PA-003 |
| id_replace | runway_elevation | replaced key parameter with PA-004 |
| id_replace | M_s | replaced key parameter with PA-006 |
| id_replace | g | replaced key parameter with PA-007 |
| id_replace | piston_zdd_out | replaced key parameter with PA-005 |
| id_replace | v_s_state | replaced key parameter with PA-018 |
| id_replace | y_s_state | replaced key parameter with PA-019 |
| id_replace | K_t | replaced key parameter with PA-009 |
| id_replace | M_u | replaced key parameter with PA-008 |
| id_replace | penetration | replaced key parameter with PA-020 |
| id_replace | v_u_state | replaced key parameter with PA-021 |
| id_replace | y_u_state | replaced key parameter with PA-022 |
| id_replace | K_s | replaced key parameter with PA-012 |
| id_replace | damping_force | replaced key parameter with PA-010 |
| id_replace | oleo_compression_speed | replaced key parameter with PA-011 |
| id_replace | oleo_compression_state | replaced key parameter with PA-023 |
| id_replace | C_v | replaced key parameter with PA-013 |
| id_replace | C_v2 | replaced key parameter with PA-014 |
| id_replace | measured_damping_force | replaced key parameter with PA-016 |
| id_replace | measured_piston_zdd_out | replaced key parameter with PA-015 |
| id_replace | AirframeEquivalentMassLogic | replaced used_in with MO-004 |
| id_replace | HydraulicDampingLogic | replaced used_in with MO-008 |
| id_replace | ReleaseFixtureActuator | replaced used_in with MO-013 |
| id_replace | GroundConstraintEnforcer | replaced used_in with MO-014 |
| id_replace | AirframeMassDynamics | replaced used_in with MO-015 |
| id_replace | TireContactDynamics | replaced used_in with MO-016 |
| id_replace | OleoGasSpringDynamics | replaced used_in with MO-017 |
| id_replace | HydraulicDamperDynamics | replaced used_in with MO-018 |
| id_replace | SensorAndTelemetrySystem | replaced used_in with MO-019 |
| id_replace | PhysicalScenarioClock | replaced used_in with MO-011 |
| id_replace | ScenarioTimelineSource | replaced related_model with MO-001 |
| id_replace | DropTestScenarioTimeline | replaced related_model with MO-002 |
| id_replace | ReleaseFixtureLogic | replaced related_model with MO-003 |
| id_replace | AirframeEquivalentMassLogic | replaced related_model with MO-004 |
| id_replace | TireWheelAssemblyLogic | replaced related_model with MO-005 |
| id_replace | GroundContactBoundaryLogic | replaced related_model with MO-006 |
| id_replace | OleoPneumaticStrutLogic | replaced related_model with MO-007 |
| id_replace | HydraulicDampingLogic | replaced related_model with MO-008 |
| id_replace | AccelerationObservationLogic | replaced related_model with MO-009 |
| id_replace | ScenarioEventMarkerRecorder | replaced related_model with MO-010 |
| id_replace | AirframeMassDynamics | replaced related_model with MO-015 |
| id_replace | GroundConstraintEnforcer | replaced related_model with MO-014 |
| id_replace | TireContactDynamics | replaced related_model with MO-016 |
| id_replace | OleoGasSpringDynamics | replaced related_model with MO-017 |
| id_replace | HydraulicDamperDynamics | replaced related_model with MO-018 |
| id_replace | SensorAndTelemetrySystem | replaced related_model with MO-019 |
| unknown_standardized | unknown | transferred_variable standardized to unknown because no parameter entity matched |
| unknown_standardized | LOGIC_EVT_TOUCHDOWN | transferred_variable standardized to unknown because no parameter entity matched |
| unknown_standardized | LOGIC_EVT_DESCENT_START | transferred_variable standardized to unknown because no parameter entity matched |
| id_replace | clock_inst.simulation_time -> scenario_clock_inst.simulation_time | human_check item mapped to CP-019 |
| id_replace | clock_inst.PHYS_EVT_DESCENT_START -> scenario_clock_inst.in_PHYS_EVT_DESCENT_START | human_check item mapped to CP-020 |
| id_replace | clock_inst.PHYS_EVT_TOUCHDOWN -> scenario_clock_inst.in_PHYS_EVT_TOUCHDOWN | human_check item mapped to CP-021 |
| id_replace | scenario_clock_inst.PHYS_EVT_DESCENT_START -> release_fixture_inst.PHYS_EVT_DESCENT_START | human_check item mapped to CP-022 |
| id_replace | scenario_clock_inst.PHYS_EVT_TOUCHDOWN -> ground_constraint_inst.PHYS_EVT_TOUCHDOWN | human_check item mapped to CP-023 |
| id_replace | release_fixture_inst.release_force -> airframe_mass_inst.release_force | human_check item mapped to CP-024 |
| id_replace | ground_constraint_inst.ground_height -> tire_contact_inst.ground_height | human_check item mapped to CP-025 |
| id_replace | airframe_mass_inst.y_s -> tire_contact_inst.y_s | human_check item mapped to CP-026 |
| id_replace | airframe_mass_inst.y_s -> oleo_strut_inst.y_s | human_check item mapped to CP-027 |
| id_replace | airframe_mass_inst.v_s -> oleo_strut_inst.v_s | human_check item mapped to CP-028 |
| id_replace | tire_contact_inst.y_u -> oleo_strut_inst.y_u | human_check item mapped to CP-029 |
| id_replace | tire_contact_inst.v_u -> oleo_strut_inst.v_u | human_check item mapped to CP-030 |
| id_replace | oleo_strut_inst.oleo_compression_speed -> hydraulic_damper_inst.oleo_compression_speed | human_check item mapped to CP-031 |
| id_replace | hydraulic_damper_inst.damping_force -> oleo_strut_inst.damping_force | human_check item mapped to CP-032 |
| id_replace | oleo_strut_inst.strut_force -> airframe_mass_inst.strut_force | human_check item mapped to CP-033 |
| id_replace | oleo_strut_inst.strut_force -> tire_contact_inst.strut_force | human_check item mapped to CP-034 |
| id_replace | airframe_mass_inst.y_s -> telemetry_inst.y_s | human_check item mapped to CP-035 |
| id_replace | tire_contact_inst.y_u -> telemetry_inst.y_u | human_check item mapped to CP-036 |
| id_replace | airframe_mass_inst.v_s -> telemetry_inst.v_s | human_check item mapped to CP-037 |
| id_replace | tire_contact_inst.v_u -> telemetry_inst.v_u | human_check item mapped to CP-038 |
| id_replace | airframe_mass_inst.piston_zdd_out -> telemetry_inst.piston_zdd_out | human_check item mapped to CP-039 |
| id_replace | tire_contact_inst.tire_deflection -> telemetry_inst.tire_deflection | human_check item mapped to CP-040 |
| id_replace | oleo_strut_inst.oleo_compression -> telemetry_inst.oleo_compression | human_check item mapped to CP-041 |
| id_replace | hydraulic_damper_inst.damping_force -> telemetry_inst.damping_force | human_check item mapped to CP-042 |
| id_replace | scenario_clock_inst.PHYS_EVT_DESCENT_START -> telemetry_inst.PHYS_EVT_DESCENT_START | human_check item mapped to CP-043 |
| id_replace | scenario_clock_inst.PHYS_EVT_TOUCHDOWN -> telemetry_inst.PHYS_EVT_TOUCHDOWN | human_check item mapped to CP-044 |
| id_replace | simulation | human_check item mapped to SC-036 |
| id_replace | simulation_scenario | human_check item mapped to SC-037 |
| id_replace | req0 | human_check item mapped to SC-038 |
| id_replace | req23 | human_check item mapped to SC-039 |
| id_replace | req24 | human_check item mapped to SC-040 |
| id_replace | scenario_states[0] | human_check item mapped to SC-041 |
| id_replace | scenario_states[1] | human_check item mapped to SC-042 |
| id_replace | scenario_states[2] | human_check item mapped to SC-043 |
| id_replace | req28 | human_check item mapped to SC-044 |
| id_replace | req10 | human_check item mapped to SC-067 |
| id_replace | req11 | human_check item mapped to SC-068 |
| id_replace | req12 | human_check item mapped to SC-069 |
| id_replace | req15 | human_check item mapped to SC-070 |
| id_replace | req18 | human_check item mapped to SC-071 |
| id_replace | req19 | human_check item mapped to SC-072 |
| id_replace | req20 | human_check item mapped to SC-073 |
| id_replace | scenario_alignment_rules | human_check item mapped to SC-074 |
| id_replace | impact_load_transfer_active | human_check item mapped to PA-001 |
| id_replace | damping_activated | human_check item mapped to PA-002 |
| id_replace | initial_support_force | human_check item mapped to PA-003 |
| id_replace | runway_elevation | human_check item mapped to PA-004 |
| id_replace | piston_zdd_out | human_check item mapped to PA-005 |
| id_replace | M_s | human_check item mapped to PA-006 |
| id_replace | g | human_check item mapped to PA-007 |
| id_replace | M_u | human_check item mapped to PA-008 |
| id_replace | K_t | human_check item mapped to PA-009 |
| id_replace | damping_force | human_check item mapped to PA-010 |
| id_replace | oleo_compression_speed | human_check item mapped to PA-011 |
| id_replace | K_s | human_check item mapped to PA-012 |
| id_replace | C_v | human_check item mapped to PA-013 |
| id_replace | C_v2 | human_check item mapped to PA-014 |
| id_replace | measured_piston_zdd_out | human_check item mapped to PA-015 |
| id_replace | measured_damping_force | human_check item mapped to PA-016 |
| id_replace | physical_event_marker_clock | human_check item mapped to PA-017 |
| id_replace | v_s_state | human_check item mapped to PA-018 |
| id_replace | y_s_state | human_check item mapped to PA-019 |
| id_replace | penetration | human_check item mapped to PA-020 |
| id_replace | v_u_state | human_check item mapped to PA-021 |
| id_replace | y_u_state | human_check item mapped to PA-022 |
| id_replace | oleo_compression_state | human_check item mapped to PA-023 |
| id_replace | BeforeSchedule to EvtDescentStart Transition Scenario | human_check item mapped to SC-001 |
| id_replace | EvtDescentStart to EvtTouchdown Transition Scenario | human_check item mapped to SC-002 |
| id_replace | EvtTouchdown End State Transition Scenario | human_check item mapped to SC-003 |
| id_replace | PreScenario to DescentScenarioActive Transition Scenario | human_check item mapped to SC-004 |
| id_replace | DescentScenarioActive to TouchdownScenarioActiveEntry Transition Scenario | human_check item mapped to SC-005 |
| id_replace | Touchdown Scenario Active Entry Phase | human_check item mapped to SC-006 |
| id_replace | Touchdown Scenario Active Phase | human_check item mapped to SC-007 |
| id_replace | Aircraft Holding and Release Phase | human_check item mapped to SC-008 |
| id_replace | Post-Release Touchdown Phase | human_check item mapped to SC-009 |
| id_replace | Release Fixture Inactive Transition Phase | human_check item mapped to SC-010 |
| id_replace | Release Fixture Logic - Touchdown Scenario Active | human_check item mapped to SC-011 |
| id_replace | Airframe Equivalent Mass Logic - Supported Initial Condition to Released Descent | human_check item mapped to SC-012 |
| id_replace | Airframe Equivalent Mass Logic - Released Descent to Impact Load Transfer | human_check item mapped to SC-013 |
| id_replace | Airframe Equivalent Mass Logic - Impact Load Transfer to Touchdown Scenario Active | human_check item mapped to SC-014 |
| id_replace | Airframe Equivalent Mass Logic - Touchdown Scenario Active | human_check item mapped to SC-015 |
| id_replace | AirborneNoContact to ClearanceTracking Transition | human_check item mapped to SC-016 |
| id_replace | ClearanceTracking to ContactEstablished Transition | human_check item mapped to SC-017 |
| id_replace | ContactEstablished to TouchdownScenarioActive Transition | human_check item mapped to SC-018 |
| id_replace | TouchdownScenarioActive Self-Transition | human_check item mapped to SC-019 |
| id_replace | GroundReferenceDefined to ClearanceBoundaryMonitoring Transition | human_check item mapped to SC-020 |
| id_replace | ClearanceBoundaryMonitoring to ContactConstraintActive Transition | human_check item mapped to SC-021 |
| id_replace | ContactConstraintActive to TouchdownScenarioActive Transition | human_check item mapped to SC-022 |
| id_replace | ExtendedStroke to StrokeAvailable Transition | human_check item mapped to SC-023 |
| id_replace | StrokeAvailable to CompressionStroke Transition | human_check item mapped to SC-024 |
| id_replace | OleoPneumaticStrutLogic.CompressionStroke | human_check item mapped to SC-025 |
| id_replace | OleoPneumaticStrutLogic.TouchdownScenarioActive | human_check item mapped to SC-026 |
| id_replace | HydraulicDampingLogic.DampingStandby | human_check item mapped to SC-027 |
| id_replace | HydraulicDampingLogic.RelativeMotionMonitoring | human_check item mapped to SC-028 |
| id_replace | HydraulicDampingLogic.DampingActivated | human_check item mapped to SC-029 |
| id_replace | HydraulicDampingLogic.TouchdownScenarioActive | human_check item mapped to SC-030 |
| id_replace | AccelerationObservationLogic.ObservationIdle | human_check item mapped to SC-031 |
| id_replace | AccelerationObservationLogic.BaselineAccelerationRecording | human_check item mapped to SC-032 |
| id_replace | AccelerationObservationLogic.ImpactAccelerationMonitoring | human_check item mapped to SC-033 |
| id_replace | AccelerationObservationLogic.TouchdownScenarioActive | human_check item mapped to SC-034 |
| id_replace | Monitoring State Timeover Event | human_check item mapped to SC-035 |
| id_replace | MainLandingGearDropTest Simulation | human_check item mapped to SC-036 |
| id_replace | MainLandingGearDropTest Physical Context | human_check item mapped to SC-037 |
| id_replace | Vertical Landing Impact Condition | human_check item mapped to SC-038 |
| id_replace | Runway Contact Condition | human_check item mapped to SC-039 |
| id_replace | Repeated Vertical Load-Cycle Condition | human_check item mapped to SC-040 |
| id_replace | PreScenario | human_check item mapped to SC-041 |
| id_replace | DescentStart | human_check item mapped to SC-042 |
| id_replace | Touchdown | human_check item mapped to SC-043 |
| id_replace | Allowed Degradation Condition | human_check item mapped to SC-044 |
| id_replace | PreScenario to DescentScenarioActive Transition | human_check item mapped to SC-045 |
| id_replace | DescentScenarioActive to TouchdownScenarioActiveEntry Transition | human_check item mapped to SC-046 |
| id_replace | TouchdownScenarioActiveEntry to TouchdownScenarioActive Transition | human_check item mapped to SC-047 |
| id_replace | HoldingAircraft to Released Transition | human_check item mapped to SC-048 |
| id_replace | ReleaseFixtureLogic.Released to InactiveAfterRelease on LOGIC_EVT_TOUCHDOWN | human_check item mapped to SC-049 |
| id_replace | ReleaseFixtureLogic.InactiveAfterRelease to TouchdownScenarioActive on timeover | human_check item mapped to SC-050 |
| id_replace | ReleaseFixtureLogic.TouchdownScenarioActive self-transition on timeover | human_check item mapped to SC-051 |
| id_replace | AirframeEquivalentMassLogic.SupportedInitialCondition to ReleasedDescent on LOGIC_EVT_DESCENT_START | human_check item mapped to SC-052 |
| id_replace | AirframeEquivalentMassLogic.ReleasedDescent to ImpactLoadTransfer on LOGIC_EVT_TOUCHDOWN | human_check item mapped to SC-053 |
| id_replace | ImpactLoadTransfer to TouchdownScenarioActive Transition | human_check item mapped to SC-054 |
| id_replace | TouchdownScenarioActive timeover transition | human_check item mapped to SC-055 |
| id_replace | GroundReferenceDefined to ClearanceBoundaryMonitoring transition | human_check item mapped to SC-020 |
| id_replace | ClearanceBoundaryMonitoring to ContactConstraintActive transition | human_check item mapped to SC-021 |
| id_replace | ContactConstraintActive to TouchdownScenarioActive transition | human_check item mapped to SC-022 |
| id_replace | OleoPneumaticStrutLogic ExtendedStroke to StrokeAvailable Transition | human_check item mapped to SC-056 |
| id_replace | OleoPneumaticStrutLogic StrokeAvailable to CompressionStroke Transition | human_check item mapped to SC-057 |
| id_replace | OleoPneumaticStrutLogic CompressionStroke to TouchdownScenarioActive Transition | human_check item mapped to SC-058 |
| id_replace | OleoPneumaticStrutLogic TouchdownScenarioActive Self-Transition | human_check item mapped to SC-059 |
| id_replace | HydraulicDampingLogic DampingStandby to RelativeMotionMonitoring Transition | human_check item mapped to SC-060 |
| id_replace | Touchdown event triggers DampingActivated state | human_check item mapped to SC-061 |
| id_replace | Timeover triggers TouchdownScenarioActive state | human_check item mapped to SC-062 |
| id_replace | Timeover maintains TouchdownScenarioActive state | human_check item mapped to SC-063 |
| id_replace | Descent start event triggers BaselineAccelerationRecording state | human_check item mapped to SC-064 |
| id_replace | Touchdown event triggers ImpactAccelerationMonitoring state | human_check item mapped to SC-065 |
| id_replace | ImpactAccelerationMonitoring to TouchdownScenarioActive Transition | human_check item mapped to SC-066 |
| id_replace | Peak Vertical Shock Acceleration Limit | human_check item mapped to SC-067 |
| id_replace | Maximum Compression Stroke Limit | human_check item mapped to SC-068 |
| id_replace | Hard Bottoming Prevention | human_check item mapped to SC-069 |
| id_replace | Tire Vertical Stiffness Range | human_check item mapped to SC-070 |
| id_replace | Hydraulic Damping Characteristics Range | human_check item mapped to SC-071 |
| id_replace | Sealing Integrity | human_check item mapped to SC-072 |
| id_replace | Load Path Integrity | human_check item mapped to SC-073 |
| id_replace | Physical Simulation Time Alignment | human_check item mapped to SC-074 |
| id_replace | 1D Vertical Translation Constraint | human_check item mapped to SC-075 |
| id_replace | Rigid Runway Surface | human_check item mapped to SC-076 |
| id_replace | Linear Tire Spring Assumption | human_check item mapped to SC-077 |
| id_replace | No Fluid Aeration or Cavitation | human_check item mapped to SC-078 |
| id_replace | Ideal Sensor Assumption | human_check item mapped to SC-079 |

## Appendix. Atomic Refinement Item Counts

- object_refinements: 19
- relation_refinements: 44
- parameter_refinements: 28
- scenario_refinements: 91

