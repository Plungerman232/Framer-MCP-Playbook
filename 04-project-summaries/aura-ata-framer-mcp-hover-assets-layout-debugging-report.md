# Aura TS + ATA Framer MCP Build Notes: Claude Code Prompting, Hover Effects, Image Compression, and Layout Debugging

## 1. Chat Title / Topic

**Aura TS + ATA Framer MCP Build Workflow — Claude Code Prompting, Image Asset Handling, Hover Animations, Layout Fixes, and Web-Build Troubleshooting**

This chat covered two active Framer projects:

1. **Aura TS / Aura Creative**
   - Premium cinematic creative studio site.
   - Dark cosmic/purple visual system.
   - Framer MCP + Claude Code used to build and adjust sections, text, spacing, animation layers, Page 2 button hover videos, Page 3 layout, and contact section.

2. **ATA / Athletes Training Athletes**
   - Athletic training company site.
   - Dark premium sports brand system.
   - Focus on hero section, athlete proof cards, Foundation Athletes / THE FIRST 10, ATA Alumni, hover image animations, image compression, and code-component troubleshooting.

---

## 2. Main Problem or Build Goal

The main goal was to use **Claude Code connected through Framer MCP** to build and refine premium Framer websites while keeping full creative control through precise prompts.

The major build goals were:

- Create a premium **Aura Creative** site based on a reference layout.
- Add exact typography, spacing, headers, section transitions, footer/contact layout, and cinematic animation effects.
- Add hover/click animation videos to Page 2 service cards: Visual, Digital, Creative.
- Add subtle Framer-native hero effects: rolling scanline, ambient storm glow, shield-world shimmer, and faint glitch energy.
- Build a premium **Athletes Training Athletes** site with a serious training-brand feel.
- Create athlete card components with:
  - main card image,
  - three hover images,
  - background blur/dim effect,
  - premium hologram-style hover layout.
- Troubleshoot image compression, object-position, Framer code-component image props, and Cloudinary/local asset replacement.
- Develop reusable prompt patterns for Claude Code so it changes exactly what is requested and does not randomly redesign working sections.

---

## 3. Tools Used

### Framer
Used as the main visual builder and preview environment.

Key Framer concepts used:
- Breakpoints: Desktop Lg, Desktop, Tablet, Phone.
- Native stacks and frames.
- Code components for athlete hover cards.
- Image/video layers.
- Fixed vs relative sizing.
- Object fit and object position.
- Section height, padding, z-index, divider lines, and full-width frames.
- Live View testing at specific widths like 1390px and 1200px.

### Framer MCP
Used as the bridge between Claude Code and the Framer project.

Important MCP notes:
- Keep the Framer MCP panel open while Claude Code is working.
- If MCP disconnects mid-task, do not send more prompts until it reconnects and Claude finishes or errors out.
- Never share or commit the MCP server URL because it contains a personal session key.

### Claude Code
Used as the main build/edit agent.

Main use cases:
- Editing Framer layout.
- Adding/replacing code-component image props.
- Uploading local files or generating public image references.
- Renaming stack/layer structures.
- Adding hover effects, blur effects, and animation behavior.
- Debugging layout issues.

### Runway
Used for short cinematic hover animation videos.

Use cases:
- Page 2 Visual animation.
- Page 2 Digital animation.
- Page 2 Creative animation.
- Potential future hero ambient video.

Important Runway lesson:
Runway often adds its own interpretation, so prompts must say:
- keep exact composition,
- no new objects,
- no camera movement unless requested,
- subtle motion only,
- no text/logos/UI,
- avoid warping/flickering.

### Cloudinary
Used to host image assets publicly.

Use cases:
- Replacing placeholder image URLs in code components.
- Hosting Xavier Hutchinson main and hover images.
- Testing whether Cloudinary URLs worked better than local/temporary image references.

### TinyJPG / TinyJPEG
Used to compress large JPEGs before upload.

Key result:
Compressing large high-resolution images solved a lot of graininess/blurriness caused by Framer/browser/CDN rendering.

### Windows File Explorer / Paint
Used for local image management and resizing.

Common paths:

```text
C:\Users\Charl\Desktop\Ata\Copy Right\
C:\Users\charleshockey3\Desktop\Ata\Copy Right\
C:\Users\Charl\Desktop\New Aura Hero Site\Color Graded\
```

