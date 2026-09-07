# Step9 Logic Ablation Task Set

`rflp_logic_step9_ablation_tasks.jsonl` contains 18 benchmark tasks selected from the Section 4.4 system-level comparison task set at `../../system_level_comparison/tasks/rflp_benchmark_tasks.jsonl`.

Each JSONL row contains:

- `task_id`
- `domain`
- `system_name`
- `requirement_zh`
- `expected_scenario_features`
- `notes`

## Included Tasks

```text
rflp_001 landing_gear
rflp_002 water_tank
rflp_003 thermal_management
rflp_004 vehicle_braking
rflp_005 robotics
rflp_007 pump_valve
rflp_008 wind_turbine
rflp_009 elevator_platform
rflp_010 hvac
rflp_013 medical_infusion
rflp_016 warehouse_agv
rflp_017 hydraulic_press
rflp_018 air_compressor
rflp_019 smart_irrigation
rflp_021 crane_anti_sway
rflp_022 cold_chain
rflp_023 pipeline_leak
rflp_024 prosthetic_knee
```

The set provides complete Step1-Step8 preparation for every listed case and supports paired evaluation across the four Step9 ablation conditions.
