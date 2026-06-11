# Aura Moon / Aura Creative Framer MCP Troubleshooting Playbook

## 1. Chat title / topic

**Aura Moon / Aura Creative — Framer MCP, Claude Code, Cloudinary, image asset, and layout troubleshooting**

This chat focused on rebuilding an Aura Creative landing page in Framer using a cinematic moon/purple visual system, while troubleshooting repeated failures from Framer MCP, Claude Code, image generation, local HTML builds, Cloudinary imports, and display color mismatch across screens.

---

## 2. Main problem or build goal

Build a premium, cinematic **Aura Creative** homepage/site that matches a visual reference as closely as possible.

Core site structure:

- **Page 1 / Hero:** full viewport hero image with Aura branding, nav, footer-style hero labels, and no separate service cards.
- **Page 2 / Services:** 100vh section with left intro text and three service rows: Visual, Digital, Creative.
- **Page 3 / About:** tall image section using the full sitting-man image, fit-content or image-height based.
- **Page 4 / Contact:** 100vh contact section with simple CTA, email link, phone link, social/location info, and footer.

Main recurring issue:

> The agents kept interpreting the design creatively instead of mechanically matching the reference. This caused layout drift, oversized text, broken stacks, overlapping text, card misplacement, bad image crops, and incorrect section sizing.

---

## 3. Tools used

- Framer
- Framer MCP
- Claude Code
- Claude
- ChatGPT
- ChatGPT image generation/editing
- Cloudinary
- Local HTML / Node preview server
- Windows File Explorer
- Chrome local preview
- Photoshop / Lightroom suggested for image correction
- Windows display/color profile settings

Repo target:

`https://github.com/Plungerman232/Framer-MCP-Playbook`

---

## 4. What worked

### Use Framer MCP for structure, not creativity

Best instruction style:

> “Build this exact section using these exact frames, slots, images, dimensions, and positions.”

Avoid:

> “Make it premium / match the vibe / recreate the mood.”

Framer MCP worked better when given narrow mechanical tasks:

- preserve existing section height
- place image at exact fill mode
- create three rows
- add dividers
- add text blocks
- stop after one section

### Work one section at a time

The full-site prompt repeatedly failed because Claude Code/Framer MCP ran out of context and tried to fix too many things at once.

Best build order:

1. Hero
2. Page 2 services
3. Page 3 about image/text
4. Page 4 contact/footer
5. Sticky nav and effects
6. Responsive variants

### Use baked hero image when exact hero visual matters

For the hero, the cleanest decision was:

- use the completed hero image **with text already baked in**
- do not recreate all hero text/icons/nav as editable Framer layers
- add a real sticky header only after the user scrolls past the hero

This avoids duplicate text at the top of the page and preserves the exact hero look.

### Sticky header can still work with a baked hero

Recommended setup:

- hero image includes the perfect baked-in nav/title/text
- separate sticky/fixed header exists in Framer
- sticky header opacity is `0` while hero is visible
- sticky header fades in after the hero scrolls away
- sticky header uses a subtle dark glass/blur backing

### Cloudinary URLs worked better than local files for Framer MCP

Useful Cloudinary assets:

```text
Hero no text:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780456619/Hero_Image_No_Text_mngdz8.png

Hero with text:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780456619/Hero_With_Text_nup4tv.png

Visual Page 2:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780456617/Visual_Page_2_cn3cqn.png

Digital Page 2:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780456619/Digital_Page_2_stnqzz.png

Creative Page 2:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780456617/Creative_Page_2_ythdvg.png

Aura Home Page 3 Image:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780456618/Aura_Home_Page_3_Image_rihdwh.png
```

### Editing an exact image worked better than regenerating a similar image

For removing text from the hero image, the best instruction was not:

> “Generate a similar hero image without text.”

It was:

> “Use this exact image as the base. Remove only the text and symbols. Fill in the removed areas with surrounding background. Preserve the exact moon, colors, sharpness, mountain definition, water reflection, and composition.”

### Framer image color mismatch was usually not a Framer quality setting

Likely causes:

