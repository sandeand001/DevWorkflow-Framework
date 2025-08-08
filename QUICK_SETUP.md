# Quick Setup: DevWorkflow Agent System

> **30-second setup for AI-powered development workflow**

## Prerequisites

- Git installed
- AI assistant (GitHub Copilot, ChatGPT, Claude, etc.)

## 30-Second Setup

### Add to Any Project

```bash
# Add as submodule (recommended)
git submodule add https://github.com/sandeand001/DevWorkflow-Framework.git devworkflow

# Or copy directly
cp -r /path/to/DevWorkflow-Framework ./devworkflow
```

> **Note**: This framework provides AI instruction files, not executable code.

### Start Using Agents

In your AI chat (GitHub Copilot, Claude, etc.):

1. **Initialize**: "Please follow the agent system described in `devworkflow/AGENT_SYSTEM.md`"

2. **Use agents**: 
   - `@docwriter update the README.md`
   - `@explorer analyze this codebase`
   - `@reviewer check this code for issues`
   - `@coder implement a new feature`
   - `@tester design tests for this feature`
   - `@fixer debug this authentication error`
   - `@refactorer improve this code structure`
   - `@cleaner remove dead code and duplicates`
   - `@troubleshooter investigate this performance issue`

3. **Switch agents**: Just use a different `@agent` command

## Available Agents

| Agent | Purpose | Example |
|-------|---------|---------|
| `@docwriter` | Documentation & README | `@docwriter create API docs` |
| `@explorer` | Code architecture analysis | `@explorer map the data flow` |
| `@reviewer` | Code quality & security | `@reviewer check for vulnerabilities` |
| `@coder` | Feature implementation | `@coder build REST API endpoints` |
| `@tester` | Test strategy & coverage | `@tester design unit tests` |
| `@fixer` | Bug diagnosis & fixes | `@fixer debug login issues` |
| `@refactorer` | Code improvement | `@refactorer reduce technical debt` |
| `@cleaner` | Codebase optimization | `@cleaner eliminate duplicate functions` |
| `@troubleshooter` | Problem investigation | `@troubleshooter analyze crashes` |

## That's It!

Each agent has detailed instructions in `devworkflow/instructions/[agent].md`. The AI will automatically follow those specialized instructions when you use the `@agent` commands.

## Quick Verification

Test the setup:
- [ ] Try: `@explorer what is the structure of this codebase?`
- [ ] Verify the AI references the instruction files
- [ ] Switch roles: `@docwriter` → `@reviewer` → etc.

## Need More Help?

**Full documentation**: See `devworkflow/AGENT_SYSTEM.md`  
**Issues**: Check the troubleshooting section in the full docs
