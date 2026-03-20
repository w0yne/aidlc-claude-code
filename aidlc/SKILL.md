---
name: aidlc
description: >-
  AI-DLC (AI-Driven Development Life Cycle) — an adaptive software development
  methodology that intelligently tailors workflow stages to project complexity.
  Use when building new features, creating applications, refactoring systems,
  or any software development task that benefits from structured planning,
  requirements analysis, and phased execution. Invoked with /aidlc or
  automatically when a development task would benefit from structured methodology.
license: MIT-0
metadata:
  author: AI-DLC Team (AWS Samples)
  version: "1.0"
  source: https://github.com/aws-samples/sample-aidlc-kiro-power
  ported-by: w0yne
---

# AI-DLC Development Methodology

AI-DLC is a comprehensive, adaptive software development lifecycle. It analyzes your requirements, existing codebase, and complexity to determine which stages add value and which can be safely skipped.

**Key Principles:**
- **Adaptive Execution**: Only runs stages that add value
- **Quality Gates**: Built-in checkpoints ensure alignment
- **Complete Documentation**: Full audit trail in `aidlc-docs/`
- **Risk-Based Approach**: Complex projects get full treatment, simple changes stay efficient

## How to Start

1. Display the welcome message from [references/common/welcome-message.md](references/common/welcome-message.md)
2. Load common rules: [references/common/process-overview.md](references/common/process-overview.md), [references/common/content-validation.md](references/common/content-validation.md), [references/common/question-format-guide.md](references/common/question-format-guide.md)
3. Begin with **Workspace Detection** (always first)

## Three-Phase Lifecycle

### 🔵 INCEPTION PHASE — Planning & Architecture

**Purpose**: Determine WHAT to build and WHY

| Stage | When | Details |
|-------|------|---------|
| Workspace Detection | ALWAYS | [references/inception/workspace-detection.md](references/inception/workspace-detection.md) |
| Reverse Engineering | Brownfield only | [references/inception/reverse-engineering.md](references/inception/reverse-engineering.md) |
| Requirements Analysis | ALWAYS (adaptive depth) | [references/inception/requirements-analysis.md](references/inception/requirements-analysis.md) |
| User Stories | CONDITIONAL | [references/inception/user-stories.md](references/inception/user-stories.md) |
| Workflow Planning | ALWAYS | [references/inception/workflow-planning.md](references/inception/workflow-planning.md) |
| Application Design | CONDITIONAL | [references/inception/application-design.md](references/inception/application-design.md) |
| Units Generation | CONDITIONAL | [references/inception/units-generation.md](references/inception/units-generation.md) |

### 🟢 CONSTRUCTION PHASE — Design, Implementation & Test

**Purpose**: Determine HOW to build it

Per-unit loop (each unit completes design + code before next):

| Stage | When | Details |
|-------|------|---------|
| Functional Design | CONDITIONAL, per-unit | [references/construction/functional-design.md](references/construction/functional-design.md) |
| NFR Requirements | CONDITIONAL, per-unit | [references/construction/nfr-requirements.md](references/construction/nfr-requirements.md) |
| NFR Design | CONDITIONAL, per-unit | [references/construction/nfr-design.md](references/construction/nfr-design.md) |
| Infrastructure Design | CONDITIONAL, per-unit | [references/construction/infrastructure-design.md](references/construction/infrastructure-design.md) |
| Code Generation | ALWAYS, per-unit | [references/construction/code-generation.md](references/construction/code-generation.md) |
| Build and Test | ALWAYS (after all units) | [references/construction/build-and-test.md](references/construction/build-and-test.md) |

### 🟡 OPERATIONS PHASE — Placeholder

Future expansion for deployment and monitoring. See [references/operations/operations.md](references/operations/operations.md).

## Execution Rules

### For Every Stage:

1. **Read the detailed workflow file** linked in the tables above before executing that stage
2. **Log all user input** in `aidlc-docs/audit.md` with ISO 8601 timestamps — capture complete raw input, never summarize
3. **Wait for explicit user approval** before proceeding to the next stage (except Workspace Detection which auto-proceeds)
4. **Update progress** in `aidlc-docs/aidlc-state.md` after each stage

### Adaptive Assessment:

The AI intelligently assesses what stages are needed based on:
1. User's stated intent and clarity
2. Existing codebase state (brownfield vs greenfield)
3. Complexity and scope of change
4. Risk and impact assessment

### Content Validation:

Before creating ANY file, validate content per [references/common/content-validation.md](references/common/content-validation.md):
- Validate Mermaid diagram syntax
- Escape special characters
- Provide text alternatives for complex visuals

### Question Format:

All questions MUST follow the format in [references/common/question-format-guide.md](references/common/question-format-guide.md):
- Multiple choice format (A, B, C, D, E options)
- Always include "Other" as last option
- Use `[Answer]:` tags
- Place questions in dedicated `.md` files, never in chat

### Checkpoint Tracking:

- **Plan-Level**: Track execution progress with `[x]` checkboxes in plan files
- **Stage-Level**: Track overall progress in `aidlc-docs/aidlc-state.md`
- Update immediately in the SAME interaction where work is completed

### Audit Trail:

```markdown
## [Stage Name]
**Timestamp**: [ISO timestamp]
**User Input**: "[Complete raw input]"
**AI Response**: "[Response or action taken]"
**Context**: [Stage, action, or decision]
---
```

Always APPEND to `aidlc-docs/audit.md` — never overwrite.

## Conditional Stage Logic

### User Stories — Execute IF:
- New user-facing features or multiple user types
- Complex business requirements with acceptance criteria needs
- Cross-functional team collaboration required

### User Stories — Skip IF:
- Pure refactoring with zero user impact
- Simple bug fixes with clear scope
- Infrastructure-only or dev tooling changes

### Application Design — Execute IF:
- New components or services needed
- Service layer design required

### Units Generation — Execute IF:
- System needs decomposition into multiple units
- Complex system requiring structured breakdown

### NFR stages — Execute IF:
- Performance, security, or scalability requirements exist
- Tech stack selection needed

## Output Directory Structure

```
aidlc-docs/
├── aidlc-state.md              # Workflow state tracking
├── audit.md                     # Complete audit trail
├── inception/
│   ├── plans/
│   ├── reverse-engineering/     # Brownfield only
│   ├── requirements/
│   ├── user-stories/
│   └── application-design/
└── construction/
    ├── plans/
    ├── {unit-name}/
    │   ├── functional-design/
    │   ├── nfr-requirements/
    │   ├── nfr-design/
    │   ├── infrastructure-design/
    │   └── code/
    └── build-and-test/
```

## Additional References

- [Adaptive Depth Levels](references/common/depth-levels.md) — how detail adapts to complexity
- [Session Continuity](references/common/session-continuity.md) — resuming interrupted workflows
- [Error Handling](references/common/error-handling.md) — recovery procedures
- [Overconfidence Prevention](references/common/overconfidence-prevention.md) — questioning guidelines
- [Terminology](references/common/terminology.md) — glossary of AI-DLC terms
- [Workflow Changes](references/common/workflow-changes.md) — handling mid-workflow modifications
- [Core Workflow Reference](references/core-workflow.md) — complete orchestration logic with all conditional rules
