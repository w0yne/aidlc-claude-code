# AI-DLC Agent Skill

[AI-DLC (AI-Driven Development Life Cycle)](https://github.com/awslabs/aidlc-workflows) adaptive workflow, packaged as an [Agent Skill](https://agentskills.io) for Claude Code and other compatible tools.

## Installation

### Claude Code

```bash
# Copy to personal skills (available across all projects)
cp -r aidlc ~/.claude/skills/

# Or add to a specific project
cp -r aidlc .claude/skills/
```

After installing, invoke with `/aidlc` or describe a development task — Claude will activate the skill automatically when relevant.

### Other Compatible Agents

This skill follows the [Agent Skills](https://agentskills.io) open standard and works with compatible agents (Cursor, Gemini CLI, OpenCode, etc.). Copy the `aidlc/` directory to your agent's skills location.

## Source

All workflow content is from [awslabs/aidlc-workflows](https://github.com/awslabs/aidlc-workflows). See the original repo for full documentation, methodology details, and platform-specific setup instructions.

## License

Apache-2.0 — see [LICENSE](LICENSE)
