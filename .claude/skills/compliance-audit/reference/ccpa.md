# CCPA Compliance Checklist

## Overview
California Consumer Privacy Act (CCPA) and California Privacy Rights Act (CPRA) compliance requirements for businesses that collect personal information from California residents.

**Effective Date:** CCPA (2020), CPRA (January 2023)

---

## CCPA/CPRA Applicability

### Does CCPA Apply to Your Business?

Your business must comply if it meets ANY of the following thresholds AND does business in California:

- [ ] Annual gross revenues exceed $25 million
- [ ] Buys, sells, or shares personal information of 100,000+ California consumers or households
- [ ] Derives 50%+ of annual revenue from selling or sharing California consumers' personal information

**Note:** Under CPRA, "sharing" for cross-context behavioral advertising now counts toward the 100,000 threshold.

### Service Provider vs Business
- **Business:** Determines purposes and means of processing
- **Service Provider:** Processes on behalf of Business per contract
- **Contractor:** Similar to Service Provider under CPRA
- **Third Party:** Receives personal information without service provider contract

---

## Personal Information Under CCPA/CPRA

### Categories of Personal Information
- [ ] Identifiers (name, email, IP address, device ID, etc.)
- [ ] Commercial information (purchase history, preferences)
- [ ] Biometric information
- [ ] Internet/network activity (browsing history, interactions)
- [ ] Geolocation data
- [ ] Audio, electronic, visual, or similar information
- [ ] Professional or employment information
- [ ] Education information
- [ ] Inferences (profiles, preferences, behavior predictions)
- [ ] Sensitive personal information (see below)

### Sensitive Personal Information (CPRA)
Additional restrictions apply to:
- [ ] Social Security, driver's license, passport numbers
- [ ] Account login + password/credentials
- [ ] Precise geolocation
- [ ] Racial or ethnic origin
- [ ] Religious or philosophical beliefs
- [ ] Union membership
- [ ] Genetic data
- [ ] Biometric data for identification
- [ ] Health information
- [ ] Sex life or sexual orientation
- [ ] Citizenship or immigration status

---

## Consumer Rights Under CCPA/CPRA

### 1. Right to Know (§1798.100, §1798.110, §1798.115)

#### 1.1 Information to Provide
- [ ] Categories of personal information collected
- [ ] Sources of personal information
- [ ] Business/commercial purpose for collecting
- [ ] Categories of third parties with whom shared
- [ ] Specific pieces of personal information collected
- [ ] Categories sold or shared (if applicable)
- [ ] Categories disclosed for business purposes

#### 1.2 Implementation Requirements
- [ ] Respond within 45 days (extendable to 90 days)
- [ ] Verify consumer identity
- [ ] Provide information free of charge
- [ ] Provide information for preceding 12 months
- [ ] Deliver information via mail or electronically
- [ ] Make information portable and readily usable

**Expected endpoints:**
- `POST /api/privacy/data-request`
- `GET /api/privacy/data-export/:token`

### 2. Right to Delete (§1798.105)

#### 2.1 Deletion Requirements
- [ ] Delete personal information upon verified request
- [ ] Direct service providers to delete
- [ ] Respond within 45 days (extendable to 90 days)
- [ ] Confirm deletion to consumer
- [ ] Document exceptions to deletion

#### 2.2 Exceptions (You may retain data if needed for)
- [ ] Complete transaction/provide service
- [ ] Detect security incidents
- [ ] Debug and repair errors
- [ ] Exercise free speech
- [ ] Comply with legal obligations
- [ ] Internal uses reasonably aligned with expectations
- [ ] Scientific, historical, or statistical research

**Expected endpoints:**
- `POST /api/privacy/deletion-request`
- `DELETE /api/users/:id/data`

### 3. Right to Correct (§1798.106) - CPRA

#### 3.1 Correction Requirements
- [ ] Allow consumers to correct inaccurate information
- [ ] Verify consumer identity
- [ ] Respond within 45 days (extendable to 90 days)
- [ ] Consider nature and purposes of processing
- [ ] Direct service providers to correct

