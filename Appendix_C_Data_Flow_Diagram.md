# Appendix C: Data Flow Diagram (DFD)

**Health Sync Systems — Care Predict AI System**
**Version:** 1.0 | **COM6020M — Privacy & Data Protection**

---

## Overview

This diagram maps patient data across five lifecycle phases collection, processing, storage, sharing, and deletion with privacy controls applied at each stage. 
**Also the Diagram Provided in the Portfolio Section 2.**

---

## Phase 1 — Data Collection

| Source | Data Elements | Protocol | Controls |
|--------|--------------|----------|----------|
| Hospital EHR Systems | Demographics, diagnoses, medications, lab results, clinical notes | HL7 FHIR API + OAuth 2.0 | TLS 1.3, input validation, audit logging |
| Wearable Devices | Heart rate, blood pressure, activity, sleep, blood glucose, SpO2 | HTTPS + OAuth 2.0 | Device encryption, pseudonymisation, consent check |
| Third-Party Databases | Population health stats, drug interactions, clinical research | Encrypted SFTP batch | DPA verification, anonymisation check, k-anonymity (k=5) |

---

## Phase 2 — Data Processing

```
[Encrypted Data Lake]
    ↓ Extract minimal required features – Data Minimization
[Preprocessing Service]
    ↓ Feature normalization, outlier analysis, feature construction
    ↓ Pseudonymization using SHA-256 hashing, deleting direct identifiers
[Dataset for AI training]
    ↓ Implementing differential privacy (ε=1.0) when training models
    ↓ Test for fairness among demographics
[Deployed AI model]
    ↓ Scores in range 0-100, explainability via SHAP/LIME
[Clinician Dashboard]
```

| Phase | Task | Measures |
| ------| ----- | -------- |
| Data Pre-processing | Normalization, outlier removal | Data reduction, pseudonymization, audit logs |
| AI Model Training | Gradient boosting, neural networks, ensembles | Differential privacy (ε=1.0), fairness evaluation |
| Inference | Risk scoring, treatment suggestions | Pseudonymized inference, SHAP explainability, human review alert |

---

## Phase 3 - Data Storage

| Storage       | Contents                     | Region                  | Control                 |
| ------------- | ---------------------------- | ----------------------- | ----------------------- |
| Primary DB    | Patient records and prediction model results, audit logs | AWS Frankfurt (EU) / US-East (US) | AES-256-GCM encryption, RBAC, application-level encryption |
| Analytics Db  | Anonymous aggregated data on populations   | Same region – different server | k-anonymity (k=5), l-diversity|
| Backup Storage| Encrypted backup of primary database        | Same geographic region          | 30 day retention, encrypted|

---

## Phase 4 - Data Sharing

| Recipient          | Shared data                        | Safeguards                          |
|-------------------|------------------------------------|-------------------------------------|
| Healthcare Providers| Risk scores, contributing factors and recommended intervention  | MFA, RBAC for specific patient only, TLS 1.3 and 15-minute session timeout|
| Researchers        | Anonymous datasets (k=5)           | Ethics Approval, DPA, Watermarking, limited time access|
| Third-party Vendors| Infrastructure access only – no PHI | DPAs, IP whitelisting, Access revocation|
| Cross-border Data Flow| As appropriate for service      | SCCs|
---

## Phase 5 — Data Deletion

| Type | Trigger | Process | Timeline |
|------|---------|---------|----------|
| Automated | 90-day inactivity | Retention engine → soft delete → NIST SP 800-88 hard delete | Continuous |
| Patient-requested | GDPR Article 17 / CCPA | Identity check → legal hold check → database + backup purge → deletion certificate | 30 days (GDPR) / 45 days (CCPA) |
| Regulatory expiry | Retention period end | Scheduled secure deletion with audit log | Per retention schedule |

---

## Summary of Privacy Controls

| Phase        | Controls              |
| -------------| --------------------- |
| Collection   | TLS 1.3, OAuth 2.0, Consent check, Audit logging                  |
| Processing   | Pseudonymisation, Data Minimisation, Differential privacy ε=1.0, Fairness Testing                       |
| Storage      | AES-256-GCM, RBAC, Application level encryption, Geo-redundancy                |
| Sharing      | Data processing agreement, K-anonymity, Purpose limitation, SCCs for EU-US transfer            |
| Deletion     | NIST SP 800-88, Automated retention engine, Deletion certificates                 |
| Monitoring   | 24/7 SOC, Blockchain based auditing, Machine learning based anomaly detection                      |


---

## Data Residency

| Region | Patients | Reason |
|--------|----------|--------|
| AWS Frankfurt | EU patients | GDPR compliance — data localisation |
| AWS US-East | US patients | HIPAA compliance |
| Cross-border | Service delivery only | SCCs applied |

---
*COM6020M — Privacy & Data Protection | York St John University*
---

## Refernces

- European Union (2016). *GDPR Article 5(1)(c) — Data Minimisation; Article 5(1)(e) — Storage Limitation; Article 17 — Right to Erasure*. Available at: https://eur-lex.europa.eu/eli/reg/2016/679/oj

- NIST (2020). *Privacy Framework Version 1.0 — Identify-P Function*. Available at: https://www.nist.gov/privacy-framework

- Kissel, R., Regenscheid, A., Scholl, M. and Stine, K. (2014). *NIST SP 800-88 Rev 1 — Guidelines for Media Sanitization*. Available at: https://csrc.nist.gov/pubs/sp/800/88/r1/final

- Cavoukian, A. (2011). *Privacy by Design: The 7 Foundational Principles*. Information and Privacy Commissioner of Ontario. Available at: https://www.ipc.on.ca/wp-content/uploads/Resources/7foundationalprinciples.pdf

- Dwork, C. and Roth, A. (2014). The Algorithmic Foundations of Differential Privacy. *Foundations and Trends in Theoretical Computer Science*, 9(3-4), pp.211–407. Available at: https://doi.org/10.1561/0400000042

- ISO (2025). *ISO/IEC 27701:2025 — Privacy Information Management*. Available at: https://www.iso.org/standard/27701

---