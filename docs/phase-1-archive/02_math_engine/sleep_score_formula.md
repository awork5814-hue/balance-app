# Sleep Score Formula

## Purpose
Convert wearable sleep duration into a standardized 0–100 sleep quality score
aligned with recovery-focused performance design.

---

## Inputs
- `actual_sleep_hours` (float)
- `sleep_target_hours` (from Users table, default: 8.0)
- `time_in_bed_hours` (optional, if available)

---

## Step 1 — Base Score
The base sleep score is calculated as:

Score = (actual_sleep_hours / sleep_target_hours) × 100

---

## Step 2 — Efficiency Penalty
If time in bed is significantly higher than time asleep
(indicating restlessness or fragmentation):

- Condition:
