# DevWorkflow Agent Role System

## Overview

The DevWorkflow Framework includes a specialized AI agent role-switching system that allows you to interact with AI assistants (like GitHub Copilot) using specific role-based commands. Each agent has detailed instructions and specialized knowledge for different development tasks.

> **Note**: This is an instruction-based system that works with any AI assistant. The framework provides structured roles and guidelines rather than executable code.

## 🔍 **IMPORTANT: Complete Role Understanding Required**

**When an AI assistant adopts an agent role, it must:**

1. **📖 Read the Entire Agent Instruction File** - Review all sections, guidelines, and behavioral specifications
2. **📝 Follow Report Generation Requirements** - Each agent role includes specific report creation responsibilities
3. **✅ Apply Quality Standards** - Adhere to all quality checkpoints and validation protocols outlined in the instructions
4. **🎯 Maintain Role Consistency** - Stay in character and follow the specialized expertise defined for that agent

**Key Requirement**: All agents must generate standardized reports using templates from the `reports/` directory as specified in their individual instruction files.

## Prerequisites

- Git (for submodule management)
- AI assistant that can read instruction files (GitHub Copilot, ChatGPT, etc.)
- Basic understanding of role-based AI prompting

## How It Works

When you use `@agent` commands in your AI chat, the AI assistant will:

1. **📚 Read the Complete Instruction File** - The AI must review the entire corresponding instruction file (e.g., `instructions/explorer.md`)
2. **🎯 Adopt the Specialized Role** - Take on the full behavioral specification and expertise defined in the instructions
3. **📝 Follow Report Requirements** - Generate appropriate reports using standardized templates from `reports/` directory
4. **✅ Apply Quality Standards** - Implement all quality checkpoints and validation protocols specified in the role
5. **🔄 Maintain Role Persistence** - Continue in that specialized role until explicitly switched or ended

> **Critical**: Each agent role includes specific deliverables and report generation requirements. The AI must review all sections of the instruction file to understand the complete scope of responsibilities.

## Agent Commands & Report Outputs

