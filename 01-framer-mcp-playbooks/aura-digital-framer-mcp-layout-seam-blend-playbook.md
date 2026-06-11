# Aura Digital Framer MCP Build Playbook
## Seam Blending, Transition Assets, Hero Backgrounds, and Native Framer Layout Workflow

## 1. Chat Title / Topic

**Aura Digital / Intelligence in Motion / Motion Is Perception — Framer MCP + Claude Code Build Workflow**

This report extracts the reusable Framer MCP, Claude Code, Cloudinary, image-generation, and web-build troubleshooting information from the chat. It focuses on building premium Aura Digital layouts, debugging Framer section seams, using native Framer layers before components, and preparing reusable agent instructions.

---

## 2. Main Problem or Build Goal

The main goal was to build a premium **Aura Digital** website system for the web design branch of Aura / `enter_aura`.

Two connected build tracks were discussed.

### Track A — 4-Page Aura Digital Template

A Framer project used four main full-viewport sections:

1. Page 1 — Hero / homepage
2. Page 2 — Video showcase
3. Page 3 — Motion / about section
4. Page 4 — CTA / contact section

Each page was intended to stay:

- `height: 100vh`
- `width: 100%`

The problem was that the four sections felt like hard-cut stacked pages instead of one cohesive cinematic scroll experience. The goal became to blend seams while preserving the 100vh structure.

### Track B — Aura Digital Homepage with 9 Placeholders

The later goal was to build the actual **Aura Digital homepage** for web design and digital experiences. The target reference was a one-page cinematic layout with:

- One clean scenic background plate
- Large centered `AURA DIGITAL` hero title
- Subtitle: `WEB DESIGN & DIGITAL EXPERIENCES`
- CTA buttons
- Exactly 9 editable placeholder cards arranged in 3 rows of 3
- Row labels:
  - `TEMPLATES`
  - `CREATIVE BUILDS`
  - `AI MOTION CONCEPTS`
- Footer metadata
- Native Framer layers first, with components only after the layout is approved

---

## 3. Tools Used

### Framer

Used as the main visual site builder. Important concepts used:

- Frames
- Stacks
- Absolute positioning
- Relative positioning
- Viewport-height sections
- Image fills
- Video placeholders
- Gradient fills
- Shadows
- Opacity
- Layer order
- Z-index
- Responsive breakpoints
- Layer naming

### Framer MCP

Used to let Claude Code inspect and manipulate the Framer project. It was useful, but the chat showed that MCP can create technically valid layers that do not visually solve the issue if instructions are not tightly scoped.

### Claude Code

Used to direct Framer MCP changes, including:

- Inspecting files/projects
- Adding/replacing image assets
- Creating transition bands
- Creating seam-blend attempts
- Updating memory files
- Building native Framer layers
- Preserving existing page structure

### ChatGPT Image Generation

Used to create:

- Page 2 background imagery
- Full-site layout mockups
- Transition banner concepts
- Feathered seam-blend assets
- Clean Aura Digital hero background plates with no text/cards/UI

### Cloudinary

Used to host generated images and pass direct URLs into Framer/Claude Code.

Example URLs from this workflow:

```text
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780269616/page_2_holder_e2iyq8.png
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780332046/banner_1_f4sz25.png
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780332046/banner_2_bgrvvo.png
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780332046/banner_3_hbhkcx.png
```

### GitHub

Target repo:

```text
https://github.com/Plungerman232/Framer-MCP-Playbook
```

This report is meant to be stored in the repo as a reusable Framer MCP playbook.

---

## 4. What Worked

### Build Native Layers First

The strongest workflow decision was to build all page elements as **native Framer layers first**, then convert to components later. This is better for visual tuning because it allows fast adjustment of:

- card size
- card position
- row spacing
- text alignment
- opacity
- shadows
- responsive behavior
- background placement

Rule:

> Native Framer layers first. Components later.

### Cloudinary URL Asset Workflow

Cloudinary worked well for moving generated assets into Framer:

1. Generate an image
2. Upload it to Cloudinary
3. Copy the URL
4. Give Claude Code the URL
5. Tell Claude exactly where to insert it

This is cleaner than repeatedly attaching local files.

### Full-Site Mockups Before Framer Changes

Generating full-site mockups helped establish creative direction before instructing Claude Code. Mockups were useful for:

- testing whether transitions looked coherent
- comparing banner-based transitions vs seam blending
- defining hierarchy and layout before touching Framer
- giving Claude Code a visual target

### Avoid Repeated Homepage Headers

The site felt less professional when every section repeated the homepage header and nav. Final direction:

> Only Page 1 should feel like the homepage. Inner sections should use subtle section labels instead of repeated full nav/header treatment.

