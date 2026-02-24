---
name: token-efficient-coder
description: Mandatory guide and guidelines for generating, modifying, and refactoring code, ensuring the lowest possible token consumption and ultra-precise responses. Use whenever writing or editing code.
---

# Token Efficient Coder

## Overview

This skill establishes the definitive rules for the AI agent to minimize input (context) and output (generation) token usage when working with code. It maximizes efficiency and prevents exceeding token limits by making surgical edits and avoiding redundant explanations.

## 1. Surgical File Modification

- **NEVER use `write_to_file` to edit:** If the file already exists, exclusively use `replace_file_content` or `multi_replace_file_content`.
- **Exact and Minimal Match:** In `TargetContent`, include only the strictly necessary lines to make a unique match. In `ReplacementContent`, include only the new code. Do not include entire functions if only one line changes.
- **Avoid Context Over-reading:** If a file is huge (thousands of lines), use terminal tools like `grep_search` to find line numbers, and then do a `view_file` only of that range (`StartLine`, `EndLine`). Do not read the entire file unless inevitable.

## 2. Strict Code Generation

- **Zero Unnecessary Explanations:** Omit introductions like "Sure, here is the code", "I'm going to modify the file", or post-code explanations unless requested by the user. Be an efficient robot.
- **Use of Placeholders:** If asked to show example code or a preview of a large class, DO NOT print the complete code. Use `// ... existing code ...` or `# ...` in the parts that did not change.
- **Minimal Comments:** Do not generate comments in the code unless the logic is cryptic. The code must be clean and self-descriptive through naming choices (short but clear names).

## 3. Optimization of Created Code

- **Return Early (Guard Clauses):** Avoid excessive nesting levels (indentation); reduce the complexity of the generated code.
- **Refactoring Delegated to the Console:** If a task requires finding and replacing the same variable across 50 files, DO NOT use LLM tools file by file. Instead, use `run_command` with predictable and fast command-line tools or mini-scripts (e.g., `sed`, `rg -l | xargs sed`, brief python scripts) to make modifications en masse without consuming output tokens by editing documents.
- **Concise Syntax:** Use language features that allow it (e.g., list comprehensions in Python, arrow functions, and simple ternaries in JS/TS).

## 4. Agent Responses (Communication with the User)

- Limit descriptive responses. If you fixed a bug, simply reply with "Bug fixed in [function/file]" and nothing more, unless the error was architectural.
- If you need to ask a question, ask it directly. Do not add unnecessary "context" or "reflections" in the user-visible output (use your internal `thought` block to think).

## When to Use This Skill

This skill is the standard stance and must be CONSTANTLY taken into account in every interaction where there is code writing or editing to save resources and accelerate response times.