**Expected endpoints:**
- `POST /api/privacy/correction-request`
- `PATCH /api/users/:id/data`

### 4. Right to Opt-Out of Sale/Sharing (§1798.120, §1798.121)

#### 4.1 Opt-Out Requirements
- [ ] Do not sell personal information after opt-out request
- [ ] Do not share for cross-context behavioral advertising
- [ ] Honor opt-out for at least 12 months
- [ ] Allow re-opt-in
- [ ] Process requests within 15 business days
- [ ] No discrimination for opting out

#### 4.2 "Do Not Sell or Share My Personal Information" Link
- [ ] Prominent link on homepage
- [ ] Link on every page where information collected
- [ ] Clear and conspicuous
- [ ] Easy to execute opt-out
- [ ] No account creation required for opt-out

**Expected implementation:**
- `/do-not-sell` or `/opt-out` page
- Cookie-based or account-based opt-out tracking
- Global Privacy Control (GPC) support

#### 4.3 Global Privacy Control (GPC)
- [ ] Recognize and process GPC signals (CPRA requirement)
- [ ] Treat GPC as valid opt-out request
- [ ] Document GPC implementation

### 5. Right to Limit Use of Sensitive Personal Information (§1798.121) - CPRA

#### 5.1 Limitation Requirements
- [ ] "Limit the Use of My Sensitive Personal Information" link
- [ ] Honor limitation requests
- [ ] Use/disclose SPI only for permitted purposes:
  - Providing requested goods/services
  - Preventing security incidents
  - Verifying/maintaining quality
  - Short-term, transient use
  - Performing services per service provider contract
  - Activities that don't infer characteristics about consumer

**Expected implementation:**
- `/limit-sensitive-info` page
- Granular consent for sensitive data

### 6. Right to Non-Discrimination (§1798.125)

#### 6.1 Non-Discrimination Requirements
- [ ] Do not deny goods or services for exercising rights
- [ ] Do not charge different prices or rates
- [ ] Do not provide different quality of goods/services
- [ ] Do not suggest different prices/quality

#### 6.2 Financial Incentives (Allowed)
- [ ] May offer financial incentives for collection/sale
- [ ] Must be reasonably related to value of data
- [ ] Must provide notice and obtain opt-in consent
- [ ] Must allow revocation of consent

---

## Notice Requirements

### 1. Privacy Policy (§1798.130)

#### 1.1 Required Content
- [ ] Categories of personal information collected
- [ ] Purposes for collection/use
- [ ] Categories of sources
- [ ] Categories shared with third parties
- [ ] Business/commercial purposes for disclosing
- [ ] Whether personal information is sold or shared
- [ ] Categories of third parties receiving personal information
- [ ] Retention period or criteria for determining retention
- [ ] Consumer rights under CCPA/CPRA
- [ ] How to exercise rights
- [ ] Link to "Do Not Sell or Share My Personal Information"
- [ ] Link to "Limit the Use of My Sensitive Personal Information"
- [ ] Right to opt-in if under 16 years old

#### 1.2 Privacy Policy Requirements
- [ ] Post conspicuously on website
- [ ] Update at least every 12 months
- [ ] Effective date on privacy policy
- [ ] Archive prior versions for at least 12 months
- [ ] Use plain language
- [ ] Available before or at point of collection

**Location:** `/privacy-policy` or `/privacy`

### 2. Notice at Collection (§1798.100(b))

#### 2.1 Information to Provide at Collection
- [ ] Categories of personal information collected
- [ ] Purposes for each category
- [ ] Link to privacy policy
- [ ] Notice before/at time of collection
- [ ] If selling/sharing, provide link to opt-out
- [ ] If collecting sensitive PI, provide limit link

#### 2.2 Format Requirements
- [ ] Clear and conspicuous
- [ ] Separate from privacy policy
- [ ] Easily accessible
- [ ] Update within 30 days of changes

