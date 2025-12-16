# HIPAA Compliance Checklist

## Overview
Health Insurance Portability and Accountability Act (HIPAA) compliance requirements for applications that create, receive, maintain, or transmit Protected Health Information (PHI).

**Applies to:** Covered Entities (healthcare providers, health plans, healthcare clearinghouses) and Business Associates

---

## Understanding PHI (Protected Health Information)

### What is PHI?
Any individually identifiable health information that relates to:
- Past, present, or future physical/mental health condition
- Provision of healthcare
- Past, present, or future payment for healthcare

### 18 PHI Identifiers
1. Names
2. Geographic subdivisions smaller than state
3. Dates (except year) - birth, admission, discharge, death, age over 89
4. Telephone numbers
5. Fax numbers
6. Email addresses
7. Social Security numbers
8. Medical record numbers
9. Health plan beneficiary numbers
10. Account numbers
11. Certificate/license numbers
12. Vehicle identifiers and serial numbers
13. Device identifiers and serial numbers
14. Web URLs
15. IP addresses
16. Biometric identifiers (fingerprints, retinal scans)
17. Full-face photos
18. Any other unique identifying number, characteristic, or code

---

## HIPAA Rules Overview

### Privacy Rule
Protects PHI privacy and establishes patient rights

### Security Rule
Establishes standards for ePHI (electronic PHI) security

### Breach Notification Rule
Requires notification of PHI breaches

### Omnibus Rule
Extends HIPAA to Business Associates

---

## HIPAA Security Rule: Administrative Safeguards

### 1. Security Management Process (§164.308(a)(1))

#### 1.1 Risk Analysis
- [ ] Conduct thorough risk analysis of ePHI
- [ ] Identify potential threats and vulnerabilities
- [ ] Document risk analysis findings
- [ ] Assess current security measures
- [ ] Determine likelihood and impact of threats
- [ ] Review risk analysis annually

#### 1.2 Risk Management
- [ ] Implement security measures to reduce risks
- [ ] Document risk mitigation strategies
- [ ] Prioritize risks by severity
- [ ] Track risk remediation progress
- [ ] Review and update risk management plan

#### 1.3 Sanction Policy
- [ ] Establish disciplinary policy for security violations
- [ ] Document sanctions for violations
- [ ] Apply sanctions consistently
- [ ] Train workforce on sanction policy

#### 1.4 Information System Activity Review
- [ ] Review logs and audit trails regularly
- [ ] Monitor system activity for security incidents
- [ ] Document review process
- [ ] Investigate anomalies and exceptions

### 2. Assigned Security Responsibility (§164.308(a)(2))
- [ ] Designate security official
- [ ] Document security officer responsibilities
- [ ] Ensure adequate authority and resources
- [ ] Security officer title and contact info published

### 3. Workforce Security (§164.308(a)(3))

#### 3.1 Authorization and Supervision
- [ ] Implement authorization procedures for workforce access
- [ ] Supervise workforce members with ePHI access
- [ ] Document authorization process
- [ ] Define job roles and access levels

#### 3.2 Workforce Clearance
- [ ] Determine appropriate access for workforce members
- [ ] Background checks where appropriate
- [ ] Clearance procedures documented

#### 3.3 Termination Procedures
- [ ] Revoke access immediately upon termination
- [ ] Retrieve all devices and credentials
- [ ] Document termination procedures
- [ ] Disable accounts and change passwords

### 4. Information Access Management (§164.308(a)(4))

#### 4.1 Access Authorization
- [ ] Implement policies for authorizing access
- [ ] Grant access based on role and need
- [ ] Document access authorization process
- [ ] Review access rights regularly

#### 4.2 Access Establishment and Modification
- [ ] Procedures for granting access
- [ ] Procedures for modifying access
- [ ] Procedures for revoking access
- [ ] Document all access changes

### 5. Security Awareness and Training (§164.308(a)(5))

#### 5.1 Security Reminders
- [ ] Periodic security reminders to workforce
- [ ] Updates on security threats
- [ ] Security bulletins and newsletters

