# Contributing

This repo is meant to grow as more ChatGPT, Claude Code, Framer MCP, Codex, and Aura project reports are added.

## Add new raw reports

1. Save the original markdown report as source material.
2. Do not delete, flatten, or rewrite the raw report.
3. Use lowercase kebab-case filenames.
4. Put the report in the best matching numbered folder.
5. If unsure, place it in `/09-inbox-unsorted` and mark it for later review.

## Folder guide

- `/01-framer-mcp-playbooks`: Framer MCP build lessons, native layer rules, layout systems, template builds.
- `/02-claude-code-prompts`: reusable Claude Code prompts.
- `/03-image-asset-workflows`: Cloudinary, image uploads, local paths, compression, background image, Runway/video workflows.
- `/04-project-summaries`: project-specific summaries, especially combined or multi-project reports.
- `/05-agent-instructions`: future agent instructions and agent design docs.
- `/06-debugging-rules`: errors, MCP failures, random placement, tool loops, and troubleshooting rules.
- `/07-aura-brand-systems`: Aura branding, style, visual direction, colors, typography, copy, and sub-brand cohesion.
- `/08-reference-builds`: reference screenshots, recreation prompts, finished layout references.
- `/09-inbox-unsorted`: unclear reports that need review.

## Naming conventions

Use lowercase kebab-case:

```txt
aura-digital-image-motion-framer-workflow.md
framer-mcp-claude-code-connection-debugging-aura-ahp.md
premium-small-business-framer-template-systems.md
```

Good filenames include:

- project or brand
- main tool/workflow
- main lesson or report type

Avoid:

- `report.md`
- `notes-final-final.md`
- spaces
- vague dates without topic

## Preserve raw reports

Raw reports should keep:

- exact prompts
- exact paths
- exact URLs
- Cloudinary links
- Framer project names
- tool behavior notes
- mistakes and fixes
- recommended folders/filenames

Only do minor formatting cleanup when needed. Do not rewrite a raw report into a polished article.

## Update the index

Every time a markdown report or handbook file is added:

1. Update `PLAYBOOK_INDEX.md`.
2. Add a one-line description.
3. Add helpful tags.
4. Keep empty folders listed if they are part of the planned system.

## Update the handbook

When a new report repeats a lesson already seen in other reports:

1. Add or refine the relevant file in `00-handbook/rules`.
2. Add or refine a SOP in `00-handbook/sops`.
3. Add reusable prompts to `00-handbook/prompts`.
4. Add or refine agent instructions in `00-handbook/agents` or `AGENTS.md`.
5. Do not paste the entire raw report into the handbook.

## Future Codex session checklist

When Codex is asked to organize new reports:

1. Check repo status.
2. Read new markdown reports.
3. Categorize into numbered source folders.
4. Preserve original content.
5. Update `PLAYBOOK_INDEX.md`.
6. Extract repeated rules into `00-handbook`.
7. Run a final repo check.
8. Commit with a clear message.
9. Push when access is available.

## Future Claude Code session checklist

When Claude Code finishes a Framer MCP session:

1. Summarize what changed.
2. List project/page/section/layers touched.
3. Preserve asset paths and URLs.
4. List prompts that worked.
5. List failures and fixes.
6. Recommend a markdown filename and folder.
7. Use `00-handbook/prompts/claude-code-session-handoff-prompt.md` when possible.

