# Edge Case Logic

## 1. Day Boundary Rule (4 AM)
Any manual log recorded before 04:00 local time
is assigned to the previous calendar day.

Rationale:
Supports late-night users without fragmenting daily data.

---

## 2. Partial Sync State
If wearable data has not yet synced:

- Mark day as `sync_state = partial`
- Display provisional scores
- Recalculate automatically when data arrives

---

## 3. Stale Data
If no wearable sync occurs for ≥ 72 hours:

- Mark day as `sync_state = stale`
- Display neutral copy:
  “Waiting for wearable data”

No warnings or alerts are triggered.

---

## 4. Extreme Score Protection
If Mood = 100 and Steps = 0:

- Holistic Score reflects inactivity via Steps_adj = 0
- Sleep anchor prevents collapse
- Score remains balanced, not punitive

---

## 5. Trend Guardrail
Trend calculations only include days where:

sync_state = final

This prevents false optimism or panic.

---

## 6. Slump Trigger Suppression
If the user completes:
- a practice session
- or increases score by ≥ +10

All slump nudges are suppressed for 48 hours.
