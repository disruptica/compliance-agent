# PCI DSS Compliance Checklist

## Overview
Payment Card Industry Data Security Standard (PCI DSS) v4.0 requirements for applications that store, process, or transmit cardholder data.

**Scope:** Any system component that stores, processes, or transmits cardholder data (CHD) or sensitive authentication data (SAD), or could impact the security of the cardholder data environment (CDE).

---

## Cardholder Data (CHD) vs Sensitive Authentication Data (SAD)

### Cardholder Data (CHD) - May be stored if needed
- Primary Account Number (PAN)
- Cardholder Name
- Expiration Date
- Service Code

### Sensitive Authentication Data (SAD) - NEVER store after authorization
- Full magnetic stripe data
- CAV2/CVC2/CVV2/CID (card verification codes)
- PIN/PIN blocks

---

## Requirement 1: Install and Maintain Network Security Controls

### 1.1 Network Security Controls
- [ ] Firewall rules documented and reviewed
- [ ] Firewall configuration standards defined
- [ ] Network segmentation implemented (CDE separated from other networks)
- [ ] Restrict inbound/outbound traffic to necessary protocols
- [ ] DMZ implemented between internet and CDE
- [ ] Deny all inbound/outbound traffic by default
- [ ] Review firewall rules every 6 months

### 1.2 Network Diagram
- [ ] Current network diagram exists
- [ ] Shows all connections to CDE
- [ ] Documents network segmentation
- [ ] Shows cardholder data flows
- [ ] Updated when network changes
- [ ] Shows wireless networks

### 1.3 Wireless Security
- [ ] Change default wireless encryption keys
- [ ] Use strong encryption (WPA2/WPA3)
- [ ] Change default SSID
- [ ] Disable SSID broadcast
- [ ] Restrict wireless access to CDE
- [ ] Document approved wireless access points

**Implementation files:**
- `docs/NETWORK_DIAGRAM.md`
- `docs/FIREWALL_RULES.md`
- Infrastructure as Code (Terraform, CloudFormation)

---

## Requirement 2: Apply Secure Configurations

### 2.1 Configuration Standards
- [ ] Configuration standards for all system components
- [ ] Change default passwords before deployment
- [ ] Remove unnecessary services/protocols
- [ ] Configure only one primary function per server
- [ ] Remove unnecessary accounts
- [ ] Disable insecure services (Telnet, FTP, etc.)
- [ ] Enable security features in frameworks

### 2.2 Vendor Defaults
- [ ] Change all default passwords
- [ ] Change default SNMP community strings
- [ ] Remove default accounts
- [ ] Change default encryption keys
- [ ] Remove sample applications/content
- [ ] Disable unnecessary default accounts

### 2.3 Encryption & Security Protocols
- [ ] Use strong cryptography (TLS 1.2+ required, TLS 1.3 recommended)
- [ ] Disable SSL and early TLS (TLS 1.0, TLS 1.1)
- [ ] Implement strong cipher suites only
- [ ] Certificate validation implemented
- [ ] Use trusted certificates only
- [ ] Proper certificate management

**Expected implementations:**
- Configuration management code
- Baseline hardening scripts
- Security configuration templates

---

## Requirement 3: Protect Stored Cardholder Data

### 3.1 Data Storage and Retention
- [ ] **CRITICAL:** Define data retention policy
- [ ] Store ONLY necessary cardholder data
- [ ] Minimize data retention time
- [ ] Implement data retention and disposal procedures
- [ ] Automatic deletion after retention period
- [ ] Document business justification for stored data
- [ ] Quarterly review of stored data

### 3.2 Cardholder Data Protection
- [ ] **NEVER store SAD (Sensitive Authentication Data):**
  - [ ] No full magnetic stripe data
  - [ ] No CAV2/CVC2/CVV2/CID
  - [ ] No PIN/PIN blocks
- [ ] Mask PAN when displayed (show max first 6 and last 4 digits)
- [ ] PAN unreadable anywhere it's stored:
  - [ ] Strong cryptography with key management
  - [ ] One-way hashes (SHA-256 minimum)
  - [ ] Truncation (not a replacement for encryption)
  - [ ] Tokenization

