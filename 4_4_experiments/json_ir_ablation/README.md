# JSON IR Step9 Logic Ablation Experiment

This directory provides the Section 4.4 Step9 ablation experiment. It isolates logical-model generation and evaluates two factors:

- use of `SystemModel` JSON IR before XLanguage generation;
- use of a static gate with bounded gate-guided rework.

The complementary system-level multi-agent comparison is documented in `../system_level_comparison/`.

## Task Set

`tasks/rflp_logic_step9_ablation_tasks.jsonl` contains 18 cross-domain tasks with complete Step1-Step8 preparation. Each task records its identifier, domain, system name, Chinese requirement, expected scenario features, and notes.

The experiment uses a common upstream artifact basis for all four Step9 conditions. The upstream artifact types comprise stakeholder needs, system context, use cases, functional analysis, subsystem analysis, structured requirements, XLanguage requirements, architecture descriptions, and behavior descriptions.

## Experiment Groups

The four conditions are defined in `configs/ablation_groups.json`.

| Group | Representation | Gate setting | Evaluation role |
| --- | --- | --- | --- |
| `json_ir_guarded` | `SystemModel` JSON IR | Schema, normalization, and semantic-rule gate with bounded rework | Tests JSON IR with structural guidance. |
| `json_ir_ungated` | `SystemModel` JSON IR | Direct deterministic code generation | Isolates the JSON IR representation effect. |
| `direct_xl_static_gate` | Direct logical XLanguage | Matched static/semantic gate with bounded rework | Tests gate support for direct generation. |
| `direct_xl_ungated` | Direct logical XLanguage | Final evaluation path | Provides the direct-generation reference condition. |

## Controlled Evaluation

All four groups target Step9 logical-model generation and use a final one-shot compiler evaluation. Static or semantic gate feedback is available to the corresponding guarded conditions, while compiler diagnostics serve as final evaluation evidence. This design separates representation and gate effects within a shared task and evaluation setting.

The primary metric is `compiler_pass`, defined as successful compilation/build of the generated Step9 logical XLanguage model. Secondary metrics cover artifact production, syntax, static-gate status, generation status, gate-rework count, and complete XCom evaluation.

## Main Comparisons

| Comparison | Effect measured |
| --- | --- |
| `json_ir_ungated` vs `direct_xl_ungated` | JSON IR representation effect. |
| `json_ir_guarded` vs `json_ir_ungated` | Schema, normalization, semantic-rule, and bounded-rework contribution. |
| `direct_xl_static_gate` vs `direct_xl_ungated` | Matched gate contribution for direct XLanguage generation. |
| `json_ir_guarded` vs `direct_xl_static_gate` | Representation comparison under matched static guidance. |

## Evidence Files

| File or folder | Contents |
| --- | --- |
| `configs/ablation_groups.json` | Four condition definitions and common controls. |
| `tasks/rflp_logic_step9_ablation_tasks.jsonl` | Eighteen benchmark tasks. |
| `JSON_IR_ABLATION_EXPERIMENT_REPORT.md` | Full method, metrics, statistical analysis, and conclusions. |
| `public_results/four_model_360_metrics.csv` | Consolidated four-model aggregate metrics. |
| `public_results/four_model_task_model_dynamic_pass_rates_18x4_long.csv` | Long-form task-by-model dynamic pass rates. |
| `public_results/four_model_task_level_dynamic_pass_rates_18x4_average.csv` | Task-level four-model averages. |
| `public_results/four_model_paired_permutation_tests.csv` | Pairwise permutation-test results. |
| `public_results/four_model_average_paired_permutation_tests.csv` | Average paired permutation-test results. |
| `public_results/figures/four_model_pass_rates.{png,svg,pdf}` | Four-model comparison figure in three publication formats. |

## Review Path

Begin with `JSON_IR_ABLATION_EXPERIMENT_REPORT.md`, verify condition settings in `configs/ablation_groups.json`, inspect task coverage in `tasks/`, and then use the CSV tables and consolidated figure under `public_results/`.
