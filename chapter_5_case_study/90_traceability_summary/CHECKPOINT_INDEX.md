# Curated Traceability Checkpoints

## Purpose

These files provide representative evidence of how the landing-gear case progressed from requirements to a validated physical model. The seven checkpoints form a concise, inspectable model-evolution chain.

## Evidence Chain

| Stage | Public checkpoint | What it demonstrates |
| --- | --- | --- |
| 1. Requirement preparation | `checkpoints/01_requirements/` | System boundary, stakeholder needs, structured requirements, and requirement trace links. |
| 2. Functional analysis | `checkpoints/02_functional_analysis/` | Function decomposition and allocation of functions to logical subsystem carriers. |
| 3. Use-case modeling | `checkpoints/03_use_case/use_case_model.json` | Actors, use cases, system boundary, and use-case correlations. |
| 4. Logical architecture | `checkpoints/04_logical_architecture/` | Clean logical subsystem/connection structure and its simulation contract. |
| 5. Logic-to-physics transition | `checkpoints/05_logic_physics_transition/` | Mapping from logical variables and events to physical entities, behavior, interfaces, and scenario context. |
| 6. Physical model preparation | `checkpoints/06_physical_model/physical_model_clean.json` | Clean structured physical-model candidate used before final XLanguage delivery. |
| 7. Validation evidence | `checkpoints/07_validation/` | Compile/simulation status, touchdown-time alignment, and representative state-transition CSV traces. |

## Provenance And Curation

- The checkpoint files were selected from the local case-study trace generated on 2026-07-18 and 2026-07-19.
- Public filenames were normalized to describe their role in the evidence chain.
- Artifact contents preserve the selected stage outputs, with public relative paths used for cross-file navigation.
- Files named `*_clean.json` are normalized model artifacts selected as milestone outputs.
- The CSV evidence covers the scenario clock, tire contact, shock-strut state, hydraulic damping state, and acceleration observation.
- `CHECKSUMS.sha256` records the SHA-256 digest of every checkpoint artifact.
