# Okta OIDC Project – Full Documentation

## 📌 Problem Statement
Build and test an OIDC application in Okta and document the full IAM workflow.

---

## 📐 Solution Design

### Components:
- Okta OIDC App  
- Authentication Policies  
- User Assignment  
- OAuth Debugger  
- Token endpoints  

---

## 🏗 Architecture

```
User → Okta Login → Policy Evaluation → Authorization Code → Token Endpoint → Tokens Returned
```

---

## 🛠 Implementation Steps

1. Create OIDC app  
2. Assign users  
3. Configure Authentication Policy  
4. Test Authorization Code flow  
5. Validate tokens  

---

## 🧪 Test Plan

| Test Case | Expected Result | Actual Result | Status |
|----------|----------------|---------------|--------|
| User not assigned | Error | Error | Pass |
| MFA required | Policy error | Policy error | Pass |
| Correct policy | Tokens returned | Tokens returned | Pass |

---

## 📊 Results
- Successful OIDC authentication  
- Tokens generated correctly  
- Policy evaluation understood  
- Errors resolved  

---

## 🧠 Lessons Learned
- Developer Console hides Authentication Policies  
- Classic UI must be used for policy assignment  
- MFA breaks OAuth Debugger  
- OIDC requires exact redirect URI matching  