#### 5.2 Protection from Malicious Software
- [ ] Train on malware threats
- [ ] Train on safe browsing practices
- [ ] Phishing awareness training

#### 5.3 Log-in Monitoring
- [ ] Train workforce on log-in monitoring
- [ ] Detect and report suspicious activity

#### 5.4 Password Management
- [ ] Password creation and management training
- [ ] Password security best practices
- [ ] No password sharing policy

#### 5.5 Training Requirements
- [ ] Annual security training mandatory
- [ ] Training upon hire
- [ ] Training when security responsibilities change
- [ ] Document training completion
- [ ] Test understanding of training

### 6. Security Incident Procedures (§164.308(a)(6))

#### 6.1 Response and Reporting
- [ ] Incident response plan documented
- [ ] Identify and respond to suspected incidents
- [ ] Report security incidents
- [ ] Document incidents and responses
- [ ] Mitigate harmful effects
- [ ] Test incident response plan

### 7. Contingency Plan (§164.308(a)(7))

#### 7.1 Data Backup Plan
- [ ] Regular backups of ePHI
- [ ] Test backup restoration
- [ ] Document backup procedures
- [ ] Offsite backup storage
- [ ] Encrypted backups

#### 7.2 Disaster Recovery Plan
- [ ] Document disaster recovery procedures
- [ ] Define recovery time objectives (RTO)
- [ ] Define recovery point objectives (RPO)
- [ ] Test disaster recovery plan annually
- [ ] Update plan as needed

#### 7.3 Emergency Mode Operation Plan
- [ ] Procedures for operating in emergency mode
- [ ] Access to ePHI during emergencies
- [ ] Alternate processing site if needed

#### 7.4 Testing and Revision
- [ ] Test contingency plan annually
- [ ] Review and revise based on test results
- [ ] Update after system changes

#### 7.5 Applications and Data Criticality Analysis
- [ ] Prioritize applications and data
- [ ] Determine criticality of systems
- [ ] Document dependencies

### 8. Evaluation (§164.308(a)(8))
- [ ] Conduct periodic technical and non-technical evaluations
- [ ] Evaluate based on risk analysis
- [ ] Evaluate after environmental changes
- [ ] Document evaluation results
- [ ] Perform evaluations annually at minimum

### 9. Business Associate Contracts (§164.308(b)(1))

#### 9.1 Written Contracts
- [ ] Obtain satisfactory assurances from Business Associates
- [ ] Execute Business Associate Agreements (BAAs)
- [ ] Specify permitted uses of PHI
- [ ] Require appropriate safeguards
- [ ] Require breach notification
- [ ] Require subcontractor BAAs
- [ ] Right to audit Business Associates
- [ ] Termination provisions

**Required BAAs with:**
- Cloud hosting providers (AWS, GCP, Azure)
- Email service providers
- Payment processors (if handling PHI)
- SMS/notification services
- Analytics providers (if PHI exposed)
- Support/ticketing systems
- Backup services

---

## HIPAA Security Rule: Physical Safeguards

### 1. Facility Access Controls (§164.310(a)(1))

#### 1.1 Contingency Operations
- [ ] Procedures for facility access during emergencies
- [ ] Backup power systems
- [ ] Physical security during emergencies

#### 1.2 Facility Security Plan
- [ ] Physical security measures documented
- [ ] Building access controls
- [ ] Visitor management
- [ ] Security cameras where appropriate

#### 1.3 Access Control and Validation
- [ ] Control and validate physical access
- [ ] Badge system for personnel
- [ ] Visitor sign-in/escort procedures
- [ ] Lock systems for sensitive areas

#### 1.4 Maintenance Records
- [ ] Document facility repairs and modifications
- [ ] Track physical security maintenance
- [ ] Log facility access for maintenance

### 2. Workstation Use (§164.310(b))
- [ ] Define proper workstation use
- [ ] Policies for workstation security
- [ ] Physical safeguards for workstations
- [ ] Screen privacy filters where needed
- [ ] Automatic screen lock
- [ ] Clean desk policy

