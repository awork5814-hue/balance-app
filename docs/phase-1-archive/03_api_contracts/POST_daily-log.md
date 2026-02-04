# POST /daily-log

## Purpose
Submit manual daily inputs (Mood, Energy) from the mobile app.

---

## Request Body
```json
{
  "user_id": "UUID",
  "timestamp": "ISO_8601",
  "mood": 0-100,
  "energy": 0-100
}
{
  "status": "ok",
  "sync_state": "partial",
  "updated_scores": {
    "mental_score": 72,
    "holistic_score": 68
  }
}


---

## 5️⃣ `GET_dashboard-summary.md`

```md
# GET /dashboard-summary

## Purpose
Fetch all data required to render the Hero Dashboard.

---

## Response Payload
```json
{
  "date": "YYYY-MM-DD",
  "sync_state": "final | partial | stale",
  "scores": {
    "holistic": 74,
    "mental": 78,
    "physical": 69
  },
  "trends": {
    "mental_7d": +4,
    "physical_7d": -2
  },
  "flags": {
    "dissonance": false
  }
}

---

## 6️⃣ `sync_states.md`

```md
# Sync States

## final
All wearable and manual data present.

## partial
Manual data present; wearable data pending.

## stale
No wearable data for ≥ 72 hours.

---

## UX Rules
- Never show error states
- Never block usage
- Always preserve user trust


