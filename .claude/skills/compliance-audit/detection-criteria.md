# Framework Detection Criteria

This document provides detailed criteria for determining which compliance frameworks apply to a software project.

## GDPR (General Data Protection Regulation)

### Automatically Applies If:
- Project collects any personal data (names, emails, IP addresses, cookies, etc.)
- Users could be from the EU/EEA
- Website/app is accessible from EU countries

### Key Indicators:
- User registration or authentication
- Email collection (newsletters, contact forms)
- Analytics tracking (Google Analytics, etc.)
- Cookies or local storage
- User profiles or accounts
- Any EU-specific features or language support
- GDPR-related dependencies or packages

### Questions to Ask:
1. "Does your application collect any personal information from users (emails, names, addresses, etc.)?"
2. "Is your application accessible to users in the European Union?"
3. "Do you use cookies or tracking technologies?"

### When to Skip:
- Purely internal tools with no user data
- Static websites with no data collection
- Completely anonymous services (very rare)

**Default stance:** If uncertain and the project has users, assume GDPR applies.

---

## HIPAA (Health Insurance Portability and Accountability Act)

### Automatically Applies If:
- Application is for healthcare providers, health plans, or healthcare clearinghouses
- Handles Protected Health Information (PHI)
- Medical records, patient data, health information

### Key Indicators:
- "health", "medical", "patient", "clinic", "hospital" in project name/description
- HIPAA-related dependencies
- Medical/healthcare domain terminology in code
- Patient models/tables in database
- EHR/EMR integration
- Healthcare-specific APIs (HL7, FHIR)
- Diagnosis codes, prescription data
- Health insurance information

### Questions to Ask:
1. "Does your application handle any health or medical information?"
2. "Are you a healthcare provider, health plan, or business associate of one?"
3. "Do you store, process, or transmit Protected Health Information (PHI)?"

### When to Skip:
- General wellness apps without medical records
- Fitness trackers that don't share with healthcare providers
- Health content/education sites without user medical data
- Non-healthcare applications

**Default stance:** Only apply if clear healthcare context. Don't apply to general wellness/fitness apps unless they handle actual medical records.

---

## PCI-DSS (Payment Card Industry Data Security Standard)

### Automatically Applies If:
- Application stores, processes, or transmits credit/debit card data
- Handles Primary Account Numbers (PANs)
- Accepts direct card payments

### Key Indicators:
- "payment", "checkout", "cart", "billing" functionality
- Payment form fields (card number, CVV, expiration)
- Payment-related database tables
- Direct payment processing code
- E-commerce functionality
- PCI-related dependencies

### Does NOT Apply If:
- Using hosted payment forms (Stripe Checkout, PayPal)
- Payment processor handles all card data
- No direct access to card information (most common)

### Questions to Ask:
1. "Does your application accept credit or debit card payments?"
2. "Do you handle card data directly, or do you use a payment processor like Stripe?"
3. "If using a payment processor, do you use hosted payment forms or do you collect card data in your application?"

### When to Skip:
- Using payment processors with hosted forms (Stripe Checkout, PayPal Standard)
- No payment functionality
- Only handles payment tokens, never actual card data

**Default stance:** Most modern apps don't need PCI-DSS because they use payment processors. Only apply if there's evidence of direct card data handling.

---

## CCPA/CPRA (California Consumer Privacy Act / Privacy Rights Act)

### Automatically Applies If:
- Business operates in California or has California users
- Collects personal information
- Meets one of these thresholds:
  - Annual gross revenues > $25 million
  - Buys/sells/shares PI of 100,000+ CA consumers/households
  - Derives 50%+ revenue from selling CA consumer PI

### Key Indicators:
- US-based application
- User registration with state/location
- California-specific features
- "Do Not Sell My Personal Information" link exists
- CCPA-related terms in privacy policy
- Analytics, advertising, or data sharing

### Questions to Ask:
1. "Does your application serve users in California?"
2. "Do you collect personal information from users?"
3. "Do you share user data with third parties (analytics, advertising, etc.)?"
4. "Does your business meet any of the CCPA thresholds?" (provide the three criteria)

### When to Skip:
- Non-US applications with no US users
- Internal tools not serving California consumers
- Very small businesses under all thresholds

**Default stance:** If the project is US-based with any users, assume CCPA applies.

---

## SOC 2 (Service Organization Control 2)

### Automatically Applies If:
- Project is a SaaS platform
- Service provider that handles customer data
- B2B application that customers rely on
- Cloud service or technology service provider

### Key Indicators:
- Multi-tenant architecture
- Customer data isolation
- SaaS business model
- B2B service offering
- "Enterprise", "business", "platform" in description
- Customer/tenant models in database
- Service Level Agreements (SLAs)

### Questions to Ask:
1. "Is this a SaaS (Software as a Service) product?"
2. "Do you provide services to other businesses that handle their customer data?"
3. "Do your customers ask for SOC 2 reports?"
4. "Is this a B2B platform or service?"

### When to Skip:
- B2C consumer applications
- Internal tools
- Open source projects
- Single-tenant applications
- Small side projects

**Default stance:** Only apply to B2B SaaS platforms and service providers. Skip for consumer apps and internal tools.

---

## Detection Algorithm

### Step 1: Initial Analysis
1. Read README.md, package.json/requirements.txt, database schema
2. Search for keywords related to each framework
3. Analyze data models and API endpoints
4. Review dependencies for compliance-related packages

### Step 2: Build Hypothesis
- Create a list of likely applicable frameworks
- Rate confidence for each (High, Medium, Low)

### Step 3: Confirm with User
- For High confidence: Confirm briefly
- For Medium confidence: Ask detailed questions
- For Low confidence: Ask if it could apply

### Step 4: Final Selection
- Present confirmed frameworks to user
- Explain why others were excluded
- Allow user to request additional framework audits if desired

## Example Decision Tree

```
Does the project collect user data?
├── No → Skip GDPR, CCPA (unless handling cookies/analytics)
└── Yes
    ├── Health/medical context?
    │   ├── Yes → Include HIPAA
    │   └── No → Skip HIPAA
    │
    ├── Direct payment card handling?
    │   ├── Yes → Include PCI-DSS
    │   └── No → Skip PCI-DSS
    │
    ├── EU users possible?
    │   ├── Yes → Include GDPR
    │   └── No → Skip GDPR (rare)
    │
    ├── California/US users?
    │   ├── Yes → Include CCPA
    │   └── No → Skip CCPA
    │
    └── B2B SaaS platform?
        ├── Yes → Include SOC 2
        └── No → Skip SOC 2
```

## Edge Cases

### Fitness/Wellness Apps
- **Include GDPR/CCPA** if collecting user data
- **Skip HIPAA** unless integrated with healthcare providers
- Ask: "Do you share data with healthcare providers or insurance companies?"

### E-commerce Platforms
- **Include GDPR/CCPA** for user data
- **Skip PCI-DSS** if using payment processors with hosted forms
- **Consider SOC 2** if B2B marketplace

### Open Source Projects
- May still need GDPR/CCPA if deployed version collects data
- Focus on code that could lead to compliance issues
- Provide guidance for users deploying the software

### Internal Tools
- May skip most frameworks
- Focus on security best practices instead
- SOC 2 might apply if it's internal infrastructure for a service company

Remember: When in doubt, err on the side of inclusion and let the user confirm. It's better to ask than to miss a relevant framework.
