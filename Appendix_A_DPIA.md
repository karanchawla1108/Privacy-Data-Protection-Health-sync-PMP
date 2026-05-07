# Appendix A: Data Protection Impact Assessment (DPIA)

**Organisation:** Health Sync Systems Ltd
**System:** Care Predict AI Platform
**Date:** 07/05/2026 | **Version:** 1.0 | **Review:** Annually

---

## 1. Project Overview

| Field | Details |
|-------|---------|
| Project Name | Care Predict AI-Driven Health Prediction Platform |
| Data Controller | Health Sync Systems Ltd |
| Assessor | Privacy Consultant / DPO |
| Legal Trigger | GDPR Article 35 — mandatory for high-risk AI processing |

**Why DPIA required:** Care Predict fulfills all three criteria – use of special category health data in large scale (15 million entries), automated decision-making that has significant consequences for individuals (Article 22), and systematic profiling through the use of wearable devices.

---

## 2. Data Processing Description

### 2.1 Personal Data Processed

| Data Category | Specific Data Points | Classification |
|---------------|---------------------|----------------|
| Demographic | Name, age, gender, address, ethnicity | Personal Data — Article 6 |
| Health Records | Diagnoses, medications, lab results, clinical notes | Special Category — Article 9 |
| Wearable Data | Heart rate, blood pressure, activity, sleep, blood glucose | Special Category — Article 9 |
| Biometric | ECG readings, continuous glucose monitoring | Special Category — Article 9 |
| Behavioural | Exercise patterns, medication adherence | Personal Data — Article 6 |
| Third-Party | Anonymised population statistics, drug interaction data | Anonymised — not personal data |

### 2.2 Data Sources
- EHRs through HL7 FHIR APIs with OAuth 2.0 security
- Data from wearable devices like Fitbit, Apple watch, and CGM using encryption
- Health database providers – de-identified population data and research
- Data from patients directly using the Care Predict mobile app

### 2.3 Processing Activities
- Data collection, normalization, and aggregation of data from diverse sources
- Training of AI models using differential privacy (ε=1.0)
- Prediction of risks related to heart conditions, diabetes, and lungs
- Storage on AWS Frankfurt (EU region) and AWS US-East (US)
- Data sharing with healthcare practitioners and researchers under DPAs

---

## 3. Privacy Risk Assessment

| Privacy Risk | Likelihood | Severity | Initial Risk | Residual Risk | Mitigation |
|-------------|------------|----------|-------------|--------------|------------|
| Data breach exposing PHI | 4 — High | 5 — Critical | **20 Critical** | 8 Medium | AES-256, RBAC, 24/7 SOC, audit logging |
| Algorithmic bias | 4 — High | 4 — High | **16 High** | 6 Low | Fairness testing, SHAP explainability |
| Unauthorised employee access | 3 — Medium | 4 — High | **12 High** | 4 Low | RBAC, MFA, 15-min session timeout |
| Re-identification of anonymised data | 2 — Low | 5 — Critical | **10 Medium** | 3 Low | K-anonymity (k=5), differential privacy |
| Inadequate consent | 4 — High | 3 — Medium | **12 High** | 3 Low | Granular consent dashboard, easy withdrawal |
| Cross-border transfer violations | 3 — Medium | 5 — Critical | **15 High** | 5 Low | Standard Contractual Clauses, data localisation |
| Third-party vendor misuse | 3 — Medium | 4 — High | **12 High** | 4 Low | DPAs, annual vendor audits |
| Function creep | 3 — Medium | 3 — Medium | **9 Medium** | 3 Low | Purpose controls, consent verification |

---

## 4. Compliance Assessment

| GDPR Article | Requirement | Status |
|-------------|-------------|--------|
| Article 5 | Data processing principles | Implemented |
| Article 6 | Lawful basis — explicit consent | Implemented |
| Article 9 | Special category data | Implemented |
| Article 22 | Human review of automated decisions | Implemented |
| Article 25 | Privacy by Design | Implemented |
| Article 28 | Data Processing Agreements | Partial — BAAs pending |
| Article 30 | Records of Processing Activities | Implemented |
| Article 33 | 72-hour breach notification | Implemented |
| Article 35 | DPIA | This document |

**HIPAA**: Encryption (AES-256), Multi-factor authentication, RBAC, 60-day breach notification under 45 CFR 164.400-414.

**CCPA**: Privacy Dashboard, Deletion request handled within 45 days, No selling of personal information.

---

## 5. Mitigation Measures
**Technical:** Data-at-rest protection (AES-256-GCM), data-in-transit encryption (TLS 1.3), data pseudonymisation (SHA-256), differential privacy (ε = 1.0), RBAC with least privilege, blockchain audit log retention period (7 years), automated data deletion following NIST SP 800-88.

**Organisational:** Privacy-by-design throughout the software development life cycle, appointment of data protection officer, employee privacy training quarterly, privacy clauses in contracts with third-party service providers, annual privacy audit, incident management process compliant with ISO/IEC 27035.

**User Rights:** Portal for Personal Access, Correction, Erasure within 45 Days, Data Portability (FHIR/CSV), Opt-Out for Automated Decisions, Explainable

---

## 6. Consultation

| Stakeholder | Outcome |
|-------------|---------|
| Data Protection Officer | Approved. Recommends annual DPIA review. |
| Clinical Advisory Board | Clinical utility justifies risks. Endorses human review. |
| Patient Representatives | Requested simplified consent forms and transparency dashboard. |
| IT Security Team | Technical controls validated. Quarterly penetration testing recommended. |
| Legal Counsel | GDPR/HIPAA compliance confirmed. Updated DPAs required. |

---

## 7. Conclusion and Sign-Off

**Conclusion:** Processing can continue. All remaining risks mitigated to an acceptable level.

**Important Recommendations:**
- Business Associate Agreements signed before deployment
- Fairness assessment using algorithmic testing for each subgroup
- Federated learning to limit data aggregation and storage (Q2 2027)
- AI Ethics Review Board to be established

| Role | Signature | Date |
|------|-----------|------|
| Data Protection Officer | __________________ | ___/___/2026 |
| Chief Technology Officer | _________________ | ___/___/2026 |
| Chief Medical Officer | _________________ | ___/___/2026 |

---
*COM6020M — Privacy & Data Protection | York St John University*

---
Here you go:
markdown# References by Appendix

---

## Refernces

- European Union (2016). *Regulation (EU) 2016/679 — General Data Protection Regulation (GDPR)*, Articles 9, 22, 25, 35. Available at: https://eur-lex.europa.eu/eli/reg/2016/679/oj

- ICO (2020). *Data Protection Impact Assessments (DPIAs)*. Information Commissioner's Office. Available at: https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/accountability-and-governance/data-protection-impact-assessments/

- NIST (2020). *Privacy Framework Version 1.0*. Available at: https://www.nist.gov/privacy-framework

- US Department of Health and Human Services (2013). *HIPAA Security Rule — 45 CFR Part 164*. Available at: https://www.hhs.gov/hipaa/for-professionals/security/index.html

- State of California (2018). *California Consumer Privacy Act — Cal. Civ. Code § 1798.100*. Available at: https://oag.ca.gov/privacy/ccpa

- Dwork, C. and Roth, A. (2014). The Algorithmic Foundations of Differential Privacy. *Foundations and Trends in Theoretical Computer Science*, 9(3-4), pp.211–407. Available at: https://doi.org/10.1561/0400000042

- European Parliament (2024). *EU Artificial Intelligence Act — Regulation (EU) 
---