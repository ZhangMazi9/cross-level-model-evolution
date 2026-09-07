# Qwen3.8-Flash and MiniMax-M2.5 Supplementary Experiment Summary

Each model was evaluated under four configurations across 18 tasks and five repetitions, producing 360 records per model and 720 records in total. G1 denotes `json_ir_guarded`, G2 denotes `json_ir_ungated`, G3 denotes `direct_xl_static_gate`, and G4 denotes `direct_xl_ungated`.

The dynamic-change criterion requires successful compilation and either a numerical-variable change or a `current_state`/state-machine transition in the simulation CSV. The first 10 G1 records for MiniMax-M2.5 cost 3.4012 RMB, which satisfied the 20 RMB continuation threshold used for the complete run.

## Pass Rates

| Model | Group | Compile pass | Dynamic-change pass | Compile count | Dynamic count |
| --- | ---: | ---: | ---: | ---: | ---: |
| qwen3.8-flash | G1 | 81.11% | 71.11% | 73/90 | 64/90 |
| qwen3.8-flash | G2 | 30.00% | 6.67% | 27/90 | 6/90 |
| qwen3.8-flash | G3 | 26.67% | 25.56% | 24/90 | 23/90 |
| qwen3.8-flash | G4 | 23.33% | 11.11% | 21/90 | 10/90 |
| MiniMax-M2.5 | G1 | 46.67% | 43.33% | 42/90 | 39/90 |
| MiniMax-M2.5 | G2 | 1.11% | 0.00% | 1/90 | 0/90 |
| MiniMax-M2.5 | G3 | 10.00% | 10.00% | 9/90 | 9/90 |
| MiniMax-M2.5 | G4 | 13.33% | 2.22% | 12/90 | 2/90 |

## Cost Summary

| Model | Calls | Input tokens | Output tokens | Estimated cost (RMB) |
| --- | ---: | ---: | ---: | ---: |
| qwen3.8-flash | 521 | 15,217,711 | 16,406,139 | 56.4707 |
| MiniMax-M2.5 | 724 | 19,997,764 | 3,307,757 | 69.7805 |

## Result Files

- `qwen38_minimax_m25_360_metrics.csv`: aggregate metrics for these two models.
- `four_model_360_metrics.csv`: unified aggregate metrics for all four evaluated models.
- `four_model_task_model_dynamic_pass_rates_18x4_long.csv`: long-form task-by-model dynamic pass rates.
- `four_model_task_level_dynamic_pass_rates_18x4_average.csv`: task-level mean dynamic pass rates across the four models.
