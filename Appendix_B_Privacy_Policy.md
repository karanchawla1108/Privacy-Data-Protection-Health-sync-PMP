# Appendix B: Privacy Policy — Care Predict AI Platform

**Health Sync Systems Ltd**
**Effective Date:** [Date] | **Version:** 1.0

---

## 1. Introduction


Health Sync Systems takes the  personal health information seriously. In this document, It explain the privacy policies for the use of the data through Care Predict.

**Data Controller:** Health Sync Systems Ltd, [Address]
**Data Protection Officer:** [Name], [Email], [Phone]
**HIPAA Privacy Official:** [Name], [Email], [Phone]

---

## 2. Information We Collect

| Category | Data Points |
|----------|-------------|
| Health Records | Diagnoses, medications, lab results, clinical notes, allergies |
| Wearable Data | Heart rate, blood pressure, activity, sleep, blood glucose, SpO2 |
| Biometric | ECG readings, continuous glucose monitoring |
| Behavioural | Exercise patterns, medication adherence, appointment attendance |
| Demographic | Name, age, gender, address, contact details, ethnicity |
| Usage Data | Access logs, feature interactions, system performance |

---

## 3. Legal Basis for Processing

| Purpose | Legal Basis | GDPR Article |
|---------|-------------|-------------|
| Health risk predictions | Explicit consent | Article 9(2)(a) |
| Healthcare delivery | Healthcare purposes | Article 9(2)(h) |
| System security | Legitimate interests | Article 6(1)(f) |
| Regulatory compliance | Legal obligation | Article 6(1)(c) |
| Research analytics | Separate explicit consent | Article 9(2)(a) |

---

## 4. Data Sharing

It exchange information with:
- **Healthcare providers** – only those healthcare professionals with confirmed access rights 
- **Cloud infrastructure** – AWS, which has end-to-end encryption
- **Analytics vendors** – only anonymized or pseudonymized data sets

Every third party is required to sign a Data Processing Agreement. **We do not monetize patients’ data.**
---

## 5. Data Security

| Safeguard | Implementation |
|-----------|---------------|
| Encryption at rest | AES-256-GCM per-patient keys |
| Encryption in transit | TLS 1.3 |
| Access controls | RBAC with mandatory MFA |
| Audit logging | Tamper-evident logs retained 7 years |
| Pseudonymisation | Applied before all AI processing |
| Penetration testing | Quarterly by independent auditors |

---

## 6. Data Retention

| Data Type | Retention Period |
|-----------|-----------------|
| Active patient data | Duration of Care Predict service use |
| Inactive accounts | Deleted after 90 days of inactivity |
| Audit logs | 7 years — regulatory requirement |
| Anonymised research data | Indefinite — cannot be re-identified |

Deletion follows NIST SP 800-88 secure erasure standards.

---

## 7. Your Rights

### GDPR Rights (for EU/EEA residents)
- **Access** – the right to access your personal data
- **Rectification** – correcting any incorrect personal data
- **Erasure** – request for deletion (answered within 30 days)
- **Data Portability** – obtain personal data in FHIR or CSV formats
- **Object** – objection to any automated decision-making
- **Withdrawal of Consent** – immediate effect through the privacy dashboard

### HIPAA Rights (for US residents)
- Accessing and amending Protected Health Information
- Accounting of disclosures – view people accessing your information
- Requesting limitations on specific uses

### CCPA Rights (For California Residents Only)
- Right to know
- Right to delete (within 45 days)
- Right to opt out of selling information

---

## 8. Automated Decision-Making

Care Predict utilizes artificial intelligence for health predictions. Your rights include:
- Requesting human clinical assessment of any artificial intelligence prediction
- Receiving information on the determinants of the prediction
- Disputing decisions that have a substantial impact on you
---
## 9. Cross-Border Data Transfer

Data of EU citizens is housed solely within AWS Frankfurt, while US citizens' data is stored in AWS US-East. Cross-border data transfer relies entirely on the Standard Contractual Clauses (SCCs) authorized by the European Commission.

---

## 10. Contact and Complaints

**DPO Email:** [dpo@healthsync.com]
**Response time:** 30 days (GDPR) / 45 days (CCPA)

You have the right to lodge a complaint with your national supervisory authority (UK: ICO — ico.org.uk).

---

## 11. Consent

**For Special Category Data Processing (GDPR Article 9):**

- [ ] I consent to processing my health data for personalised health predictions
- [ ] I consent to sharing my anonymised data for medical research
- [ ] I consent to receiving insights from my wearable device data

**Signature:** ___________________ **Date:** ___/___/______

---
*Complies with GDPR (EU), HIPAA (US), and CCPA (California)*
*COM6020M — Privacy & Data Protection | York St John University*

---

## Refernces

- European Union (2016). *GDPR Articles 5, 6, 7, 9, 12, 13, 17, 22*. Available at: https://eur-lex.europa.eu/eli/reg/2016/679/oj

- ICO (2023). *Guide to Privacy Notices, Transparency and Control*. Available at: https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/individual-rights/

- US Department of Health and Human Services (2013). *HIPAA Notice of Privacy Practices*. Available at: https://www.hhs.gov/hipaa/for-individuals/notice-privacy-practices/index.html

- State of California (2018). *CCPA — Right to Know, Delete, and Opt-Out*. Available at: https://oag.ca.gov/privacy/ccpa

- Kissel, R., Regenscheid, A., Scholl, M. and Stine, K. (2014). *NIST SP 800-88 Rev 1 — Guidelines for Media Sanitization*. Available at: https://csrc.nist.gov/pubs/sp/800/88/r1/final

---