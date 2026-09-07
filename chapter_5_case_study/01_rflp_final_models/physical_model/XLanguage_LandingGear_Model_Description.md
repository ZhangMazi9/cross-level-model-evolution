# XLanguage Landing Gear Physical Model Description

This task folder uses the no-added-constraint landing gear physical model for optimization.

## Tire Model Alignment

The tire model has been aligned with the original CAE design-interface parameter `dimension2`.

Current concept-design equation:

```text
raw_deflection = ground_height + tire_radius - y_u
tire_deflection = max(raw_deflection, 0)
tire_force = tire_stiffness * tire_deflection
```

Parameter mapping:

```text
tire_stiffness = dimension2
```

Baseline:

```text
tire_stiffness = 1700000.0
```

## Main Modules

| Module | Role |
| --- | --- |
| `DropTestGroundBlock` | Ground reference for drop test |
| `MainGearTireWheelAssembly` | Tire deflection and linear tire force |
| `ShockStrutSlidingJoint` | Oleo compression, compression speed, and air-chamber deflection |
| `ShockStrutGasChamber` | Gas chamber force table |
| `ShockStrutOilChamber` | Oil chamber restoring-force table |
| `HydraulicDampingChannel` | Linear and quadratic hydraulic damping |
| `OleoPneumaticShockStrutAssembly` | Sum of gas, oil, and damping forces |
| `EquivalentAirframeWheelMassAssembly` | Two-mass vertical dynamics |
| `DropTestReleaseFixture` | Initial release transient |
| `OleoPistonRod` | Output acceleration mapping |

## Main Equations

Vertical dynamics:

```text
a_s = -g + oleo_force / sprung_mass
a_u = -g - oleo_force / wheel_mass + tire_force / wheel_mass + release_force / wheel_mass

der(y_s) = v_s
der(v_s) = a_s
der(y_u) = v_u
der(v_u) = a_u
```

Oleo compression:

```text
oleo_raw_compression = oleo_initial_axial_length - (y_s - y_u) / oleo_axis_vertical_projection
oleo_compression = smooth_min(oleo_initial_axial_length, smooth_max(oleo_raw_compression, 0))
oleo_compression_speed = smooth_max((v_u - v_s) / oleo_axis_vertical_projection, 0)
```

Gas and oil restoring forces:

```text
air_force = AirCurve(air_deflection) - AirCurve(0)
oil_force = OilCurve(oleo_compression) - OilCurve(0)
```

Hydraulic damping:

```text
damping_force =
    linear_damping_coeff * oleo_compression_speed
    + quadratic_damping_gain * oleo_compression_speed^2
```

Shock strut total force:

```text
oleo_force = air_force + oil_force + damping_force
```

Output acceleration:

```text
piston_zdd_out =
    piston_accel_sprung_weight * a_s
    + (1 - piston_accel_sprung_weight) * a_u
```

## Optimized Variables

| Variable | CAE reference | Baseline |
| --- | --- | ---: |
| `wheel_mass` | `dimension1` | 300.0 |
| `tire_stiffness` | `dimension2` | 1700000.0 |
| `linear_damping_coeff` | mapped from `dimension3` | 153475.1727204978 |
| `quadratic_damping_gain` | mapped from `dimension4` | 1.9602485837391784 |
