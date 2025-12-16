# Compliance Audit Plugin for Claude Code

An intelligent Claude Code plugin that automatically audits your software projects for compliance with major regulatory frameworks including GDPR, HIPAA, PCI-DSS, CCPA/CPRA, and SOC 2.

## Features

✨ **Smart Framework Detection** - Automatically determines which compliance frameworks apply to your project based on codebase analysis

📊 **Tiered Reporting** - Provides both executive summaries and detailed technical reports

🎯 **Risk-Based Prioritization** - Categorizes findings by severity (Critical, High, Medium, Low)

🔍 **Thorough Analysis** - Examines code, databases, APIs, third-party integrations, and documentation

📋 **Actionable Recommendations** - Provides specific implementation guidance without writing code

🚀 **Easy to Use** - Just ask Claude to audit your project for compliance

## Supported Frameworks

- **GDPR** (General Data Protection Regulation) - EU data protection
- **HIPAA** (Health Insurance Portability and Accountability Act) - US healthcare data
- **PCI-DSS** (Payment Card Industry Data Security Standard) - Payment card data
- **CCPA/CPRA** (California Consumer Privacy Act/Privacy Rights Act) - California privacy
- **SOC 2** (Service Organization Control 2) - SaaS security and privacy

## Installation

### Option 1: From GitHub (Recommended)

Install directly from the GitHub repository:

```shell
# Add this repository as a marketplace
/plugin marketplace add disruptica/compliance-agent

# Install the plugin
/plugin install compliance-audit@compliance-agent
```

### Option 2: Manual Installation

If you prefer not to use the plugin system, you can install the skill manually:

**For a specific project:**
```bash
# Clone the repository
git clone https://github.com/disruptica/compliance-agent.git

# Copy the skill to your project
cp -r compliance-agent/skills/compliance-audit /path/to/your/project/.claude/skills/
```

**For all your projects:**
```bash
# Clone the repository
git clone https://github.com/disruptica/compliance-agent.git

# Copy to your global skills directory
cp -r compliance-agent/skills/compliance-audit ~/.claude/skills/
```

## Usage

Simply ask Claude Code to audit your project for compliance:

```
"Can you audit my project for compliance?"
```

```
"Check if my application complies with GDPR"
```

```
"Perform a compliance audit for data protection regulations"
```

### How It Works

1. **Analysis** - Claude analyzes your codebase, database schemas, API endpoints, and dependencies

2. **Detection** - Based on what it finds, Claude determines which compliance frameworks likely apply
   - Finds health data → HIPAA
   - Sees payment processing → PCI-DSS
   - Detects user data + EU presence → GDPR
   - US-based with users → CCPA
   - B2B SaaS platform → SOC 2

3. **Confirmation** - Claude asks you targeted questions to confirm applicability:
   - "Does your application serve users in the European Union?"
   - "Do you handle Protected Health Information (PHI)?"
   - etc.

4. **Audit** - Claude performs a thorough audit against the relevant frameworks

5. **Executive Summary** - You receive a high-level report with:
   - Compliance scores for each framework
   - Critical gaps requiring immediate attention
   - High-priority improvements
   - Actionable roadmap with timeline

6. **Detailed Report** (optional) - Request in-depth technical analysis for specific frameworks with:
   - Requirement-by-requirement breakdown
   - Specific file paths and code locations
   - Implementation recommendations
   - Effort estimates

## Example Output

### Executive Summary
```markdown
# Compliance Audit Executive Summary

**Project:** Your App
**Frameworks Assessed:** GDPR, CCPA

## Overall Compliance Scores
- GDPR: 45% compliant (28 gaps found)
- CCPA: 52% compliant (19 gaps found)

## Critical Gaps (Immediate Action Required)
1. No Data Deletion Mechanism - GDPR Art. 17 & CCPA §1798.105
   - Risk: Potential fines up to €20M (GDPR) or $7,500/violation (CCPA)
   - Action: Implement account deletion API
   - Effort: 3-4 days

[... more findings ...]

## Recommended Roadmap
Phase 1 (Weeks 1-2): Critical Gaps
Phase 2 (Weeks 3-6): High-Priority Improvements
[...]
```

## Plugin Structure