**Implementation:**
- Notice on forms where data collected
- Pop-ups or banners on data collection
- Checkbox with link to full notice

### 3. Notice of Right to Opt-Out

#### 3.1 "Do Not Sell or Share My Personal Information"
- [ ] Interactive form or single-step process
- [ ] Clear instructions
- [ ] Link from homepage
- [ ] No account required
- [ ] No personal information required (except for verification)

### 4. Notice of Financial Incentive (§1798.125(b))

If offering financial incentives:
- [ ] Material terms of program
- [ ] How to opt-in
- [ ] How to revoke consent
- [ ] Value of consumer's data (optional but recommended)
- [ ] Method for calculating value

---

## Verification Requirements (§1798.140(w))

### 1. Identity Verification Process

#### 1.1 Two-Step Verification Required
- [ ] Match 2+ data points provided by consumer with existing data
- [ ] Declare under penalty of perjury
- [ ] Signed declaration if not online

#### 1.2 Verification Methods
- [ ] Email verification for low-risk requests
- [ ] Multi-factor authentication for sensitive requests
- [ ] Government ID verification for deletion/correction
- [ ] Existing account credentials

#### 1.3 Verification Standards
- [ ] Reasonable degree of certainty
- [ ] Risk-based approach
- [ ] More stringent for sensitive information
- [ ] Document verification process
- [ ] Retain verification records

### 2. Authorized Agent Requests
- [ ] Accept requests via authorized agents
- [ ] Verify agent's authority
- [ ] Require written permission from consumer
- [ ] Verify consumer's identity
- [ ] May require direct consumer confirmation

---

## Service Provider/Contractor Contracts (§1798.140(w))

### 1. Required Contract Terms

#### 1.1 Service Provider Agreement Must Include
- [ ] Prohibit retaining, using, or disclosing PI except per contract
- [ ] Prohibit selling or sharing personal information
- [ ] Prohibit retaining, using, or disclosing PI for any purpose other than performing services
- [ ] Certify understanding of CCPA restrictions
- [ ] Grant business right to take corrective action
- [ ] Allow business to monitor compliance
- [ ] Require subcontractor certification

#### 1.2 Contractor Agreement (CPRA) Must Include
- [ ] Similar restrictions as service providers
- [ ] Specify processing purposes
- [ ] Limit retention, use, and disclosure
- [ ] Allow business to audit compliance

**Required contracts with:**
- Cloud hosting providers
- Analytics services
- Email/SMS providers
- Payment processors
- Customer support tools
- Marketing platforms

---

## Data Sale and Sharing

### 1. What Constitutes "Sale" Under CCPA?

Sale = Selling, renting, releasing, disclosing, disseminating, making available, transferring, or otherwise communicating personal information for monetary or other valuable consideration

**Common scenarios that count as "sale":**
- [ ] Sharing data with advertising partners
- [ ] Selling customer lists
- [ ] Affiliate marketing with data sharing
- [ ] Data broker relationships

**Not considered "sale":**
- Service provider relationships with proper contracts
- Asset sales in M&A (with proper notice)
- Intentional consumer actions (clicking a link)

### 2. What Constitutes "Sharing" Under CPRA?

Sharing = Disclosing personal information for cross-context behavioral advertising

**Common scenarios:**
- [ ] Third-party advertising cookies
- [ ] Social media pixels (Facebook Pixel, etc.)
- [ ] Advertising IDs shared with ad networks

### 3. If You Sell or Share Personal Information

- [ ] Conspicuous "Do Not Sell or Share My Personal Information" link
- [ ] Honor opt-out requests
- [ ] Update privacy policy to disclose sales/sharing
- [ ] List categories sold/shared
- [ ] List categories of third parties
- [ ] Do not sell/share information of consumers under 16 without opt-in

---

## Children's Privacy (Under 16)

