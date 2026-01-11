---
name: Continue Rules Writing Guide
globs: "**/.continue/rules/*.md"
alwaysApply: true
description: Guidelines for writing Continue rules files
---

# Continue Rules Writing Standards

Reference: https://docs.continue.dev/customize/deep-dives/rules

## File Format
- Use Markdown (.md) files in `.continue/rules/` directory (workspace) or `~/.continue/rules/` (global)
- Include YAML frontmatter with properties below

## Frontmatter Properties
- `name`: Display name for the rule (required for YAML format)
- `globs`: File patterns to trigger the rule (e.g., `"**/*.{ts,tsx}"` or array `["src/**/*.ts", "tests/**/*.ts"]`)
- `regex`: Regex patterns to match file content
- `description`: Helps agent decide when to apply the rule (used when `alwaysApply: false`)
- `alwaysApply`: 
  - `true` = always included
  - `false` = included if globs match OR agent decides based on description
  - `undefined` = included if no globs OR globs match

## Content Guidelines
- Write clear, actionable instructions as bullet points
- Be concise and specific
- Group related instructions under headings
- Use code examples when helpful

## File Naming
- Prefix with numbers for ordering: `01-general.md`, `02-frontend.md`
- Use descriptive names: `typescript-standards.md`, `security-rules.md`

## Example
```md
---
name: TypeScript Best Practices
globs: ["**/*.ts", "**/*.tsx"]
alwaysApply: false
description: Standards for TypeScript development
---

# TypeScript Rules

- Always use TypeScript interfaces for object shapes
- Use strict null checks
- Include proper JSDoc comments for public APIs