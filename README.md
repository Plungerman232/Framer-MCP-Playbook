# Framer MCP Playbook

This repo is a working handbook for building, debugging, and documenting Framer projects with ChatGPT, Claude Code, Codex, Framer MCP, GitHub, Cloudinary, and related image/motion tools.

The original markdown reports are preserved as source material. The `00-handbook` folder turns the repeated lessons from those reports into reusable rules, SOPs, prompts, and future agent instructions. More reports will be added over time, so this repo is structured as a living playbook rather than a finished document.

## How to use this repo

Start with [HANDBOOK.md](HANDBOOK.md) for the synthesized system. Use [PLAYBOOK_INDEX.md](PLAYBOOK_INDEX.md) to find source reports by topic, tag, and folder.

Use the handbook files this way:

- `00-handbook/rules`: rules that should be copied into Claude Code, Codex, or future agent instructions.
- `00-handbook/sops`: step-by-step workflows for Framer builds and troubleshooting sessions.
- `00-handbook/prompts`: reusable prompts for handoffs, extraction, and saving reports.
- `00-handbook/agents`: proposed specialized agents for Framer builds, debugging, image assets, prompt engineering, and final QA.

Use the raw reports this way:

- Read them when a handbook rule needs context.
- Preserve exact paths, URLs, prompts, project names, and tool behavior notes.
- Add new reports to the best matching numbered source folder.
- Update `PLAYBOOK_INDEX.md` and the relevant handbook file when a new report repeats or changes an existing rule.

## Folder structure

```txt
/00-handbook
/00-handbook/rules
/00-handbook/sops
/00-handbook/prompts
/00-handbook/agents
/01-framer-mcp-playbooks
/02-claude-code-prompts
/03-image-asset-workflows
/04-project-summaries
/05-agent-instructions
/06-debugging-rules
/07-aura-brand-systems
/08-reference-builds
/09-inbox-unsorted
```

## Tool roles

**ChatGPT** is the strategist and extractor. It turns project chats into reports, writes build prompts, extracts rules, and keeps the playbook organized.

**Claude Code** is the Framer implementation agent. It should connect through Framer MCP, confirm the exact project, request needed edit approval up front for long sessions, build natively where possible, and report exactly what changed.

**Codex** is the repo organizer and handbook maintainer. It audits markdown reports, updates indexes, extracts repeatable patterns, commits clean documentation changes, and preserves raw source files.

**Framer MCP** is the live bridge into Framer. It should be used carefully: inspect before editing, build inside the intended project only, avoid broad tool loops, and stop when connection state or permissions are unclear.

**Cloudinary** is the reliable asset reference layer when local file paths or ChatGPT download links are unstable. Preserve Cloudinary URLs and exact file mappings in reports and prompts.

## Core operating principles

- Preserve raw reports. Do not delete, flatten, or rewrite them into the handbook.
- Build natively in Framer with frames, stacks, text, buttons, cards, image layers, and components before reaching for code components.
- Use code components only for special effects, reusable interactions, or cases where native layers cannot safely produce the result.
- Scope Claude Code prompts narrowly: one section, one card, one image slot, one crop, one text block, or one fix at a time unless the user explicitly wants a full rebuild.
- Use exact project names, section names, layer names, file paths, URLs, pixel values, and exclusions.
- Stop loops early. If MCP disconnects, uploads fail repeatedly, images keep warping, or Claude cannot identify the target layer, pause and ask for the missing input.

