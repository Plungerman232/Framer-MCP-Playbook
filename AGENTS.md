# Agents

This file lists the proposed future agents for the Framer MCP Playbook system. Each agent has a detailed spec in `00-handbook/agents`.

## Agent map

| Agent | Use when | Main tools |
| --- | --- | --- |
| Framer Native Builder Agent | Building editable Framer pages, sections, templates, and card systems | Framer MCP, Claude Code, Cloudinary references |
| Framer Debugger Agent | Fixing MCP disconnects, layout drift, random placement, hover bugs, links, or breakpoint issues | Framer MCP, Claude Code |
| Image Asset Handler Agent | Mapping, compressing, hosting, replacing, and validating image/video assets | Cloudinary, local paths, Framer MCP |
| Claude Code Prompt Engineer Agent | Turning rough requests into safe, scoped Claude Code prompts | ChatGPT, Codex, Claude Code |
| Final QA Agent | Checking final Framer builds, handbook updates, links, assets, and preserved sections | Framer MCP, browser preview, GitHub docs |

## How the agents connect

**ChatGPT** usually starts the system. It turns raw ideas, chat history, screenshots, or reports into structured prompts, rules, and build briefs.

**Claude Code** executes Framer implementation through Framer MCP. Claude Code should receive scoped prompts from the Prompt Engineer Agent and should report back in a form that can be saved to GitHub.

**Framer MCP** provides live project access. Builder, Debugger, Asset Handler, and QA agents should inspect before editing and stop when connection or layer identity is unclear.

**Codex** maintains this repo. It audits new markdown reports, updates the index, extracts rules into `00-handbook`, commits documentation changes, and preserves raw reports.

**GitHub** stores the durable playbook: raw reports, handbook files, prompts, SOPs, agent specs, asset links, and implementation notes.

**Cloudinary** provides stable asset URLs when local paths, ChatGPT links, or uploads are unreliable.

**Aura projects** provide the main brand context. Aura agents must preserve the connected Aura Creative / Aura Visual / Aura Digital universe and avoid generic agency/template drift.

## Framer Native Builder Agent

Detailed spec: [framer-native-builder-agent.md](00-handbook/agents/framer-native-builder-agent.md)

What it does:

- Builds native Framer pages and sections.
- Creates parent frames before child layers.
- Names layers clearly.
- Uses screenshots and Cloudinary mockups as references, not as flat final sites.
- Keeps layouts editable.

Use it for:

- Aura home/service pages
- ATA pages
- barber/photography/small-business templates
- 3x3 card grids
- landing page sections
- reference recreation

## Framer Debugger Agent

Detailed spec: [framer-debugger-agent.md](00-handbook/agents/framer-debugger-agent.md)

What it does:

- Diagnoses MCP failures, random placement, layout mismatch, image issues, link problems, and hover/preloader issues.
- Fixes one issue at a time.
- Reports before/after values.

Use it when:

- Framer MCP disconnects
- layers land in the wrong parent
- overlays block buttons
- crops look wrong
- desktop/mobile breakpoints drift
- Claude Code begins looping

## Image Asset Handler Agent

Detailed spec: [image-asset-handler-agent.md](00-handbook/agents/image-asset-handler-agent.md)

What it does:

- Maps filenames to sections/cards/image slots.
- Compresses or recommends compressed assets.
- Uses Cloudinary for stable references.
- Protects layout during source replacement.
- Decides when to stop upload/video-generation loops.

Use it for:

- Cloudinary workflows
- local asset folders
- hover-card replacements
- image quality audits
- Runway fallback decisions

## Claude Code Prompt Engineer Agent

Detailed spec: [claude-code-prompt-engineer-agent.md](00-handbook/agents/claude-code-prompt-engineer-agent.md)

What it does:

- Converts rough tasks into safe Claude Code prompts.
- Adds exact scope, exclusions, stop conditions, and report requirements.
- Keeps prompts practical and measurable.

Use it before:

- long Framer MCP sessions
- risky layout edits
- image replacement batches
- debugging sessions
- final QA requests

## Final QA Agent

Detailed spec: [final-qa-agent.md](00-handbook/agents/final-qa-agent.md)

What it does:

- Checks layout, links, hover states, preloaders, image quality, layer names, parent frames, breakpoints, and protected sections.
- Produces a pass/fail report and smallest remaining fixes.

Use it before:

- ending a Claude Code session
- saving a report
- committing documentation
- handing a Framer build back to the user

## Suggested multi-agent sequence

1. **Claude Code Prompt Engineer Agent** turns the user request into a scoped prompt.
2. **Image Asset Handler Agent** maps and prepares assets.
3. **Framer Native Builder Agent** builds the page or section.
4. **Framer Debugger Agent** fixes targeted failures.
5. **Final QA Agent** checks the result.
6. **Codex** saves the report, updates `PLAYBOOK_INDEX.md`, and extracts any new recurring rule into `00-handbook`.

