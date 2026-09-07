# JSON IR Step9 Logic Ablation Experiment

## 1. Objective

This experiment evaluates whether a JSON intermediate representation (JSON IR) improves the successful generation of RFLP logical models in XLanguage. It compares two generation routes:

- generation of a structured SystemModel JSON IR followed by deterministic XLanguage code generation;
- direct XLanguage generation by a large language model.

The experiment also evaluates the contribution of Schema checks, static and semantic gates, and bounded gate-guided rework. The measurement target is Step9 logical-model generation, which isolates representation and gate effects.

## 2. Scope and Controls

All groups start from the same complete Step1-Step8 artifacts for the corresponding tasks in ../system_level_comparison/. These upstream artifacts cover requirements, use cases, functional analysis, subsystem analysis, architecture descriptions, and behavior descriptions.

The shared controls are:

- Step9 logical-model generation as the modeling and evaluation target;
- final compiler diagnostics applied in a common one-shot evaluation;
- CSV state and numerical traces used for final dynamic-change evaluation;
- shared semantic-review, scenario-timeline, and event-recorder settings;
- model temperature of 0;
- five repetitions per case;
- up to three rounds of gate-guided rework for G1 and G3.

The experimental variables are the Step9 representation and the gate/rework setting.

## 3. Task Set

The experiment uses 18 cases with complete Step1-Step8 artifacts. Each case is evaluated five times under four conditions:

18 cases x 5 repetitions x 4 groups = 360 runs

| Task | Domain | System |
| --- | --- | --- |
| rflp_001 | landing_gear | MainLandingGearRetractionSystem |
| rflp_002 | water_tank | DualTankLevelControlSystem |
| rflp_003 | thermal_management | BatteryPackThermalManagementSystem |
| rflp_004 | vehicle_braking | AutonomousVehicleBrakeAssistSystem |
| rflp_005 | robotics | RobotArmJointPositioningSystem |
| rflp_007 | pump_valve | ChemicalDosingFlowControlSystem |
| rflp_008 | wind_turbine | WindTurbinePitchControlSystem |
| rflp_009 | elevator_platform | IndustrialLiftSafetyControlSystem |
| rflp_010 | hvac | SmartHVACZoneControlSystem |
| rflp_013 | medical_infusion | InfusionPumpSafetySystem |
| rflp_016 | warehouse_agv | WarehouseAGVPathFollowingSystem |
| rflp_017 | hydraulic_press | HydraulicPressForceControlSystem |
| rflp_018 | air_compressor | AirCompressorPressureControlSystem |
| rflp_019 | smart_irrigation | SmartIrrigationMoistureControlSystem |
| rflp_021 | crane_anti_sway | CraneAntiSwayControlSystem |
| rflp_022 | cold_chain | ColdChainCabinetTemperatureSystem |
| rflp_023 | pipeline_leak | PipelineLeakDetectionIsolationSystem |
| rflp_024 | prosthetic_knee | ProstheticKneeDampingControlSystem |

## 4. Experimental Groups

### 4.1 G1: json_ir_guarded

G1 generates a SystemModel JSON IR, applies JSON Schema checks, low-risk normalization, semantic-rule checks, and bounded gate-guided rework, and then uses deterministic code generation to produce the logical XLanguage model.

### 4.2 G2: json_ir_ungated

G2 generates a SystemModel JSON IR and sends it directly to deterministic code generation. This condition isolates the effect of the JSON IR representation.

### 4.3 G3: direct_xl_static_gate

G3 generates logical XLanguage directly and then applies an XLanguage static/semantic gate of matched or lower strength. The checks cover basic format, declared ports and states, connections, transition targets, time-driven output sources, and bounded gate-guided rework.

### 4.4 G4: direct_xl_ungated

G4 directly generates the logical XLanguage model and serves as the direct-generation reference condition.

## 5. Evaluation Criterion

The primary criterion is dynamic_change_pass. A sample passes when it compiles and its simulation CSV contains either a numerical-variable change or a state-machine transition:

dynamic_change_pass =
  compiler_pass
  AND (numeric_variable_changed OR state_machine_state_changed)

A simulator timeout is counted as a pass when a CSV trace has already been produced and contains a valid change. This rule evaluates whether the candidate produces meaningful dynamics.

Compiler pass rate is reported as a secondary metric.

## 6. Result Data

The final dataset contains 360 evaluation records from four groups, 18 cases, and five repetitions per case. Dynamic evaluation is recorded for every row.

The repository provides:

- public_results/four_model_360_metrics.csv: four-model aggregate metrics;
- public_results/four_model_task_model_dynamic_pass_rates_18x4_long.csv: long-form case-by-model results;
- public_results/four_model_task_level_dynamic_pass_rates_18x4_average.csv: case-level mean pass rates;
- public_results/four_model_paired_permutation_tests.csv: within-model paired permutation tests;
- public_results/four_model_average_paired_permutation_tests.csv: cross-model average paired permutation tests;
- public_results/figures/four_model_pass_rates.*: consolidated four-model figure.

## 7. Results

### 7.1 Dynamic-Change Pass Rate

