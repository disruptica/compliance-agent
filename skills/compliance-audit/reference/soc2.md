# SOC 2 Compliance Checklist

## Overview
System and Organization Controls (SOC) 2 is an auditing framework developed by the American Institute of CPAs (AICPA) for managing customer data based on five Trust Service Criteria (TSC).

**SOC 2 Type I:** Controls in place at a specific point in time
**SOC 2 Type II:** Operating effectiveness of controls over a period (typically 6-12 months)

---

## Trust Service Criteria (TSC)

### Available Criteria
1. **Security (CC)** - Required for all SOC 2 audits
2. **Availability (A)** - Optional
3. **Processing Integrity (PI)** - Optional
4. **Confidentiality (C)** - Optional
5. **Privacy (P)** - Optional

**Note:** Security (Common Criteria) is mandatory. Select additional criteria based on your business needs.

---

## Common Criteria (CC) - Security

### CC1: Control Environment

#### CC1.1 Organization Structure
- [ ] Organization demonstrates commitment to integrity and ethical values
- [ ] Board of directors demonstrates independence
- [ ] Management establishes structures, reporting lines, authorities
- [ ] Commitment to competence
- [ ] Hold individuals accountable for internal control responsibilities

**Implementation:**
- Code of conduct documented
- Organizational chart
- Roles and responsibilities documented
- Performance reviews include security responsibilities

#### CC1.2 Board Independence
- [ ] Board oversight of system design and operations
- [ ] Board independence from management
- [ ] Board oversight of risk management
- [ ] Board oversight of compliance

**Implementation:**
- Board meeting minutes
- Risk management oversight documentation
- Compliance monitoring documentation

#### CC1.3 Management's Philosophy and Operating Style
- [ ] Management demonstrates commitment to ethics
- [ ] Tone at the top promotes security culture
- [ ] Management establishes oversight responsibilities

**Implementation:**
- Leadership communication on security
- Security awareness programs
- Whistleblower mechanisms

#### CC1.4 Organizational Structure
- [ ] Define reporting lines and authorities
- [ ] Appropriate segregation of duties
- [ ] Document organizational structure

**Implementation:**
- Organization chart with security roles
- Segregation of duties matrix
- Role descriptions

#### CC1.5 Commitment to Competence
- [ ] Define competencies for positions
- [ ] Evaluate competence and address shortcomings
- [ ] Training programs

**Implementation:**
- Job descriptions with required skills
- Training requirements documented
- Training completion tracking

### CC2: Communication and Information

#### CC2.1 Internal Communication
- [ ] Communicate security policies and procedures
- [ ] Separate communication lines for sensitive matters
- [ ] Internal reporting mechanisms for control failures

**Implementation:**
- Security policy distribution
- Internal security newsletter
- Incident reporting channels

#### CC2.2 External Communication
- [ ] Enable external parties to communicate control failures
- [ ] Customer support channels
- [ ] Vendor communication channels

**Implementation:**
- Security email (security@company.com)
- Bug bounty program (optional)
- Vendor management communication

#### CC2.3 Relevant Quality Information
- [ ] Identify information requirements
- [ ] Obtain relevant data from reliable sources
- [ ] Process data into quality information
- [ ] Maintain relevance and quality over time

**Implementation:**
- Data classification policy
- Information quality standards
- Data sources documented

### CC3: Risk Assessment

#### CC3.1 Specify Objectives
- [ ] Objectives defined with sufficient clarity
- [ ] Risk tolerance defined
- [ ] Security objectives aligned with business

**Implementation:**
- Security objectives documented
- Risk appetite statement
- Alignment with business strategy

#### CC3.2 Identify and Analyze Risks
- [ ] Risk identification mechanisms
- [ ] Analyze significance and likelihood of risks
- [ ] Consider risk across the organization

**Implementation:**
- Risk register
- Risk assessment methodology
- Annual risk assessment

#### CC3.3 Fraud Risk Assessment
- [ ] Consider fraud risk
- [ ] Assess incentives and pressures
- [ ] Identify opportunities for fraud
- [ ] Assess attitudes and rationalizations

**Implementation:**
- Fraud risk assessment
- Anti-fraud controls
- Fraud response procedures

#### CC3.4 Identify and Assess Changes
- [ ] Monitor external changes affecting security
- [ ] Monitor internal changes
- [ ] Assess impact of changes on controls

