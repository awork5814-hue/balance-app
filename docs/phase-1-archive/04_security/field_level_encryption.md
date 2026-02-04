# Field-Level Encryption Specification

## Purpose
Prevent exposure of sensitive mental and biometric values
even in the event of a server-side breach.

---

## Encrypted Fields

### Daily Logs Table
- `mood`
- `energy`

### Practice Sessions Table
- `heart_rate_post`

These fields must be encrypted **before persistence**.

---

## Encryption Requirements
- Encryption occurs at the application layer
- Encryption keys are managed outside the database
- Keys are rotated periodically

---

## Security Outcome
- Raw biometric values are unreadable at rest
- `user_id` alone cannot reconstruct personal health data
- Database dumps are mathematically useless without keys

---

## Design Rationale
Mental and physiological data is treated as
high-sensitivity personal information,
not standard analytics data.
