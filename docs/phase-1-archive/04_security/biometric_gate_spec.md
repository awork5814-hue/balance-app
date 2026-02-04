# Biometric Gate Specification

## Purpose
Protect sensitive mental and biometric data without adding friction
for high-performing users.

Speed is treated as a security feature.

---

## Authentication Flow

### App Launch
1. On app open, check for valid biometric session (FaceID / TouchID).
2. If valid:
   - Restore session silently
   - Fetch data scoped to authenticated `user_id`
3. If invalid or expired:
   - Prompt biometric authentication immediately

---

## Session Scope
- Each session is bound to a single `user_id`
- No cross-user data access is permitted
- Session tokens are short-lived and auto-rotated

---

## Private Mode
Users may enable **Private Mode** from Settings.

### Behavior
- Hero Dashboard scores are blurred by default
- Biometric scan is required to unblur
- Blurring applies only to score values, not navigation

### Use Case
Protects user privacy in public or shared environments.

---

## Failure Handling
- No error messages displayed
- App remains usable but data remains hidden
- No language implying risk or fault