| Command | Role | Instruction File | Purpose | **Report Output** |
|---------|------|------------------|---------|-------------------|
| `@docwriter` | Technical Documentation Specialist | `instructions/docwriter.md` | README creation, API docs, technical writing | **documentation/** reports |
| `@explorer` | Codebase Architecture Analyst | `instructions/explorer.md` | Code exploration, architecture mapping | **exploration/** reports |
| `@fixer` | Bug Diagnosis & Resolution | `instructions/fixer.md` | Issue diagnosis, minimal surgical fixes | **fixes/** reports |
| `@refactorer` | Code Quality Improvement | `instructions/refactorer.md` | Structure improvement, debt reduction | **refactoring/** reports |
| `@reviewer` | Code Quality & Standards | `instructions/reviewer.md` | Code review, security, standards compliance | **code-reviews/** reports |
| `@tester` | Test Strategy & Implementation | `instructions/tester.md` | Test design, coverage analysis | **testing/** reports |
| `@troubleshooter` | Problem Investigation | `instructions/troubleshooter.md` | Root cause analysis, systematic debugging | **troubleshooting/** reports |

## Usage Examples

### Documentation Tasks
```
@docwriter update the README.md to include installation instructions
@docwriter create API documentation for the user service
@docwriter review and improve the project documentation structure
```
**Expected Output**: Comprehensive documentation + report in `reports/documentation/`

### Code Exploration
```
@explorer analyze the architecture of this codebase
@explorer identify the main entry points and data flow
@explorer map the dependencies and external interfaces
```
**Expected Output**: Architectural analysis + detailed report in `reports/exploration/`

### Bug Fixing
```
@fixer diagnose why the authentication is failing
@fixer the user registration endpoint returns 500 errors
@fixer investigate the memory leak in the background tasks
```
**Expected Output**: Targeted fixes + resolution documentation in `reports/fixes/`

### Code Review
```
@reviewer analyze this pull request for security issues
@reviewer check the code quality and standards compliance
@reviewer assess the performance implications of these changes
```
**Expected Output**: Comprehensive review + evaluation report in `reports/code-reviews/`

### Testing
```
@tester design a test strategy for the payment module
@tester analyze current test coverage and identify gaps
@tester recommend testing frameworks for this project
```
**Expected Output**: Test strategy + coverage analysis in `reports/testing/`

### Refactoring
```
@refactorer identify opportunities to improve code structure
@refactorer suggest ways to reduce technical debt
@refactorer analyze this component for potential improvements
```
**Expected Output**: Refactoring plan + improvement documentation in `reports/refactoring/`

### Troubleshooting
```
@troubleshooter investigate why the deployment keeps failing
@troubleshooter analyze the performance degradation in production
@troubleshooter diagnose the intermittent database connection issues
```
**Expected Output**: Root cause analysis + resolution guide in `reports/troubleshooting/`

> **Important**: Each example above includes both the immediate response AND the requirement to generate a standardized report using the appropriate template from the `reports/` directory.

## Setup Instructions

### For New Projects

1. **Copy the Framework**
   ```bash
   # Option 1: Git Submodule (Recommended)
   git submodule add https://github.com/sandeand001/DevWorkflow-Framework.git devworkflow

   # Option 2: Direct Copy
   cp -r /path/to/DevWorkflow-Framework ./devworkflow
   ```

2. **Reference in Your Project**
   - Add a section to your project's README pointing to the agent system
   - Include the `devworkflow/` directory in your project structure

3. **AI Assistant Configuration**
   - Inform your AI assistant about the agent system location
   - Reference this file when starting a new chat session

### For Existing Projects

1. **Add as Submodule**
   ```bash
   git submodule add https://github.com/sandeand001/DevWorkflow-Framework.git devworkflow
   git submodule update --init --recursive
   ```

2. **Update Project Documentation**
   ```markdown
   ## Development Workflow

   This project uses the DevWorkflow Framework for specialized AI assistance.
   See `devworkflow/AGENT_SYSTEM.md` for available agent commands.
   ```

### Keeping the Framework Updated

```bash
# Update submodule to latest version
git submodule update --remote devworkflow
```

## Agent Behavior Rules

### 📋 **Complete Role Adoption Requirements**

When an AI assistant activates an agent role, it must:

1. **📖 Review Entire Instruction File**: Read all sections, guidelines, behavioral specifications, and requirements
2. **🎯 Understand Role Scope**: Comprehend the agent's expertise, limitations, and deliverable expectations  
3. **📝 Follow Report Generation**: Create standardized reports using appropriate templates from `reports/` directory
4. **✅ Apply Quality Standards**: Implement all quality checkpoints and validation protocols specified
5. **🔄 Maintain Consistency**: Stay in character throughout the interaction

### Role Persistence
- Once you use an `@agent` command, the AI stays in that role and **must follow ALL role requirements**
- The agent role continues until you use a different `@agent` command
- Non-prefixed messages are handled by the current active agent **including report generation responsibilities**

### Role Switching
```
@docwriter create API documentation    # Switches to docwriter role + report requirements
Can you also add examples?            # Still docwriter (includes report generation)
@reviewer check this code             # Switches to reviewer role + report requirements  
What about security concerns?         # Still reviewer (includes report generation)
```

### Role Ending
```
@docwriter update the README
Actually, nevermind, go back to normal mode    # Explicitly end agent role
```

> **Critical Reminder**: Every agent interaction should result in both immediate assistance AND appropriate report generation using standardized templates.

## Integration with AI Assistants

### GitHub Copilot Chat
1. Start a new chat session
2. Reference this document: "Please follow the agent system in devworkflow/AGENT_SYSTEM.md"
3. **Emphasize complete role adoption**: "When using @agent commands, read the entire instruction file and follow ALL requirements including report generation"
4. Use `@agent` commands as needed

### Other AI Assistants
1. Provide context about the agent system
2. Reference the instruction files in `devworkflow/instructions/`
3. **Clarify expectations**: "Each agent role requires reading the complete instruction file and generating reports using templates"
4. Use the `@agent` command pattern

### 🎯 **AI Assistant Onboarding Checklist**

Before starting agent work, ensure the AI understands:
- [ ] Read the **entire** agent instruction file (not just summaries)
- [ ] Follow **all** behavioral specifications and guidelines
- [ ] Apply **quality standards** and validation protocols
- [ ] Maintain **role consistency** throughout the interaction
- [ ] Generate **standardized reports** using appropriate templates

## File Structure

When using this system, your project should include:

```
your-project/
├── devworkflow/                 # DevWorkflow Framework
│   ├── instructions/           # Agent instruction files
│   │   ├── docwriter.md
│   │   ├── explorer.md
│   │   ├── fixer.md
│   │   ├── refactorer.md
│   │   ├── reviewer.md
│   │   ├── tester.md
│   │   └── troubleshooter.md
│   ├── reports/               # Generated reports
│   ├── AGENT_SYSTEM.md       # This file
│   └── README.md             # Framework documentation
├── src/                      # Your project code
├── README.md                 # Your project README
└── package.json             # Your project config
```

## Tips for Effective Use

### Be Specific including during Report Requirements
```
# Good - Clear task + implicit report expectation
@docwriter create installation instructions for Windows users with Node.js 18+

# Even Better - Explicit about deliverables
@docwriter create installation instructions for Windows users with Node.js 18+ and generate a documentation report

# Less Good  
@docwriter help with docs
```

### Context Matters
```
# Provide context + expect comprehensive output
@fixer the login endpoint returns 401 errors even with valid credentials, 
started happening after the JWT library update. Please investigate and create a fix report.

# Better than just
@fixer login broken
```

### Request Complete Agent Execution
```
# Comprehensive request
@explorer analyze this microservice architecture #and provide a complete exploration report without being specifically asked 

# Chain with explicit reporting
@reviewer assess the security implications of this service design #and document findings without being specifically asked
@tester recommend integration testing strategies #and create a testing report without being specifically asked
```

> **Best Practice**: Always expect both immediate assistance AND a formal report when using agent commands. AI SHOULD create reports without being specifically asked outside of the role instructions

## Advanced Usage

### Custom Instructions
You can modify the instruction files in `devworkflow/instructions/` to customize agent behavior for your specific project needs.

### Report Generation System
**Each agent generates standardized reports** in the following structure:
- **File Location**: `devworkflow/reports/[category]/YYYY-MM-DD-HH-MM_[description].md`
- **Template Source**: `devworkflow/reports/[category]/_TEMPLATE.md`
- **Quality Standards**: Built-in validation and consistency checks

**Report Categories**:
- `exploration/` - Architectural analysis and research findings (@explorer)
- `documentation/` - Technical specifications and guides (@docwriter)  
- `code-reviews/` - Quality assessments and security audits (@reviewer)
- `testing/` - Test strategies and coverage analysis (@tester)
- `fixes/` - Bug resolution documentation (@fixer)
- `refactoring/` - Code improvement plans (@refactorer)
- `troubleshooting/` - Problem diagnosis guides (@troubleshooter)

### Integration with Development Workflow
- Use `@reviewer` before merging pull requests → **generates code review report**
- Use `@tester` when adding new features → **generates test strategy report**
- Use `@explorer` when onboarding new team members → **generates architectural overview report**
- Use `@troubleshooter` for production issues → **generates diagnostic report**

> **Framework Expectation**: Every agent interaction should produce both immediate assistance and a documented report for future reference and team knowledge sharing.

## Quick Start Checklist

For teams getting started with the agent system:

- [ ] Add DevWorkflow Framework to your project (git submodule or copy)
- [ ] Reference `AGENT_SYSTEM.md` in your AI chat sessions
- [ ] Test with a simple command like `@explorer analyze this codebase`
- [ ] Update your project README to mention the agent system
- [ ] Train team members on the `@agent` command patterns
- [ ] Bookmark commonly used agent combinations for your workflow

## Troubleshooting the Agent System

### Agent Not Following Complete Instructions
1. Verify the instruction file exists and is readable
2. Re-reference this document in your chat
3. Be explicit: "Please read the ENTIRE instruction file devworkflow/instructions/docwriter.md and follow ALL requirements including report generation"
4. Confirm the AI understands both immediate tasks AND report requirements

### Role Not Generating Reports
1. Explicitly request: "Please generate the appropriate report using the template"
2. Reference the specific template: "Use the template from devworkflow/reports/exploration/_TEMPLATE.md"
3. Clarify expectations: "Each agent role includes report generation as a core requirement"

### Role Not Switching Properly
1. Use clear `@agent` commands
2. Verify agent name spelling
3. Start a new chat session if needed
4. Emphasize complete role adoption: "Read the entire instruction file for this role"

### Missing Context or Incomplete Outputs
1. Provide project-specific context when starting
2. Reference relevant files and documentation
3. Use specific, actionable requests
4. Always expect both immediate assistance AND formal documentation

---

**Version**: 2.0.0  
**Last Updated**: August 7, 2025  
**Framework**: DevWorkflow-Framework  
**License**: MIT