- display profile differences
- HDR / Night Light / adaptive brightness
- laptop screen crushing shadows
- different gamma/contrast between monitor and laptop
- overlays/blend modes/effects in Framer
- pasted images instead of uploaded assets

Best practical fix:

- upload high-quality PNG through **Assets → Upload**
- opacity `100%`
- blend mode `Normal`
- no overlays/effects/filters
- export images in **sRGB**
- slightly lift shadows/midtones so the image survives darker screens

---

## 5. What failed

### Full-site one-shot prompts

Large prompts telling Claude Code or Framer MCP to build the whole site at once caused:

- context exhaustion
- broad creative interpretation
- inconsistent text sizing
- broken stack behavior
- overlapping sections
- bad crops
- old nodes remaining
- white default backgrounds
- hero/button/card placement drifting

Reusable failure rule:

> Do not ask Framer MCP to rebuild a full visual website in one pass when exact layout matters.

### Pure code/HTML/TSX did not solve visual precision

Claude suggested code would work better, but the coded version performed worse for this project because the goal was exact visual recreation and manual layer control.

Problems:

- code did not match the visual reference closely enough
- HTML file was not directly pasteable into Framer
- Framer requires React/TSX code components, not raw HTML
- local server created port conflicts
- code structure added another troubleshooting layer

Final call:

> Use code only for isolated effects or possible Framer code components. Use Framer MCP/manual Framer layers for the page layout.

### Hero service cards/buttons caused too many problems

The three Visual/Digital/Creative cards on the hero repeatedly:

- got clipped
- moved between page 1 and page 2
- were affected by fit/stack/container behavior
- became hard to manually correct
- created layout instability

Final decision:

> Remove hero cards from the hero page. Use nav links for Visual/Digital/Creative. Reuse the card visuals later on their respective pages or in Page 2.

### Relative stacks caused layout problems

Stacks were useful for flow layout, but some text/card areas needed fixed visual placement. Relative positioning caused elements to push or wrap unexpectedly.

Common symptoms:

- text stack could not be dragged freely
- heading wraps caused text below to overlap
- row content shifted unexpectedly
- card row jumped under hero

Fix direction:

- preserve outer section as a clean frame/stack
- use fixed/absolute frames inside that section when exact placement is required
- use auto-layout stacks only where content needs to push other content naturally

### Hand-positioned fixed frames caused overlapping text

The Page 2 overlap came from text blocks with fixed positions/heights. When a heading wrapped to more lines, the text below did not move down.

Reusable diagnosis:

> If text wraps but the content below does not move, the layout is not flowing. It is fixed-positioned or fixed-height. Rebuild that content block as an auto-layout stack.

### Framer MCP cannot reliably create custom SVG icons

Repeated attempts to create SVG icons through MCP wasted context.

Fix:

- use simple text symbols where possible
- use existing Framer icons if available
- import icon images/SVG manually
- do not let the agent spend many calls trying to synthesize SVG icons

### Local server port conflict

The local build failed with:

```text
Error: listen EADDRINUSE: address already in use :::3000
```

Cause:

- another local server already used port `3000`

Fix:

- open `http://localhost:3000` and check what is running
- close old terminal/server
- or ask Claude Code to change server to `3001`
- add auto-port fallback in future projects

### Wrong Framer settings panel for image quality

Workspace settings are not image quality settings.

Correct place:

- select image layer
- right panel
- Fill / image thumbnail
- Effects
- Overlays
- Opacity
- Blend
- Fill mode / Fit mode
- Position

---

## 6. Final decisions

### Final build strategy

Use **Framer MCP + manual Framer layer control**, not pure code, for the visual site.

### Final page structure

- **Page 1:** 100vh hero using baked hero image with text
- **Page 2:** 100vh services layout
- **Page 3:** fit-content/tall image section using full Page 3 sitting-man image
- **Page 4:** 100vh contact/footer section

### Final hero strategy

Use the baked hero with text for the visible hero page.

Then add a separate sticky header that:

- is invisible on the hero
- fades in after scrolling
- has a subtle glass/dark backing
- contains real clickable nav links

### Final services strategy

Build Page 2 separately and mechanically:

- left intro block
- right service list
- three rows
- one thumbnail per row
- number/title/details/arrow/divider
- match reference image rather than inventing a new composition