### 3. Workstation Security (§164.310(c))
- [ ] Physical safeguards for workstations
- [ ] Restrict workstation access
- [ ] Lock down workstations
- [ ] Cable locks where appropriate
- [ ] Secure workstations in public areas

### 4. Device and Media Controls (§164.310(d)(1))

#### 4.1 Disposal
- [ ] Secure disposal procedures for ePHI
- [ ] Shred paper containing PHI
- [ ] Wipe/destroy electronic media
- [ ] Certificate of destruction
- [ ] Document disposal activities

#### 4.2 Media Re-use
- [ ] Remove ePHI before re-using media
- [ ] Document media sanitization
- [ ] Verification of ePHI removal

#### 4.3 Accountability
- [ ] Track hardware and electronic media
- [ ] Inventory of devices containing ePHI
- [ ] Document media movements
- [ ] Chain of custody procedures

#### 4.4 Data Backup and Storage
- [ ] Encrypted backup media
- [ ] Secure offsite storage
- [ ] Document backup locations
- [ ] Test backup restoration

---

## HIPAA Security Rule: Technical Safeguards

### 1. Access Control (§164.312(a)(1))

#### 1.1 Unique User Identification
- [ ] Unique user ID for each person
- [ ] No shared credentials
- [ ] Service accounts properly managed
- [ ] Track user IDs to individuals

#### 1.2 Emergency Access Procedure
- [ ] Break-glass procedures for emergencies
- [ ] Emergency access documented
- [ ] Monitor emergency access use
- [ ] Audit emergency access events

#### 1.3 Automatic Logoff
- [ ] Implement session timeout
- [ ] Terminate sessions after inactivity
- [ ] Configurable timeout periods
- [ ] Document timeout policies

#### 1.4 Encryption and Decryption
- [ ] Encrypt ePHI at rest (strongly recommended)
- [ ] Encrypt ePHI in transit (required when over internet)
- [ ] Use strong encryption (AES-256)
- [ ] Document encryption methods
- [ ] Key management procedures

### 2. Audit Controls (§164.312(b))
- [ ] Implement hardware/software audit controls
- [ ] Log all ePHI access
- [ ] Log system access
- [ ] Log user activities
- [ ] Protect audit logs from alteration
- [ ] Review logs regularly
- [ ] Retain logs for 6 years minimum

**What to log:**
- User logins/logouts
- PHI access (read, write, delete)
- Administrative actions
- Security incidents
- System changes
- Failed access attempts

### 3. Integrity Controls (§164.312(c)(1))

#### 3.1 Mechanism to Authenticate ePHI
- [ ] Ensure ePHI is not improperly altered
- [ ] Digital signatures or checksums
- [ ] Version control
- [ ] Detect unauthorized modifications
- [ ] Document integrity verification methods

### 4. Person or Entity Authentication (§164.312(d))
- [ ] Verify identity before granting access
- [ ] Strong authentication methods
- [ ] Multi-factor authentication (strongly recommended)
- [ ] Password complexity requirements:
  - Minimum 8 characters (12+ recommended)
  - Mix of upper/lower/numbers/symbols
  - Change every 90 days maximum
  - No password reuse (last 24 passwords)
- [ ] Account lockout after failed attempts

### 5. Transmission Security (§164.312(e)(1))

#### 5.1 Integrity Controls
- [ ] Ensure ePHI not improperly modified in transit
- [ ] Use checksums or digital signatures
- [ ] Verify data integrity after transmission

#### 5.2 Encryption
- [ ] Encrypt ePHI during transmission (required)
- [ ] TLS 1.2+ for all ePHI transmission
- [ ] VPN for remote access
- [ ] Encrypted email for PHI
- [ ] No unencrypted ePHI transmission

---

## HIPAA Privacy Rule Requirements

### 1. Notice of Privacy Practices
- [ ] Create Notice of Privacy Practices (NPP)
- [ ] Provide NPP to patients at first contact
- [ ] Post NPP prominently on website
- [ ] Obtain acknowledgment of receipt
- [ ] Update NPP when practices change
- [ ] Available in plain language

### 2. Patient Rights