| Group | Pass | Fail | Total | Pass rate | Numerical-change pass | State-only pass | Compile failure | No-change failure |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| G1 json_ir_guarded | 68 | 22 | 90 | 75.56% | 56 | 12 | 14 | 8 |
| G2 json_ir_ungated | 5 | 85 | 90 | 5.56% | 4 | 1 | 68 | 17 |
| G3 direct_xl_static_gate | 37 | 53 | 90 | 41.11% | 37 | 0 | 48 | 5 |
| G4 direct_xl_ungated | 10 | 80 | 90 | 11.11% | 4 | 6 | 47 | 33 |

G1 achieved the highest pass rate. G3 also substantially exceeded G4, showing that static/semantic gating and diagnostic rework improved dynamic validity for direct XLanguage generation.

### 7.2 Compiler Pass Rate

| Group | Compile pass | Total | Compile pass rate |
| --- | ---: | ---: | ---: |
| G1 json_ir_guarded | 76 | 90 | 84.44% |
| G2 json_ir_ungated | 22 | 90 | 24.44% |
| G3 direct_xl_static_gate | 42 | 90 | 46.67% |
| G4 direct_xl_ungated | 43 | 90 | 47.78% |

G3 and G4 had similar compilation rates, whereas their dynamic-change pass rates were 41.11% and 11.11%, respectively. The gate therefore contributed more strongly to meaningful dynamic behavior than to compilation alone.

### 7.3 Paired Comparisons

Pairs match the same case and repetition. left_only indicates a pass only for the left-hand group, right_only indicates a pass only for the right-hand group, and left_advantage equals left_only minus right_only.

| Comparison | left_only | right_only | Both pass | Both fail | Net advantage |
| --- | ---: | ---: | ---: | ---: | ---: |
| G1 vs G2 | 63 | 0 | 5 | 22 | +63 |
| G3 vs G4 | 32 | 5 | 5 | 48 | +27 |
| G1 vs G3 | 38 | 7 | 30 | 15 | +31 |
| G2 vs G4 | 4 | 9 | 1 | 76 | -5 |

The paired results show strong gate benefits for both generation routes and a further advantage for JSON IR under guarded conditions.

## 8. Gate-Guided Rework

| Group | Mean rework count | 0 rounds | 1 round | 2 rounds | 3 rounds |
| --- | ---: | ---: | ---: | ---: | ---: |
| G1 json_ir_guarded | 1.03 | 0 | 87 | 3 | 0 |
| G3 direct_xl_static_gate | 0.90 | 11 | 77 | 2 | 0 |

Most G1 samples underwent one JSON IR gate-guided revision and achieved the highest dynamic pass rate. Most G3 samples also triggered revision, but direct edits to XLanguage were associated with more compilation failures.

## 9. Interpretation

### 9.1 Contribution of JSON IR

G1 and G3 both use gates, yet their pass rates were 75.56% and 41.11%. JSON IR therefore serves as a structured constraint boundary on which Schema validation, normalization, and semantic rules can operate reliably.

G2 and G4 represent the ungated routes, with pass rates of 5.56% and 11.11%. The comparison indicates that the value of JSON IR emerges from its combination with structured checking, normalization, bounded revision, and deterministic generation.

### 9.2 Contribution of the Gate

The net advantages were +63 for G1 over G2 and +27 for G3 over G4. In the JSON IR route, the gate can directly identify structural issues in ports, states, connections, and actions before deterministic XLanguage generation. In the direct route, revision operates on XLanguage text itself and can introduce syntax defects such as extra end statements or mismatched blocks.

### 9.3 Compilation versus Dynamic Validity

Compilation alone did not distinguish G3 from G4, but the dynamic-change criterion did. G4 produced many compilable models with static simulation traces, whereas the G3 gate reduced this outcome and increased the number of models with numerical changes. Dynamic-change pass rate is therefore the primary success measure for this experiment.

## 10. Conclusions

1. JSON IR combined with Schema checks, low-risk normalization, semantic gating, and diagnostic rework substantially improved Step9 logical-model generation.
2. The ungated JSON IR condition performed poorly, showing that structured representation and structured checking operate as a combined mechanism.
3. Static/semantic gating improved dynamic validity for direct XLanguage generation, while syntax stability remained more challenging than in the JSON IR route.
4. Compiler pass rate alone was insufficient to measure logical-model validity; numerical changes and state-machine transitions provided additional behavioral evidence.
5. G1 json_ir_guarded was the best-performing condition under the 18-case, five-repetition design, with a dynamic-change pass rate of 75.56%.

Overall, JSON IR functions as an inspectable and correctable semantic carrier for complex RFLP logical-model constraints rather than merely as an additional output format.

## 11. Result File Index

| File | Contents |
| --- | --- |
| configs/ablation_groups.json | Four experimental conditions and shared controls |
| tasks/rflp_logic_step9_ablation_tasks.jsonl | Eighteen benchmark tasks |
| public_results/four_model_360_metrics.csv | Four-model aggregate metrics |
| public_results/four_model_task_model_dynamic_pass_rates_18x4_long.csv | Long-form case-by-model results |
| public_results/four_model_task_level_dynamic_pass_rates_18x4_average.csv | Case-level mean pass rates |
| public_results/four_model_paired_permutation_tests.csv | Within-model paired permutation tests |
| public_results/four_model_average_paired_permutation_tests.csv | Cross-model average paired permutation tests |
| public_results/figures/four_model_pass_rates.png | Consolidated four-model pass-rate figure |