### Final effects strategy

Do not add effects until the static layout is approved.

Effects to add after layout:

- preloader
- sticky nav fade-in
- subtle hero atmospheric movement
- light scan/glitch line
- water shimmer/glisten
- slow cloud/mist movement
- page transition / nav click movement effect

---

## 7. Reusable rules

### Rule 1 — Do not let the agent reinterpret the design

Bad:

```text
Make it premium and cinematic like the reference.
```

Good:

```text
Match the reference mechanically. Do not reinterpret the design. Preserve the section size, image crop, text scale, alignment, and spacing.
```

### Rule 2 — One section per Framer MCP session

Build or repair one section at a time:

1. Page 1 hero
2. Page 2 services
3. Page 3 about
4. Page 4 contact
5. effects
6. responsive variants

### Rule 3 — Preserve existing Framer section frames

```text
Do not change the outer page frame, breakpoint frame, section height, or root stack structure.
Only add/edit children inside the target section.
```

### Rule 4 — Use Cloudinary URLs when MCP asset handling is unreliable

Cloudinary URLs reduce local file ambiguity and avoid some Framer import issues.

### Rule 5 — Avoid full-site rebuilds when exact matching matters

If the goal is exact visual recreation, do not tell the agent to rebuild the whole site at once.

### Rule 6 — Use baked images for visually complex hero sections

For a cinematic hero with exact text, symbols, and image grading, a baked hero image can be more reliable than editable text layers.

### Rule 7 — Use sticky header after hero, not on top of baked hero

If nav text is already baked into the hero image, use a real sticky header only after scrolling past the hero.

### Rule 8 — For text overlap, switch to auto-layout stacks

If text overlaps because headings wrap, the content block must become a vertical auto-layout stack with real gaps.

### Rule 9 — For exact visual position, use fixed/absolute children inside a stable parent

Use fixed or absolute positioning only inside a known 100vh section frame. Do not let absolute children escape the page section.

### Rule 10 — Do not paste images from clipboard into Framer

Use:

```text
Assets → Upload → select image → place/use as fill
```

Then verify:

- Opacity: 100%
- Blend: Normal
- Effects: Off
- Overlays: None
- Fill mode: Fill or Fit as needed
- Position: Center

### Rule 11 — Export images in sRGB

For cross-device consistency:

- use sRGB profile
- slightly lift shadows/midtones
- avoid crushing black edges
- test on laptop and external monitor

### Rule 12 — Never share Framer MCP session URL publicly

The MCP panel warns that the URL contains a personal session key. Do not paste it into public repos, screenshots, or reports.

---

## 8. Reusable prompt snippets

### Section-only Framer MCP prompt

```text
Do not rebuild the whole site.

Only work on [SECTION NAME] right now.

The section already exists and has the correct outer size. Preserve the outer frame, breakpoint, root stack, width, and height.

Only add or edit child layers inside this section.

Match the provided reference mechanically:
- same text
- same spacing
- same visual hierarchy
- same image placement
- same alignment
- same typography style
- same divider positions

Do not reinterpret the design.
Do not add effects.
Do not work on other sections.
Stop after this section is complete and report exactly what changed.
```

### Page 2 services prompt

```text
Only work on Page 2.

Page 2 is already set to 100vh. Do not change the Page 2 outer frame height or breakpoint structure.

Create the services section to match the reference:

Left column:
- small label: [ WHAT WE DO ]
- large serif headline:
  CRAFTING
  EXPERIENCES
  THAT RESONATE.
- small uppercase paragraph
- LEARN MORE link

Right column:
Create 3 service rows.

Each row must include:
- large number: 01 / 02 / 03
- image thumbnail
- service title: VISUAL / DIGITAL / CREATIVE
- service details text
- arrow on far right
- thin divider line

Use these image URLs:
Visual: [VISUAL_URL]
Digital: [DIGITAL_URL]
Creative: [CREATIVE_URL]

Important layout rules:
- Do not let text overlap.
- Use auto-layout stack for each text group.
- Use fixed row heights if needed.
- Keep dividers thin and subtle.
- Keep the section transparent/dark, no white background.
- Match the reference, do not redesign.
- Stop after Page 2 only.
```

