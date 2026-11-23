# Active Directory & L1 IT Service Desk Home Lab (Samba AD DC)

A virtualized **Active Directory Domain Controller** deployed on Ubuntu Linux using **Samba AD DC**, built to practice core **L1 Technical Support, Identity & Access Management (IAM), and Incident Resolution** workflows.

## Lab Architecture
* **Hypervisor:** Oracle VirtualBox
* **Domain Controller (`dc01.corp.novadesk.local`):** Ubuntu Linux running Samba AD DC (AD DS, Internal DNS, LDAP, Kerberos KDC)
* **Realm / Domain:** `CORP.NOVADESK.LOCAL` (NetBIOS: `CORP`)

## L1 Support Workflows Completed
1. **Service & AD DS Deployment:** Verified `samba-ad-dc` daemon health, provisioned an Active Directory forest, and validated `_ldap._tcp` DNS SRV records alongside Kerberos authentication (`kinit` / `klist`).
2. **OU Architecture & User Provisioning:** Created departmental Organizational Units (`Employees` → `HR`, `IT_Support`), Security Groups (`HR-Staff`, `IT-Helpdesk`), and onboarded users (`rverma`, `pmehta`) with role-based group memberships.
3. **Password & Account Lockout Policy:** Enforced a 10-character minimum password length, 3-attempt lockout threshold, and 15-minute lockout duration via `samba-tool domain passwordsettings`.
4. **Incident Diagnostics & Account Unlocks:** Simulated an account lockout (`Client's credentials have been revoked`), inspected `badPwdCount` and `lockoutTime` attributes, unlocked the account, reset the password, and verified restored login.

## Lab Verification Screenshots

### 1. Samba AD DC Daemon Health
<img width="1235" height="513" alt="WhatsApp Image 2026-11-23 at 22 41 23" src="https://github.com/user-attachments/assets/6881004f-42b2-42d2-94eb-009a726aa09c" />

### 2. Domain Info & DNS SRV Verification
<img width="756" height="195" alt="WhatsApp Image 2026-11-23 at 22 48 31" src="https://github.com/user-attachments/assets/9e6f082d-abac-4dff-943e-aa4ae9fd1f9e" />

### 3. Kerberos Domain Authentication (`kinit` & `klist`)
<img width="790" height="202" alt="WhatsApp Image 2026-11-23 at 22 49 09" src="https://github.com/user-attachments/assets/e3c311b7-5b30-4cd1-ab4b-6fb12c8256f4" />

### 4. Organizational Units, Security Groups & User Provisioning
<img width="915" height="446" alt="WhatsApp Image 2026-11-23 at 22 49 42" src="https://github.com/user-attachments/assets/a7adbd15-38fc-41e7-81f7-99db9ca4da5d" />

### 5. Domain Password & Account Lockout Policy
<img width="673" height="552" alt="WhatsApp Image 2026-11-23 at 22 50 06" src="https://github.com/user-attachments/assets/9a506409-c73c-4641-930b-ba75dc25749b" />

### 6. Account Lockout Trigger (`Client's credentials have been revoked`)
<img width="882" height="222" alt="WhatsApp Image 2026-11-23 at 22 50 49" src="https://github.com/user-attachments/assets/e041fb38-b1de-45b9-a268-e847ffb5b841" />

### 7. L1 Lockout Triage, Account Unlock, Password Reset & Re-Login
<img width="945" height="402" alt="WhatsApp Image 2026-11-23 at 22 51 13" src="https://github.com/user-attachments/assets/616ce590-d908-48d6-baf3-c32f9b7ad171" />