**Implementation:**
- Change management process
- Regular environmental scans
- Control review after significant changes

### CC4: Monitoring Activities

#### CC4.1 Ongoing and Periodic Evaluations
- [ ] Ongoing monitoring activities
- [ ] Periodic separate evaluations
- [ ] Evaluate results and remediate deficiencies

**Implementation:**
- Continuous monitoring tools
- Internal audit schedule
- Remediation tracking

#### CC4.2 Evaluate and Communicate Deficiencies
- [ ] Communicate deficiencies to management
- [ ] Communicate deficiencies to board
- [ ] Track remediation of deficiencies

**Implementation:**
- Deficiency reporting process
- Management reporting
- Remediation tracking system

### CC5: Control Activities

#### CC5.1 Select and Develop Control Activities
- [ ] Control activities support risk mitigation
- [ ] Consider entity-specific factors
- [ ] Implement through policies and procedures

**Implementation:**
- Control activities documented
- Policies and procedures manual
- Control effectiveness reviews

#### CC5.2 Technology Controls
- [ ] Technology general controls
- [ ] Technology application controls
- [ ] Technology infrastructure controls

**Implementation:**
- Access controls
- Change management
- System monitoring

#### CC5.3 Policies and Procedures
- [ ] Establish policies and procedures
- [ ] Review and update periodically
- [ ] Ensure personnel understand responsibilities

**Implementation:**
- Policy management system
- Annual policy review
- Policy acknowledgment tracking

### CC6: Logical and Physical Access Controls

#### CC6.1 Logical Access - Authorization
- [ ] Grant access based on job responsibilities
- [ ] Principle of least privilege
- [ ] Segregation of duties
- [ ] Review access rights periodically

**Implementation:**
- RBAC system
- Access request/approval process
- Quarterly access reviews
- Segregation of duties matrix

#### CC6.2 Logical Access - Registration and Authentication
- [ ] Identify and authenticate all users
- [ ] Strong password requirements
- [ ] Multi-factor authentication
- [ ] Session management

**Implementation:**
- Identity management system
- MFA enforcement
- Password policy (12+ characters, complexity)
- Session timeout

#### CC6.3 Logical Access - Provisioning and Deprovisioning
- [ ] Timely user provisioning
- [ ] Immediate deprovisioning upon termination
- [ ] Disable inactive accounts
- [ ] Document provisioning/deprovisioning procedures

**Implementation:**
- HR onboarding/offboarding integration
- Automated account lifecycle management
- 90-day inactive account review

#### CC6.4 Logical Access - Removal and Modification
- [ ] Remove access when no longer needed
- [ ] Update access when roles change
- [ ] Track and approve access changes

**Implementation:**
- Access change request process
- Approval workflows
- Access change logging

#### CC6.5 Logical Access - Credentials
- [ ] Secure storage of credentials
- [ ] Protect credentials in transit
- [ ] Secure credential issuance and distribution
- [ ] Password rotation policies

**Implementation:**
- Secrets management (HashiCorp Vault, AWS Secrets Manager)
- Encrypted credential transmission
- Service account management

#### CC6.6 Physical Access
- [ ] Physical access controls to facilities
- [ ] Visitor management
- [ ] Physical access logging
- [ ] Badge systems
- [ ] Video surveillance (where appropriate)

**Implementation:**
- Badge access system
- Visitor sign-in procedures
- Security cameras
- Escort policies

#### CC6.7 Data Center Physical Security (if applicable)
- [ ] Restricted access to data centers
- [ ] Environmental controls
- [ ] Fire suppression systems
- [ ] Power redundancy

**For cloud environments:**
- Review SOC 2 reports of cloud providers
- Verify physical security certifications

#### CC6.8 Removable Media
- [ ] Control use of removable media
- [ ] Encrypt sensitive data on removable media
- [ ] Secure disposal of media

**Implementation:**
- Removable media policy
- USB device restrictions
- Media disposal procedures

### CC7: System Operations

#### CC7.1 System Operation Management
- [ ] Monitor system capacity and performance
- [ ] Manage system capacity to meet objectives
- [ ] Plan for future capacity needs

**Implementation:**
- Performance monitoring tools
- Capacity planning process
- Resource utilization tracking