### 3.3 Encryption of CHD
- [ ] Encrypt CHD at rest in databases
- [ ] Encrypt CHD in files
- [ ] Encrypt CHD in removable media
- [ ] Use strong cryptography (AES-256 or stronger)
- [ ] Document encryption methods
- [ ] Cryptographic key management implemented

### 3.4 PAN Rendering
- [ ] Mask PAN in applications (show max 6 + last 4)
- [ ] Mask PAN in logs
- [ ] Mask PAN in screen displays
- [ ] Mask PAN in reports
- [ ] Full PAN only visible to authorized roles
- [ ] Business justification for full PAN access

**Database columns to encrypt:**
- `card_number` / `pan`
- `cvv` (should NEVER be stored)
- Cardholder name
- Expiration date

**Code implementation:**
- Encryption service
- PAN masking utilities
- Data retention cron jobs
- Audit logging for PAN access

---

## Requirement 4: Protect Cardholder Data in Transit

### 4.1 Transmission Security
- [ ] Strong cryptography for transmission over open/public networks
- [ ] TLS 1.2+ for all cardholder data transmission
- [ ] No sending of unencrypted PANs via email, messaging, chat
- [ ] Secure protocols for wireless transmission
- [ ] Never send PAN via end-user messaging technologies

### 4.2 SSL/TLS Configuration
- [ ] Use trusted certificates
- [ ] Certificates from trusted CAs only
- [ ] Valid certificates (not expired)
- [ ] Certificate renewal process
- [ ] Strong cipher suites only
- [ ] Certificate pinning (where applicable)
- [ ] HTTPS everywhere in payment flows

### 4.3 Network Transmission
- [ ] Encrypt PAN over wireless networks
- [ ] Use secure versions of protocols (SSH, not Telnet)
- [ ] Implement proper certificate validation
- [ ] No unencrypted transmission of CHD

**Expected implementations:**
- HTTPS/TLS configuration
- Certificate management system
- Network encryption policies

---

## Requirement 5: Protect All Systems and Networks from Malicious Software

### 5.1 Malware Protection
- [ ] Anti-malware software deployed on all systems (where applicable)
- [ ] Anti-malware kept up to date
- [ ] Automatic updates enabled
- [ ] Regular scans performed
- [ ] Scan results reviewed
- [ ] Anti-malware cannot be disabled by users
- [ ] Logs retained and monitored

### 5.2 Application Security
- [ ] Input validation on all user inputs
- [ ] Output encoding
- [ ] Protect against injection attacks
- [ ] Protect against XSS
- [ ] Protect against CSRF
- [ ] Regular security updates applied
- [ ] Vulnerability scanning performed

**Implementation notes:**
- Container security scanning
- Dependency vulnerability scanning
- SAST/DAST tools integration

---

## Requirement 6: Develop and Maintain Secure Systems and Software

### 6.1 Secure Development
- [ ] Secure coding practices followed
- [ ] Security training for developers
- [ ] Code review process includes security
- [ ] Separate development/test/production environments
- [ ] CHD never in development/test environments
- [ ] Test accounts removed before production
- [ ] Secure SDLC implemented

### 6.2 Vulnerability Management
- [ ] Stay informed about security vulnerabilities
- [ ] Assign risk rankings to vulnerabilities
- [ ] Patch critical vulnerabilities within 1 month
- [ ] Security patches applied promptly
- [ ] Inventory of system components maintained
- [ ] Track security patches

### 6.3 Application Security
- [ ] Prevent common coding vulnerabilities:
  - [ ] SQL Injection
  - [ ] Cross-Site Scripting (XSS)
  - [ ] Cross-Site Request Forgery (CSRF)
  - [ ] Buffer overflows
  - [ ] Insecure cryptographic storage
  - [ ] Insecure communications
  - [ ] Improper error handling
  - [ ] Injection flaws
  - [ ] Authentication/authorization flaws
- [ ] Follow OWASP Top 10
- [ ] Input validation
- [ ] Output encoding
- [ ] Parameterized queries
- [ ] Proper error handling (no sensitive data in errors)

