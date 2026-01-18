---
name: post-work-analysis
description: After completing a complex debugging or development task, analyze root causes and create/update skill documents to archive lessons learned for future reference.
---

# Post-Work Analysis and Skill Archiving

After completing a task involving significant debugging, research, or problem-solving, follow this workflow to capture and preserve the knowledge gained.

## When to Apply

Use this workflow when:
- You solved a non-trivial bug or issue
- You discovered root causes through investigation
- The solution involved multiple iterations or approaches
- The knowledge would be valuable for similar future problems

## Workflow Steps

### 1. Identify the Direct Cause
Summarize what directly caused the problem:
```
Direct Cause: [One-line description]
Example: "Head colliders were too large, blocking hair from falling"
```

### 2. Analyze Root Causes
Go deeper - why does this problem exist? Consider:
- **Design flaws**: Is this a common architectural issue?
- **Tool/platform limitations**: Known bugs or missing features?
- **Human factors**: Common mistakes during development?
- **Documentation gaps**: Missing or unclear documentation?

Use web search if needed to validate hypotheses and find supporting evidence.

### 3. Document in Skill Format

Create or update a skill file at `.agent/skills/<topic>/SKILL.md`:

```markdown
---
name: [skill-name]
description: [Brief description of what this skill covers]
---

# [Title]

## Symptoms
- [Observable problem 1]
- [Observable problem 2]

## Root Causes
### Cause 1: [Name]
- **Problem**: [Description]
- **Why it happens**: [Root cause analysis]
- **Diagnosis**: [How to confirm]
- **Solution**: [How to fix]

### Cause 2: [Name]
...

## Code Solutions
[Reusable code snippets]

## Key Learnings
- [Bullet point lessons]
```

### 4. Clean Up Debug Code
Remove temporary debugging code from the codebase, keeping only:
- The actual fix
- Useful diagnostic logs (with clear prefixes)

### 5. Summarize to User
Report findings to user including:
- What was fixed
- Root cause summary
- Where knowledge is archived
- Any remaining known issues

## Example Application

See the VRM physics debugging session that led to:
- **Direct cause**: Oversized head colliders
- **Root causes**: Model scaling inconsistency, Unity export bugs, lack of visual feedback during creation
- **Skill created**: `.agent/skills/vrm-physics/SKILL.md`

## Benefits

- **Knowledge preservation**: Insights don't get lost after conversation ends
- **Faster future debugging**: Can reference documented solutions
- **Pattern recognition**: Related issues become easier to identify
- **Team sharing**: Skills can be shared across projects