#### CC7.2 Detection and Response
- [ ] Implement monitoring to detect anomalies
- [ ] Incident detection mechanisms
- [ ] Alert generation and escalation
- [ ] Incident response procedures

**Implementation:**
- SIEM or log aggregation
- Intrusion detection systems (IDS)
- Security information and event management
- 24/7 monitoring or on-call rotation

#### CC7.3 Job Scheduling
- [ ] Job scheduling procedures
- [ ] Job execution monitoring
- [ ] Job failure handling

**Implementation:**
- Cron jobs or task schedulers
- Job monitoring and alerting
- Failure notification procedures

#### CC7.4 Data Backup and Recovery
- [ ] Regular backups of critical data
- [ ] Secure backup storage
- [ ] Test backup restoration
- [ ] Document backup/recovery procedures

**Implementation:**
- Automated backup schedules
- Offsite or geo-redundant backup storage
- Quarterly restore testing
- RTO/RPO defined

#### CC7.5 System Logging
- [ ] Comprehensive logging of security events
- [ ] Centralized log management
- [ ] Log retention policies
- [ ] Log review procedures
- [ ] Protect logs from tampering

**Implementation:**
- Centralized logging (ELK, Splunk, CloudWatch)
- Log at least 1 year
- Weekly log reviews
- Immutable or write-once log storage

### CC8: Change Management

#### CC8.1 Change Management Process
- [ ] Formal change management procedures
- [ ] Change request and approval process
- [ ] Testing of changes before deployment
- [ ] Document and track all changes
- [ ] Emergency change procedures

**Implementation:**
- Change advisory board (CAB)
- Change request tickets
- Testing/staging environments
- Change log

#### CC8.2 Change Authorization
- [ ] Authorize changes before implementation
- [ ] Document business justification
- [ ] Risk assessment for changes
- [ ] Rollback plans

**Implementation:**
- Change approval workflows
- Risk-based change categories
- Documented rollback procedures

#### CC8.3 System Development Lifecycle (SDLC)
- [ ] SDLC methodology documented
- [ ] Requirements definition
- [ ] Design and development standards
- [ ] Testing procedures
- [ ] Deployment procedures

**Implementation:**
- SDLC documentation
- Code review requirements
- Automated testing (CI/CD)
- Deployment checklists

#### CC8.4 Infrastructure and Software
- [ ] Authorize infrastructure changes
- [ ] Document infrastructure as code
- [ ] Version control for configuration
- [ ] Security patch management

**Implementation:**
- Infrastructure as Code (Terraform, CloudFormation)
- Git version control
- Patch management process
- Vulnerability scanning

### CC9: Risk Mitigation

#### CC9.1 Vendor Management
- [ ] Vendor risk assessment before engagement
- [ ] Due diligence on vendors
- [ ] Contractual obligations for security
- [ ] Monitor vendor performance
- [ ] Review vendor security periodically

**Implementation:**
- Vendor assessment questionnaires
- Vendor contracts with security requirements
- Annual vendor reviews
- Vendor SOC 2 reports reviewed

#### CC9.2 Encryption
- [ ] Encrypt data at rest
- [ ] Encrypt data in transit
- [ ] Use strong encryption algorithms
- [ ] Key management procedures

**Implementation:**
- Database encryption (AES-256)
- TLS 1.2+ for all transmissions
- Key rotation policies
- Encryption key storage (KMS)

#### CC9.3 Incident Response
- [ ] Incident response plan documented
- [ ] Incident response team identified
- [ ] Detection and reporting procedures
- [ ] Containment and eradication procedures
- [ ] Post-incident review

**Implementation:**
- Incident response playbooks
- On-call rotation
- Incident tracking system
- Post-mortem process

---

## Availability (A) - Optional

### A1: Availability Commitments
- [ ] Define availability objectives
- [ ] Communicate availability commitments to users
- [ ] Measure and monitor availability
- [ ] Service Level Agreements (SLAs) documented

**Implementation:**
- SLA documentation (e.g., 99.9% uptime)
- Status page (status.company.com)
- Availability metrics tracking

### A2: Environmental Protections
- [ ] Environmental controls (temperature, humidity)
- [ ] Power redundancy
- [ ] Fire suppression
- [ ] Physical security of infrastructure

**For cloud environments:**
- Review cloud provider availability measures
- Multi-region/multi-AZ architecture

