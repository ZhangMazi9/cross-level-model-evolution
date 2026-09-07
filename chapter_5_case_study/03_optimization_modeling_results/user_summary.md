# User Summary: LandingGearDropOptimization

## Optimization Elements

| Element | Name | Subsystem | Direction / Type |
|---|---|---|---|
| Design variable | `wheel_mass` | `EquivalentAirframeWheelMassAssembly` | continuous |
| Design variable | `tire_stiffness` | `MainGearTireWheelAssembly` | continuous |
| Design variable | `linear_damping_coeff` | `HydraulicDampingChannel` | continuous |
| Design variable | `quadratic_damping_gain` | `HydraulicDampingChannel` | continuous |
| Objective | `max_positive_acceleration` | `LandingGearAccelerationMetrics` | minimize |
| Objective | `max_negative_acceleration_peak` | `LandingGearAccelerationMetrics` | minimize |
| Constraint | `max_positive_acceleration_limit` | `LandingGearAccelerationMetrics` | `max_positive_acceleration <= 20.0 m/s^2` |

## Minimal Validation

| Check | Status | Detail |
|---|---|---|
| variable_count | pass | 4 design variable(s) |
| objective_count | pass | 2 objective(s) |
| constraint_count | pass | 1 requirement-derived constraint |
| binding_check | pass | all selected bindings exist |
| engineering_semantics | pass | no issues |
| mdo_syntax | pass | no issues |
| mdo_text | pass | generated MDO text matches IR |

