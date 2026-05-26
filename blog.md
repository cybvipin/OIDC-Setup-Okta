# Blog – Understanding Okta OIDC (Beginner Friendly)

## 🔥 What is OIDC?
OIDC is an identity layer built on top of OAuth 2.0.  
It provides authentication using ID Tokens.

---

## 🔐 Why Use Okta?
- Easy to configure  
- Secure  
- Supports OAuth, OIDC, SAML  
- Great for IAM learning  

---

## 🧪 My Experience Debugging OIDC
I faced two major errors:

### ❌ Error 1: User not assigned  
Cause: User assigned in Developer Console, not Classic UI.

### ❌ Error 2: Policy evaluation failed  
Cause: Authentication Policy required MFA.

Fix: Change to **Password only**.

---

## 🎯 Key Takeaways
- Always use Classic UI for policies  
- OAuth Debugger cannot handle MFA  
- Redirect URI must match exactly  
- OIDC flow is simple once understood  

---

## 🏁 Final Thoughts
This project helped me understand:

- OIDC flows  
- Okta policies  
- IAM troubleshooting  
- Token-based authentication  