Useful section labels:

```text
OUR WORK
ABOUT AURA
LET’S CONNECT
IN MOTION
```

### Clean Background Plate Workflow

For the Aura Digital homepage, the background image should be a clean plate only:

- no text
- no cards
- no buttons
- no logo
- no nav
- no footer

All UI should be recreated as editable Framer layers on top.

---

## 5. What Failed

### Full-Page Dark Overlays

Claude Code repeatedly added overlays that darkened entire pages. This made the design muddy and less premium.

Rule:

> Do not use full-page dark overlays unless explicitly requested. Use localized text backing, top/bottom gradients, or small seam overlays instead.

### Plain Black Transition Bands

The first transition bands looked like black strips between sections. They made the page look worse because they felt like dividers rather than cinematic transitions.

Rule:

> Transition bands should never look like generic bars. They must either match the adjacent imagery or be removed.

### Random Generated Transition Banners

Some generated transition banners looked good on their own but did not match the real active Framer pages. They failed because the color palette and imagery did not match the exact neighboring sections.

Rule:

> Transition assets must be generated for the exact two pages they connect, not just from a general brand vibe.

### Cropping Exact Banners Too Thin

Cropping thin strips from a mockup created decorative slivers, not usable transition assets.

Rule:

> If extracting a transition from a mockup, crop a taller region around the seam, not only the visible seam line.

### Single SeamBlend Across Two Pages

Trying to make one overlay frame span two 100vh sections caused Framer to treat it like a normal layout block or new section. It created hard bars, pushed layout, or only affected one page.

Rule:

> Do not rely on one frame spanning two viewport sections. Use paired overlays inside each page or use a feathered image seam asset.

### Framer Effects Confusion

Framer’s `Effects +` menu showed animation/interactions such as Appear, Hover, Press, Loop, Drag, Scroll, and Flow. This was not the same as visual blur.

Rule:

> Do not assume Framer’s Effects menu means visual blur. For seam softness, use gradients, image-based feathering, duplicate blurred slices, or shadows if available.

### Gradient Frames Still Created Hard Lines

Even with a transparent top stop, gradient frames could still read as rectangular bars because the frame itself had a visible start edge.

Rule:

> If a gradient overlay still creates a visible edge, use a feathered image seam asset or remove the overlay.

---

## 6. Final Decisions

### 4-Page Template

Keep the four main pages:

```text
Page 1: 100vh
Page 2: 100vh
Page 3: 100vh
Page 4: 100vh
```

Do not add large new transition pages. Use subtle seam treatment only if it improves the design.

Preferred order of solutions:

1. No transition if the hard cut looks cleaner
2. Paired top/bottom gradients inside each page
3. Feathered image seam asset
4. Carefully designed transition band matching the exact adjacent imagery

Avoid:

- full-page dark overlays
- generic black bars
- repeated homepage headers
- random transition images that do not match the actual pages

### Aura Digital Homepage

Build a single homepage from the reference:

- clean full-page scenic background
- editable hero title/subtitle/buttons
- 9 native placeholder cards
- 3 rows of 3
- labels for Templates, Creative Builds, and AI Motion Concepts
- footer metadata

Do **not** bake the cards into the background.

### Components Come Later

Do not convert the 9 placeholder cards into components immediately. First build and tune them as native layers. Convert to reusable components after the layout is approved.

---

## 7. Reusable Rules

### Framer Layout Rules

1. Main sections can stay at `100vh`.
2. Do not add giant transition sections unless intentionally designing a new scroll chapter.
3. Put overlays inside the relevant page section.
4. Use absolute positioning for seam overlays.
5. Keep overlay z-index above the background and below text/nav/buttons.
6. Do not put seam overlays inside text/content stacks.
7. Avoid repeated homepage nav on every section.
8. Build native layers before components.
9. Check desktop, tablet, and phone separately.

### Overlay Rules

1. No full-page dark overlays unless explicitly requested.
2. Use localized text backing instead of global darkening.
3. Keep seam overlays subtle.
4. If a gradient reads as a bar, remove it or use a feathered image asset.
5. Judge effects in Preview, not only while selected in the editor.

### Claude Code Rules

Always start with:

```text
Inspect the current Framer file with MCP before making changes.
```

Always preserve:

```text
Do not redesign unrelated sections.
Do not change page heights.
Do not change existing images/videos/text unless explicitly requested.
Make changes as native Framer layers first.
```

### Image Asset Rules

1. Generate clean background plates without UI.
2. Add text/cards in Framer afterward.
3. Use Cloudinary URLs for easy insertion.
4. If a downloaded image opens as broken text, use the actual PNG file, not a broken file-link text result.
5. Keep backgrounds clear enough for future overlays and cards.

