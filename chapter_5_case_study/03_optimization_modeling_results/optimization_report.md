# Optimization Modeling Report

## Design Variables

| id | kind | binding | initial_value | lower_bound | upper_bound |
|---|---|---|---:|---:|---:|
| DV-001 | continuous | `EquivalentAirframeWheelMassAssembly.wheel_mass` | 300.0 | 240.0 | 430.0 |
| DV-002 | continuous | `MainGearTireWheelAssembly.tire_stiffness` | 1700000.0 | 1300000.0 | 2000000.0 |
| DV-003 | continuous | `HydraulicDampingChannel.linear_damping_coeff` | 153475.1727204978 | 102316.7818136652 | 204633.5636273304 |
| DV-004 | continuous | `HydraulicDampingChannel.quadratic_damping_gain` | 1.9602485837391784 | 0.9801242918695892 | 31.363977339826854 |

## Objectives

| id | binding | direction | definition |
|---|---|---|---|
| OBJ-001 | `LandingGearAccelerationMetrics.max_positive_acceleration` | minimize | `max_t(OleoPistonRod.piston_zdd_out(t))` over the drop process |
| OBJ-002 | `LandingGearAccelerationMetrics.max_negative_acceleration_peak` | minimize | `abs(min_t(OleoPistonRod.piston_zdd_out(t)))` over the drop process |

## Constraints

| id | binding | kind | bound | source |
|---|---|---|---|---|
| CON-001 | `LandingGearAccelerationMetrics.max_positive_acceleration` | inequality | `max_positive_acceleration <= 20.0 m/s^2` | `MLG-REQ-010A` |

