# AI-DLC for Claude Code

**AI-DLC (AI-Driven Development Life Cycle)** — an adaptive software development methodology, ported to [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

Originally a [Kiro Power](https://github.com/aws-samples/sample-aidlc-kiro-power) by the AI-DLC team at AWS Samples, this project adapts the methodology for use with Claude Code's project conventions (`CLAUDE.md` + custom slash commands).

## What is AI-DLC?

AI-DLC is a comprehensive, adaptive software development lifecycle that intelligently tailors workflow stages to project complexity and requirements. It guides teams through three phases:

- **🔵 INCEPTION** — Planning & Architecture: workspace detection, reverse engineering, requirements analysis, user stories, workflow planning, application design, units generation
- **🟢 CONSTRUCTION** — Design, Implementation & Test: functional design, NFR requirements/design, infrastructure design, code generation, build & test
- **🟡 OPERATIONS** — Deployment & Monitoring *(placeholder for future expansion)*

### Key Principles

- **Adaptive Execution** — only runs stages that add value to your specific project
- **Quality Gates** — built-in checkpoints ensure quality and stakeholder alignment
- **Complete Documentation** — maintains full audit trail of decisions and rationale
- **Risk-Based Approach** — complex projects get full treatment, simple changes stay efficient

## Installation

### Option 1: Use as Project Template

```bash
# Clone this repo as your new project
git clone https://github.com/w0yne/aidlc-claude-code.git my-project
cd my-project
rm -rf .git && git init  # Fresh git history
```

### Option 2: Add to Existing Project

```bash
# Copy AI-DLC files into your project
cp CLAUDE.md /path/to/your/project/
cp -r .claude /path/to/your/project/
cp -r aidlc-workflows /path/to/your/project/
```

## Usage

### With the Custom Slash Command

In Claude Code, use the `/aidlc` command:

```
/aidlc Build a REST API for a todo application with user authentication
```

### By Asking Directly

Just describe your development task — the methodology is loaded from `CLAUDE.md` automatically:

```
I need to add a payment processing module to the existing e-commerce system
```

## Project Structure

```
├── CLAUDE.md                    # Core methodology (auto-loaded by Claude Code)
├── .claude/
│   └── commands/
│       └── aidlc.md             # /aidlc slash command
├── aidlc-workflows/
│   ├── common/                  # Cross-phase guidelines
│   │   ├── content-validation.md
│   │   ├── depth-levels.md
│   │   ├── error-handling.md
│   │   ├── overconfidence-prevention.md
│   │   ├── process-overview.md
│   │   ├── question-format-guide.md
│   │   ├── session-continuity.md
│   │   ├── terminology.md
│   │   ├── welcome-message.md
│   │   └── workflow-changes.md
│   ├── inception/               # INCEPTION phase workflows
│   │   ├── workspace-detection.md
│   │   ├── reverse-engineering.md
│   │   ├── requirements-analysis.md
│   │   ├── user-stories.md
│   │   ├── workflow-planning.md
│   │   ├── application-design.md
│   │   └── units-generation.md
│   ├── construction/            # CONSTRUCTION phase workflows
│   │   ├── functional-design.md
│   │   ├── nfr-requirements.md
│   │   ├── nfr-design.md
│   │   ├── infrastructure-design.md
│   │   ├── code-generation.md
│   │   └── build-and-test.md
│   └── operations/              # OPERATIONS phase (placeholder)
│       └── operations.md
```

## Generated Artifacts

When you run AI-DLC, it creates documentation in `aidlc-docs/`:

```
aidlc-docs/
├── aidlc-state.md              # Workflow state tracking
├── audit.md                     # Complete audit trail
├── inception/                   # Planning phase artifacts
│   ├── requirements/
│   ├── user-stories/
│   ├── application-design/
│   └── plans/
└── construction/                # Implementation phase artifacts
    ├── [unit-name]/
    │   ├── functional-design/
    │   ├── nfr-requirements/
    │   ├── nfr-design/
    │   └── code/
    ├── build-and-test/
    └── plans/
```

## Differences from Kiro Power

| Aspect | Kiro Power | Claude Code |
|--------|-----------|-------------|
| Instructions | POWER.md + steering/ | CLAUDE.md |
| Activation | Powers panel | `/aidlc` slash command |
| File reading | `readFile` tool | Native file access |
| Config path | `.kiro/` or `.amazonq/` | `aidlc-workflows/` |
| Workflow files | Loaded on-demand via tool | Read naturally by Claude |

The methodology itself is **identical** — only the delivery mechanism changed.

## Credits

- **Original**: [aws-samples/sample-aidlc-kiro-power](https://github.com/aws-samples/sample-aidlc-kiro-power) by the AI-DLC Team
- **Ported by**: Claude (AI assistant) for use with Claude Code

## License

MIT-0 — see [LICENSE](LICENSE)
