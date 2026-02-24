# AI Agent Skills — Token Efficient Coder

A specialized repository for AI agent skills aimed at optimizing coding interactions. This particular repository currently offers the **Token Efficient Coder** skill, which establishes definitive guidelines to minimize LLM token usage (input and output) when making code modifications.

Compatible with Claude Code, GitHub Copilot, and other AI coding assistants.

## Installation

### Add specific skill

```bash
# Add the token-efficient-coder skill
npx skills add token-efficient-coder/skills
```
*(If published via `npx skills`)* 

### Manual Installation

Copy to your project's skills directory:

```bash
# Claude Code / local directory
cp -r skills/* .agents/skills/
# or
cp -r skills/* .claude/skills/

# Global GitHub Copilot
cp -r skills/* ~/.copilot/skills/
```

## Available Skills

| Skill | Description | Triggers |
|-------|-------------|----------|
| **[token-efficient-coder](skills/token-efficient-coder/SKILL.md)** | Mandatory guidelines for generating, modifying, and refactoring code to ensure low token consumption. | code modification, refactoring, code editing, token efficient |

## Contributing

1. Create a new directory within `skills/<skill-name>/`.
2. Write a `SKILL.md` following the provided YAML frontmatter.
3. Keep tokens in mind!

## License

MIT
