# Okta OIDC Lab – Step‑by‑Step Guide

This lab walks through the full setup and testing of an OIDC application in Okta.

---

# 1️⃣ Create Okta Developer Account

1. Go to developer.okta.com  
2. Create a free developer account  
3. Log in to the Okta Admin Console  

---

# 2️⃣ Create an OIDC Application

1. Navigate to:
   ```
   Applications → Applications → Create App Integration
   ```
2. Choose:
   - **OIDC – OpenID Connect**
   - **Web Application**
3. Configure:
   - App name: `Demo_OIDC Test`
   - Grant type: Authorization Code
   - Redirect URI:
     ```
     https://oauthdebugger.com/debug
     ```
4. Save.

---

# 3️⃣ Assign Users

1. Go to:
   ```
   Applications → Demo_OIDC Test → Assignments
   ```
2. Assign user:
   - `alice.demo` (or your test user)

---

# 4️⃣ Configure Authentication Policy

1. Go to:
   ```
   Security → Authentication Policies
   ```
2. Create a new policy:
   - Name: `OIDC Test Policy`
3. Add rule:
   - IF: Any user  
   - THEN: Allow with **Password only**  
   - Re-authentication: Never  

4. Assign this policy to the OIDC app:
   ```
   Applications → Demo_OIDC Test → Sign On → Edit → Change Policy
   ```

---

# 5️⃣ Test with OAuth Debugger

1. Go to:
   https://oauthdebugger.com  
2. Enter:
   - Client ID  
   - Authorization endpoint  
   - Redirect URI  
3. Click **Authorize**  
4. Login as `alice.demo`  
5. You should receive:
   - Authorization Code  
   - ID Token  
   - Access Token  

---

# 6️⃣ Test Cases

### ✔ Test Case 1 — User Not Assigned
**Expected:**  
Error: `User is not assigned to the client application.`  
**Actual:**  
Matches expected.

### ✔ Test Case 2 — MFA Required
**Expected:**  
Error: `Policy evaluation failed for this request.`  
**Actual:**  
Matches expected.

### ✔ Test Case 3 — Successful Login
**Expected:**  
Tokens returned.  
**Actual:**  
Success.

---

# 7️⃣ Troubleshooting

### ❌ Error: User not assigned  
Fix: Assign user in **Classic UI**, not Developer Console.

### ❌ Error: Policy evaluation failed  
Fix: Authentication Policy requires MFA → change to Password only.

### ❌ Error: Invalid redirect URI  
Fix: Ensure redirect URI matches exactly.

---

# 8️⃣ Lab Completed  
You have successfully configured and tested an Okta OIDC application.