```
compliance-agent/
├── .claude-plugin/
│   └── plugin.json            # Plugin manifest and metadata
├── skills/
│   └── compliance-audit/
│       ├── SKILL.md           # Main skill definition with instructions
│       ├── detection-criteria.md  # Framework applicability logic
│       ├── examples.md        # Sample audit reports
│       ├── templates/
│       │   ├── executive-summary.md  # Executive report template
│       │   └── detailed-report.md    # Technical report template
│       └── reference/
│           ├── gdpr.md        # GDPR compliance checklist
│           ├── hipaa.md       # HIPAA compliance checklist
│           ├── pci-dss.md     # PCI-DSS compliance checklist
│           ├── ccpa.md        # CCPA/CPRA compliance checklist
│           └── soc2.md        # SOC 2 compliance checklist
├── README.md                  # This file
├── INSTALL.md                 # Installation guide
└── CHANGELOG.md               # Version history
```

## What the Skill Does

✅ **Analyzes** your codebase for compliance indicators
✅ **Identifies** which regulations apply to your project
✅ **Audits** against comprehensive regulatory checklists
✅ **Finds** specific files, code, and configurations that need attention
✅ **Categorizes** findings by risk and priority
✅ **Recommends** concrete implementation approaches
✅ **Estimates** effort required for remediation
✅ **Provides** actionable roadmaps for compliance

## What the Skill Doesn't Do

❌ **Generate code** - Identifies issues and suggests approaches, but doesn't write full implementations
❌ **Provide legal advice** - Recommends consulting legal counsel for critical decisions
❌ **Guarantee compliance** - Compliance is a legal determination; this is a technical assessment
❌ **Replace auditors** - For official SOC 2 or other certifications, you still need professional auditors

## When to Use This Skill

Use this skill when you:
- Are preparing for a compliance audit
- Need to understand your compliance gaps
- Want to prioritize security/privacy work
- Are launching in a new jurisdiction (EU, California)
- Have customers asking about compliance
- Want to assess third-party integration risks

## Configuration

The skill works out of the box with no configuration needed. It automatically:
- Detects your technology stack
- Identifies data handling patterns
- Determines applicable frameworks
- Asks for confirmation before auditing

## Customization

You can customize the skill by editing:

- **SKILL.md** - Modify detection logic or reporting style
- **detection-criteria.md** - Adjust framework applicability rules
- **reference/*.md** - Add/remove specific compliance requirements
- **templates/*.md** - Change report formats

## Privacy & Security

This skill:
- Runs entirely locally within Claude Code
- Does not send your code to external services
- Analyzes code structure and patterns, not actual user data
- Generates reports based on technical assessment

## Limitations

- **Not a replacement for legal counsel** - Consult lawyers for legal compliance questions
- **Point-in-time assessment** - Compliance is ongoing; re-audit after major changes
- **Best-effort detection** - May not catch every edge case
- **Framework versions** - Based on current regulations; may need updates as laws change

## Contributing

To improve this skill:

1. Update checklists in `reference/` as regulations evolve
2. Add new frameworks by creating new reference files
3. Improve detection logic in `detection-criteria.md`
4. Enhance report templates in `templates/`

## Version

**Version:** 1.0.0
**Last Updated:** December 2024
**Frameworks:** GDPR (2016/679), HIPAA (2023), PCI-DSS (v4.0), CCPA/CPRA (2023), SOC 2 (2017 TSC)

## Resources

- [GDPR Official Text](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- [HIPAA Information](https://www.hhs.gov/hipaa/)
- [PCI Security Standards](https://www.pcisecuritystandards.org/)
- [California Privacy Protection Agency](https://cppa.ca.gov/)
- [AICPA SOC 2](https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/sorhome)

## Support

For issues or questions:
1. Check the `examples.md` file for sample audit reports
2. Review `detection-criteria.md` for framework applicability logic
3. Consult the framework-specific checklists in `reference/`

## License

This skill is provided as-is for use with Claude Code. Compliance with regulations is ultimately your legal responsibility. Always consult with qualified legal counsel for compliance decisions.

## Acknowledgments

Built using:
- Claude Code Skills SDK documentation
- Official regulatory frameworks and guidance
- Industry best practices and standards

---

**Made with ❤️ for developers building compliant software**
