# Framer MCP Rules

Use these rules when Claude Code, Codex, or a future agent is controlling Framer through MCP.

## Framer MCP usage rules

1. Confirm the exact Framer project name before editing.
2. Inspect the page, section, and relevant layers before making changes.
3. Work only inside the intended project, page, section, and breakpoint.
4. Ask for broad edit approval up front for long sessions if the user may be away.
5. Never expose Framer MCP session URLs, tokens, or secret connection details in public docs.
6. If MCP disconnects, stop editing, reconnect, inspect the current state, then continue.
7. If the target layer cannot be found, do not guess. Ask for a screenshot, layer name, project name, or user confirmation.

## Native Framer layer rules

1. Build natively first using Framer sections, frames, stacks, text layers, buttons, cards, image/video layers, and interactions.
2. Use code components only for special effects, reusable interactions, complex animation, or cases where native layers cannot safely produce the result.
3. Do not place a mockup or screenshot as the final website.
4. Use visual references as guides for spacing, hierarchy, section order, color, and mood.
5. Prefer editable placeholders when final images/video are not ready.
6. Keep important text, nav, CTAs, and labels as editable Framer text instead of baking them into images or videos.

## Layer naming rules

Name layers as if another agent will inspect the file later.

Use names like:

- `Hero Section`
- `Hero Background Image`
- `Hero Overlay Scanline`
- `Primary CTA Button`
- `Services Section`
- `Service Card - Visual`
- `Service Card - Digital`
- `Service Card - Creative`
- `Template Grid`
- `Northfield Card`
- `Foundation Athlete Card - Xavier`
- `Hover Image 1`

Avoid vague names like:

- `Frame 123`
- `Rectangle`
- `Image`
- `New Layer`
- `Copy 4`

## Layout positioning rules

1. Create parent frames before child layers.
2. Put children inside the correct parent frame instead of leaving them floating on the canvas.
3. Prefer stacks, grids, constraints, and frame layout over random absolute positioning.
4. Use exact measurements when matching screenshots: width, height, gap, margin, x/y offset, section height, and card count.
5. When fixing a crop or image position, adjust only that image slot unless the whole pattern is intentionally changing.
6. Do not globally change object-fit, object-position, spacing, or typography to solve one local problem.
7. Check z-index/layer order when buttons are not clickable; decorative overlays should not block links.

## Parent frame rules

1. Every section should have a named parent frame.
2. Every card group should have a named stack/grid parent.
3. Every repeated card should have a stable naming pattern.
4. Hover layers, overlays, and decorative effects should stay inside their relevant card or section parent.
5. If Framer MCP places an element at a strange offset, move it into the correct parent frame before continuing with visual polish.

## When to avoid code components

Avoid code components when:

- The section can be built with normal Framer frames, stacks, images, text, and buttons.
- The user needs to visually edit the layout later.
- The task is a straightforward landing page, service section, card grid, CTA, nav, or footer.
- A screenshot/mockup is only a visual reference.

Use code components when:

- A native Framer layer cannot produce the interaction safely.
- A reusable hover/animation component already exists.
- The requested effect needs custom timing, state, or dynamic logic.
- You are editing an existing code component and the target image/text lives inside it.

## Stop rules for tool loops and errors

Stop and report when:

- Framer MCP disconnects.
- The tool returns repeated placement errors.
- Layers are repeatedly created outside the intended parent frame.
- Claude Code cannot identify the correct project, page, section, or layer.
- A broad prompt starts changing unrelated sections.
- The same fix fails two or three times without new evidence.
- A permission dialog blocks progress.

When stopping, report:

- what was attempted
- what changed
- what did not change
- the likely cause
- the exact input needed to continue