### GitHub / Codex
The final markdown reports are intended to be saved into:

```text
https://github.com/Plungerman232/Framer-MCP-Playbook
```

Codex was not directly used in this chat, but the workflow assumes future Codex organization of markdown reports, prompts, SOPs, and agent rules into the playbook repo.

---

## 4. What Worked

### Precise Claude Code prompts worked best

Claude performed much better when instructions were specific and scoped.

Good format:

```text
Update only [specific card/section].
Use this folder/path.
Replace only [specific image prop].
Do not change layout, sizing, animation, blur, spacing, typography, or other cards.
After finishing, confirm exact files/values changed.
```

Vague prompts like “move it up” or “make it closer” were not reliable. Pixel targets and before/after values worked much better.

### Image compression fixed visual quality issues

Some high-resolution action shots looked grainy/blurry in Framer even though they looked sharp locally.

The working solution:
- Compress images with TinyJPG/TinyJPEG.
- Export web-sized copies.
- Replace existing image props with compressed versions.

Recommended export sizes:
- Card/profile images: **1000–1400px wide**
- Hover/action images: **1400–1800px wide**
- JPEG quality: **85–92%**
- Color profile: **sRGB**

A 10 MB JPEG dropping to 3 MB is normal and often still excellent for web.

### Per-card object-position controls worked better than global image changes

When only one athlete image was cropped wrong, the correct fix was not global object-fit/object-position. It was a per-card or per-image positioning prop.

Useful examples:

```text
hoverPos1
hoverPos2
mainPos
objectPosition: "center 40%"
objectPosition: "center center"
objectPosition: "center top"
```

Key lesson:
Do not change global object-position when only one athlete/photo is wrong.

### Framer code-component image replacement worked

For the ATA athlete cards, the image placeholders/props inside the code component could be replaced with:
- local images uploaded/converted to URLs,
- Cloudinary URLs,
- compressed images,
- named files inside athlete folders.

Working image-swap pattern:

```text
Replace only the image source/prop for [athlete].
Keep animation, layout, sizing, spacing, blur, text, and other cards unchanged.
```

### Hover card effect became a reusable pattern

The Foundation Athletes cards developed a strong reusable hover system:

- active athlete card stays sharp,
- background/other cards blur and dim,
- three hover images appear above the active card,
- hover images have subtle overlap,
- premium glow/hologram feel,
- no heavy collage look,
- hover images are positioned as overlays and should not push layout.

This became one of the most reusable interaction patterns from the chat.

### Pixel-specific Framer layout prompts worked best

For Aura TS, layout fixes improved when prompts included exact targets.

Examples:

```text
Page 2 height: 600–650px
Page 2 content top: 65px from top
Right service list top: 35–45px
Page 3 image width: 720px
Page 3 image right edge: around 1280px from left edge
Right margin: 150–170px
Approximate image x position: 560px
```

Claude needs specific measurement targets, especially when matching a visual reference.

### Short correction prompts worked better than repeating huge instruction lists

Once Claude already had the project context, shorter correction prompts were more effective.

Example:

```text
Fix Camryn Simmons Hover Image 1 only.
Move it down slightly from the current position.
Keep the ball visible overhead.
Do not change image source, sizing, layout, animation, or any other athlete.
Tell me the before/after object-position value.
```

---

## 5. What Failed

### Vague positioning language caused wrong results

Phrases like:
- “move it up”
- “make it closer”
- “center it”
- “fix the positioning”
- “make it look like the reference”

were not enough. Claude often interpreted these too broadly.

Better:

```text
Set top padding to 65px.
Move image right edge to 1280px.
Change hoverPos1 from center 65% to center 45%.
Reduce Page 2 height to 625px.
```

### Claude sometimes changed the wrong layer

Example:
The prompt accidentally told Claude to center Tori’s main card image, but the actual issue was Tori Hover Image 2. This caused the user to pause the command.

Rule:
Never say “center [athlete] image” if the issue is only one hover image. Always name:
- athlete,
- exact image slot,
- exact desired direction,
- exclusions.

Correct:

```text
Do NOT touch Tori’s main card.
Only adjust Tori Grambo Hover Image 2.
Move the image downward slightly from the current position.
```

### MCP disconnects can interrupt tasks

