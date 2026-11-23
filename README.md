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
![Samba AD Service Status](screenshots/AD-SS-active%20running.jpeg)

### 2. Domain Info & DNS SRV Verification
![Domain Info and DNS SRV](screenshots/2nd%20SS%20domain_info_and_dns.jpeg)

### 3. Kerberos Domain Authentication (`kinit` & `klist`)
![Kerberos Auth Check](screenshots/03_kerberos_auth_check.jpeg)

### 4. Organizational Units, Security Groups & User Provisioning
![OU Groups and Users](screenshots/04_ou_groups_and_users.jpeg)

### 5. Domain Password & Account Lockout Policy
![Password Lockout Policy](screenshots/05_password_lockout_po.jpeg)

### 6. Account Lockout Trigger (`Client's credentials have been revoked`)
![Account Lockout Trigger](screenshots/06_account_lockout_trigger.jpeg)

### 7. L1 Lockout Triage, Account Unlock, Password Reset & Re-Login
![Lockout Triage and Unlock](screenshots/07_lockout_triage_and_unlock.jpeg)