#### 2.1 Right to Access
- [ ] Provide PHI within 30 days of request
- [ ] Can extend by 30 days with notice
- [ ] Provide in requested format if feasible
- [ ] Fees limited to cost of production
- [ ] Document access requests

#### 2.2 Right to Amendment
- [ ] Allow patients to request amendments
- [ ] Accept or deny within 60 days
- [ ] Document amendment requests
- [ ] Append amendments to records

#### 2.3 Right to Accounting of Disclosures
- [ ] Track disclosures of PHI
- [ ] Provide accounting upon request
- [ ] Document disclosures for 6 years
- [ ] Include date, recipient, purpose

#### 2.4 Right to Request Restrictions
- [ ] Allow patients to request restrictions
- [ ] Must honor restrictions for services paid out-of-pocket
- [ ] Document restriction requests

#### 2.5 Right to Confidential Communications
- [ ] Allow alternative communication methods
- [ ] Accommodate reasonable requests
- [ ] Document communication preferences

### 3. Minimum Necessary Rule
- [ ] Access only minimum PHI necessary
- [ ] Limit routine disclosures
- [ ] Define minimum necessary for each role
- [ ] Review and update periodically
- [ ] Document minimum necessary determinations

### 4. Uses and Disclosures
- [ ] Obtain authorization for non-permitted uses
- [ ] Document all disclosures
- [ ] Track consent and authorizations
- [ ] Revocation process for authorizations
- [ ] Distinguish treatment/payment/operations disclosures

---

## HIPAA Breach Notification Rule

### 1. Breach Definition
**Breach:** Acquisition, access, use, or disclosure of PHI that compromises security or privacy

### 2. Breach Risk Assessment
- [ ] Document breach assessment methodology
- [ ] Assess probability PHI was compromised
- [ ] Consider nature and extent of PHI
- [ ] Consider who accessed PHI
- [ ] Consider whether PHI was actually viewed
- [ ] Consider mitigation efforts

### 3. Notification Requirements

#### 3.1 Individual Notification
- [ ] Notify affected individuals within 60 days
- [ ] Send written notice (email acceptable)
- [ ] Include description of breach
- [ ] Include types of PHI involved
- [ ] Include steps individuals should take
- [ ] Include what entity is doing
- [ ] Include contact information

#### 3.2 Media Notification
- [ ] If breach affects 500+ residents of a state
- [ ] Notify prominent media outlets
- [ ] Same content as individual notices

#### 3.3 HHS Notification
- [ ] If breach affects 500+ individuals: notify immediately
- [ ] If breach affects <500 individuals: annual notification
- [ ] Submit breach report to HHS
- [ ] Use HHS breach reporting portal

#### 3.4 Business Associate Notification
- [ ] Business Associates must notify Covered Entity
- [ ] Notification without unreasonable delay
- [ ] Maximum 60 days after discovery

### 4. Breach Log
- [ ] Maintain log of all breaches
- [ ] Include breaches affecting <500 individuals
- [ ] Include date of breach
- [ ] Include brief description
- [ ] Include number of individuals affected

---

## Implementation Checklist

### Critical (Must Implement)
1. [ ] Encryption of ePHI at rest and in transit
2. [ ] Unique user identification
3. [ ] Access controls and authentication
4. [ ] Audit logging
5. [ ] Business Associate Agreements
6. [ ] Risk analysis
7. [ ] Breach notification procedures
8. [ ] Notice of Privacy Practices

### High Priority
1. [ ] Security awareness training
2. [ ] Incident response plan
3. [ ] Contingency/disaster recovery plan
4. [ ] Minimum necessary policies
5. [ ] Patient rights procedures
6. [ ] Termination procedures
7. [ ] Session timeout
8. [ ] Password policies

### Medium Priority
1. [ ] Physical safeguards
2. [ ] Workstation security policies
3. [ ] Device and media controls
4. [ ] Data backup procedures
5. [ ] Regular security evaluations
6. [ ] Sanction policies

---

## Technical Implementation Guide

### Backend Requirements
```
- User model with role-based access
- Audit logging service
- PHI encryption at rest (database, files)
- Session management with timeout
- Authentication with MFA
- Authorization middleware
- Breach detection system
- Data backup automation
```

