Dosage Rules — Box Breathing (Alpha)
Purpose

Dosage controls how long a Box Breathing session runs based on the user’s current physiological and data state.
The goal is to apply the minimum effective intervention without disrupting work flow.

Dosage Levels
Level 1 — The Reset

Duration: 60 seconds

Use Case: Minor dips, uncertainty, or incomplete biometric data

Intent: Low-friction nervous system downshift without commitment

Level 2 — The Stabilizer

Duration: 120 seconds

Use Case: Default Alpha intervention

Intent: Meaningful autonomic regulation within the Two-Minute Rule

Level 3 — The Recovery

Duration: 300 seconds

Use Case: Significant dissonance or sustained stress indicators

Intent: Full parasympathetic re-engagement when performance risk is detected

⚠️ Level 3 is not part of Alpha execution but is defined now to prevent future logic debt.

Dosage Triggering Logic
1. Dissonance Override
IF Dissonance Badge = active
→ Dosage Level = 3 (Recovery)


Mental and physical states are significantly misaligned

Longer duration is required to produce measurable autonomic change

User is not asked to choose duration

2. Data Confidence Safeguard
IF sync_state = stale
→ Dosage Level = 1 (Reset)


Biometric confidence is low

Keep intervention short, safe, and non-intrusive

Prevents false authority from incomplete data

3. Default Path
IF no overrides triggered
→ Dosage Level = 2 (Stabilizer)


Standard Alpha experience

Optimized for between-meeting use

The Repeat Loop Rule
Post-Session Evaluation

After a Box Breathing session completes:

IF resonance_delta < threshold
→ Coach suggests an additional 60-second session

Key Constraints

Suggestion only — never auto-repeat

Only one immediate repeat allowed

Repeat session always uses Level 1 (60s)

Rationale

Avoids fatigue or annoyance

Keeps user in control

Maintains trust in the system’s restraint

Coach Language Constraint

When suggesting a repeat:

No emotional framing

No urgency

Data-first phrasing only

Example:

“Heart rate recovery is minimal. Another 60 seconds may help.”

Alpha Scope Notes

Alpha execution supports Levels 1 and 2 only

Level 3 is logic-defined but feature-gated

No manual duration selection in Alpha

Implementation Summary (for Engineers)

Dosage is system-determined, not user-selected

Duration maps directly to practice_sessions.duration_seconds

Repeat sessions create new practice_session entries

Resonance evaluation occurs post-sync finalization
