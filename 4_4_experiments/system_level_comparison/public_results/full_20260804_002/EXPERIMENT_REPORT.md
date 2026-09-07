# RFLP Agent Comparison Experiment Report

Run ID: `full_20260804_002`

Date: 2026-08-04 to 2026-08-05

Task set: 24 cross-domain RFLP tasks

Groups:

- `multi_agent_current`: original Step1-Step13 multi-agent system.
- `single_agent_sequential_oneshot`: one single agent role, four sequential
  one-shot generations: requirement, use case, logical XLanguage, physical
  XLanguage. Validation was performed only after generation and was not fed back
  for repair.

Execution controls:

- Max concurrency: 6 task/group subprocesses.
- Per-task timeout: 7200 seconds.
- Multi-agent max repairs: 6.
- Single-agent generation calls per task: 4.
- LLM judge inputs were restricted to the original user requirement, final
  logical model text, and final physical model text.
- Samples missing either final logical or final physical model text were assigned
  score 1 for all five LLM-judge criteria.

## Hard Metrics

| Group | N | Req/UseCase Syntax Pass | Logical XCom Compile Pass | Physical XCom Compile Pass | All Hard Pass |
|---|---:|---:|---:|---:|---:|
| multi_agent_current | 24 | 20/24 = 83.33% | 15/24 = 62.50% | 13/24 = 54.17% | 13/24 = 54.17% |
| single_agent_sequential_oneshot | 24 | 22/24 = 91.67% | 0/24 = 0.00% | 0/24 = 0.00% | 0/24 = 0.00% |

## LLM Judge Scores

Scores use a 1-5 scale. Values below are mean +/- standard deviation.

### Paired Tasks Where Multi-Agent Has Final Outputs

This table uses only the 13 tasks where `multi_agent_current` produced both a
final logical model and a final physical model. The single-agent group is
restricted to the same 13 task IDs for a paired comparison.

| Group | Valid N | Logical Architecture | Physical Architecture | Logical Simulation | Physical Simulation | Logical-Physical Consistency |
|---|---:|---:|---:|---:|---:|---:|
| multi_agent_current | 13 | 2.85 +/- 0.80 | 4.23 +/- 0.93 | 2.69 +/- 1.03 | 4.23 +/- 1.09 | 3.23 +/- 1.09 |
| single_agent_sequential_oneshot | 13 | 3.46 +/- 0.78 | 3.54 +/- 0.97 | 3.46 +/- 0.88 | 3.92 +/- 0.76 | 2.85 +/- 1.07 |

### All 24 Tasks

Rows missing final logical or physical model text are included as score 1.

| Group | N | Missing Final Outputs | Logical Architecture | Physical Architecture | Logical Simulation | Physical Simulation | Logical-Physical Consistency |
|---|---:|---:|---:|---:|---:|---:|---:|
| multi_agent_current | 24 | 11 | 2.00 +/- 1.10 | 2.75 +/- 1.78 | 1.92 +/- 1.14 | 2.75 +/- 1.82 | 2.21 +/- 1.38 |
| single_agent_sequential_oneshot | 24 | 0 | 3.58 +/- 0.78 | 3.62 +/- 1.01 | 3.62 +/- 0.92 | 4.08 +/- 0.78 | 2.88 +/- 1.08 |

## Run Outcomes

| Group | Completed Runs | Model-Failed Runs |
|---|---:|---:|
| multi_agent_current | 13 | 11 |
| single_agent_sequential_oneshot | 24 | 0 |

Two multi-agent task subprocesses reached the 7200-second timeout and were
recorded as model-failed runs:

- `rflp_003`
- `rflp_024`

## Interpretation Notes

- The single-agent sequential baseline produced syntactically valid
  requirement/use-case models more often than the multi-agent system, but none
  of its logical or physical XLanguage models compiled through XCom.
- The multi-agent system achieved nonzero logical and physical XCom pass rates,
  including 13/24 full hard-metric passes.
- Under the revised blind-judge protocol without the explicit compilation
  instruction paragraph, the single-agent outputs still score higher on most
  text-only semantic criteria, while having zero logical and physical XCom
  compilation success.
- Among multi-agent samples that did produce final logical and physical models,
  the physical architecture and physical simulation scores are high; the all-24
  averages drop because 11/24 multi-agent samples lacked final outputs and were
  assigned score 1 by rule.
- The added logical-physical consistency score shows a useful nuance: on valid
  paired outputs, multi-agent models have stronger physical modeling and
  logic-to-physics consistency than the single-agent baseline, but the all-24
  average is lower because of missing final multi-agent outputs.
- The hard metrics are therefore the more decisive engineering evidence for
  executable model generation. The LLM scores are useful as complementary
  qualitative signals, not as replacements for syntax/XCom validation.

## Output Files

- Hard and LLM-judge summary: `evaluation/summary.json`
- Per-task table: `evaluation/results.csv`
- Paired 13-task summary: `evaluation/paired_multi_valid_summary.json`
- Paired 13-task table: `evaluation/paired_multi_valid_results.csv`
- Subprocess logs: `_process_logs/`
- Group/task artifacts: `multi_agent_current/` and
  `single_agent_sequential_oneshot/`