### A3: System Availability Monitoring
- [ ] Real-time monitoring of system availability
- [ ] Automated alerting for downtime
- [ ] Incident escalation procedures
- [ ] Response time objectives

**Implementation:**
- Uptime monitoring (Pingdom, UptimeRobot)
- Application Performance Monitoring (APM)
- On-call escalation policies

### A4: Backup and Recovery
- [ ] Backup procedures ensure availability
- [ ] Test disaster recovery plan
- [ ] RTO (Recovery Time Objective) defined
- [ ] RPO (Recovery Point Objective) defined

**Implementation:**
- Automated backups every 24 hours
- Cross-region backup replication
- Annual DR test
- Document RTO < 4 hours, RPO < 1 hour

### A5: Redundancy and Failover
- [ ] Redundant systems and components
- [ ] Automatic failover mechanisms
- [ ] Load balancing
- [ ] Geographic redundancy

**Implementation:**
- Multi-AZ deployment
- Auto-scaling groups
- Database replication
- CDN for static assets

---

## Processing Integrity (PI) - Optional

### PI1: Processing Integrity Commitments
- [ ] Define processing integrity objectives
- [ ] Communicate processing commitments
- [ ] System processes data accurately and completely

**Implementation:**
- Processing requirements documented
- Data validation rules
- Error handling procedures

### PI2: Input Validation
- [ ] Validate input for completeness and accuracy
- [ ] Prevent injection attacks
- [ ] Input sanitization
- [ ] Range and format checks

**Implementation:**
- Input validation on all forms
- Parameterized queries
- Whitelisting vs blacklisting

### PI3: Processing Controls
- [ ] Transactions processed correctly
- [ ] Duplicate transaction detection
- [ ] Error handling and logging
- [ ] Processing logs and audit trails

**Implementation:**
- Transaction logging
- Idempotency keys
- Error monitoring and alerting

### PI4: Output Accuracy
- [ ] Output validation procedures
- [ ] Reconciliation of processing results
- [ ] Review of processing exceptions

**Implementation:**
- Output verification checks
- Automated reconciliation processes
- Exception reporting

### PI5: Data Quality
- [ ] Data accuracy controls
- [ ] Data completeness controls
- [ ] Data integrity controls
- [ ] Regular data quality reviews

**Implementation:**
- Data validation rules
- Data quality metrics
- Regular data audits

---

## Confidentiality (C) - Optional

### C1: Confidentiality Commitments
- [ ] Define confidentiality objectives
- [ ] Communicate confidentiality commitments
- [ ] Identify confidential information
- [ ] Document handling procedures

**Implementation:**
- Data classification policy
- Confidentiality agreements
- Handling procedures by classification

### C2: Encryption
- [ ] Encrypt confidential data at rest
- [ ] Encrypt confidential data in transit
- [ ] Use strong encryption standards
- [ ] Key management for encryption

**Implementation:**
- AES-256 for data at rest
- TLS 1.2+ for transmission
- Key rotation procedures

### C3: Access to Confidential Information
- [ ] Restrict access based on need
- [ ] Confidential data access logging
- [ ] Review access to confidential data
- [ ] Data loss prevention measures

**Implementation:**
- Confidential data access controls
- DLP tools (optional)
- Regular access reviews

### C4: Disposal of Confidential Information
- [ ] Secure disposal procedures
- [ ] Data destruction policies
- [ ] Certificate of destruction
- [ ] Disposal tracking

**Implementation:**
- Secure deletion procedures
- Media destruction
- Digital shredding tools

### C5: Confidentiality Breaches
- [ ] Breach notification procedures
- [ ] Incident response for confidentiality breaches
- [ ] Post-breach remediation
- [ ] Communication with affected parties

**Implementation:**
- Breach notification templates
- Incident response plan
- Legal/compliance consultation

---

## Privacy (P) - Optional

### P1: Privacy Notice
- [ ] Privacy notice provided to data subjects
- [ ] Describes data collection and use
- [ ] Easy to find and understand
- [ ] Updated when practices change

**Implementation:**
- Privacy policy on website
- Notice at point of collection
- Version control for privacy policy

### P2: Choice and Consent
- [ ] Obtain consent for data collection
- [ ] Allow opt-out mechanisms
- [ ] Respect user choices
- [ ] Document consent