### 6.4 Change Control
- [ ] Document changes to systems
- [ ] Obtain approval for changes
- [ ] Test changes before deployment
- [ ] Back-out procedures documented
- [ ] Separate development/test/production
- [ ] Production data not used in test
- [ ] Removal of test data before production

**Required processes:**
- Secure code review checklist
- Vulnerability management process
- Change control procedures
- Patch management process

---

## Requirement 7: Restrict Access to System Components and CHD

### 7.1 Access Control
- [ ] Access based on need-to-know and job responsibilities
- [ ] Least privilege principle
- [ ] Default deny all access
- [ ] Role-Based Access Control (RBAC) implemented
- [ ] Document access authorization
- [ ] Review access rights every 6 months

### 7.2 User Access Management
- [ ] Unique IDs for all users
- [ ] No shared/group accounts
- [ ] Immediately revoke access for terminated users
- [ ] Remove inactive accounts every 90 days
- [ ] Disable accounts after 90 days of inactivity
- [ ] Vendor access managed and monitored
- [ ] Just-in-time access for privileged operations

### 7.3 Application Access Control
- [ ] Enforce access control in application
- [ ] Deny by default
- [ ] Authorization checks on every request
- [ ] Session management properly implemented
- [ ] Prevent direct object references
- [ ] Enforce authorization for all API endpoints

**Expected implementations:**
- RBAC middleware
- Permission system
- Access audit logs
- User management system

---

## Requirement 8: Identify Users and Authenticate Access

### 8.1 User Identification
- [ ] Unique user IDs for all users
- [ ] No shared credentials
- [ ] No generic/group accounts
- [ ] User IDs cannot be reused
- [ ] Service accounts managed separately
- [ ] Document service account usage

### 8.2 Strong Authentication
- [ ] Multi-factor authentication (MFA) for:
  - [ ] Remote access to CDE
  - [ ] Administrative access
  - [ ] Access to CHD
- [ ] Strong password requirements:
  - [ ] Minimum 12 characters (15+ recommended)
  - [ ] Upper and lowercase letters
  - [ ] Numbers and special characters
  - [ ] Cannot be same as last 4 passwords
  - [ ] Password expires every 90 days
- [ ] Account lockout after 6 failed attempts
- [ ] Lockout duration minimum 30 minutes
- [ ] Session timeout after 15 minutes of inactivity

### 8.3 Password Management
- [ ] Passwords not stored in plaintext
- [ ] Strong hashing algorithm (bcrypt, Argon2, PBKDF2)
- [ ] Adequate salt
- [ ] First-time passwords must be changed
- [ ] Password reset requires identity verification
- [ ] No password hints
- [ ] Passwords transmitted encrypted only

### 8.4 Session Management
- [ ] Secure session management
- [ ] Session ID changes after authentication
- [ ] Secure, random session IDs
- [ ] Session timeout implemented
- [ ] Sessions invalidated on logout
- [ ] Prevent session fixation attacks

**Expected implementations:**
- Authentication service
- MFA implementation
- Password policy enforcement
- Session management middleware

---

## Requirement 9: Restrict Physical Access to Cardholder Data

### 9.1 Physical Access Controls
- [ ] Physical access controls to CDE facilities
- [ ] Video cameras monitor access points
- [ ] Physical access logs maintained
- [ ] Visitor badges distinguish visitors from personnel
- [ ] Escort visitors in CDE
- [ ] Secure storage for media
- [ ] Proper disposal of media containing CHD

### 9.2 Device Management
- [ ] Maintain inventory of devices
- [ ] Inspect devices periodically
- [ ] Train personnel to recognize tampering
- [ ] Point-of-sale (POS) device protection
- [ ] Secure destruction of devices/media

**For cloud/SaaS applications:**
- Verify cloud provider's physical security
- Review SOC 2 reports
- Review datacenter security certifications

---

## Requirement 10: Log and Monitor All Access

### 10.1 Audit Logging
- [ ] Log all access to CHD
- [ ] Log all actions by privileged users
- [ ] Log all access to audit logs
- [ ] Log invalid access attempts
- [ ] Log security events
- [ ] Automated audit trail for system components