### 1. Children Under 13
- [ ] Obtain verifiable parental consent before selling
- [ ] "Sell My Personal Information" button
- [ ] Age verification mechanism

### 2. Children 13-15
- [ ] Obtain opt-in consent from child before selling
- [ ] Age verification mechanism
- [ ] Clear disclosure of sale practices

### 3. Actual Knowledge Standard
- [ ] Do not sell if you have actual knowledge consumer is under 16
- [ ] Without opt-in consent
- [ ] Implement age-gating if targeting children

---

## Data Security and Retention

### 1. Reasonable Security (§1798.150)

#### 1.1 Security Requirements
- [ ] Implement and maintain reasonable security procedures
- [ ] Appropriate to nature of information
- [ ] Prevent unauthorized access, destruction, use, modification, or disclosure
- [ ] Written information security program (WISP)

#### 1.2 Security Measures
- [ ] Encryption at rest and in transit
- [ ] Access controls
- [ ] Regular security assessments
- [ ] Incident response plan
- [ ] Employee training
- [ ] Vendor management
- [ ] Audit logging

### 2. Data Retention

#### 2.1 Retention Requirements
- [ ] Do not retain PI longer than reasonably necessary
- [ ] Document retention purposes
- [ ] Implement data retention schedules
- [ ] Automatic deletion after retention period
- [ ] Disclose retention periods in privacy policy

---

## Record-Keeping Requirements (§1798.130(a)(5))

### 1. Metrics to Track (24-month rolling period)

#### 1.1 Required Metrics
- [ ] Number of requests to know received
- [ ] Number of requests to know complied with (whole or in part)
- [ ] Number of requests to know denied
- [ ] Median/mean days to respond to requests to know
- [ ] Number of requests to delete received
- [ ] Number of requests to delete complied with (whole or in part)
- [ ] Number of requests to delete denied
- [ ] Median/mean days to respond to requests to delete
- [ ] Number of requests to opt-out received
- [ ] Number of requests to opt-out complied with (whole or in part)
- [ ] Number of requests to opt-out denied
- [ ] Median/mean days to respond to opt-out requests

#### 1.2 CPRA Additional Metrics
- [ ] Number of correction requests received
- [ ] Number of correction requests complied with
- [ ] Number of correction requests denied
- [ ] Number of requests to limit received
- [ ] Number of requests to limit complied with

#### 1.3 Reporting Requirements
- [ ] Compile metrics every 12 months
- [ ] Post metrics in privacy policy
- [ ] Option to provide more granular data

**Implementation:**
- Database table tracking all privacy requests
- Dashboard for compliance metrics
- Automated metric calculation

---

## Risk Assessments and Audits (CPRA)

### 1. Cybersecurity Audit (§1798.185(a)(15))

For businesses processing PI of 10+ million consumers:
- [ ] Annual cybersecurity audit
- [ ] Submit audit to California Privacy Protection Agency
- [ ] Document security practices
- [ ] Identify risks
- [ ] Report mitigation measures

### 2. Risk Assessment for Processing

- [ ] Conduct risk assessment before processing activities
- [ ] Assess risks to consumer privacy
- [ ] Document risk mitigation
- [ ] Review assessments regularly

---

## California Privacy Protection Agency (CPPA)

### 1. CPPA Authority (CPRA)
- [ ] Awareness of CPPA enforcement powers
- [ ] Monitor CPPA regulations and guidance
- [ ] Prepare for potential investigations
- [ ] Maintain compliance documentation

### 2. Penalties
- [ ] Up to $2,500 per violation (unintentional)
- [ ] Up to $7,500 per intentional violation
- [ ] Additional penalties for violations involving minors
- [ ] Private right of action for data breaches

---

## Implementation Priority

### Critical (Must Implement)
1. Privacy policy with required disclosures
2. Notice at collection
3. Consumer rights request handling (know, delete, opt-out)
4. "Do Not Sell or Share" link and mechanism
5. Service provider contracts
6. Data security measures

