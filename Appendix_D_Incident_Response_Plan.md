# Appendix D: Incident Response Plan

**Health Sync Systems — Data Breach Response Protocol**
**Standard:** ISO/IEC 27035, NIST SP 800-61
**Version:** 1.0 | **COM6020M — Privacy & Data Protection**

---

## 1. Overview

This plan provides the framework to deal with, respond to, and recover from security and privacy-related events related to Care Predict patient information.

**Scope:** All events where there is unauthorized access, disclosure, modification, and/or destruction of PHI/Personal information.

---

## 2. Incident Classification

| Priority | Description | Examples | Response Time |
|-----------|-------------|---------|---------------|
| P1 – Critical | Threat to patient safety or widespread exposure | Ransomware attack, massive data loss, unencrypted protected health information (PHI) exposure | <1 hour |
| P2 – High | High-profile access issues | Staff member snooping, vendor security breach, between 100-500 patients impacted | <4 hours |
| P3 – Medium | Access but small scope or limited impact on patients | Access to single record by someone not authorized | <24 hours |
| P4 – Low | Possible security issue needing investigation | Access activity or failed login attempts | <72 hours |
---

## 3. The Incident Response Team

| Position     | Duties                                    |
|-------------|-------------------------------------------|
| IR Manager  | Coordination and decision-making           |
| DPO         | Regulatory compliance and notification      |
| CISO        | Attack containment and forensics analysis   |
| Legal       | Legal repercussions and regulatory compliance|
| Comms. Dir. | Communication to stakeholders and the public |
| Clinician   | Patient safety                             |

---

## 4. Six-Stage Response Procedure

### Stage 1 — Detection
- Real-time monitoring with SIEM utilizing machine learning-based anomaly detection.
- Categorize incidents P1-P4 within one hour of discovery.
- Assemble IR team for P1/P2 incidents.

### Stage 2 — Containment
- Disable compromised accounts and authenticate tokens.
- Network isolation of impacted systems.
- Forensic evidence collection – Do not overwrite logs.
- Incident timeline documentation.

### Stage 3 — Investigation
- Identify attack source and extent of data breach. 
- Estimate number of impacted patients and types of data involved.
- Engage third-party forensics if needed.

### Phase 4 — Notify

| Regulation | Recipient | Timeline | Trigger |
|------------|-----------|----------|---------|
| GDPR Article 33       | ICO                | 72 hours      | All breaches involving personal data|
| GDPR Article 34       | Patients           | Immediate     | When there is high-risk involved for individuals' rights   |
| HIPAA Breach Rule     | HHS & individuals  | **60 days**   | 500 patients affected           |
| HIPAA Media Rule      | Media              | 60 days       | More than 500 in the same state   |
| CCPA                 | California residents | Immediate    | Personal data breach             |

### Phase 5 - Recovery
- Restore from clean backups.
- Repair vulnerabilities before restoring services.
- Activate monitoring systems.
- Confirm integrity after restoration.

### Phase 6 - Post-Incident Review (Within 5 Days)
- Conduct a blameless review identifying root causes and sequence of events.
- Risk register and DPIA update with new threats intelligence.
- Tighten up any control processes to mitigate further breaches.
- Report learnings to DPO and board of directors.

---

## 5. Templates for Regulatory Notifications

### Supervisory Authority Notification (GDPR – Article 33)

```
Subject: Personal Data Breach Notification — [Incident ID]

To [Data Protection Authority],

This is to inform you about a personal data breach in accordance with Article 33 of the GDPR.

Nature of breach: [Description]
Data subjects affected: [Number] — categories: [Health records / wearable data]
Personal data records: [Number]
DPO contact: [Name, Email, Phone]
Likely consequences: [Risk assessment summary]
Measures taken: [Containment and remediation actions]

[DPO Name], Health Sync Systems Ltd
```

### Individual Notification (HIPAA)

```
Dear [Patient Name],

On [Date] we became aware of a security breach that could affect your protected health information.

What happened: [Brief description]
Information involved: [Data categories]
What we are doing: [Containment and remediation steps]
What you can do: Be sure to monitor your health insurance statements and your credit reports.

Contact: breach-response@healthsync.com | [Phone]

[Name, Title], Health Sync Systems Ltd
```

---

## 6. Important Checklists

### Containment
- [ ] Compromised accounts locked
- [ ] Affected systems isolated
- [ ] Forensic images collected
- [ ] Logs retained
- [ ] Legal consultation done

### GDPR Breach Notification Process
- [ ] Risk assessment conducted
- [ ] Notification to DPA within 72 hours
- [ ] Notification of data subjects if high-risk
- [ ] Documentation of notifications kept

### HIPAA Breach Notification Process
- [ ] Notifications to individuals sent within 60 days
- [ ] Notification to HHS completed
- [ ] Public media notification if more than 500 affected
- [ ] Breach log updated

---

## 7. Contacts

| Role                | Name         | Phone       | Email                     |
|---------------------|--------------|------------|---------------------------|
| Incident Response   | [Name]       | [Phone]    | [Email]                   |
| Data Protection     | [Name]       | [Phone]    | [Email]                   |
| CISO               | [Name]       | [Phone]    | [Email]                    |
| HHS OCR (HIPAA)        | Office for Civil Rights  | 1-800-368-1019      | ocrportal.hhs.gov |

**Last Updated:** [Date] | **Next Review:** [Date] | **Approved By:** [CISO, DPO]

---
*COM6020M — Privacy & Data Protection | York St John University*

---

## References

- European Union (2016). *GDPR Articles 33 and 34 — Breach Notification*. Available at: https://eur-lex.europa.eu/eli/reg/2016/679/oj

- US Department of Health and Human Services (2013). *HIPAA Breach Notification Rule — 45 CFR §164.400–414*. Available at: https://www.hhs.gov/hipaa/for-professionals/breach-notification/index.html

- ISO/IEC (2016). *ISO/IEC 27035 — Information Security Incident Management*. International Organisation for Standardisation.

- NIST (2012). *SP 800-61 Rev 2 — Computer Security Incident Handling Guide*. Available at: https://csrc.nist.gov/pubs/sp/800/61/r2/final

- State of California (2018). *CCPA — Cal. Civ. Code § 1798.82 — Breach Notification*. Available at: https://oag.ca.gov/privacy/ccpa

- ICO (2021). *Personal Data Breaches — Guidance for Controllers*. Available at: https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/personal-data-breaches/

---
