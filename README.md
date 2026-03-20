# AI-DLC Agent Skill

**AI-DLC (AI-Driven Development Life Cycle)** — an adaptive software development methodology, packaged as an [Agent Skill](https://agentskills.io) for Claude Code, Cursor, Gemini CLI, and other compatible tools.

Originally a [Kiro Power](https://github.com/aws-samples/sample-aidlc-kiro-power) by the AI-DLC team at AWS Samples, ported to the open Agent Skills standard.

## What is AI-DLC?

An adaptive development lifecycle that intelligently tailors workflow stages to project complexity:

- **🔵 INCEPTION** — Planning & Architecture: workspace detection, reverse engineering, requirements analysis, user stories, workflow planning, application design, units generation
- **🟢 CONSTRUCTION** — Design, Implementation & Test: functional design, NFR requirements/design, infrastructure design, code generation, build & test
- **🟡 OPERATIONS** — Deployment & Monitoring *(placeholder for future expansion)*

### Key Principles

- **Adaptive Execution** — only runs stages that add value
- **Quality Gates** — built-in checkpoints ensure alignment
- **Complete Documentation** — full audit trail of decisions
- **Risk-Based** — complex projects get full treatment, simple changes stay efficient

## Installation

### Claude Code

```bash
# Install from GitHub
npx skills add w0yne/aidlc-claude-code

# Or manually copy to personal skills
cp -r aidlc ~/.claude/skills/

# Or add to a project
cp -r aidlc .claude/skills/
```

After installing, invoke with `/aidlc` or just describe a development task — Claude will activate the skill automatically when relevant.

### Other Compatible Agents

This skill follows the [Agent Skills](https://agentskills.io) open standard and works with:
- Cursor
- Gemini CLI
- OpenCode
- Junie (JetBrains)
- VS Code Copilot
- And [more](https://agentskills.io)

Copy the `aidlc/` directory to your agent's skills location.

## Skill Structure

```
aidlc/
├── SKILL.md                     # Skill metadata + core instructions
└── references/                  # Detailed workflow files (loaded on demand)
    ├── core-workflow.md          # Complete orchestration logic
    ├── common/                   # Cross-phase guidelines
    │   ├── content-validation.md
    │   ├── depth-levels.md
    │   ├── error-handling.md
    │   ├── overconfidence-prevention.md
    │   ├── process-overview.md
    │   ├── question-format-guide.md
    │   ├── session-continuity.md
    │   ├── terminology.md
    │   ├── welcome-message.md
    │   └── workflow-changes.md
    ├── inception/                # INCEPTION phase workflows
    │   ├── workspace-detection.md
    │   ├── reverse-engineering.md
    │   ├── requirements-analysis.md
    │   ├── user-stories.md
    │   ├── workflow-planning.md
    │   ├── application-design.md
    │   └── units-generation.md
    ├── construction/             # CONSTRUCTION phase workflows
    │   ├── functional-design.md
    │   ├── nfr-requirements.md
    │   ├── nfr-design.md
    │   ├── infrastructure-design.md
    │   ├── code-generation.md
    │   └── build-and-test.md
    └── operations/               # OPERATIONS phase (placeholder)
        └── operations.md
```

## Usage Examples

```
/aidlc Build a REST API for a todo application with user authentication

/aidlc Add payment processing to the existing e-commerce system

/aidlc Refactor the monolith into microservices
```

## Credits

- **Original**: [aws-samples/sample-aidlc-kiro-power](https://github.com/aws-samples/sample-aidlc-kiro-power) by the AI-DLC Team
- **Ported by**: Stev Wayne

## License

MIT-0 — see [LICENSE](LICENSE)