### 10.2 Log Contents
- [ ] User identification
- [ ] Type of event
- [ ] Date and time
- [ ] Success/failure indication
- [ ] Origination of event
- [ ] Identity/name of affected resource

### 10.3 Log Protection
- [ ] Protect audit logs from alteration
- [ ] Logs cannot be modified by users
- [ ] Logs backed up to secure location
- [ ] Logs retained for at least 1 year
- [ ] At least 3 months immediately available

### 10.4 Log Monitoring
- [ ] Daily review of logs
- [ ] Review logs of all system components
- [ ] Review logs for exceptions and anomalies
- [ ] Automated log monitoring tools
- [ ] Alert on suspicious activity
- [ ] Incident response procedures for alerts

### 10.5 Time Synchronization
- [ ] Synchronized time across all systems
- [ ] Use NTP or similar
- [ ] Time data protected

**Expected implementations:**
- Centralized logging service
- Log aggregation (ELK, Splunk, CloudWatch)
- Audit log table/service
- Log monitoring and alerting
- SIEM integration

---

## Requirement 11: Test Security of Systems and Networks

### 11.1 Wireless Security Testing
- [ ] Test for unauthorized wireless access points
- [ ] Detect rogue wireless access points
- [ ] Quarterly wireless testing

### 11.2 Vulnerability Scanning
- [ ] Internal vulnerability scans quarterly
- [ ] External vulnerability scans quarterly
- [ ] Scans performed by Approved Scanning Vendor (ASV) for external
- [ ] Rescan after significant changes
- [ ] All "high-risk" vulnerabilities resolved

### 11.3 Penetration Testing
- [ ] Internal penetration testing annually
- [ ] External penetration testing annually
- [ ] Application-layer penetration testing
- [ ] Network-layer penetration testing
- [ ] Penetration test after significant changes
- [ ] Exploitable vulnerabilities corrected and retested

### 11.4 Intrusion Detection/Prevention
- [ ] Deploy intrusion detection/prevention systems (IDS/IPS)
- [ ] Monitor all traffic at CDE perimeter
- [ ] Monitor all critical system files
- [ ] Alert on unauthorized modifications
- [ ] IDS/IPS signatures kept up to date

### 11.5 File Integrity Monitoring
- [ ] Implement file integrity monitoring (FIM)
- [ ] Monitor critical system files
- [ ] Alert on unauthorized changes
- [ ] Compare files weekly minimum

**Expected implementations:**
- Vulnerability scanning tools
- IDS/IPS configuration
- File integrity monitoring tools
- Penetration testing schedule

---

## Requirement 12: Support Information Security with Policies and Programs

### 12.1 Security Policy
- [ ] Information security policy established
- [ ] Policy reviewed annually
- [ ] Policy published to all personnel
- [ ] Risk assessment performed annually
- [ ] Critical assets identified
- [ ] Threats and vulnerabilities identified

### 12.2 Personnel Training
- [ ] Security awareness training for all personnel
- [ ] Training upon hire
- [ ] Annual security training
- [ ] Personnel acknowledge training
- [ ] Training covers responsibilities
- [ ] Training covers acceptable use

### 12.3 Personnel Management
- [ ] Background checks before hiring (where permitted)
- [ ] Acceptable use policies signed
- [ ] Establish termination procedures
- [ ] Disable access immediately upon termination
- [ ] Return all physical devices and access cards

### 12.4 Service Providers
- [ ] Maintain list of service providers
- [ ] Written agreement with each service provider
- [ ] Acknowledge responsibility for CHD security
- [ ] Due diligence before engagement
- [ ] Monitor service provider PCI DSS compliance
- [ ] Service provider PCI DSS compliance verified annually

### 12.5 Incident Response
- [ ] Incident response plan documented
- [ ] Incident response team identified
- [ ] Roles and responsibilities defined
- [ ] Communication procedures defined
- [ ] Coverage for all system components
- [ ] Training on incident response
- [ ] Test incident response plan annually
- [ ] Incident response procedures updated
- [ ] Monitor and respond to security alerts

