# GitHub Save Report Prompt

Use this when asking a chat to prepare a report for this repo.

```text
Prepare this as a markdown report for the GitHub repo:

https://github.com/Plungerman232/Framer-MCP-Playbook

The repo preserves raw reports and extracts reusable handbook material over time.

Create a clean markdown file that keeps:
- project context
- exact Framer project names
- exact file paths
- Cloudinary URLs
- prompts
- mistakes
- fixes
- SOPs
- agent-ready instructions

Recommend the best folder:
- /01-framer-mcp-playbooks for Framer MCP build lessons, native layer rules, and layout systems
- /02-claude-code-prompts for reusable Claude Code prompts
- /03-image-asset-workflows for Cloudinary, images, uploads, local paths, and background image workflows
- /04-project-summaries for Aura or project-specific summaries
- /05-agent-instructions for future agent instructions or agent design docs
- /06-debugging-rules for errors, loops, MCP failures, random placement, and troubleshooting
- /07-aura-brand-systems for Aura branding, style, visual direction, colors, and typography
- /08-reference-builds for reference screenshots, recreation prompts, and finished layout references
- /09-inbox-unsorted if unclear

Use a lowercase kebab-case filename.

Do not delete raw source material.
Do not rewrite exact prompts so much that they lose useful details.
Do not expose private MCP URLs, secrets, or credentials.
```