### High Priority
1. Verification procedures
2. GPC signal processing
3. "Limit Sensitive Information" mechanism
4. Right to correct implementation
5. Record-keeping and metrics
6. Data retention policies

### Medium Priority
1. Financial incentive notices (if applicable)
2. Age verification for minors (if applicable)
3. Risk assessments
4. Annual compliance audits
5. Employee training

---

## Technical Implementation Guide

### Backend Requirements
```
Privacy API endpoints:
- POST /api/privacy/request-data (Right to Know)
- POST /api/privacy/delete-data (Right to Delete)
- POST /api/privacy/correct-data (Right to Correct)
- POST /api/privacy/opt-out (Do Not Sell/Share)
- POST /api/privacy/limit-sensitive (Limit Sensitive Info)

Database:
- privacy_requests table
- opt_out_tracking table
- consent_records table
- request_metrics table

Services:
- Verification service
- Data export service
- Data deletion service
- Opt-out tracking service
- GPC signal processor
```

### Frontend Requirements
```
Pages:
- /privacy-policy
- /do-not-sell
- /limit-sensitive-info
- /privacy-request (unified request form)

Components:
- Notice at collection banners
- Consent management
- Cookie consent (with opt-out)
- GPC detection script

Forms:
- Right to Know request form
- Right to Delete request form
- Right to Correct request form
- Opt-out form
```

### Infrastructure
```
- HTTPS/TLS everywhere
- Database encryption
- Access controls
- Audit logging
- Backup procedures
- Incident response capability
```

---

## Testing Checklist

- [ ] Test data export functionality
- [ ] Test data deletion (complete removal)
- [ ] Test data correction workflow
- [ ] Test opt-out mechanism
- [ ] Test GPC signal recognition
- [ ] Test verification process
- [ ] Verify notice at collection displays
- [ ] Verify privacy policy completeness
- [ ] Test record-keeping and metrics
- [ ] Verify service provider contracts
- [ ] Security audit completed

---

## Common CCPA/CPRA Violations to Avoid

1. **No "Do Not Sell or Share" link**
2. **Incomplete privacy policy**
3. **Missing notice at collection**
4. **Not honoring opt-out requests**
5. **Discriminating against consumers exercising rights**
6. **Inadequate verification procedures**
7. **Missing service provider contracts**
8. **Not recognizing GPC signals**
9. **Failing to provide data upon request**
10. **Excessive retention of personal information**

---

## Documentation Required

1. `PRIVACY_POLICY.md` - Comprehensive privacy policy
2. `NOTICE_AT_COLLECTION.md` - Collection notices
3. `SERVICE_PROVIDER_CONTRACTS/` - Contract folder
4. `VERIFICATION_PROCEDURES.md` - Identity verification process
5. `DATA_RETENTION_POLICY.md` - Retention schedules
6. `SECURITY_MEASURES.md` - Security documentation
7. `PRIVACY_REQUEST_LOG.csv` - Request tracking
8. `COMPLIANCE_METRICS.md` - Annual metrics report
9. `RISK_ASSESSMENTS/` - Risk assessment documents
10. `INCIDENT_RESPONSE_PLAN.md` - Breach response procedures

---

## Resources

- [CCPA Official Text](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?division=3.&part=4.&lawCode=CIV&title=1.81.5)
- [CPRA Official Text](https://oag.ca.gov/system/files/initiatives/pdfs/19-0021A1%20%28Consumer%20Privacy%20-%20Version%203%29_1.pdf)
- [California Privacy Protection Agency](https://cppa.ca.gov/)
- [California AG CCPA Guidance](https://oag.ca.gov/privacy/ccpa)
- [IAPP CCPA Resources](https://iapp.org/resources/topics/california-consumer-privacy-act/)

---

**Last Updated:** [DATE]
**Next Review:** [DATE]
**Privacy Officer:** [NAME/ROLE]
**Applies to California Consumers:** YES