### 12.6 Security Monitoring
- [ ] Establish security incident detection and response
- [ ] Analyze security events
- [ ] Automated monitoring tools
- [ ] Alert on suspicious activity
- [ ] Incident response procedures
- [ ] Modify procedures based on lessons learned

**Required documentation:**
- `INFORMATION_SECURITY_POLICY.md`
- `INCIDENT_RESPONSE_PLAN.md`
- `ACCEPTABLE_USE_POLICY.md`
- `RISK_ASSESSMENT.md`
- `SERVICE_PROVIDER_LIST.md`
- Training records
- Background check records

---

## PCI DSS Validation Levels

### Level 1
- Over 6 million transactions/year
- Annual onsite assessment by QSA
- Quarterly network scans by ASV
- Attestation of Compliance (AOC)

### Level 2
- 1-6 million transactions/year
- Annual Self-Assessment Questionnaire (SAQ)
- Quarterly network scans by ASV
- Attestation of Compliance (AOC)

### Level 3
- 20,000-1 million e-commerce transactions/year
- Annual Self-Assessment Questionnaire (SAQ)
- Quarterly network scans by ASV

### Level 4
- Fewer than 20,000 e-commerce transactions/year
- Annual Self-Assessment Questionnaire (SAQ)
- Quarterly network scans by ASV (recommended)

---

## Recommended Architecture: Minimize PCI Scope

### Option 1: No CHD Storage (Recommended)
- Use payment processor hosted forms (Stripe Checkout, PayPal)
- Never touch CHD in your application
- Minimal PCI scope
- Use tokenization
- SAQ-A: 22 questions

### Option 2: Tokenization
- Capture CHD temporarily
- Immediately send to payment processor
- Receive token for future use
- Store only tokens
- SAQ A-EP: 160+ questions

### Option 3: Full CHD Handling
- Store and process CHD
- Requires full PCI DSS compliance
- Most expensive and complex
- SAQ D: 300+ questions

**Recommendation:** Use Option 1 whenever possible to minimize compliance burden.

---

## Implementation Priority

### Critical (Must Have)
1. Never store SAD (CVV, full magnetic stripe, PIN)
2. Encrypt CHD at rest and in transit
3. Implement strong access controls
4. Use strong authentication (MFA)
5. Mask PAN when displayed

### High Priority
1. Audit logging of CHD access
2. Network segmentation
3. Vulnerability scanning
4. Secure development practices
5. Data retention policies

### Medium Priority
1. Penetration testing
2. File integrity monitoring
3. Incident response plan
4. Security awareness training
5. Service provider management

---

## Testing Checklist

- [ ] Verify no SAD is stored
- [ ] Verify PAN encryption at rest
- [ ] Verify PAN masking in UI
- [ ] Test MFA functionality
- [ ] Test session timeout
- [ ] Test account lockout
- [ ] Verify audit logging
- [ ] Test access controls
- [ ] Penetration testing completed
- [ ] Vulnerability scan completed
- [ ] ASV scan completed (if applicable)

---

## Common PCI DSS Violations to Avoid

1. **Storing CVV/CVC codes** - NEVER do this
2. **Storing full magnetic stripe data** - NEVER do this
3. **Storing PINs** - NEVER do this
4. **Unencrypted CHD storage**
5. **Unmasked PANs in logs**
6. **Weak passwords**
7. **No MFA on administrative access**
8. **Shared credentials**
9. **No audit logging**
10. **Using default passwords**

---

## Resources

- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [PCI DSS v4.0 Official Documentation](https://www.pcisecuritystandards.org/document_library/)
- [Self-Assessment Questionnaires (SAQs)](https://www.pcisecuritystandards.org/document_library/)
- [Approved Scanning Vendors (ASVs)](https://www.pcisecuritystandards.org/assessors_and_solutions/approved_scanning_vendors)
- [Qualified Security Assessors (QSAs)](https://www.pcisecuritystandards.org/assessors_and_solutions/qualified_security_assessors)

---

**Last Updated:** [DATE]
**Next Assessment:** [DATE]
**Merchant Level:** [1/2/3/4]
**Compliance Owner:** [NAME/ROLE]
**QSA/ASV:** [COMPANY NAME]
