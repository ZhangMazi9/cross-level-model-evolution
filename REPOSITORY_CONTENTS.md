# Repository Contents

This index maps each manuscript claim area to the corresponding public evidence in the repository.

## Chapter 4: Section 4.4 Experiments

### System-Level Comparison

Location: `4_4_experiments/system_level_comparison/`

| Material | Location | Purpose |
| --- | --- | --- |
| Experiment definition | `configs/experiment_groups.json` | Defines the multi-agent treatment and sequential single-agent baseline. |
| Evaluation definition | `configs/evaluation_metrics.json` | Records artifact, syntax, compilation, execution, and paired-comparison metrics. |
| Benchmark tasks | `tasks/rflp_benchmark_tasks.jsonl` | Provides cross-domain RFLP task inputs and expected scenario features. |
| Baseline prompt | `prompts/single_agent_sequential_oneshot_prompt.md` | Documents the sequential single-agent generation condition. |
| Method and analysis | `EXPERIMENT_METHOD_AND_ANALYSIS.md` | Describes experimental design, fairness controls, evaluation, and analysis. |
| Reported results | `public_results/full_20260804_002/` | Provides per-task rows, run summaries, paired valid comparisons, and the experiment report. |

### JSON IR Ablation

Location: `4_4_experiments/json_ir_ablation/`

| Material | Location | Purpose |
| --- | --- | --- |
| Ablation definition | `configs/ablation_groups.json` | Defines the four representation/gating conditions and shared controls. |
| Benchmark tasks | `tasks/rflp_logic_step9_ablation_tasks.jsonl` | Provides the 18 complete Step9 benchmark cases. |
| Experiment report | `JSON_IR_ABLATION_EXPERIMENT_REPORT.md` | Describes design, metrics, statistical comparisons, and conclusions. |
| Aggregate results | `public_results/*.csv` | Provides model-level, task-level, and paired permutation-test statistics. |
| Four-model figure | `public_results/figures/four_model_pass_rates.{png,svg,pdf}` | Visualizes pass rates for all four evaluated models. |

## Chapter 5: Landing-Gear Case Study

Location: `chapter_5_case_study/`

| Material | Location | Purpose |
| --- | --- | --- |
| Final RFLP models | `01_rflp_final_models/` | Provides requirement, use-case, logical, and physical model artifacts. |
| Engineering refinement | `02_engineering_refinement_for_engineers/` | Provides the readable refinement report, structured package, run summary, and engineering confirmation record. |
| Optimization modeling | `03_optimization_modeling_results/` | Provides optimization inputs, model IR, XLanguage model, summaries, and validation report. |
| Traceability evidence | `90_traceability_summary/` | Provides the seven-stage evidence chain, representative validation traces, summaries, and checksums. |

## Verification Anchors

- Section 4.4 system-level results: `4_4_experiments/system_level_comparison/public_results/full_20260804_002/summary.json`
- Section 4.4 ablation statistics: `4_4_experiments/json_ir_ablation/public_results/four_model_360_metrics.csv`
- Chapter 5 flow status: `chapter_5_case_study/90_traceability_summary/rflp_flow_summary.json`
- Chapter 5 checkpoint provenance: `chapter_5_case_study/90_traceability_summary/CHECKPOINT_INDEX.md`
- Chapter 5 checkpoint integrity: `chapter_5_case_study/90_traceability_summary/CHECKSUMS.sha256`