---

## 8. Reusable Prompt Snippets

### Replace a Framer Image with Cloudinary URL

```text
We are working in file/project [PROJECT NAME].

Do not redesign or change anything else. Only update the specified image source.

Use this image URL:
[IMAGE URL]

Apply it to:
[SECTION / PAGE / FRAME NAME]

Settings:
- width: 100%
- height: 100%
- object-fit: cover
- object-position: center center
- no tiling
- no stretching
- no black bars
- keep existing text, layout, videos, and page heights unchanged
```

### Build Native Layers Before Components

```text
Important workflow note:

Do not make the cards into components immediately.

First build the homepage using native Framer layers, frames, and stacks only. I want to visually tune the layout first through the Framer MCP.

Create the placeholder cards as normal editable Framer frames/layers first. Name them clearly and keep the structure clean, but do not convert them into reusable components yet.

After the layout, spacing, sizing, and responsive behavior are correct, we can convert the card design into reusable components later.
```

### Prevent Full-Page Overlays

```text
Do not add any full-page dark overlays.

If readability needs improvement, use only localized support:
- small text backing
- top gradient behind nav
- bottom seam fade
- subtle directional gradient

The background image/video should remain luminous and visible.
```

### 4-Page Seam Blend Instruction

```text
Keep the 4 main pages at 100vh and 100% width.

Do not add large transition pages.

Use subtle seam blending only:
- Page 1 bottom fades into Page 2
- Page 2 top/bottom fades into adjacent sections
- Page 3 top/bottom fades into adjacent sections
- Page 4 top fades from Page 3

Each seam layer should be:
- inside the relevant page
- absolute positioned
- width: 100%
- height: 120–180px
- above the background
- below text/content/nav
- pointer-events: none if available

Do not let any seam layer become a normal layout block or spacer.
```

### Aura Digital Homepage Build Prompt

```text
We are building the homepage for Aura Digital, the web design / digital experiences branch of Aura / enter_aura.

Use the attached reference image as the visual/layout target. I will provide the clean background image without cards or text. Use that clean image as the full-page background, then build editable Framer text, buttons, and placeholder cards on top.

Build this as one homepage only.

Do not bake the cards into the background.

Create exactly 9 editable native Framer placeholder cards in 3 rows of 3:

Row 1 label:
TEMPLATES

Row 2 label:
CREATIVE BUILDS

Row 3 label:
AI MOTION CONCEPTS

Each card should be:
- real editable Framer layer/frame
- clickable/link-ready
- rounded corners
- subtle translucent cream/glass fill
- thin border
- subtle shadow
- placeholder text/image area
- native layer first, not a component yet

Keep the design close to the reference:
- premium cinematic background
- large centered AURA DIGITAL title
- subtitle: WEB DESIGN & DIGITAL EXPERIENCES
- buttons: VIEW SERVICES and START A PROJECT
- small uppercase nav
- footer metadata
```

### Clean Background Plate Generation Prompt

```text
Generate a clean background plate based on the reference image.

Keep the same:
- scenic world
- water
- mountains/canyon framing
- clouds
- lighting
- colors
- mood
- perspective

Remove:
- all text
- logos
- nav
- buttons
- placeholder cards
- footer text
- UI elements
- lines

Output only the clean background image so the website elements can be recreated as editable Framer layers afterward.
```

---

## 9. SOPs / Step-by-Step Workflows

## SOP 1 — Manual Seam Overlay in Framer

Use this only when trying to soften a seam between two 100vh sections.

### Hero Bottom Overlay

1. Open the target breakpoint, such as `Desktop LG`.
2. In Layers, open `Desktop LG → Hero Page`.
3. Select `Hero Page`.
4. Create a new frame.
5. Drag the new frame inside `Hero Page`.
6. Rename it `Hero Bottom Blend`.
7. Set layer order:
   ```text
   Text / buttons / nav
   Hero Bottom Blend
   Background image/video
   ```
8. Set:
   ```text
   Position: Absolute
   Width: 100%
   Height: 120–160px
   Left: 0
   Right: 0
   Bottom: 0
   ```
9. Fill:
   ```text
   Linear gradient
   Top: transparent
   Bottom: dark navy #06080F at 35–60%
   ```
10. Preview before adding shadows or blur.

### Page 2 Top Overlay

1. Duplicate the seam frame.
2. Move duplicate inside `Page 2`.
3. Rename it `Page 2 Top Blend`.
4. Set:
   ```text
   Position: Absolute
   Width: 100%
   Height: 120–160px
   Top: 0
   Left: 0
   Right: 0
   ```
5. Fill:
   ```text
   Linear gradient
   Top: dark navy #06080F at 35–60%
   Bottom: transparent
   ```
