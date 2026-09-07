# RFLP System-Level Comparison Experiment

This directory provides the Section 4.4 system-level benchmark comparing the Step1-Step13 multi-agent RFLP/XLanguage workflow with a sequential single-agent baseline.

## Research Question

Under the same base model, tool access policy, repair budget, task inputs, and final validation standards, does the stage-routed multi-agent workflow produce more complete and verifiable RFLP/XLanguage models than sequential single-agent generation with equivalent workflow knowledge?

## Experiment Groups

The group definitions are recorded in `configs/experiment_groups.json`.

- `multi_agent_current`: the Step1-Step13 multi-agent workflow used as the treatment group.
- `single_agent_sequential_oneshot`: a single role generating requirement, use-case, logical XLanguage, and physical XLanguage model texts in four sequential calls. Each call receives syntax guidance, a one-shot example, and the upstream generated models.

## Benchmark Tasks

`tasks/rflp_benchmark_tasks.jsonl` contains the cross-domain benchmark. Each JSONL row records:

- `task_id`
- `domain`
- `system_name`
- `requirement_zh`
- `expected_scenario_features`
- `notes`

The domain coverage tests workflow behavior across multiple cyber-physical systems and provides a common task basis for paired comparison.

## Shared Controls

Both groups use the same model family and temperature, user task text, maximum repair count, XCom timeout, final pass/fail metrics, and memory policy. The single-agent condition performs its four sequential generations before final validator and XCom evaluation.

## Evidence Files

| File or folder | Contents |
| --- | --- |
| `configs/experiment_groups.json` | Group definitions and common controls. |
| `configs/evaluation_metrics.json` | Artifact, syntax, compilation, execution, and comparison metrics. |
| `prompts/single_agent_sequential_oneshot_prompt.md` | Baseline generation prompt. |
| `tasks/rflp_benchmark_tasks.jsonl` | Benchmark task records. |
| `EXPERIMENT_METHOD_AND_ANALYSIS.md` | Full experiment method and analysis. |
| `public_results/full_20260804_002/results.csv` | Per-task results. |
| `public_results/full_20260804_002/summary.json` | Run-level summary metrics. |
| `public_results/full_20260804_002/paired_multi_valid_results.csv` | Paired valid-output comparisons. |
| `public_results/full_20260804_002/paired_multi_valid_summary.json` | Paired-comparison summary. |
| `public_results/full_20260804_002/EXPERIMENT_REPORT.md` | Human-readable result report. |

## Review Path

Begin with `EXPERIMENT_METHOD_AND_ANALYSIS.md`, verify group settings in `configs/`, inspect task inputs in `tasks/`, and then compare the aggregate and paired results under `public_results/full_20260804_002/`.
