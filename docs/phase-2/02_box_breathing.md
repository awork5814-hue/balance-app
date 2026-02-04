# Box Breathing — Alpha Intervention

---

## Purpose

Box Breathing is the sole nervous-system intervention included in the Alpha build.

Its goal is to:
- Reduce heart rate
- Support autonomic regulation
- Produce a measurable Resonance response within 2 minutes

This intervention is designed to fit between meetings and require no preparation.

---

## Protocol (Alpha Locked)

- Inhale: 4 seconds  
- Hold: 4 seconds  
- Exhale: 4 seconds  
- Hold: 4 seconds  

Total session duration:
- Minimum: 60 seconds  
- Maximum: 120 seconds  

The protocol is fixed for Alpha. No customization is permitted.

---

## Session Intro (Physiological First)

> “This breathing pattern slows your heart rate and stabilizes your nervous system.  
> It works by balancing your inhale and exhale timing.”

---

## Instructional Cues (1–3 Words Rule)

The following cues are delivered once per phase:

- “Inhale 4”
- “Hold”
- “Exhale 4”
- “Hold”

No additional language is permitted during the cycle.

---

## Audio Policy

- Silence is the default
- Optional white noise or brown noise may be enabled
- Music and melodic audio are explicitly excluded

Audio starts only after the user presses Play and stops immediately on exit.

---

## Data Capture (practice_sessions)

Each session records the following metrics:

- heart_rate_pre
- heart_rate_post
- duration_seconds

Optional (if available):
- heart_rate_peak

All values are sourced from HealthKit / Health Connect.

---

## Success Criteria (Alpha)

A Box Breathing session is considered effective if any of the following occur:

- Heart rate decreases by ≥ 5 BPM  
- Heart rate recovery is faster than baseline  
- The session completes without user interruption  

No negative scoring is applied if no change is detected.

---

## Resonance Signal

The difference between heart_rate_pre and heart_rate_post contributes to the
Resonance trend but does not directly alter the Holistic Score.

This preserves trust during early experimentation.

---

## Failure Handling

If heart rate data is unavailable:
- The session completes normally
- No Resonance signal is calculated
- The user is not notified of missing data

---

## Alpha Scope Lock

Box Breathing is the only intervention included in Alpha.

Movement-based or advanced breathing techniques are intentionally excluded.
