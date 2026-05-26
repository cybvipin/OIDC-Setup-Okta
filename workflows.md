# IAM Workflows – Okta OIDC Project

## 🔄 1. OIDC Authentication Flow

```
User → Login → Policy Evaluation → Authorization Code → Token Exchange → ID Token
```

---

## 🔐 2. Token Generation Flow

1. User authenticates  
2. Okta issues Authorization Code  
3. Client sends code to token endpoint  
4. Okta returns:
   - ID Token  
   - Access Token  

---

## 🧩 3. Policy Evaluation Flow

1. User attempts login  
2. Okta checks:
   - Authentication Policy  
   - User assignment  
   - Group membership  
   - MFA requirements  
3. If all conditions pass → allow  
4. If not → error  

---

## 👥 4. User Assignment Workflow

1. Admin assigns user to app  
2. User becomes eligible for authentication  
3. Policy applies  
4. Login allowed  

---

## 🔐 5. Authorization Server Flow

1. Client requests authorization  
2. Okta validates client  
3. Okta validates user  
4. Okta issues tokens  