When Framer MCP disconnected during Claude edits, the safest response was:

```text
Wait. Do not send another prompt.
Reconnect Framer MCP.
Let Claude finish or error out.
If the result is wrong, tell it to stop and revert only the last attempted changes after the disconnect.
```

### Some hidden Framer lines were hard to locate manually

The Aura Page 2 → Page 3 divider issue showed that a visible line might be:
- a child frame,
- a border-bottom,
- a row divider,
- a pseudo-divider baked into a row stack,
- an absolute frame,
- or hidden behind another image due to z-index.

The line under Creative needed to be removed from the row, while the actual page divider needed to be full-width and placed between Page 2 and Page 3 above the Page 3 image.

### High-res images sometimes looked worse than compressed images

Uploading huge images directly caused Framer/browser/CDN rendering to look grainy or blurry.

Conclusion:
For card/hover images, web-optimized compressed copies are better than massive originals.

### Cloudinary/local uploads need exact naming and mapping

Claude can upload or reference images, but the prompt must clearly say:
- which folder,
- which file,
- which athlete,
- which slot,
- what not to touch.

When images were unnamed, Claude could choose the wrong one. Named files like:

```text
Main Card Compressed
Hover Image 1
Hover Image 2 Compressed
Hover Image 3
```

worked better.

---

## 6. Final Decisions

### Aura TS / Aura Creative

Final design direction:
- Dark cosmic/purple premium creative studio.
- Keep the hero iconic and stable.
- Use subtle Framer-native animation before spending more Runway credits.
- Add a rolling scanline/glitch overlay to the hero.
- Add subtle shield-world shimmer and storm-energy pulse.
- Add Page 2 hover videos for Visual, Digital, Creative.
- Keep Page 4 contact simple and chilled, not corporate.

Aura contact section content:

```text
[ GET IN TOUCH ]

LET’S CREATE
SOMETHING
TIMELESS.

Have a project in mind?
Reach out and let’s talk.

EMAIL
Coming soon

INSTAGRAM
@enter_aura

PHONE
Coming soon
```

Aura Page 2:
- Page 2 should be shorter than viewport height.
- Page 2 content should start closer to the hero.
- Page 2 buttons should use hover animation videos.
- Background outside active image can blur/dim subtly on hover.

Aura Page 3:
- Image should align right with the end of Page 2 row lines/arrows.
- Do not just make Page 3 height equal to image height if it causes divider problems.
- Divider between Page 2 and Page 3 should be full-width and not hidden behind the Page 3 image.

### ATA / Athletes Training Athletes

Final design direction:
- Dark premium athletic brand.
- Minimal hero text.
- Strong proof through real athlete cards.
- Use “Foundation Athletes / THE FIRST 10” as a credibility anchor.
- Use hover image animations for Foundation cards.
- ATA Alumni gets profile images but not full hover animations unless requested later.

ATA hover effect:
- Keep active card sharp.
- Blur/dim surrounding cards.
- Show three hover images above active card.
- Slight overlap is fine; heavy collage overlap is not.
- Hover images should feel holographic/premium, not like a random photo pile.

Image pipeline:
- Compress images before using in Framer/code components.
- Use local folder names by athlete.
- Keep Xavier and Charlie untouched unless specifically requested.
- Camryn main card is copyright-approved and should not be replaced.
- Adjust individual hover image crops with per-image position values.

---

## 7. Reusable Rules

### Rule 1 — Always scope Claude Code edits narrowly

Bad:

```text
Fix the card images.
```

Good:

```text
Update only Tori Grambo Hover Image 2 inside the Foundation Athletes code component. Do not touch her main card, other hover images, layout, sizing, animation, blur effect, or any other athlete.
```

### Rule 2 — Use pixel values for layout matching

Bad:

```text
Move Page 2 closer to Page 1.
```

Good:

```text
Set Page 2 height to 600–650px. Move the Page 2 content stack so the label starts 65px below the top of Page 2.
```

### Rule 3 — Ask Claude to report before/after values

For positioning fixes, always ask:

```text
After applying, tell me the exact before/after object-position or prop values changed.
```

This makes it easier to nudge the next fix.

### Rule 4 — Do not globally change object-fit/object-position for one bad image

If only one photo is off, add or adjust a per-image prop.

Example:

```text
mainPos
hoverPos1
hoverPos2
hoverPos3
```

