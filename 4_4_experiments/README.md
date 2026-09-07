# Section 4.4 Experiments

This directory contains the two experiments reported in Section 4.4. Together, they evaluate system-level workflow performance and the contribution of JSON intermediate representation and static gating to logical-model generation.

## Experiment Map

| Experiment | Research focus | Main evidence |
| --- | --- | --- |
| `system_level_comparison/` | Multi-agent Step1-Step13 workflow versus a sequential single-agent baseline | Cross-domain task set, controlled group definitions, evaluation metrics, per-task results, paired comparisons, and full experiment report. |
| `json_ir_ablation/` | JSON IR versus direct XLanguage generation under guarded and ungated conditions | Four-condition configuration, 18-task set, aggregate metrics, paired permutation tests, and four-model pass-rate figure. |

## Recommended Reading Order

1. Read `system_level_comparison/EXPERIMENT_METHOD_AND_ANALYSIS.md` for the system-level evaluation design.
2. Inspect `system_level_comparison/public_results/full_20260804_002/` for reported comparison results.
3. Read `json_ir_ablation/JSON_IR_ABLATION_EXPERIMENT_REPORT.md` for the Step9 ablation design and conclusions.
4. Inspect `json_ir_ablation/public_results/` for model-level and task-level statistics.
5. View `json_ir_ablation/public_results/figures/four_model_pass_rates.*` for the consolidated four-model comparison.

## Shared Evidence Structure

Both experiments provide machine-readable task definitions, explicit condition configurations, evaluation criteria, aggregate result tables, and human-readable analysis documents. These materials connect the manuscript's Section 4.4 claims to inspectable repository artifacts.