### Hero baked image + sticky nav prompt

```text
Use the provided hero image with text as the complete visible hero background.

Do not recreate the hero title, subtitle, icon row, footer text, or nav as separate visible layers on top of the hero, because they are already baked into the image.

Create a separate sticky/fixed navigation header that is hidden at the top of the page and fades in only after the user scrolls past the hero.

Sticky nav design:
- fixed top
- subtle dark translucent glass background
- slight blur
- thin bottom border
- small uppercase letter-spaced nav links
- links: VISUAL, DIGITAL, CREATIVE, ABOUT, CONTACT
- opacity 0 on hero
- fade to opacity 1 after hero section
```

### Cloudinary asset amendment

```text
Use these Cloudinary-hosted assets instead of local files or old Framer cached images.

Hero no text:
[URL]

Hero with text:
[URL]

Visual Page 2:
[URL]

Digital Page 2:
[URL]

Creative Page 2:
[URL]

Aura Home Page 3:
[URL]

Do not use old framerusercontent hashes. Do not reuse cached uploads. Replace the image fills with these exact Cloudinary URLs.
```

### Framer image quality troubleshooting prompt

```text
Check the selected image layer only.

Do not open workspace settings.

Verify:
- opacity is 100%
- blend mode is Normal
- no effects
- no overlays
- no filters
- no dark gradient layer above it
- image fill mode is correct
- image position is correct
- the asset was uploaded through Framer Assets, not pasted from clipboard
```

### Local server port fallback prompt

```text
Update the local dev server so it does not fail if port 3000 is already in use.

Requirements:
- try port 3000 first
- if unavailable, automatically try 3001, then 3002
- print the final local URL clearly in the terminal
- update start.bat so double-clicking it runs the server
- do not require manual port troubleshooting
```

---

## 9. SOPs / step-by-step workflows

### SOP 1 — Framer MCP exact layout build

1. Create section frames manually in Framer first.
2. Lock or preserve outer section structure:
   - Page 1: 100vh
   - Page 2: 100vh
   - Page 3: fit content/tall image
   - Page 4: 100vh
3. Upload or host images on Cloudinary.
4. Give Claude Code/Framer MCP one section only.
5. Tell it not to touch any other section.
6. After it finishes, visually inspect in Framer.
7. Manually fix layer positions if needed.
8. Only then move to the next section.
9. Add effects last.

### SOP 2 — Page 2 services rebuild

1. Keep Page 2 section at 100vh.
2. Create a left content column.
3. Create a right service list frame.
4. Build each row as a contained row component/frame.
5. Use auto-layout inside text blocks.
6. Use fixed dimensions for thumbnails.
7. Use subtle divider lines.
8. Confirm no text overlap.
9. Confirm image thumbnails match correct services.
10. Stop and review before adding animations.

### SOP 3 — Hero image workflow

1. Decide whether hero text must be editable.
2. If exact visual match matters more than editability, use baked hero image with text.
3. Upload hero with text to Framer/Cloudinary.
4. Set section to 100vh.
5. Set image to fill the section.
6. Avoid duplicate text layers on top.
7. Add real sticky nav separately.
8. Hide sticky nav until after hero scroll.
9. Test preview/publish.

### SOP 4 — Textless image generation/editing

Use this approach when you need a clean version of a generated image:

1. Start from the exact image with text.
2. Ask for an edit, not a new generation.
3. Remove only text and symbols.
4. Fill removed areas with surrounding background.
5. Preserve:
   - exact color
   - sharpness
   - moon
   - mountains
   - water
   - glow
   - composition
6. Compare against text version.
7. Reject if the new image is darker, softer, less saturated, or compositionally different.

### SOP 5 — Cross-display color consistency

1. Compare image on external monitor and laptop.
2. On Windows laptop, check:
   - HDR off
   - Night Light off
   - adaptive brightness off
   - color profile set to sRGB if available
3. In image editor:
   - Shadows: +10 to +15
   - Exposure: +0.05 to +0.15
   - Blacks: +5 to +10
   - Vibrance/Saturation: +2 to +5 max