**Implementation:**
- Consent management system
- Opt-out mechanisms
- Consent audit trail

### P3: Collection
- [ ] Collect only necessary data
- [ ] Data minimization principle
- [ ] Document business need for collection

**Implementation:**
- Data collection assessment
- Remove unnecessary fields
- Regular review of collected data

### P4: Use, Retention, and Disposal
- [ ] Use data only for stated purposes
- [ ] Define retention periods
- [ ] Secure disposal after retention
- [ ] Data subject rights (access, delete, correct)

**Implementation:**
- Data retention policy
- Automated deletion schedules
- Data subject rights request process

### P5: Access
- [ ] Allow data subjects to access their data
- [ ] Provide data in usable format
- [ ] Reasonable timeframe for access

**Implementation:**
- Data export functionality
- Self-service data access (user dashboard)

### P6: Disclosure to Third Parties
- [ ] Obtain consent for third-party disclosure
- [ ] Third-party contracts protect privacy
- [ ] Monitor third-party compliance

**Implementation:**
- Data processing agreements
- Vendor privacy requirements
- Third-party audit rights

### P7: Quality
- [ ] Maintain data accuracy
- [ ] Allow data correction
- [ ] Verify data periodically

**Implementation:**
- Data correction workflows
- Regular data quality checks

### P8: Monitoring and Enforcement
- [ ] Monitor privacy controls
- [ ] Privacy compliance audits
- [ ] Enforce privacy policies
- [ ] Disciplinary actions for violations

**Implementation:**
- Privacy compliance reviews
- Sanction policies
- Privacy officer oversight

---

## SOC 2 Audit Preparation

### Pre-Audit Checklist

#### 1. Readiness Assessment (3-6 months before audit)
- [ ] Gap analysis against TSC
- [ ] Identify control gaps
- [ ] Prioritize remediation
- [ ] Estimate timeline to readiness

#### 2. Documentation Preparation
- [ ] Policies and procedures documented
- [ ] System description prepared
- [ ] Data flow diagrams
- [ ] Network diagrams
- [ ] Vendor/third-party lists
- [ ] Risk assessments
- [ ] Incident logs
- [ ] Change logs
- [ ] Access reviews
- [ ] Training records

#### 3. Evidence Collection
- [ ] Control evidence for Type II (6-12 months)
- [ ] Screenshots of configurations
- [ ] System-generated reports
- [ ] Meeting minutes
- [ ] Approval emails
- [ ] Logs and monitoring data
- [ ] Penetration test reports
- [ ] Vulnerability scan results

#### 4. Select Auditor
- [ ] CPA firm licensed and experienced in SOC 2
- [ ] Define audit scope (which TSC criteria)
- [ ] Agree on audit timeline
- [ ] Determine Type I vs Type II

#### 5. Management Review
- [ ] Review all documentation for accuracy
- [ ] Test controls internally
- [ ] Fix any identified issues
- [ ] Management assertion prepared

### During Audit
- [ ] Provide evidence to auditors
- [ ] Respond to auditor requests promptly
- [ ] Walkthrough of controls
- [ ] Management interviews
- [ ] System demonstrations

### Post-Audit
- [ ] Review draft report
- [ ] Address any findings
- [ ] Obtain final SOC 2 report
- [ ] Share report with customers (under NDA)
- [ ] Plan for next audit cycle

---

## Evidence Repository Structure

Recommended folder structure for SOC 2 evidence:

```
/SOC2-Evidence/
├── Policies-and-Procedures/
│   ├── Information-Security-Policy.pdf
│   ├── Access-Control-Policy.pdf
│   ├── Change-Management-Policy.pdf
│   ├── Incident-Response-Policy.pdf
│   └── ...
├── System-Documentation/
│   ├── System-Description.pdf
│   ├── Network-Diagram.pdf
│   ├── Data-Flow-Diagram.pdf
│   └── Architecture-Overview.pdf
├── Risk-Management/
│   ├── Risk-Assessment-2024.pdf
│   ├── Risk-Register.xlsx
│   └── Risk-Treatment-Plan.pdf
├── Access-Controls/
│   ├── Q1-Access-Review.xlsx
│   ├── Q2-Access-Review.xlsx
│   ├── User-Provisioning-Records/
│   └── User-Deprovisioning-Records/
├── Change-Management/
│   ├── Change-Log-2024.xlsx
│   ├── Change-Requests/
│   └── Emergency-Changes/
├── Monitoring-and-Logging/
│   ├── Log-Review-Records/
│   ├── Monitoring-Configurations/
│   └── Alert-Notifications/
├── Vendor-Management/
│   ├── Vendor-List.xlsx
│   ├── Vendor-Assessments/
│   ├── Vendor-Contracts/
│   └── Vendor-SOC2-Reports/
├── Incident-Management/
│   ├── Incident-Log-2024.xlsx
│   ├── Incident-Reports/
│   └── Post-Incident-Reviews/
├── Training-and-Awareness/
│   ├── Training-Records.xlsx
│   ├── Training-Materials/
│   └── Acknowledgments/
├── Testing-and-Audits/
│   ├── Penetration-Test-Report.pdf
│   ├── Vulnerability-Scans/
│   └── Internal-Audit-Reports/
└── Business-Continuity/
    ├── Backup-Logs/
    ├── DR-Test-Results/
    └── BCP-Documentation.pdf
```

---

## Common Findings and How to Avoid Them

### 1. Inadequate Documentation
- **Problem:** Undocumented or outdated policies
- **Solution:** Document all policies and review annually

### 2. Missing Evidence
- **Problem:** Cannot prove control operated during audit period
- **Solution:** Collect evidence continuously throughout the year

### 3. Lack of Monitoring
- **Problem:** No evidence of log review or monitoring
- **Solution:** Document all monitoring activities, reviews, and follow-ups

### 4. Access Review Gaps
- **Problem:** Access reviews not performed or documented
- **Solution:** Quarterly access reviews with documentation

### 5. Change Management Failures
- **Problem:** Undocumented or unapproved changes
- **Solution:** Strict change management process with approvals

### 6. Vendor Management Weaknesses
- **Problem:** No vendor assessments or missing contracts
- **Solution:** Vendor risk assessment and annual reviews

### 7. Incident Response Gaps
- **Problem:** Incidents not logged or investigated
- **Solution:** Formal incident tracking and post-mortems

### 8. Training Records Missing
- **Problem:** Cannot prove security training
- **Solution:** Track training completion with timestamps

---

## Implementation Timeline

### Months 1-2: Foundation
- Conduct gap analysis
- Document policies and procedures
- Identify control owners
- Begin evidence collection

### Months 3-4: Control Implementation
- Implement missing controls
- Update system documentation
- Begin access reviews
- Implement monitoring

### Months 5-6: Testing and Refinement
- Test controls internally
- Fix identified issues
- Collect more evidence
- Update documentation

### Months 7-12: Type II Evidence Period
- Continuous evidence collection
- Regular reviews and monitoring
- Maintain documentation
- Prepare for audit

### Month 13+: Audit
- Engage auditor
- Provide evidence
- Address findings
- Obtain report

---

## Key Metrics to Track

### Security Metrics
- [ ] Number of security incidents
- [ ] Mean time to detect (MTTD)
- [ ] Mean time to respond (MTTR)
- [ ] Number of vulnerabilities (by severity)
- [ ] Patch management compliance rate

### Access Management Metrics
- [ ] Time to provision new users
- [ ] Time to deprovision terminated users
- [ ] Number of access review exceptions
- [ ] MFA adoption rate
- [ ] Failed login attempts

### Change Management Metrics
- [ ] Number of changes (authorized vs emergency)
- [ ] Change success rate
- [ ] Mean time to implement changes
- [ ] Number of rollbacks

### Availability Metrics (if applicable)
- [ ] System uptime percentage
- [ ] Number of outages
- [ ] Mean time to recovery (MTTR)
- [ ] RTO/RPO achievement rate

---

## Resources

- [AICPA Trust Services Criteria](https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/trustservicesprinciples)
- [SOC 2 Guide](https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/sorhome)
- [Vanta SOC 2 Resources](https://www.vanta.com/products/soc-2)
- [Drata SOC 2 Academy](https://drata.com/soc-2)

---

**SOC 2 Type:** [Type I / Type II]
**Audit Period:** [START DATE] - [END DATE]
**Criteria Selected:** [Security / Availability / Processing Integrity / Confidentiality / Privacy]
**Auditor:** [FIRM NAME]
**Next Audit:** [DATE]
**Compliance Owner:** [NAME/ROLE]