### Rule 5 — Compress images before blaming Framer

If a high-res image looks grainy/blurry:
1. Compress it with TinyJPG/TinyJPEG.
2. Resize to a reasonable web dimension.
3. Replace the asset.
4. Only then troubleshoot overlays/object-position.

### Rule 6 — Pause if MCP disconnects

When MCP disconnects:

```text
Stop prompting.
Reconnect MCP.
Let Claude finish or fail.
Only then send a correction/revert prompt.
```

### Rule 7 — Never expose MCP URLs

MCP URLs contain session keys. Do not:
- paste them into repo files,
- share them publicly,
- include them in markdown reports,
- commit screenshots that show them.

### Rule 8 — Do not rebuild working components

Unless specifically needed:

```text
Do not rebuild the component.
Use the existing component/code structure.
Only replace the requested props/image sources.
```

### Rule 9 — Hero effects should be subtle first

For premium cinematic sites:
- start with Framer-native scanline/glow/shimmer,
- keep opacity low,
- use slow loops,
- avoid obvious RGB glitch,
- use Runway only if Framer effects still feel too static.

---

## 8. Reusable Prompt Snippets

### Snippet A — Single image replacement in a code component

```text
Update only [ATHLETE NAME] in the existing Foundation Athletes code component.

Replace only [main image / hover image 1 / hover image 2 / hover image 3] with the file from:

[LOCAL FOLDER PATH]

Do not change:
- card size
- layout
- hover animation
- blur effect
- hover spacing
- styling
- text
- any other athlete card

After updating, confirm the exact file/source used.
```

### Snippet B — Per-image crop/focal point nudge

```text
Fix [ATHLETE NAME] — [IMAGE SLOT] only.

The image is currently sitting too [high/low/left/right].
Move the image [up/down/left/right] slightly inside the frame using the existing object-position/position prop.

Do not change:
- image source
- card size
- hover layout
- animation
- blur effect
- any other image slot
- any other athlete

After applying, tell me the exact before/after object-position value.
```

### Snippet C — Replace athlete images from labeled folder

```text
Update only [ATHLETE NAME] in the Foundation Athletes / THE FIRST 10 section.

Use the labeled files from:

[ATHLETE FOLDER PATH]

Map them as:
- Main Card = main card/profile image
- Hover Image 1 = hover image 1
- Hover Image 2 = hover image 2
- Hover Image 3 = hover image 3

Only replace image sources/props in the existing code component.

Do not change layout, sizing, hover animation, blur effect, spacing, styling, text, or any other athlete.
```

### Snippet D — Remove gradient/shimmer overlay from photos

```text
Temporarily remove any linear-gradient, shimmer, glass, or overlay layer that sits directly on top of athlete photos.

Only remove overlays crossing over the actual photo surfaces.

Do not change:
- image URLs
- crops
- object-fit/object-position
- card sizing
- layout
- hover animation
- background blur/dim effect

After finishing, confirm whether any gradient/shimmer overlays were removed from the photo surfaces.
```

### Snippet E — MCP disconnect recovery

```text
Framer MCP disconnected during the last task.

Stop and do not continue any new changes until MCP is reconnected.

After reconnecting, inspect the project state. If the last task only partially applied, either complete only the originally requested change or revert only the partial changes from after the disconnect.

Do not touch unrelated sections.
```

### Snippet F — Pixel-specific Aura Page 2 layout fix

```text
In “Aura TS (copy 2)”, adjust Page 2 using exact desktop targets.

Desktop Lg:
- Page 2 height: 600–650px
- Page 2 content top: about 65px from top of Page 2
- Right service list top: 35–45px from top of Page 2
- Left text block x: 70–80px
- Right service list x: 525–550px
- Bottom of third service row: around 540–570px from top of Page 2

Do not change typography, images, arrows, row styling, hero, Page 3, or Page 4.

After finishing, confirm exact height/top values.
```

### Snippet G — Full-width divider between Page 2 and Page 3

```text
Fix the Page 2 to Page 3 divider.

Remove the small orphan divider directly under the Creative row.

Add or reposition the real divider so it sits exactly between Page 2 and Page 3:
- position absolute at bottom of Page 2 or top of Page 3
- left: 0
- width: 100%
- height: 1px
- z-index above the Page 3 image
- subtle color: rgba(244,240,250,0.10–0.14)

Do not resize Page 3 image.
Do not change Page 2 layout.
Do not touch hero or contact section.

Confirm the orphan Creative line is gone and the full-width divider is visible.
```

