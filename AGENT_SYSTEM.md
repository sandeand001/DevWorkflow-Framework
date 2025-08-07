# DevWorkflow Agent Role System

## Overview

The DevWorkflow Framework includes a specialized AI agent role-switching system that allows you to interact with AI assistants (like GitHub Copilot) using specific role-based commands. Each agent has detailed instructions and specialized knowledge for different development tasks.

> **Note**: This is an instruction-based system that works with any AI assistant. The framework provides structured roles and guidelines rather than executable code.

## Prerequisites

- Git (for submodule management)
- AI assistant that can read instruction files (GitHub Copilot, ChatGPT, etc.)
- Basic understanding of role-based AI prompting

## How It Works

When you use `@agent` commands in your AI chat, the AI assistant will read the corresponding instruction file and adopt that specialized role until you switch to a different agent or explicitly end the session.

## Agent Commands

| Command | Role | Instruction File | Purpose |
|---------|------|------------------|---------|
| `@docwriter` | Technical Documentation Specialist | `instructions/docwriter.md` | README creation, API docs, technical writing |
| `@explorer` | Codebase Architecture Analyst | `instructions/explorer.md` | Code exploration, architecture mapping |
| `@fixer` | Bug Diagnosis & Resolution | `instructions/fixer.md` | Issue diagnosis, minimal surgical fixes |
| `@refactorer` | Code Quality Improvement | `instructions/refactorer.md` | Structure improvement, debt reduction |
| `@reviewer` | Code Quality & Standards | `instructions/reviewer.md` | Code review, security, standards compliance |
| `@tester` | Test Strategy & Implementation | `instructions/tester.md` | Test design, coverage analysis |
| `@troubleshooter` | Problem Investigation | `instructions/troubleshooter.md` | Root cause analysis, systematic debugging |

## Usage Examples

### Documentation Tasks
```
@docwriter update the README.md to include installation instructions
@docwriter create API documentation for the user service
@docwriter review and improve the project documentation structure
```

### Code Exploration
```
@explorer analyze the architecture of this codebase
@explorer identify the main entry points and data flow
@explorer map the dependencies and external interfaces
```

### Bug Fixing
```
@fixer diagnose why the authentication is failing
@fixer the user registration endpoint returns 500 errors
@fixer investigate the memory leak in the background tasks
```

### Code Review
```
@reviewer analyze this pull request for security issues
@reviewer check the code quality and standards compliance
@reviewer assess the performance implications of these changes
```

### Testing
```
@tester design a test strategy for the payment module
@tester analyze current test coverage and identify gaps
@tester recommend testing frameworks for this project
```

### Refactoring
```
@refactorer identify opportunities to improve code structure
@refactorer suggest ways to reduce technical debt
@refactorer analyze this component for potential improvements
```

### Troubleshooting
```
@troubleshooter investigate why the deployment keeps failing
@troubleshooter analyze the performance degradation in production
@troubleshooter diagnose the intermittent database connection issues
```

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

### Role Persistence
- Once you use an `@agent` command, the AI stays in that role
- The agent role continues until you use a different `@agent` command
- Non-prefixed messages are handled by the current active agent

### Role Switching
```
@docwriter create API documentation    # Switches to docwriter role
Can you also add examples?            # Still docwriter
@reviewer check this code             # Switches to reviewer role  
What about security concerns?         # Still reviewer
```

### Role Ending
```
@docwriter update the README
Actually, nevermind, go back to normal mode    # Explicitly end agent role
```

## Integration with AI Assistants

### GitHub Copilot Chat
1. Start a new chat session
2. Reference this document: "Please follow the agent system in devworkflow/AGENT_SYSTEM.md"
3. Use `@agent` commands as needed

### Other AI Assistants
1. Provide context about the agent system
2. Reference the instruction files in `devworkflow/instructions/`
3. Use the `@agent` command pattern

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

### Be Specific
```
# Good
@docwriter create installation instructions for Windows users with Node.js 18+

# Less Good  
@docwriter help with docs
```

### Context Matters
```
# Provide context
@fixer the login endpoint returns 401 errors even with valid credentials, 
started happening after the JWT library update

# Better than just
@fixer login broken
```

### Chain Commands
```
@explorer analyze this microservice architecture
# After exploration results...
@reviewer assess the security implications of this service design
# After review...
@tester recommend integration testing strategies for these services
```

## Advanced Usage

### Custom Instructions
You can modify the instruction files in `devworkflow/instructions/` to customize agent behavior for your specific project needs.

### Report Generation
Some agents generate reports in `devworkflow/reports/`. Review these for detailed analysis and recommendations.

### Integration with Development Workflow
- Use `@reviewer` before merging pull requests
- Use `@tester` when adding new features
- Use `@explorer` when onboarding new team members
- Use `@troubleshooter` for production issues

## Quick Start Checklist

For teams getting started with the agent system:

- [ ] Add DevWorkflow Framework to your project (git submodule or copy)
- [ ] Reference `AGENT_SYSTEM.md` in your AI chat sessions
- [ ] Test with a simple command like `@explorer analyze this codebase`
- [ ] Update your project README to mention the agent system
- [ ] Train team members on the `@agent` command patterns
- [ ] Bookmark commonly used agent combinations for your workflow

## Troubleshooting the Agent System

### Agent Not Following Instructions
1. Verify the instruction file exists and is readable
2. Re-reference this document in your chat
3. Be explicit: "Follow the instructions in devworkflow/instructions/docwriter.md"

### Role Not Switching
1. Use clear `@agent` commands
2. Verify agent name spelling
3. Start a new chat session if needed

### Missing Context
1. Provide project-specific context when starting
2. Reference relevant files and documentation
3. Use specific, actionable requests

---

**Version**: 2.0.0  
**Last Updated**: August 7, 2025  
**Framework**: DevWorkflow-Framework  
**License**: MIT