6. Preview the seam.

### If a Hard Line Appears

If the gradient frame still creates a visible line:

1. Do not keep increasing opacity.
2. Do not add a full-page overlay.
3. Try a taller frame.
4. Try a custom feathered image seam asset.
5. If it still looks worse, remove the effect.

---

## SOP 2 — Claude Code Framer MCP Workflow

Use this before any Framer MCP change.

1. Tell Claude:
   ```text
   Use Framer MCP to inspect the current file first.
   ```
2. Define the exact file/project:
   ```text
   We are working in file/project 7 only.
   ```
3. State what to preserve:
   ```text
   Keep page heights, layout, text, images, videos, and nav unchanged unless directly specified.
   ```
4. State the single task.
5. Give exact settings.
6. Require confirmation of what changed and what was left untouched.

---

## SOP 3 — Image Asset Workflow with Cloudinary

1. Generate image in ChatGPT.
2. Download image locally.
3. Upload image to Cloudinary.
4. Copy Cloudinary URL.
5. Give Claude Code a scoped prompt.
6. Insert the URL into Framer via MCP.
7. Check desktop, tablet, and phone.
8. If broken, verify URL and file format.

---

## SOP 4 — Aura Digital Homepage Build

1. Generate/provide clean background plate.
2. Insert it as the full-page background.
3. Add native header/nav layers.
4. Add hero title: `AURA DIGITAL`.
5. Add subtitle: `WEB DESIGN & DIGITAL EXPERIENCES`.
6. Add CTA buttons: `VIEW SERVICES` and `START A PROJECT`.
7. Add 3 card row labels:
   ```text
   TEMPLATES
   CREATIVE BUILDS
   AI MOTION CONCEPTS
   ```
8. Add 9 native placeholder cards.
9. Tune layout and spacing.
10. Check responsiveness.
11. Convert cards to components only after approval.

---

## 10. Future Agent Ideas

### Framer Layout Agent

Maintains correct Framer hierarchy, prevents overlays from becoming layout blocks, checks absolute positioning, z-index, and breakpoints.

### Aura Design Preservation Agent

Protects the Aura aesthetic by preventing cheap overlays, random black bars, repeated homepage headers, muddy darkening, and mismatched transition assets.

### Seam Blend Debugging Agent

Debugs seam issues between viewport sections. Checks if layers are relative/absolute, inside the right parent, pushing layout, or creating visible hard edges.

### Cloudinary Asset Agent

Tracks final image URLs, confirms which URL belongs to which section, verifies aspect ratios, and keeps asset usage documented.

### Native-to-Component Conversion Agent

Converts approved native Framer card layouts into reusable components with props such as:

```text
cardTitle
cardSubtitle
cardCategory
imageUrl
videoUrl
linkUrl
cardType
hoverState
```

---

## 11. Recommended Filename

```text
aura-digital-framer-mcp-layout-seam-blend-playbook.md
```

---

## 12. Recommended Folder Inside Repo

```text
/01-framer-mcp-playbooks
```

Secondary related folders for future split-outs:

```text
/02-claude-code-prompts
/03-image-asset-workflows
/06-debugging-rules
/07-aura-brand-systems
```

---

## 13. Agent-Ready Summary

This chat created a reusable Framer MCP workflow for building Aura Digital cinematic web layouts with Claude Code.

The key system is:

- Build native Framer layers first
- Keep 100vh sections intact
- Avoid full-page overlays
- Avoid random transition bars
- Use exact asset URLs via Cloudinary
- Use Framer MCP with tightly scoped Claude prompts
- Use image generation for clean background plates, not baked-in UI
- Convert to components only after layout is visually approved

For the 4-page template, maintain viewport-height pages and use subtle localized seam treatments only if they improve the design. If seam gradients create hard bars, use image-based feathered seam assets or remove transition overlays entirely.

For the Aura Digital homepage, build a single premium homepage using a clean scenic background plate, then create all text, buttons, and 9 placeholder cards as native editable Framer layers. The 9 cards should be arranged in 3 rows of 3 under the labels `TEMPLATES`, `CREATIVE BUILDS`, and `AI MOTION CONCEPTS`.

Future agents should prioritize visual preservation, scoped edits, clean layer hierarchy, and exact Framer implementation over broad redesigns.

---

# Final Save Instructions

Name the markdown file:

```text
aura-digital-framer-mcp-layout-seam-blend-playbook.md
```

Place it in this repo folder:

```text
/01-framer-mcp-playbooks
```

Primary classification:

```text
SOP
```

Secondary classifications:

```text
Framer MCP rule set
Claude Code prompt snippet library
Aura Digital agent instruction
Image asset workflow note
```
