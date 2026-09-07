The conceptual physical architecture for the Main Landing Gear (MLG) drop-test simulation comprises real physical entities, environmental boundaries, actuators, sensors, and data evaluation systems that interact to simulate vertical impact dynamics.

1. Physical Plant and Structural Entities:
- EquivalentAirframeMass: Represents the supported mass of the aircraft, acting as the primary inertial body subjected to gravity and release forces.
- WheelAndTireAssembly: The unsprung mass and pneumatic tire structure that interfaces with the ground, using the direct tire_stiffness parameter to generate tire_deflection and tire_force upon contact.
- WheelAxleAndSlidingTube: The structural linkage transmitting tire_force from the wheel assembly to the shock strut.
- OleoPneumaticShockStrutAssembly: Comprises the UpperCylinderAndMainFitting and ShockStrutGasChamber, providing the pneumatic spring force based on oleo_compression.
- ShockStrutSlidingJoint: The mechanical interface allowing relative vertical motion between the sliding tube and upper cylinder.
- HydraulicDampingChannel: The internal fluid path within the strut that generates damping_force proportional to oleo_compression_speed.
- StructuralLoadPath: The physical load transfer route connecting the airframe attachment to the wheel assembly.

2. Environment Sources and Physical Boundaries:
- Gravity Source: A constant environmental field applying gravitational_acceleration and gravity_load to the EquivalentAirframeMass.
- RunwaySurface / RunwayGroundBoundary: The rigid environmental boundary defining the ground_height constraint. It generates the ground_impact_reaction_force when the tire penetrates the surface.
- AirframeAttachment Boundary: The initial supported mass boundary that transitions to a free-fall state upon release.
- DropTestReleaseFixture Boundary: The physical mechanism holding the mass before the drop test, controlled by the release_force.

3. Actuators and Scenario Drivers:
- PhysicalScenarioClock: The master timing controller that broadcasts physical scenario time triggers, specifically initiating the EVT_DESCENT_START at 0.0s and EVT_TOUCHDOWN at 0.23s.
- ReleaseFixtureActuator: The physical driver that drops the release_force to zero at 0.0s, transitioning the EquivalentAirframeMass from a supported state to free-fall.
- GroundConstraintEnforcer: The boundary actuator that activates the ground_height constraint at 0.23s, enabling the ground_impact_reaction_force.

4. Sensors, Telemetry, and Evaluators:
- SensorAndTelemetrySystem: A distributed network of physical sensors measuring kinematic and dynamic states, including y_s, y_u, v_s, v_u, piston_zdd_out, tire_deflection, oleo_compression, oleo_compression_speed, tire_force, and damping_force.
- DataLogger: The evaluation and recording system that continuously streams sensor data to generate time-series CSV traces. It extracts safety and constraint metrics such as peak_positive_acceleration, peak_negative_acceleration, maximum_oleo_compression, bottoming_margin, and post_impact_stability. It also records physical event markers (PHYS_EVT_DESCENT_START, PHYS_EVT_TOUCHDOWN).

5. Information Flow and Signal Routing:
- The PhysicalScenarioClock triggers the ReleaseFixtureActuator to remove release_force, allowing gravity to accelerate the EquivalentAirframeMass (tracked via y_s, v_s).
- At 0.23s, the RunwayGroundBoundary enforces the ground_height constraint. The WheelAndTireAssembly calculates tire_deflection and generates tire_force.
- The tire_force is transmitted through the WheelAxleAndSlidingTube to the OleoPneumaticShockStrutAssembly, causing oleo_compression.
- The ShockStrutSlidingJoint motion generates oleo_compression_speed, which drives the HydraulicDampingChannel to produce damping_force.
- The SensorAndTelemetrySystem continuously monitors these physical responses, feeding piston_zdd_out and other variables to the DataLogger for post-processing, rebound decay evaluation, and stability assessment.