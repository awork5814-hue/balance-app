# Account Deletion Flow

## Purpose
Allow users to permanently erase their data in a single,
clear, irreversible action.

---

## Entry Point
Settings → Account → Delete Account

---

## Confirmation Copy
"This will permanently wipe your Resonance History
and Correlation Wave."

User must explicitly confirm.

---

## Deletion Logic
On confirmation:

- Execute DELETE across:
  - Users table
  - Daily Logs table
  - Practice Sessions table

- Use `user_id` as the sole key
- Operations must be atomic

---

## Post-Deletion State
- User session is terminated
- Authentication tokens invalidated
- App returns to onboarding state

---

## No Retention Policy
- No backups retain identifiable user data
- No soft deletes
- No recovery process

Deletion is final.
