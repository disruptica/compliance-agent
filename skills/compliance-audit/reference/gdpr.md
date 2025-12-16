# GDPR Compliance Checklist

## Overview
This checklist covers General Data Protection Regulation (EU) 2016/679 requirements for software applications processing personal data of EU residents.

---

## 1. Legal Basis & Consent (Articles 6, 7, 8)

### 1.1 Lawful Basis for Processing
- [ ] Identify and document lawful basis for each data processing activity
- [ ] Implement consent mechanism where consent is the legal basis
- [ ] Store records of when and how consent was obtained
- [ ] Ensure consent is freely given, specific, informed, and unambiguous
- [ ] Implement separate consent for different processing purposes
- [ ] Verify age for children's data (16 or member state minimum)

**Implementation locations:**
- Database: `consent_records` table
- Backend: Consent management service
- Frontend: Consent collection forms/modals
- API: Consent verification middleware

### 1.2 Consent Management
- [ ] Allow users to withdraw consent easily
- [ ] Provide clear consent withdrawal mechanism
- [ ] Stop processing immediately upon consent withdrawal
- [ ] Keep audit trail of consent changes
- [ ] Granular consent options (not bundled)
- [ ] Pre-checked boxes are forbidden

---

## 2. Data Subject Rights (Articles 12-23)

### 2.1 Right to Access (Article 15)
- [ ] Implement data export functionality
- [ ] Provide data in machine-readable format (JSON, CSV, XML)
- [ ] Include all personal data categories
- [ ] Respond within 1 month (extendable to 3 months)
- [ ] Verify identity before providing data

**Expected endpoints:**
- `GET /api/users/me/data-export`
- Background job for large exports
- Email notification when export is ready

### 2.2 Right to Rectification (Article 16)
- [ ] Allow users to update their personal information
- [ ] Implement validation for data accuracy
- [ ] Update data across all systems
- [ ] Notify third parties of corrections if applicable

### 2.3 Right to Erasure / "Right to be Forgotten" (Article 17)
- [ ] Implement account deletion functionality
- [ ] Soft delete vs hard delete strategy documented
- [ ] Delete or anonymize data across all systems
- [ ] Handle deletion of backups within reasonable timeframe
- [ ] Notify third parties of deletion requests
- [ ] Keep minimal data if legal obligation exists

**Expected endpoints:**
- `DELETE /api/users/me`
- Anonymization service for historical records
- Backup cleanup procedures

### 2.4 Right to Data Portability (Article 20)
- [ ] Export data in structured, commonly used format
- [ ] Allow direct transmission to another controller
- [ ] Include only user-provided and automatically generated data

### 2.5 Right to Object (Article 21)
- [ ] Implement objection mechanism for marketing
- [ ] Stop processing for direct marketing upon objection
- [ ] Provide clear objection options

### 2.6 Right to Restriction (Article 18)
- [ ] Allow users to request processing restriction
- [ ] Implement data "freeze" functionality
- [ ] Mark restricted data clearly in database

---

## 3. Data Protection by Design & Default (Article 25)

### 3.1 Privacy by Design
- [ ] Minimize data collection (collect only necessary data)
- [ ] Implement pseudonymization where possible
- [ ] Use encryption for data at rest
- [ ] Use encryption for data in transit (TLS 1.2+)
- [ ] Implement access controls based on least privilege
- [ ] Default settings are privacy-protective

### 3.2 Data Minimization
- [ ] Document why each data field is necessary
- [ ] Remove unnecessary data collection points
- [ ] Implement automatic data deletion schedules
- [ ] Review data retention policies regularly

---

## 4. Security Measures (Article 32)

### 4.1 Technical Security
- [ ] Encryption at rest (database, file storage)
- [ ] Encryption in transit (HTTPS/TLS everywhere)
- [ ] Secure password storage (bcrypt, Argon2, PBKDF2)
- [ ] Multi-factor authentication available
- [ ] Regular security updates and patches
- [ ] API rate limiting implemented
- [ ] SQL injection prevention
- [ ] XSS protection implemented
- [ ] CSRF protection implemented
- [ ] Secure session management

### 4.2 Organizational Security
- [ ] Access control and authentication system
- [ ] Role-based access control (RBAC)
- [ ] Audit logging of data access
- [ ] Regular security audits conducted
- [ ] Incident response plan documented
- [ ] Employee training on data protection

### 4.3 Logging & Monitoring
- [ ] Log all personal data access
- [ ] Log data modifications
- [ ] Log consent changes
- [ ] Log deletion requests
- [ ] Implement log retention policy
- [ ] Ensure logs don't contain sensitive personal data

