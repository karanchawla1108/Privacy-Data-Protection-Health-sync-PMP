# Appendix E: Access Control Policy Matrix

**Health Sync Systems — Role-Based Access Control (RBAC)**
**Version:** 1.0 | **COM6020M — Privacy & Data Protection**

---

## 1. Overview

This matrix provides role-based access control for the Care Predict AI platform, utilizing the least privilege principle to minimize privacy risks while complying with GDPR Article 32 and HIPAA Security Rule requirements.

---

## 2. Access Control Principles

| Principle | Description |
|-----------|-------------|
| Least Privilege            | Users have only the minimum amount of access necessary for their job role                     |
| Separation of Duties       | Important tasks split up so that there is no one central point of control                    |
| Need-to-Know               | Access limited only to assigned patients or sanctioned projects                               |
| Defence in Depth           | Various levels — MFA, RBAC, session management, and auditing                                    |
| Time-limited               | Temporary privilege access automatically 
---
## 3. Role Descriptions

### Clinical Roles
| Role          | Description  | Number of Users |
| ------------- | ------------ | --------------- |
| Physician     | Treating doctors, assigned patient cases only                 | 15,000         |
| Nurse         | Clinical staff members, assigned patient case information    | 30,000         |
| Specialist    | Consultants, read-only access when consulting                | 5,000          |
| Researcher    | Clinical researchers, approved studies                      | 500            |

### Technical Roles
| Role              | Description                                                | Number of Users |
| ----------------- | ---------------------------------------------------------- | --------------- |
| Data Scientist    | AI model developers, access to pseudonymised data only     | 50             |
| Sys Admin         | System administrators, no access to PHI                   | 20             |
| DB Admin          | Database administrators, access to encrypted data only     | 10             |
| Security Analyst  | Security monitors, access to audit log only               | 15             |

### Administrative and Patient Roles
| Role                    | Description                                            | Number of Users   |
| ----------------------- | ----------- | ----------------- |
| Privacy Officer/DPO     | Governance                                            | 5                |
| Compliance Auditor      | Internal and external compliance checks                | 10               |
| Patient                | Self-service access to personal health data only       | 15,000,000       |

---

## 4. Access Control Matrix

**Abbreviations:** RW – Read and Write, R – Read Only, PS – Pseudonymised, AG – Aggregate Only, — No Access

| Data Category          | Physician | Nurse | Specialist | Researcher | Data Scientist | Sys Admin | DB Admin | Patient |
| ---------------------- | --------- | ----- | ---------- | ---------- | -------------- | -------- | ------- | ------- |
| Patient Demographics   | R (assigned) | R (assigned) | R (consulting) | —             | PS       | —        | —       | R (own) |
| Medical History        | RW        | R     | R (consulting) | —           | PS           | —       | —        | R (own) |
| Current Diagnoses      | RW        | RW    | R (consulting) | —           | PS           | —       | —        | R (own) |
| Medications            | RW        | RW    | R (consulting) | —           | PS           | —       | —        | R (own) |
| Lab Results            | RW        | R     | R (consulting) | —           | PS           | —       | —        | R (own) |
| Clinical Notes         | RW        | RW    | R (consulting) | —           | —            | —       | —        | R (own) |
| Wearable Data          | R (assigned) | R (assigned) | R (consulting) | —           | PS           | —       | —        | R (own) |
| AI Predictions         | RW        | R     | R (consulting) | —           | AG           | —       | —        | R (own) |
| Audit Logs (System)    | —         | —     | —              | —           | —            | R        | —        | —        |
| Audit Logs (Patients)  | —         | —     | —              | —           | —            | —       | —        | R (own)  |
| Anonymised Datasets    | —         | —     | —              | R (approved) | RW           | —       | —        | —        |
| System Configurations  | —         | —     | —              | —           | —            | RW       | R        | —        |
| Encryption Keys        | —         | —     | —              | —           | —            | —       | —        | —        |

---

## 5. Authentication Policies

| Policy                     | Specification                                             |
| -------------------------- | -------------------------------------------------------- |
| Multi-Factor Authentication | Required for all users                                    |
| Session Timeout            | Automatically log out after 15 minutes of inactivity       |
| Password Minimum Length    | At least 14 characters                                    |
| Password Rotation          | Every 90 days for privileged accounts, 180 days for regular users |
| Lock Out                  | Account locks after 5 failed attempts, manual unlock required |
| Remote Access             | Virtual Private Network (VPN), certificate-based authentification required |

---

## 6. Emergency Access

**Purpose:** In life-threatening emergencies, security breaches, or system outages.

**Steps:**
1. User requests emergency access via the emergency access portal
2. Additional multi-factor authentication challenge is displayed
3. User must provide justification for access before receiving permission
4. Emergency session lasts up to 15 minutes, actions marked as "EMERGENCY ACCESS"
5. Privacy Officer is notified immediately
6. Follow-up analysis occurs within 24 hours

---

## 7. Audit and Monitoring

All access attempts are recorded, including user ID, role, timestamp, activity performed, data accessed, and source IP address.

**Alerts automatically triggered when:**
- More than 10 patients are accessed in one hour
- Access takes place outside business hours for non-clinical roles
- More than three consecutive unsuccessful authentication attempts
- New or unknown locations/devices are used
- Attempts at exporting or downloading data occur

**Log retention:** Seven years using blockchain-based integrity protection.
**Audit:** Quarterly certification by line managers; annual comprehensive audit by the privacy department.

---

## 8. Compliance Mapping

| Standard | Controls Implemented |
| -------- | -------------------- |
| GDPR Article 32 | Pseudonymisation, encryption, access control, and auditing           |
| HIPAA Security Rule | Unique User Identification (164.312(a)), emergency access (164.312(a)(2)(ii)), audit controls (164.312(b)), multifactor authentication |
| ISO 27001 | A.9.2 User Access Management, A.9.4 System Access Control, A.12.4 Logging |

---

**Last Updated:** [Date] | **Next Review:** Quarterly | **Approved By:** Privacy Officer, CISO, Legal Counsel

---
*COM6020M — Privacy & Data Protection | York St John University*
---

## References

- European Union (2016). *GDPR Article 32 — Security of Processing*. Available at: https://eur-lex.europa.eu/eli/reg/2016/679/oj

- US Department of Health and Human Services (2013). *HIPAA Security Rule — 45 CFR §164.312 — Technical Safeguards*. Available at: https://www.hhs.gov/hipaa/for-professionals/security/index.html

- ISO (2022). *ISO/IEC 27001:2022 — Annex A.9 Access Control*. International Organisation for Standardisation. Available at: https://www.iso.org/standard/27001

- NIST (2020). *SP 800-53 Rev 5 — Security and Privacy Controls — Access Control Family*. Available at: https://csrc.nist.gov/pubs/sp/800/53/r5/final

- CIS (2021). *CIS Controls Version 8 — Control 6: Access Control Management*. Centre for Internet Security. Available at: https://www.cisecurity.org/controls/v8

- Cavoukian, A. (2011). *Privacy by Design: The 7 Foundational Principles*. Available at: https://www.ipc.on.ca/wp-content/uploads/Resources/7foundationalprinciples.pdf

---