### Snippet H — Aura hero ambient effects

```text
Build subtle Framer-native ambient animation effects on the hero section.

Do not redesign the hero.
Do not change image assets, text, layout, or spacing.

Add:

1. Rolling scanline/glitch line
- very thin horizontal line
- starts below header/nav
- travels downward over 12–15 seconds
- resets and loops
- very low opacity

2. Subtle atmospheric light pulse
- faint purple/lavender glow variation in sky
- slow pulse
- brightness shift only around 3–6%

3. Shield-world shimmer
- subtle atmospheric field texture
- slight movement or opacity shift
- no obvious hard pattern

4. Micro-flicker
- rare and extremely subtle
- no harsh RGB glitch or distortion

Keep all effects premium, cinematic, slow, and subtle.
After finishing, list added layers, opacity, timing, and tweakable settings.
```

### Snippet I — Page 2 video hover effect

```text
Add video-on-hover for the three Page 2 image cards.

Folder:
C:\Users\Charl\Desktop\New Aura Hero Site\Color Graded\

Files:
- Page 2 Button 1 Animation = Visual
- Page 2 Digital Button Animation = Digital
- Page 2 Button 3 Creative animation = Creative

Behavior:
- On hover, fade still image into matching video.
- Video autoplay muted loop playsinline.
- On hover end, fade back to still image.
- Transition: 250–400ms.
- object-fit: cover.
- No controls.

Add subtle immersive focus:
- dim/blur rest of Page 2
- active image/video stays sharp
- restrained, premium, cinematic

Do not change Page 2 layout, text, arrows, image sizes, spacing, hero, Page 3, or Page 4.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP 1 — Framer MCP + Claude Code editing workflow

1. Open Framer project.
2. Open Framer MCP panel.
3. Confirm MCP is connected.
4. Give Claude Code a narrow, scoped task.
5. Include:
   - project name,
   - section name,
   - exact layer/card/asset,
   - exact change,
   - what not to touch,
   - confirmation requirements.
6. Wait for Claude to finish.
7. Check Live View at target width.
8. If wrong, send a small correction prompt with exact before/after direction.
9. If MCP disconnects, stop and reconnect before prompting again.

### SOP 2 — Image asset preparation for Framer cards

1. Choose final image.
2. Crop if needed before upload.
3. Compress through TinyJPG/TinyJPEG.
4. Export:
   - card image: 1000–1400px wide,
   - hover image: 1400–1800px wide.
5. Use sRGB.
6. Rename files clearly:
   - `Main Card Compressed.jpg`
   - `Hover Image 1 Compressed.jpg`
   - `Hover Image 2 Compressed.jpg`
   - `Hover Image 3 Compressed.jpg`
7. Place inside athlete folder.
8. Tell Claude exactly which card and slots to replace.
9. Do not let Claude change layout or sizing during image replacement.

### SOP 3 — Fixing blurry or grainy Framer images

1. Confirm source image looks sharp locally.
2. Check if image is too large or uncompressed.
3. Compress and resize.
4. Replace only the image source.
5. If still blurry, check:
   - overlays,
   - linear gradients,
   - shimmer layers,
   - opacity layers,
   - filters,
   - object-fit/object-position,
   - browser scaling.
6. Remove overlays from photo surfaces for testing.
7. Restore only effects that do not degrade image clarity.

### SOP 4 — Athlete hover card build workflow

1. Build base athlete card.
2. Add main image.
3. Add text metadata.
4. Add hover image props:
   - hover image 1,
   - hover image 2,
   - hover image 3.
5. Add hover behavior:
   - active card sharp,
   - background blurred/dimmed,
   - hover images float above card.
6. Tune hover images:
   - same size,
   - slight overlap only,
   - centered above card,
   - no heavy collage.
7. Add per-image object-position props.
8. Test each card one at a time.
9. Never apply global crop changes for one athlete.

### SOP 5 — Reference layout matching in Framer

1. Screenshot current layout and reference.
2. Identify measurable differences:
   - section height,
   - top padding,
   - x positions,
   - right edge alignment,
   - gap sizes,
   - image dimensions.
3. Convert visual differences into numbers.
4. Prompt Claude with numeric targets.
5. Ask Claude to confirm exact values changed.
6. Recheck Live View.
7. Nudge using small deltas, not broad commands.

### SOP 6 — Runway animation prompt workflow

1. Use still image as source.
2. Decide if animation is:
   - hover card,
   - hero ambience,
   - section transition.
3. Prompt Runway to keep exact composition.
4. Specify motion only:
   - fog drift,
   - subtle glow pulse,
   - reflection shimmer,
   - locked camera.
5. Add negative instructions:
   - no new objects,
   - no text/logos,
   - no warping,
   - no camera shake,
   - no overexposure.
6. Export short loop.
7. Add to Framer as hover video:
   - muted,
   - loop,
   - playsinline,
   - no controls.

---

## 10. Future Agent Ideas

### Agent 1 — Framer MCP Layout Inspector
A Claude/Codex-style agent that:
- reads Framer layer structure,
- identifies hidden dividers/borders,
- reports section heights/paddings,
- suggests exact pixel changes before editing.

### Agent 2 — Framer Asset Replacer
An agent that:
- reads local asset folders,
- matches folder names to card names,
- maps `Main Card`, `Hover Image 1`, `Hover Image 2`, `Hover Image 3`,
- replaces only image props,
- reports unresolved folders.

### Agent 3 — Framer Image Quality Auditor
An agent that:
- detects oversized images,
- recommends compression dimensions,
- checks for overlays/filters causing grain,
- flags object-fit/object-position issues.

### Agent 4 — Prompt Compiler for Claude Code
An agent that converts casual user instructions into:
- scoped Claude Code prompt,
- exact exclusions,
- confirmation checklist,
- rollback prompt.

### Agent 5 — Aura Brand Animation Agent
An agent specialized in:
- dark cinematic Framer animations,
- scanline overlays,
- subtle glow pulses,
- premium hover effects,
- Runway prompt generation.

### Agent 6 — Framer Breakpoint QA Agent
An agent that:
- checks Desktop Lg, Desktop, Tablet, Phone,
- flags overflow/wrap issues,
- detects when 1440px fits but 1390px breaks,
- suggests padding/gap reductions.

---

## 11. Recommended Filename

```text
aura-ata-framer-mcp-hover-assets-layout-debugging-report.md
```

---

## 12. Recommended Folder Inside the Repo

Primary recommended folder:

```text
/04-project-summaries
```

Secondary useful copies/excerpts could later be split into:

```text
/01-framer-mcp-playbooks
/02-claude-code-prompts
/03-image-asset-workflows
/06-debugging-rules
/07-aura-brand-systems
```

---

## 13. Agent-Ready Summary

This chat documents a real Framer MCP production workflow across two active sites: Aura Creative and Athletes Training Athletes. The user relies on Claude Code through Framer MCP to modify Framer projects, but Claude must be given narrow, exact, measurable instructions. Vague layout language causes wrong edits. Pixel values, exact section/card names, image slot names, exclusions, and before/after confirmations are essential.

For ATA, the most important system is the Foundation Athletes hover card component. Each athlete card has a main image and three hover images. On hover, the active card stays sharp while the background dims/blurs and three hover images float above. The system works best when image replacement is isolated to code-component props and when each image has per-slot object-position controls. High-res images often looked grainy in Framer, so compressed web copies from TinyJPG/TinyJPEG became the preferred asset workflow.

For Aura, the main systems are cinematic dark layout matching, Page 2 service cards, Page 3 image alignment, Page 4 contact, and subtle Framer-native hero effects. Page 2 uses Visual/Digital/Creative service cards and should support hover videos. Hero ambience should be built natively first using a rolling scanline, subtle purple glow pulse, shield-world shimmer, and micro-flicker before spending extra Runway credits. All effects must remain premium and subtle.

Critical agent rules:
- Do not rebuild working components.
- Do not globally change object-position for one bad crop.
- Do not touch excluded cards like Xavier or Charlie unless asked.
- Use compressed image assets.
- Use exact file paths and image-slot mappings.
- Ask Claude to confirm exact values changed.
- If Framer MCP disconnects, stop, reconnect, then continue or revert only partial changes.
- Never expose MCP session URLs.
