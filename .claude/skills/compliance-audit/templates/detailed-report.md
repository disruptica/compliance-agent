# Detailed Technical Report Template

Use this template to generate detailed technical compliance reports for specific frameworks.

---

# [Framework Name] Detailed Compliance Report

**Project:** [Project Name]
**Audit Date:** [Date]
**Framework Version:** [e.g., GDPR 2016/679, PCI-DSS v4.0, SOC 2 2017]
**Compliance Score:** [X]%

---

## Executive Overview

**Overall Status:** [Summary paragraph]

**Key Findings:**
- ✓ [#] requirements met
- ⚠️ [#] requirements partially met
- ✗ [#] requirements not met

---

## Requirement-by-Requirement Analysis

### [Requirement Category 1]

#### [Requirement ID]: [Requirement Title]

**Status:** [✓ Met / ⚠️ Partial / ✗ Not Met]
**Severity:** [Critical / High / Medium / Low]
**Regulation Reference:** [Article/Section number]

**Requirement:**
[What the regulation requires]

**Current Implementation:**
[What currently exists in the codebase]

**Findings:**
- **Location:** [File paths, line numbers, or "Not found"]
- **Assessment:** [Detailed analysis of current state]
- **Gaps:** [What's missing or insufficient]

**Evidence:**
```[language]
[Relevant code snippets if applicable]
```
or
- Database: [Table/column details]
- Configuration: [Config file details]
- Not implemented: [Explanation]

**Recommendations:**
1. [Specific action to take]
2. [Additional action]
3. [Implementation notes]

**Suggested Implementation Approach:**
[Step-by-step guidance on how to implement, without writing full code]

**Estimated Effort:** [X hours/days]
**Priority:** [Critical/High/Medium/Low]
**Depends On:** [Other requirements if applicable]

---

#### [Next Requirement]
...

---

## Category Summary Tables

### [Category 1 Name]

| Requirement | Status | Severity | Effort | Priority |
|------------|--------|----------|--------|----------|
| [Req ID] [Title] | ✓/⚠️/✗ | [Level] | [Time] | [Priority] |
| ... | | | | |

**Category Compliance:** [X]% ([Y] of [Z] requirements met)

---

## Implementation Checklist

Use this checklist to track remediation:

### Critical Items
- [ ] [Requirement ID]: [Brief description] - [Framework reference]
- [ ] [Next item]

### High Priority Items
- [ ] [Requirement ID]: [Brief description] - [Framework reference]
- [ ] [Next item]

### Medium Priority Items
- [ ] [Requirement ID]: [Brief description] - [Framework reference]
- [ ] [Next item]

### Low Priority Items
- [ ] [Requirement ID]: [Brief description] - [Framework reference]
- [ ] [Next item]

---

## Technical Implementation Guide

### Backend Changes Required

**Critical:**
1. [Specific change needed]
   - **Files to modify:** [List]
   - **Approach:** [Description]
   - **Testing:** [How to verify]

2. [Next change]
   ...

**High Priority:**
1. [Change needed]
   ...

### Frontend Changes Required

**Critical:**
1. [Specific change needed]
   - **Components to modify:** [List]
   - **Approach:** [Description]
   - **Testing:** [How to verify]

### Database Changes Required

**Critical:**
1. [Migration or schema change]
   - **Tables affected:** [List]
   - **Approach:** [Description]
   - **Rollback plan:** [Description]

### Infrastructure Changes Required

**Critical:**
1. [Infrastructure change]
   - **Services affected:** [List]
   - **Approach:** [Description]
   - **Downtime:** [Estimate]

### Documentation Required

1. [Policy or document needed]
   - **Purpose:** [Why it's needed]
   - **Key sections:** [What to include]
   - **Owner:** [Who should maintain it]

---

## Dependencies and Prerequisites

Before implementing compliance measures, ensure:

1. [Prerequisite 1]
2. [Prerequisite 2]
3. [Prerequisite 3]

---

## Testing and Validation

### Compliance Testing Checklist

- [ ] [Test case 1 for requirement X]
- [ ] [Test case 2]
- [ ] [Test case 3]

### Recommended Testing Approach

1. **Unit Tests:** [What to test]
2. **Integration Tests:** [What to test]
3. **Manual Verification:** [What to check]
4. **External Audit:** [When to engage third party]

---

## Risk Assessment

### Risks if Not Addressed

| Risk | Likelihood | Impact | Mitigation Priority |
|------|-----------|---------|---------------------|
| [Risk 1] | High/Med/Low | High/Med/Low | Critical/High/Med/Low |
| [Risk 2] | | | |

### Potential Consequences

**Legal Risks:**
- [Potential fines or penalties]
- [Regulatory actions]

**Business Risks:**
- [Customer trust impact]
- [Market access issues]

**Technical Risks:**
- [Security vulnerabilities]
- [Data breach potential]

---

## Resources and References

### Official Documentation
- [Link to official regulation text]
- [Link to regulatory guidance]

### Implementation Guides
- [Relevant implementation resources]

### Tools and Services
- [Recommended tools for compliance]
- [Third-party services that can help]

### Similar Projects
- [Examples of compliant implementations]

---

## Next Steps for This Framework

1. **Immediate (This Week):**
   - [Action item]
   - [Action item]

2. **Short Term (This Month):**
   - [Action item]
   - [Action item]

3. **Medium Term (This Quarter):**
   - [Action item]
   - [Action item]

4. **Ongoing:**
   - [Continuous compliance activities]

---

## Appendix

### A. Code Locations Summary

| Feature/Requirement | Current Location | Missing Components |
|---------------------|-----------------|-------------------|
| [Feature 1] | [File paths] | [What's missing] |
| [Feature 2] | Not found | [What needs to be built] |

### B. Third-Party Services Requiring Review

| Service | Purpose | Compliance Status | Action Needed |
|---------|---------|------------------|---------------|
| [Service 1] | [What it does] | [Compliant/Unknown/Non-compliant] | [Next steps] |

### C. Documentation Inventory

| Document | Status | Last Updated | Location | Action Needed |
|----------|--------|--------------|----------|---------------|
| Privacy Policy | ✓/⚠️/✗ | [Date] | [URL/Path] | [Update needed?] |
| Terms of Service | ✓/⚠️/✗ | [Date] | [URL/Path] | [Update needed?] |

---

**Report Generated:** [Date and Time]
**Auditor:** Claude Code Compliance Skill
**Report Version:** 1.0

---

*This detailed report should be used in conjunction with the executive summary. For legal compliance advice specific to your situation, please consult with qualified legal counsel.*
