# AI Agent Skills — Token Efficient Coder

A specialized repository for AI agent skills aimed at optimizing coding interactions. This repository provides the **Token Efficient Coder** skill, which establishes definitive guidelines to minimize LLM token usage (input and output) when making code modifications.

Compatible with Claude Code, GitHub Copilot, and other AI coding assistants that support skills.

## Repository

[https://github.com/artur282/Token-Efficient-Coder](https://github.com/artur282/Token-Efficient-Coder)

## Installation

### Clone the Repository

To get started, clone the repository to your local machine:

```bash
git clone https://github.com/artur282/Token-Efficient-Coder.git
cd Token-Efficient-Coder
```

### Manual Installation

Copy the skill to your project's skills directory:

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
3. Keep token efficiency in mind!

## License

MIT
