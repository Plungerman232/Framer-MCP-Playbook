# Playbook Index

Use this index to find the right source report or handbook document quickly. Tags are intentionally practical: `framer-mcp`, `claude-code`, `assets`, `cloudinary`, `aura`, `debugging`, `sop`, `prompt`, `agent`, `github`, `reference`.

## 00 Handbook

- [HANDBOOK.md](HANDBOOK.md): Master synthesized handbook for recurring Framer MCP, Claude Code, asset, debugging, prompt, SOP, agent, and Aura lessons. Tags: `handbook`, `sop`, `rules`, `agent`.
- [AGENTS.md](AGENTS.md): Master list of proposed future agents and how they connect to Framer MCP, Claude Code, Codex, GitHub, Cloudinary, and Aura work. Tags: `agent`, `framer-mcp`, `codex`.
- [CONTRIBUTING.md](CONTRIBUTING.md): Instructions for adding future markdown reports while preserving raw source files and keeping the handbook/index current. Tags: `github`, `codex`, `workflow`.

## 00 Handbook / Rules

- [framer-mcp-rules.md](00-handbook/rules/framer-mcp-rules.md): Framer MCP usage, native layer, naming, positioning, parent frame, code component, and stop-condition rules. Tags: `framer-mcp`, `rules`, `debugging`.
- [image-asset-rules.md](00-handbook/rules/image-asset-rules.md): Cloudinary, image URL, local path, background image, base64/compression, upload failure, and retry stop rules. Tags: `assets`, `cloudinary`, `rules`.
- [claude-code-rules.md](00-handbook/rules/claude-code-rules.md): Claude Code permission, continuation, stopping, reporting, and anti-loop rules. Tags: `claude-code`, `rules`, `prompt`.

## 00 Handbook / SOPs

- [framer-page-build-sop.md](00-handbook/sops/framer-page-build-sop.md): Start-to-finish SOP for Framer MCP page builds using native layers, named frames, exact measurements, and QA. Tags: `framer-mcp`, `sop`, `qa`.
- [troubleshooting-sop.md](00-handbook/sops/troubleshooting-sop.md): SOP for failed uploads, Cloudinary fallback, random layer placement, MCP loops, layout mismatch, image issues, and missing files. Tags: `debugging`, `assets`, `sop`.

## 00 Handbook / Prompts

- [claude-code-session-handoff-prompt.md](00-handbook/prompts/claude-code-session-handoff-prompt.md): Prompt for making Claude Code summarize a session and prepare a GitHub-ready report. Tags: `claude-code`, `prompt`, `github`.
- [chat-extraction-prompt.md](00-handbook/prompts/chat-extraction-prompt.md): Prompt for extracting reusable rules, SOPs, prompts, mistakes, fixes, paths, and agent ideas from old ChatGPT chats. Tags: `chatgpt`, `prompt`, `extraction`.
- [github-save-report-prompt.md](00-handbook/prompts/github-save-report-prompt.md): Prompt for preparing a markdown report for this repo with recommended folder and filename. Tags: `github`, `prompt`, `codex`.

## 00 Handbook / Agents

- [framer-native-builder-agent.md](00-handbook/agents/framer-native-builder-agent.md): Agent spec for building editable Framer pages with native layers first. Tags: `agent`, `framer-mcp`, `native`.
- [framer-debugger-agent.md](00-handbook/agents/framer-debugger-agent.md): Agent spec for diagnosing MCP, layer placement, layout, interaction, and breakpoint failures. Tags: `agent`, `debugging`, `framer-mcp`.
- [image-asset-handler-agent.md](00-handbook/agents/image-asset-handler-agent.md): Agent spec for mapping, compressing, hosting, and validating Framer image/video assets. Tags: `agent`, `assets`, `cloudinary`.
- [claude-code-prompt-engineer-agent.md](00-handbook/agents/claude-code-prompt-engineer-agent.md): Agent spec for turning rough requests into safe, scoped Claude Code prompts. Tags: `agent`, `claude-code`, `prompt`.
- [final-qa-agent.md](00-handbook/agents/final-qa-agent.md): Agent spec for final Framer QA across layout, content, links, assets, interactions, and documentation. Tags: `agent`, `qa`, `framer-mcp`.

## 01 Framer MCP Playbooks