4. Export full-size PNG with sRGB profile.
5. Upload through Framer Assets.
6. Test on both screens.

### SOP 6 — Local HTML/Framer code workflow

1. If Claude Code creates an HTML file, preview it in browser.
2. Do not paste raw HTML directly into Framer.
3. For Framer, convert to a React/TSX code component.
4. If using local server and port fails:
   - open `localhost:3000`
   - close old server
   - or change to `3001`
5. For Framer handoff, prefer either:
   - direct Framer MCP layers, or
   - one self-contained Framer code component
6. Do not mix raw HTML expectations with Framer TSX component requirements.

### SOP 7 — Effects workflow

Add effects after static layout is approved.

Recommended order:

1. Preloader
2. Sticky nav fade-in
3. Subtle hero shimmer/glisten
4. Slow cloud/mist movement
5. Light scan/glitch line
6. Page transition/nav click movement
7. Responsive cleanup

Effects must be isolated so they do not break layout.

---

## 10. Future agent ideas

### Framer Section Builder Agent

Builds one Framer section at a time from a reference, preserves outer frame dimensions, stops after each section, and reports exact changes.

### Framer Layout QA Agent

Checks if a section visually matches the reference and flags:

- text too large
- wrong crop
- overlap
- wrong alignment
- missing transparent backgrounds
- bad spacing

### Image Asset Consistency Agent

Compares text and no-text image versions and rejects regenerated images when exact inpainting is required.

### Cloudinary Asset Mapper Agent

Stores asset names and URLs, gives clean amendments for Claude Code/Framer MCP, and prevents old cached `framerusercontent` hashes from being reused.

### Prompt Slicer Agent

Converts a huge full-site prompt into section-by-section Framer MCP tasks to prevent context exhaustion.

### Framer Import Troubleshooter Agent

Diagnoses why an image looks different in Framer by checking opacity, blend mode, overlays, effects, fill mode, and browser preview.

---

## 11. Recommended filename

`aura-moon-framer-mcp-layout-troubleshooting.md`

---

## 12. Recommended folder inside the repo

Recommended folder:

`/01-framer-mcp-playbooks`

Secondary relevant folders:

- `/03-image-asset-workflows`
- `/06-debugging-rules`
- `/07-aura-brand-systems`
- `/05-agent-instructions`

Best single folder choice:

`/01-framer-mcp-playbooks`

---

## 13. Agent-ready summary

```text
We are building an Aura Creative / Aura Moon cinematic landing page in Framer.

Do not rebuild the whole site in one pass. Use Framer MCP one section at a time and preserve the manually created section frames.

The user wants exact visual matching, not creative reinterpretation.

Final structure:
- Page 1 hero: 100vh, baked hero image with text.
- Page 2 services: 100vh, left intro block plus three service rows.
- Page 3 about: fit-content/tall image using full Page 3 image.
- Page 4 contact: 100vh contact/footer section.

Use Cloudinary URLs instead of local/native assets when working through MCP.

Do not create hero service cards/buttons on Page 1. They caused clipping and placement issues. Use nav links instead.

For the sticky nav:
- hide it over the baked hero
- fade it in after the hero
- use subtle glass/dark background

For Page 2:
- build only Page 2 first
- avoid fixed-position text overlap
- use auto-layout stacks for text groups
- use exact thumbnails, dividers, numbers, titles, arrows

For effects:
- add only after static layout approval
- keep preloader, glitch/scan line, shimmer, and sticky nav effects isolated

Important failure lessons:
- Pure code/HTML did not improve visual matching.
- Full-site prompts caused context exhaustion and layout drift.
- Framer MCP cannot reliably generate SVG icons.
- Framer image mismatch is often display profile, overlay, blend mode, or paste/import issue.
- Never share the Framer MCP session URL because it contains a personal session key.
```

---

## Final classification

This report should become:

- **SOP:** yes
- **Prompt snippet collection:** yes
- **Agent instruction:** yes
- **Rule/debugging reference:** yes

Best primary type:

**SOP + Agent Instruction**

Best repo placement:

`/01-framer-mcp-playbooks/aura-moon-framer-mcp-layout-troubleshooting.md`
