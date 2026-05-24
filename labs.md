# IAM Labs

Hands-on labs built using my Okta Developer tenant and other IAM tools.

---

## Lab 1: Okta OIDC App with OAuth Debugger

**Goal:**  
Create an OIDC app in Okta and obtain ID/Access tokens using OAuth Debugger.

### Steps

1. In Okta, go to **Applications → Create App Integration**.
2. Choose **OIDC - OpenID Connect** and **Web**.
3. Name the app: `Demo OIDC App`.
4. Set Redirect URI to: `https://oauthdebugger.com/debug`.
5. Save and copy the **Client ID** and **Issuer URL**.
6. Go to `https://oauthdebugger.com`.
7. Enter:
   - Client ID (from Okta)
   - Authorization endpoint (from Okta)
   - Redirect URI (same as above)
8. Click **Authorize** and log in as `alice.demo`.

### Expected Result

- You see an **ID Token** and **Access Token**.
- You can decode the ID Token on `https://jwt.io` and see `sub`, `email`, etc.

---

## Lab 2: Okta SAML SSO for a Test App

**Goal:**  
Configure SAML SSO from Okta to a SAML test application.

### Steps

1. In Okta, go to **Applications → Create App Integration → SAML 2.0**.
2. Name the app: `Demo SAML App`.
3. Set:
   - Single Sign-On URL: SAML test app ACS URL
   - Audience URI: value from the test app
4. Configure attributes:
   - `email` → `user.email`
   - `firstName` → `user.firstName`
   - `lastName` → `user.lastName`
5. Assign the app only to the `Finance_Users` group.
6. Log in as:
   - `bob.demo` (Finance) → should see and access the app.
   - `alice.demo` (HR) → should NOT see the app.

### Expected Result

- Only Finance users can access the SAML app.
- SSO works without entering a password in the app.

---

## Lab 3: MFA Policy for High-Risk Apps

**Goal:**  
Require MFA for a specific app and test behavior.

### Steps

1. In Okta, go to **Security → Authentication Policies**.
2. Create a new policy: `High Security Apps`.
3. Add a rule:
   - Apply to: `Demo SAML App`
   - Condition: Any location
   - Action: Require MFA every sign-in
4. Assign the policy to the SAML app.
5. Log in as `bob.demo` and launch the app.

### Expected Result

- User is prompted for MFA before accessing the app.

---

## Lab 4: Joiner → Mover → Leaver in Okta

**Goal:**  
Simulate user lifecycle and access changes.

### Steps

1. **Joiner:**
   - Create user `david.demo`.
   - Assign to `HR_Users`.
   - Confirm he sees only HR-related apps.

2. **Mover:**
   - Move David from `HR_Users` to `Finance_Users`.
   - Confirm HR apps disappear and Finance apps appear.

3. **Leaver:**
   - Deactivate `david.demo`.
   - Confirm login is blocked and app access is removed.

### Expected Result

- Access changes automatically based on group membership and status.
