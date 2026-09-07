# Engineering Refinement Summary

## Source Package

- Source package: `../01_rflp_final_models`
- Refinement process: engineering-refinement pipeline producing the structured and human-readable outputs in `../02_engineering_refinement_for_engineers`.
- Public outputs: `../02_engineering_refinement_for_engineers`

## Aggregated Result

- Total atomic refinement items: 182
- Object refinements: 19
- Relation refinements: 44
- Parameter refinements: 28
- Scenario refinements: 91
- Model object cards: 19
- Interface couplings: 18
- Parameter dictionary rows: 28
- Simulation scenario rows: 91
- LLM batch completion rate: 100%
- Rule consistency status: `pass`

## Landing Gear Optimization-Relevant Parameters Captured

- `M_u`: unsprung wheel mass, corresponding to `wheel_mass = 300.0`.
- `K_t`: tire stiffness approximation, corresponding to `tire_stiffness = 1700000.0`.
- `C_v`: linear oleo damping coefficient, corresponding to `linear_damping_coeff = 153475.1727204978`.
- `C_v2`: quadratic oleo damping coefficient, corresponding to `quadratic_damping_gain = 1.9602485837391784`.

## Acceleration-Relevant Objective Evidence

- `piston_zdd_out`: vertical acceleration of the equivalent airframe mass.
- `measured_piston_zdd_out`: measured airframe acceleration.
- `Peak Vertical Shock Acceleration Limit`: scenario/metric evidence for acceleration peak evaluation.

The engineering-refinement outputs explicitly label units, ranges, transferred variables, and review-sensitive assumptions as human-check items for engineering confirmation.
