# Framer MCP Playbook Handbook

This handbook synthesizes the repeated lessons from the raw reports. It is the practical layer of the repo: use it to brief Codex, Claude Code, ChatGPT, Framer MCP sessions, and future specialized agents.

The raw reports remain the source of truth for exact project history, URLs, file paths, prompts, and edge cases. This file turns those reports into working rules.

## Core workflow

1. Clarify the target project, page, section, breakpoint, and desired outcome.
2. Gather references: screenshot, Cloudinary URL, local file path, source folder, existing Framer project name, and any protected sections.
3. Inspect before editing. Claude Code should confirm the exact Framer project and relevant layers/components before making changes.
4. Build natively first: frames, stacks, sections, text, buttons, cards, images, components, and interactions.
5. Use code components only for special animation, reusable logic, or cases where native Framer layers cannot safely express the design.
6. Make small scoped changes. Fix one section, card, image slot, crop, or behavior at a time unless the task is explicitly a full-page build.
7. QA before ending: layout, breakpoints, links, hover/click behavior, asset quality, layer names, and excluded sections.
8. Save the knowledge back into GitHub as prompts, rules, SOPs, asset links, and implementation notes.

## Repeated Framer MCP rules

- Always confirm the active Framer project name before editing.
- Inspect canvas/layers before changing a section.
- Build from parent frames first, then add child layers.
- Name every major section, stack, frame, card, image slot, and button.
- Use native Framer layers before code components.
- Do not place a reference image as the final website.
- Use reference images as visual guides only.
- Avoid random absolute positioning unless necessary.
- Use exact measurements when matching a screenshot: pixel offsets, widths, heights, row counts, gap sizes, and section order.
- Do not rebuild working components just to fix one image, text block, or crop.
- If Framer MCP disconnects, stop editing, reconnect, inspect current state, then continue.
- Never expose MCP session URLs or secrets in public docs.

## Repeated Claude Code rules

- Ask for broad edit approval at the start of long Framer MCP sessions if the user may be away.
- Do not try to bypass Framer or MCP approval systems.
- Continue without asking when the next step is clearly inside the approved scope.
- Stop and ask when the target project, layer, source image, URL, permission, or user intent is unclear.
- Report exactly what changed, what was left untouched, what failed, and what still needs manual review.
- Use short correction prompts for small fixes instead of repeating an entire giant build prompt.
- Avoid loops: after two or three failed attempts at the same tiny issue, stop, summarize, and ask for a new input or fallback.

## Repeated Codex and GitHub rules

- GitHub stores the blueprint, not the native Framer canvas state.
- Preserve raw reports and add synthesized docs beside them.
- Use lowercase kebab-case filenames.
- Add future reports to the best matching numbered folder, then update the index.
- Save reusable builds with README, design system notes, page structure, asset links, prompt, and implementation notes.
- Verify real source files exist before treating a folder audit as meaningful.
- Do not port minified Nuxt/Vue/Vite chunks into Framer; use them as references for patterns only.

## Repeated image, Cloudinary, and asset rules

- Use Cloudinary or direct stable URLs for important visual references.
- Preserve original local paths and Cloudinary URLs in reports.
- Compress large images before blaming Framer for blur, grain, lag, or glitches.
- For code/component images, fix crops with `object-position`, `background-position`, or component-level focal controls.
- Do not globally change object-fit or object-position to fix one bad crop.
- Do not animate a base image layer when exact composition must stay locked; animate overlays instead.
- If Runway or another video tool repeatedly warps the subject, stop spending attempts and recreate the motion with Framer overlays.
- If upload/base64 attempts fail repeatedly, switch to Cloudinary, smaller files, or manual upload.

## Repeated debugging and stop rules

- Stop if MCP disconnects or cannot inspect the canvas.
- Stop if Claude Code cannot identify the exact target layer.
- Stop if image upload attempts repeat without new information.
- Stop if a tool keeps placing layers randomly or outside the intended parent frame.
- Stop if broad prompts begin changing unrelated sections.
- Stop if exact user-owned photos must remain unchanged and a generative tool keeps reinterpreting them.
- Before retrying, summarize current state, attempted fixes, likely cause, and safest next action.

## Prompt patterns that keep working

Strong prompts include:

- exact Framer project name
- exact page/section/card/layer name
- exact source folder or URL
- exact intended change
- explicit exclusions
- requirement to preserve layout, typography, sizing, animations, and unrelated sections
- before/after report request

Weak prompts say things like "make it better," "fix the layout," or "move this up" without identifying the layer, direction, amount, or protected areas.

## SOP patterns

The reports repeatedly use these workflows:

- Build a Framer page from a screenshot or Cloudinary mockup.
- Replace image sources while preserving component layout.
- Fix a bad crop using focal-position controls.
- Diagnose blurry/grainy Framer images.
- Recover from Framer MCP connection failure.
- Extract chat reports into GitHub-ready markdown.
- Archive Framer template prompts, design systems, page structures, asset links, and implementation notes.

## Future agent model

The repeated agent ideas collapse into five core agents:

- Framer Native Builder Agent
- Framer Debugger Agent
- Image Asset Handler Agent
- Claude Code Prompt Engineer Agent
- Final QA Agent

See [AGENTS.md](AGENTS.md) and `00-handbook/agents`.

## Aura project context

Aura is a cinematic creative universe with three connected branches:

- **Aura Visual**: photography, editorial visuals, portraits, storytelling, lifestyle, automotive, studio work.
- **Aura Digital**: web design, interfaces, templates, digital experiences, portals, systems, and branded websites.
- **Aura Creative**: creative direction, strategy, consulting, umbrella brand, and overall atmosphere.

Aura should feel premium, atmospheric, cinematic, polished, mysterious, editorial, and intentional. It should not drift into generic SaaS, generic agency, random template, or overdone AI fantasy.

Important Aura build rules:

- Keep sub-pages connected to the Aura universe.
- Use the Aura logo/emblem top-left where possible.
- Keep service cards, preloaders, and buttons visually cohesive across Visual, Digital, and Creative.
- Use exact user-owned assets when exactness matters; do not ask generative image tools to recreate them.
- Prefer subtle Framer-native overlays for shimmer, scanlines, glow, glitch energy, and atmosphere.

## Important paths, URLs, and project names

Preserve these because they recur in reports:

- Repo: `https://github.com/Plungerman232/Framer-MCP-Playbook`
- Template repo reference: `https://github.com/Plungerman232/Framer-Templates.git`
- Local template folder reference: `C:\Users\Charl\framer-site-templates`
- ATA asset folders referenced in reports:
  - `C:\Users\Charl\Desktop\Ata\Copy Right\`
  - `C:\Users\charleshockey3\Desktop\Ata\Copy Right\`
  - `C:\Users\Charl\Desktop\Ata\Copy Right\X\x ata pics\X ATA Tiny\`
- Aura asset folder reference: `Desktop -> New Aura Hero -> Color Graded`
- Framer projects referenced: `ATA copy`, `Aura TSX`, `Aura TSX copy`, `Aura TSX (copy 2)`, `Keith will cut you`, `preloader`
- Cloudinary reference: `https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png`
- Cloudinary reference: `https://res.cloudinary.com/drr7vuxzd/image/upload/v1780345972/ATA_Site_Layout_bg4nh4.png`
- Framer MCP URL source mentioned in reports: `mcp.unframer.co`
- Known working Claude MCP transport note: `--transport http`