### Frontend Requirements
```
- Session timeout implementation
- Automatic screen lock
- Secure authentication flow
- MFA integration
- Activity monitoring
- Privacy notices display
- Patient rights request forms
```

### Database Requirements
```
- Encrypted columns for PHI
- Audit trail table
- Access log table
- Breach log table
- Patient consent records
- Disclosure accounting table
```

### Infrastructure Requirements
```
- TLS 1.2+ everywhere
- Database encryption at rest
- Encrypted backups
- VPN for remote access
- Firewall configuration
- IDS/IPS systems
- Log aggregation
- Monitoring and alerting
```

---

## De-identification Methods

### Safe Harbor Method
Remove all 18 identifiers (listed above) for the individual and relatives/employers/household members

### Expert Determination Method
Qualified expert determines risk of identification is very small

**Use de-identified data when possible to reduce compliance burden**

---

## Common HIPAA Violations to Avoid

1. **Unencrypted laptops/devices stolen**
2. **Unencrypted email containing PHI**
3. **Improper disposal of PHI**
4. **Unauthorized access to PHI**
5. **Lost/stolen unencrypted portable media**
6. **Lack of Business Associate Agreements**
7. **Insufficient access controls**
8. **Inadequate audit controls**
9. **No risk analysis conducted**
10. **Delayed breach notification**

---

## Penalties for Non-Compliance

### Civil Penalties (per violation)
- Tier 1 (Unknown): $100-$50,000
- Tier 2 (Reasonable cause): $1,000-$50,000
- Tier 3 (Willful neglect, corrected): $10,000-$50,000
- Tier 4 (Willful neglect, not corrected): $50,000+

**Annual maximum:** $1.5 million per violation type

### Criminal Penalties
- Tier 1 (Unknowing): Up to 1 year prison, $50,000 fine
- Tier 2 (False pretenses): Up to 5 years prison, $100,000 fine
- Tier 3 (Intent to sell/harm): Up to 10 years prison, $250,000 fine

---

## Required Documentation

1. `PRIVACY_POLICY.md` - Notice of Privacy Practices
2. `SECURITY_POLICIES.md` - Security policies and procedures
3. `RISK_ANALYSIS.md` - Risk analysis documentation
4. `INCIDENT_RESPONSE_PLAN.md` - Security incident procedures
5. `CONTINGENCY_PLAN.md` - Disaster recovery and backup
6. `BUSINESS_ASSOCIATE_AGREEMENTS/` - BAA folder
7. `TRAINING_RECORDS/` - Training completion records
8. `AUDIT_LOGS/` - System audit logs
9. `BREACH_LOG.md` - Breach notification log
10. `ACCESS_CONTROL_POLICIES.md` - Access authorization procedures

---

## Testing Checklist

- [ ] Verify encryption at rest
- [ ] Verify encryption in transit
- [ ] Test session timeout
- [ ] Test audit logging
- [ ] Test access controls
- [ ] Test MFA functionality
- [ ] Test breach notification process
- [ ] Test data backup and restore
- [ ] Test incident response plan
- [ ] Penetration testing conducted
- [ ] Vulnerability assessment completed

---

## Resources

- [HHS HIPAA Website](https://www.hhs.gov/hipaa/)
- [HIPAA Security Rule](https://www.hhs.gov/hipaa/for-professionals/security/index.html)
- [HIPAA Privacy Rule](https://www.hhs.gov/hipaa/for-professionals/privacy/index.html)
- [Breach Notification Rule](https://www.hhs.gov/hipaa/for-professionals/breach-notification/index.html)
- [OCR Guidance](https://www.hhs.gov/hipaa/for-professionals/security/guidance/index.html)
- [NIST HIPAA Security Rule Toolkit](https://csrc.nist.gov/publications/detail/sp/800-66/rev-2/draft)

---

**Last Updated:** [DATE]
**Next Risk Analysis:** [DATE]
**Security Officer:** [NAME/CONTACT]
**Privacy Officer:** [NAME/CONTACT]
