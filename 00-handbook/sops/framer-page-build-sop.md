# Framer Page Build SOP

Use this SOP when starting a Framer MCP build from a prompt, screenshot, Cloudinary mockup, project brief, or raw chat report.

## 1. Start the build

1. Confirm the exact Framer project name.
2. Confirm the target page and primary breakpoint.
3. Confirm whether this is a new page, a copied project, or an existing page with protected sections.
4. Gather source references:
   - screenshot or mockup
   - Cloudinary URL
   - local asset folder
   - page structure
   - copy requirements
   - brand rules
5. Ask for broad edit permission up front if the session will require many Framer MCP edits.

## 2. Inspect before editing

1. Connect through Framer MCP.
2. Confirm the project and page are accessible.
3. Inspect current layers, sections, and breakpoints.
4. Identify protected sections and working components.
5. Report any mismatch before building.

## 3. Use native Framer layers first

Build with:

- sections
- frames
- stacks
- grids
- text layers
- image/video placeholders
- buttons
- cards
- native hover/click interactions
- overlays and masks

Do not start with one giant code component unless the user explicitly asks or the effect cannot be built natively.

## 4. Create parent frames before child layers

1. Create the page/section parent frame.
2. Create inner layout frames/stacks.
3. Add content children.
4. Add background and overlay layers.
5. Add interaction layers.
6. Keep every child inside the correct parent.

## 5. Name every layer clearly

Name:

- sections
- stacks
- frames
- cards
- image slots
- buttons
- overlays
- decorative effects
- CTA groups

Use names that another agent can inspect later.

## 6. Match screenshots with exact measurements

When recreating a reference:

1. Use the screenshot as a visual guide, not a flat site image.
2. Match section order, hierarchy, spacing, and proportions.
3. Use explicit measurements:
   - `100vh`
   - `width: 100%`
   - pixel gaps
   - card counts
   - x/y offsets
   - image crop positions
4. Build Desktop Large first when the reference is desktop.
5. Adapt responsive breakpoints only after the desktop layout is approved or stable.

## 7. Protect working areas

State exclusions in the prompt:

- do not touch other pages
- do not redesign protected sections
- do not change working hover effects
- do not rename layers broadly
- do not rebuild working components
- do not replace unrelated images

## 8. QA before ending

Before ending the session, verify:

- project/page/section matches request
- all major layers are named
- no random floating layers remain
- desktop layout matches reference
- mobile/tablet did not break where checked
- buttons and links work
- hover/click/preloader interactions work
- images load and are not blurry, huge, or mis-cropped
- overlays do not block clickable elements
- excluded sections were preserved

## 9. Report back

Claude Code or the agent should report:

- what was built
- what changed
- exact assets used
- what was preserved
- QA completed
- issues still open
- recommended GitHub report filename/folder

