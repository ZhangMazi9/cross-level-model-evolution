# Optimization Modeling Results

This folder contains the formal optimization-modeling results generated from the current landing-gear RFLP physical model with the requirement-derived positive acceleration constraint. The most useful user-facing output is the concise optimization summary.

## User-Facing Outputs

| File | Purpose |
| --- | --- |
| `user_summary.md` | Optimization variables, objectives, constraints, and concise validation report |
| `user_summary.json` | Machine-readable version of the same user-facing summary |

## Modeling Deliverables

| File | Purpose |
| --- | --- |
| `LandingGearDropOptimization.xl` | Generated XLanguage MDO optimization model |
| `optimization_model.json` | Structured OptimizationModel intermediate representation |
| `optimization_report.md` | Detailed optimization-modeling report |
| `validation_report.json` | Detailed validation report for bindings, engineering semantics, MDO syntax, and generated text |

## Inputs and Run Brief

| File | Purpose |
| --- | --- |
| `landing_gear_physical_model_for_optimization.json` | Physical-model candidate input used by the optimization-modeling pipeline |
| `landing_gear_optimization_brief.txt` | Task-specific external brief, including the requested golden case and required variables/objectives |

The physical-model candidate and task-specific brief document the inputs used to construct the optimization model and its validation record.