**Expected implementations:**
- Audit log table/service
- Log rotation policies
- Monitoring alerts for suspicious activity

---

## 5. Data Processing Records (Article 30)

### 5.1 Processing Activities Record
- [ ] Document all processing activities
- [ ] Identify data controller and processors
- [ ] Document purposes of processing
- [ ] Describe categories of data subjects
- [ ] Describe categories of personal data
- [ ] Document data recipients/third parties
- [ ] Document international data transfers
- [ ] Document retention periods
- [ ] Document security measures

**Location:** Create `DATA_PROCESSING_RECORD.md` in docs

---

## 6. Data Breach Notification (Articles 33, 34)

### 6.1 Breach Detection & Response
- [ ] Implement breach detection mechanisms
- [ ] Document breach notification procedure
- [ ] Notify supervisory authority within 72 hours
- [ ] Notify affected individuals if high risk
- [ ] Keep breach register/log
- [ ] Document breach response actions

**Required documentation:**
- Incident response plan
- Breach notification templates
- Contact information for supervisory authority

---

## 7. Privacy Policy & Transparency (Articles 13, 14)

### 7.1 Privacy Notice Requirements
- [ ] Identity and contact details of controller
- [ ] Contact details of DPO (if applicable)
- [ ] Purposes and legal basis of processing
- [ ] Legitimate interests (if applicable)
- [ ] Categories of personal data
- [ ] Recipients or categories of recipients
- [ ] International transfer information
- [ ] Retention periods or criteria
- [ ] Data subject rights information
- [ ] Right to withdraw consent
- [ ] Right to lodge complaint with authority
- [ ] Information about automated decision-making
- [ ] Source of data (if not collected directly)

### 7.2 Privacy Policy Accessibility
- [ ] Privacy policy easily accessible
- [ ] Written in clear, plain language
- [ ] Available before data collection
- [ ] Updated when practices change
- [ ] Version history maintained

**Location:** `/privacy-policy` route

---

## 8. Data Protection Officer (Articles 37-39)

### 8.1 DPO Requirements (if applicable)
- [ ] Determine if DPO is required
- [ ] Appoint qualified DPO
- [ ] Publish DPO contact information
- [ ] Ensure DPO independence
- [ ] Provide resources to DPO

**When DPO is required:**
- Public authority processing
- Large scale monitoring
- Large scale special category data processing

---

## 9. Third-Party Processors (Article 28)

### 9.1 Vendor Management
- [ ] Maintain list of all data processors
- [ ] Execute Data Processing Agreements (DPAs)
- [ ] Ensure processors provide sufficient guarantees
- [ ] Audit processor compliance
- [ ] Document sub-processors
- [ ] Obtain consent for sub-processor changes

### 9.2 Third-Party Services Audit
- [ ] Payment processors (Stripe, PayPal, etc.)
- [ ] Email services (SendGrid, Mailgun, etc.)
- [ ] Analytics (Google Analytics, Mixpanel, etc.)
- [ ] Cloud hosting (AWS, GCP, Azure, etc.)
- [ ] CDN providers
- [ ] Customer support tools
- [ ] Marketing automation tools

**Required documentation:**
- DPA for each processor
- List in `THIRD_PARTY_PROCESSORS.md`

---

## 10. International Data Transfers (Articles 44-50)

### 10.1 Transfer Mechanisms
- [ ] Identify all international data transfers
- [ ] Use adequacy decisions where available
- [ ] Implement Standard Contractual Clauses (SCCs)
- [ ] Conduct Transfer Impact Assessments
- [ ] Document transfer safeguards
- [ ] Inform users of international transfers

**Common scenarios:**
- US-based cloud hosting (post-Schrems II considerations)
- International team member access
- Third-party services outside EU

---

## 11. Special Categories of Data (Article 9)

### 11.1 Sensitive Data Protection
- [ ] Identify if processing special category data:
  - Racial or ethnic origin
  - Political opinions
  - Religious beliefs
  - Trade union membership
  - Genetic data
  - Biometric data
  - Health data
  - Sex life or sexual orientation