- [ata-framer-mcp-foundation-athletes-image-optimization-playbook.md](01-framer-mcp-playbooks/ata-framer-mcp-foundation-athletes-image-optimization-playbook.md): ATA build notes for foundation athlete cards, image optimization, hover crops, navigation, copy, and alumni ordering. Tags: `framer-mcp`, `assets`, `debugging`, `prompt`, `ata`.
- [aura-animated-hero-framer-claude-code-runway-workflow.md](01-framer-mcp-playbooks/aura-animated-hero-framer-claude-code-runway-workflow.md): Aura Creative animated hero workflow using Framer, Claude Code, Runway testing, and layered still-image motion. Tags: `aura`, `framer-mcp`, `runway`, `assets`.
- [aura-creative-claude-code-cloudinary-agent-workflow.md](01-framer-mcp-playbooks/aura-creative-claude-code-cloudinary-agent-workflow.md): Aura Creative workflow covering Claude Code iteration, Cloudinary assets, layout accuracy, and future agent architecture. Tags: `aura`, `cloudinary`, `agent`, `workflow`.
- [aura-digital-framer-mcp-layout-seam-blend-playbook.md](01-framer-mcp-playbooks/aura-digital-framer-mcp-layout-seam-blend-playbook.md): Aura Digital playbook for seam blending, 100vh sections, transition assets, hero backgrounds, and native Framer layout workflow. Tags: `aura`, `framer-mcp`, `layout`, `native`.
- [aura-framer-preloader-native-effects-runway-workflow.md](01-framer-mcp-playbooks/aura-framer-preloader-native-effects-runway-workflow.md): Aura preloader and animation workflow covering Framer MCP, native effects, Runway prompts, and routing behavior. Tags: `aura`, `preloader`, `runway`, `framer-mcp`.
- [aura-moon-framer-mcp-layout-troubleshooting.md](01-framer-mcp-playbooks/aura-moon-framer-mcp-layout-troubleshooting.md): Aura Moon troubleshooting playbook for layout drift, image assets, Cloudinary imports, previews, and display color mismatch. Tags: `aura`, `debugging`, `cloudinary`, `layout`.
- [aura-site-design-buttons-template-system-northfield.md](01-framer-mcp-playbooks/aura-site-design-buttons-template-system-northfield.md): Aura Digital button, card, and template system notes, including the Northfield starter-site direction. Tags: `aura`, `template`, `framer-mcp`, `assets`.
- [framer-mcp-claude-code-connection-debugging-aura-ahp.md](01-framer-mcp-playbooks/framer-mcp-claude-code-connection-debugging-aura-ahp.md): Framer MCP and Claude Code setup/debugging workflow for connection issues, transport settings, and safe Aura hero editing. Tags: `framer-mcp`, `claude-code`, `debugging`, `aura`.
- [keith-will-cut-you-barber-framer-template.md](01-framer-mcp-playbooks/keith-will-cut-you-barber-framer-template.md): Solo barber Framer template planning report with site strategy, layout, booking/social proof requirements, and build prompts. Tags: `template`, `framer-mcp`, `cloudinary`, `small-business`.
- [photography-website-build-workflow-claude-to-framer.md](01-framer-mcp-playbooks/photography-website-build-workflow-claude-to-framer.md): Photography website workflow from portfolio assets to hero selection, structure, build instructions, and Framer implementation. Tags: `sop`, `prompt`, `photography`, `framer`.
- [premium-small-business-framer-template-systems.md](01-framer-mcp-playbooks/premium-small-business-framer-template-systems.md): Premium small-business template system notes for ATA, tinting, preloaders, GitHub archiving, and reference-site rebuild rules. Tags: `template`, `github`, `codex`, `cloudinary`, `sop`.

## 02 Claude Code Prompts

- No raw markdown reports added yet. Use `00-handbook/prompts` for synthesized reusable prompts.

## 03 Image Asset Workflows

- [aura-digital-image-motion-framer-workflow.md](03-image-asset-workflows/aura-digital-image-motion-framer-workflow.md): Aura Digital image, motion, Cloudinary, Runway, and Framer implementation rules for a digital sub-brand page. Tags: `aura`, `assets`, `cloudinary`, `runway`.
- [aura-preloader-visual-hero-asset-workflow.md](03-image-asset-workflows/aura-preloader-visual-hero-asset-workflow.md): Aura preloader and visual hero asset workflow for transition videos, Runway prompts, and service identity direction. Tags: `aura`, `preloader`, `assets`, `runway`.
- [aura-visual-homepage-exact-assets-and-branch-cohesion-rules.md](03-image-asset-workflows/aura-visual-homepage-exact-assets-and-branch-cohesion-rules.md): Aura Visual homepage and brand cohesion rules, exact-photo mockup workflows, and when to avoid generative recreation. Tags: `aura`, `assets`, `brand`, `reference`.

## 04 Project Summaries

- [aura-ata-framer-mcp-hover-assets-layout-debugging-report.md](04-project-summaries/aura-ata-framer-mcp-hover-assets-layout-debugging-report.md): Combined Aura TS and ATA summary covering hover effects, asset handling, image compression, layout fixes, and prompt patterns. Tags: `aura`, `ata`, `debugging`, `assets`, `prompt`.

## 05 Agent Instructions

- No raw markdown reports added yet. Use `00-handbook/agents` and `AGENTS.md` for synthesized agent instructions.

## 06 Debugging Rules

- No raw markdown reports added yet. Use `00-handbook/rules` and `00-handbook/sops/troubleshooting-sop.md` for synthesized debugging rules.

## 07 Aura Brand Systems

- [aura-digital-brand-handoff.md](07-aura-brand-systems/aura-digital-brand-handoff.md): Aura Digital brand handoff defining identity, visual direction, tone, page goals, and relationship to the Aura Creative universe. Tags: `aura`, `brand`, `copy`, `visual-direction`.

## 08 Reference Builds

- No raw markdown reports added yet.

## 09 Inbox Unsorted

- No raw markdown reports added yet.

