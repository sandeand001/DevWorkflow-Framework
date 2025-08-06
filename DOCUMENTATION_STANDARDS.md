# DevWorkflow-Framework Documentation Standards

**Created by**: @docwriter  
**Date**: 2025-08-06  
**Purpose**: Standardize documentation formatting across all framework components  

---

## 📋 Template Standards

### Status Indicators (Standardized)
All report templates must use these exact status indicators:

```
**Status**: 🟡 IN_PROGRESS | 🟢 COMPLETED | 🔴 BLOCKED | 🔄 NEEDS_REVIEW
```

**Status Definitions:**
- 🟡 **IN_PROGRESS**: Work is actively being done
- 🟢 **COMPLETED**: Task finished and validated
- 🔴 **BLOCKED**: Cannot proceed due to external dependencies
- 🔄 **NEEDS_REVIEW**: Ready for review/validation by another person

### Required Header Format
All report templates must include:

```markdown
# [Report Type] Report Template

**Date**: [YYYY-MM-DD]  
**[Type-specific field]**: [Value]  
**Status**: 🟡 IN_PROGRESS | 🟢 COMPLETED | 🔴 BLOCKED | 🔄 NEEDS_REVIEW  
**[Agent Field]**: AI [Agent Type] Agent  
```

### Section Header Standards
- Use `## 🎯` for objectives/goals
- Use `## 📋` for plans/overviews  
- Use `## 🔍` for analysis/findings
- Use `## 💻` for code/technical details
- Use `## ✅` for conclusions/results
- Use `## 📊` for metrics/assessments

### Agent Field Names (Standardized)
- **Code Reviews**: `**Reviewer**: AI Code Review Agent`
- **Documentation**: `**Writer**: AI Documentation Agent`
- **Exploration**: `**Explorer**: AI Code Exploration Agent`
- **Fixes**: `**Developer**: AI Fix Agent`
- **Refactoring**: `**Developer**: AI Refactoring Agent`
- **Testing**: `**Tester**: AI Testing Agent`
- **Troubleshooting**: `**Investigator**: AI Troubleshooting Agent`

---

## 🧱 Instruction File Standards

### Error Handling Requirements
All instruction files must include:
1. Reference to standardized error handling protocols
2. Agent-specific error recovery strategies
3. Clear failure reporting format
4. Graceful degradation guidelines

### File Structure Requirements
All instruction files must follow:
```markdown
# AI Agent Instructions – [Agent Name]

## 🧠 Role
[Clear role definition]

## 🎯 Primary Objectives
[Numbered list of main goals]

## [Agent-specific sections]

## ⚠️ Error Handling
[Reference to standard protocols plus agent-specific guidelines]

## 🤝 AI-Human Collaboration
[Collaboration guidelines]

## 📄 Output Format
[Expected output format and examples]
```

---

## 📝 Maintenance Guidelines

### Regular Reviews
- Monthly review of template consistency
- Quarterly update of error handling protocols
- Annual review of agent instruction completeness

### Change Management
- All template changes must be documented
- Status indicator changes require approval
- New agent types must follow established patterns

### Quality Assurance
- Validate all templates against this standard
- Check instruction files for error handling completeness
- Ensure documentation follows established patterns

---

**Approved by**: @docwriter  
**Effective Date**: 2025-08-06  
**Next Review**: 2025-09-06