- [ ] Implement additional safeguards
- [ ] Obtain explicit consent (if that's the legal basis)
- [ ] Document necessity for processing

---

## 12. Automated Decision-Making (Article 22)

### 12.1 Profiling & Automated Decisions
- [ ] Identify automated decision-making processes
- [ ] Ensure human intervention option
- [ ] Provide information about logic involved
- [ ] Allow users to challenge decisions
- [ ] Implement safeguards for automated decisions
- [ ] Conduct DPIA for high-risk automated processing

---

## 13. Data Protection Impact Assessment (Article 35)

### 13.1 DPIA Requirements
- [ ] Identify if DPIA is required
- [ ] Conduct DPIA for high-risk processing
- [ ] Document systematic description of processing
- [ ] Assess necessity and proportionality
- [ ] Assess risks to data subjects
- [ ] Document mitigation measures
- [ ] Consult DPO (if appointed)

**When DPIA is required:**
- Systematic large-scale monitoring
- Large-scale special category data
- Systematic evaluation/scoring
- Automated decision-making with legal effects
- Use of new technologies

**Location:** Create `DPIA.md` in docs

---

## 14. Cookies & Tracking (ePrivacy Directive)

### 14.1 Cookie Consent
- [ ] Implement cookie consent banner
- [ ] Categorize cookies (necessary, functional, analytics, marketing)
- [ ] Allow granular cookie choices
- [ ] Block non-essential cookies until consent
- [ ] Provide cookie policy
- [ ] Easy withdrawal of cookie consent
- [ ] Cookie consent persists appropriately

### 14.2 Cookie Documentation
- [ ] List all cookies used
- [ ] Document purpose of each cookie
- [ ] Document duration of each cookie
- [ ] Identify first-party vs third-party cookies

**Location:** `/cookie-policy` route

---

## 15. Children's Data (Article 8)

### 15.1 Child Protection Measures
- [ ] Age verification mechanism (if targeting children)
- [ ] Parental consent for children under 16 (or member state age)
- [ ] Age-appropriate privacy information
- [ ] Additional safeguards for children's data
- [ ] Limit data collection from children

---

## Implementation Priority

### Critical (Implement First)
1. Legal basis for processing
2. Security measures (encryption, access control)
3. Data subject rights (access, deletion, portability)
4. Privacy policy
5. Consent management

### High Priority
1. Data breach notification procedures
2. Audit logging
3. Third-party DPAs
4. Cookie consent
5. Data retention policies

### Medium Priority
1. DPIA for high-risk processing
2. DPO appointment (if required)
3. Transfer impact assessments
4. Processing records documentation
5. Staff training

---

## Technical Implementation Checklist

### Backend
- [ ] User model with consent fields
- [ ] Audit log service
- [ ] Data export service
- [ ] Data anonymization service
- [ ] Consent management API
- [ ] Cookie consent API
- [ ] Retention policy enforcement (cron jobs)

### Frontend
- [ ] Privacy policy page
- [ ] Cookie consent banner
- [ ] User data management dashboard
- [ ] Data export UI
- [ ] Account deletion UI
- [ ] Consent preference center

### Database
- [ ] `consent_records` table
- [ ] `audit_logs` table
- [ ] `data_deletion_requests` table
- [ ] Encryption for sensitive fields
- [ ] Retention policy metadata

### Infrastructure
- [ ] TLS/HTTPS everywhere
- [ ] Database encryption at rest
- [ ] Secure backup procedures
- [ ] Access control and IAM
- [ ] Log aggregation and monitoring

---

## Testing Checklist

- [ ] Test data export functionality
- [ ] Test account deletion (complete erasure)
- [ ] Test consent withdrawal
- [ ] Test cookie consent blocking
- [ ] Test age verification (if applicable)
- [ ] Penetration testing conducted
- [ ] Security vulnerability scanning
- [ ] GDPR compliance audit by legal team

---

## Documentation Required

1. `PRIVACY_POLICY.md` - Public privacy policy
2. `COOKIE_POLICY.md` - Cookie usage policy
3. `DATA_PROCESSING_RECORD.md` - Article 30 records
4. `THIRD_PARTY_PROCESSORS.md` - Vendor list with DPAs
5. `DPIA.md` - Data Protection Impact Assessment
6. `INCIDENT_RESPONSE_PLAN.md` - Breach notification procedures
7. `DATA_RETENTION_POLICY.md` - Retention schedules
8. `SECURITY_MEASURES.md` - Technical and organizational measures

---

## Resources

- [GDPR Official Text](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- [ICO GDPR Guide](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/)
- [EDPB Guidelines](https://edpb.europa.eu/our-work-tools/general-guidance/gdpr-guidelines-recommendations-best-practices_en)
- [NOYB GDPR Resources](https://noyb.eu/en)

---

**Last Updated:** [DATE]
**Next Review:** [DATE]
**Compliance Owner:** [NAME/ROLE]
