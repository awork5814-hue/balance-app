# Holistic Score Weights

## Purpose
Compute a single daily Holistic Score (H) that reflects balanced
mental and physical health without allowing one dimension
to overpower the others.

---

## Base Formula

H = (Sleep × 0.4) + (Steps_adj × 0.3) + (Mood × 0.3)

Where:
- Sleep = sleep quality score (0–100)
- Steps_adj = normalized step score (0–100)
- Mood = user-reported mood score (0–100)

---

## Step Normalization Rule

Steps are normalized relative to the user's daily goal.

Steps_adj = min((steps / daily_step_goal) × 100, 100)

Examples:
- 10,000 steps with a 10,000 goal → 100
- 5,000 steps → 50
- 20,000 steps → 100 (capped)

---

## Partial Data Re-Normalization

If one or more components are missing:

- Exclude missing components
- Re-normalize remaining weights proportionally

Example:
- Sleep missing
- H = (Steps_adj × 0.5) + (Mood × 0.5)

This prevents artificial score drops due to delayed sync.

---

## Design Rationale
Sleep is weighted highest to prevent performance masking.
Re-normalization preserves trust during partial data syncs.
