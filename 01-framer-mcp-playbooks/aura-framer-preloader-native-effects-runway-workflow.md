# Aura Website Framer MCP / Claude Code Preloader + Animation Workflow Report

## 1. Chat Title / Topic

**Aura Website: Framer MCP, Claude Code, Native Effects, Preloader Routing, Runway Prompting, and Animation Troubleshooting**

This chat focused on building and refining the Aura Creative website in Framer using Claude Code/MCP, with special focus on hero-page navigation, cinematic preloaders, Page 2 animated service cards, native Framer atmospheric effects, and image/video asset workflows.

---

## 2. Main Problem or Build Goal

The primary build goal was to turn the Aura website into a premium, cinematic, interactive Framer site with:

- A dark purple/pink cosmic hero section.
- Working navigation buttons on the hero/header.
- Separate preloader systems for Hero navigation and Page 2 service cards.
- Subtle native Framer animation effects.
- Premium Runway/Firefly-generated animation assets.
- Seamless video/card transition behavior.
- Cleaner organization and repeatable Claude Code prompts.

The major challenge was keeping the design visually controlled while using AI tools that often over-edit, move elements, add haze, shift colors, break layouts, or apply the wrong transition logic.

---

## 3. Tools Used

### Framer
Used as the main site builder for:

- Aura TSX / Aura TSX copy projects.
- Hero section.
- Page 2 service cards.
- Page 3 About section.
- Preloader components.
- Native animation overlays.
- Responsive breakpoints.

### Framer MCP
Used to let Claude Code inspect and modify the Framer project.

Important MCP lessons:

- Claude can add components and update code, but may place components with weird offsets such as `left: -300px`.
- Claude may claim a component is working even when the animation is too subtle or out of frame.
- Always require Claude to inspect canvas placement and preview behavior, not just type-check.

### Claude Code
Used to:

- Add/revise HeroEffects.
- Add preloader components.
- Link navigation buttons.
- Create separate trigger logic for Hero vs Page 2.
- Modify Page 2 video loop masks.
- Add click behavior and routes.
- Add Dylan Pettway to ATA alumni wall.

### Runway
Used/planned for:

- Hero video animation.
- Visual preloader card animation.
- Subtle atmospheric image-to-video effects.

Important Runway lesson:

- Runway often moves the camera or distorts baked text even when told not to.
- Prompts must be very strict: “no camera movement at all,” “text frozen,” “do not warp or duplicate text.”
- For free accounts with 1,000-character limits, prompts must be condensed.

### Adobe Firefly
Discussed as a free alternative for simple image-to-video effects.

Best use case:

- Simple wind, light, subtle atmospheric motion.
- Less ideal for premium cinematic movement than Runway, but worth testing when free.

### Local Asset Folders
Important asset folder:

`Desktop → New Aura Hero → Color Graded`

Key assets:

- `Visual Wide Preloader No Text`
- `Digital Wide Preloader No Text`
- `Creative Wide Preloader No Text`
- `Visual Preloader effect`
- `Digital Preloader Effect`
- `Creative preloader effect`
- `Page 2 Button 1 Animation`
- `Page 2 Button 2 Digital`
- `Page 2 Button 3 Creative animation`

### Cloudinary
No major Cloudinary action was executed in this chat, but prior Aura workflow uses Cloudinary for hosted image URLs. Reusable rule: when Framer/Claude cannot reliably access local files, upload final assets to Cloudinary and provide exact URLs.

---

## 4. What Worked

### Strict, Specific Claude Code Prompts Worked Best

Claude Code responded better when prompts included:

- Exact component names.
- Exact colors.
- Exact durations.
- Exact layer order.
- What not to touch.
- Explicit testing requirements.
- Fallback logic.

Useful pattern:

```text
Do not rebuild the site.
Do not move or resize existing layout.
Do not change unrelated sections.
Only adjust [specific component/behavior].
After implementing, test [specific interactions].
```

---

### Two Separate Preloader Systems Was the Correct Decision

The correct architecture became:

#### Hero/Header Navigation Preloader

Used for:

- Header Visual
- Header Digital
- Header Creative
- Hero Visual/Digital/Creative text/buttons

Uses full cinematic preloader backgrounds:

- Visual Wide Preloader No Text
- Digital Wide Preloader No Text
- Creative Wide Preloader No Text

#### Page 2 Card Portal Transition

Used for:

- Page 2 Visual card
- Page 2 Digital card
- Page 2 Creative card

Uses the clicked Page 2 thumbnail/video itself, not the full Hero preloader images.

This separation fixed a design mismatch where Page 2 clicks were using the wrong full-screen preloader style.

---

### Blurred Duplicate Background Fixed Preloader Side Bars

The preloader initially had purple side bars/borders that did not match the site.

Better solution:

- Use the same preloader image as a full-screen blurred background.
- Scale it larger.
- Blur it heavily.
- Darken it.
- Place the main preloader card centered above it.

This creates full-screen cinematic blending without ugly purple edge panels.

Reusable settings:

```text
Background duplicate:
- width: 100vw
- height: 100vh
- object-fit: cover
- scale: 1.08 to 1.15
- blur: 28px to 42px
- brightness: 0.45 to 0.6
- saturation: 0.85 to 0.95
- opacity: 0.75 to 0.9
- dark overlay: rgba(5, 7, 12, 0.35 to 0.55)
```

---

### Native Framer Effects Are Better Than Runway for Controlled UI Motion

For hero UI/text and button effects, native Framer animation is safer because:

- Baked text stays readable.
- Layout remains controlled.
- Effects can be tuned without regenerating assets.
- Hover states and preloaders can be precisely triggered.

Native Framer is best for:

- Scan lines.
- Glow pulses.
- Dot animations.
- Overlay fades.
- Card transitions.
- Loop masks.
- Click preloaders.

Runway is best for:

- Background atmospheric video.
- Wind in hair/clothing.
- Water shimmer.
- Cloud motion.

---

### Page 2 Video Loop Masking Is a Reusable Fix

Since Page 2 thumbnail videos did not loop seamlessly, the fix was to mask the end of the loop:

```text
0%–70%: normal playback
70%–86%: subtle dim begins
86%–100%: hold/freeze-like ending
restart: return to full brightness
```

Fallback if true freeze is not possible:

```text
Dark overlay opacity:
0%: 0.00
65%: 0.02
82%: 0.08
94%: 0.16
100%: 0.00

Video brightness:
0%–70%: brightness(1)
82%–94%: brightness(0.88–0.92)
100%: brightness(1)
```

This makes imperfect loops feel intentional.

---

## 5. What Failed

### Image Generation Was Accidentally Triggered Too Often

Multiple times, image generation happened when the user asked only for a prompt or text response.

Reusable rule:

```text
When the user says “do not generate an image,” “respond only,” or asks for a Runway/Claude/Framer prompt, never trigger image generation. Provide text only.
```

---

### Runway Was Not Reliable for Locked UI/Text

Runway often:

- Moved the camera.
- Warped text.
- Changed the hero composition.
- Added unwanted motion.
- Created new rocks or distorted the environment.
- Failed to keep text exactly stable.

Fix:

Use strict Runway prompts with:

```text
No camera movement at all.
No zoom.
No pan.
No tilt.
No push-in.
No pull-back.
No shake.
No reframing.
No parallax.
Keep all text/icons frozen, sharp, readable, and unchanged.
```

---

### Vague Animation Language Caused Bad Results

Bad language:

```text
Make it professional.
Add subtle effects.
Make it cinematic.
```

Better language:

```text
Opacity 0.025 → 0.055 → 0.025 over 24s.
Scan line height 1px max.
Blur 3px max.
Duration 28s to 34s.
No full-screen color popping.
No thick glow band.
```

---

### HeroEffects Layer Offset Created Confusion

Claude placed HeroEffects at `left: -300px` and claimed it compensated with width.

Problem:

- Confusing layer placement.
- Possible out-of-frame effects.
- Hard to debug visually.

Reusable instruction:

```text
HeroEffects must align with the Hero frame:
x: 0
y: 0
width: 100%
height: 100%
No -300px workaround unless absolutely unavoidable.
```

---

### Scan Line Was Too Obvious

Initial scan line felt like a visible bar.

Correct direction:

```text
Height: 1px max
Blur: 3px max
Opacity: 0.035–0.06
Duration: 28s–34s
Optional delay: 4s–6s
Almost invisible
No thick glow band
```

---

### Atmospheric Effects Looked Like Random Color Popping

The first native hero effects looked like “Rice Krispy” flickers in the middle of the image.

Correct direction:

- No broad purple flashes.
- No random full-screen color popping.
- Use subtle sky texture shimmer instead.
- Concentrate effect in the upper sky/cloud area.
- Use faint geometric/hex/circle texture.

---

### Page 2 Initially Used the Wrong Preloader

Page 2 service cards were going to use the Hero full-screen preloaders. That felt disconnected.

Correct decision:

- Hero nav uses full cinematic preloaders.
- Page 2 cards use their own clicked thumbnail/video as portal transition.

---

## 6. Final Decisions

### Aura Preloader Architecture

Use two systems:

#### `AuraPreloaderTransition`
For Hero/Header Visual, Digital, Creative.

Behavior:

- Full-screen cinematic preloader.
- Uses wide preloader assets.
- Native text overlay.
- About 3.7 seconds.
- Then routes to page.

#### `Page2CardPortalTransition`
For Page 2 Visual, Digital, Creative service cards.

Behavior:

- User clicks Page 2 card.
- Overlay opens.
- Blurred duplicate of clicked thumbnail/video fills background.
- Main clicked thumbnail/video appears as centered cinematic card.
- Holds about 3 seconds.
- Adds subtle warp/vortex pulse.
- Routes to matching page.

---

### Hero Navigation Must Be Fully Clickable

Clickable Hero items:

- AURA logo → Home/top.
- VISUAL → Visual preloader → Visual page.
- DIGITAL → Digital preloader → Digital page.
- CREATIVE → Creative preloader → Creative page.
- ABOUT → scroll to Page 3.
- CONTACT → scroll to Page 4.
- INSTAGRAM → external or placeholder link.
- X / TWITTER → external or placeholder link.
- BEHANCE → external or placeholder link.
- PRIVACY → placeholder/page.
- TERMS → placeholder/page.

---

### Preloader Text Should Stay

The bottom preloader text looked good and should remain.

Rules:

- Native/editable text, not baked in.
- Centered lower-middle/bottom.
- Wide tracking.
- Soft white `#F4F1F8`.
- Large serif title.
- Small uppercase subtitle.
- Understated ENTER.

---

### Page 2 Card Transition Should Not Stretch Full Screen

Do not stretch the thumbnail edge-to-edge.

Use:

- Full-screen blurred background.
- Centered enlarged card.
- Subtle glow.
- Subtle warp pulse.

This avoids low-quality stretched thumbnails.

---

### Runway Hero Video Prompt Needs Strict Locked Composition

Runway prompt must say:

- Use source image as exact reference.
- No camera movement at all.
- Text/icons frozen.
- Only atmosphere animates.
- Optional subtle moon rotation.
- Seamless loop.

---

## 7. Reusable Rules

### Rule: Claude Code Layout Safety

```text
Do not rebuild the site.
Do not move or resize existing layout.
Do not change unrelated sections.
Do not duplicate components unless required.
Do not create extra spacer frames.
Do not cover text with overlays.
Use pointer-events: none on visual-only overlays.
Preview after implementation.
```

---

### Rule: Framer MCP Component Placement

```text
When inserting a code component into Framer, verify:
- x/y placement
- width/height
- parent frame
- z-index/layer order
- overflow clipping
- pointer-events
- preview visibility
```

---

### Rule: AI Video with Baked Text

```text
If an image has baked text/logo:
- Tell Runway/Firefly to keep text frozen.
- No movement.
- No warp.
- No flicker.
- No duplication.
- No misspelling.
- No redraw.
```

---

### Rule: Native Effects Should Be Subtle by Numbers

Avoid vague words. Use exact opacity, duration, blur, and delay.

Example:

```text
Opacity: 0.025 → 0.055 → 0.025
Duration: 24s
Ease: ease-in-out
Repeat: infinite
Blur: 3px max
```

---

### Rule: Separate Navigation Contexts

Do not reuse one transition everywhere if the click context is different.

Hero nav:

- Full cinematic preloader.

Page 2 cards:

- Card-based portal transition.

---

### Rule: Use Blurred Duplicate Instead of Side Bars

For full-screen preloaders, avoid solid color side fills.

Use:

- Same image as blurred background.
- Dark overlay.
- Centered main card.

---

## 8. Reusable Prompt Snippets

### Snippet: Claude Code Safety Header

```text
We are working in the Aura Framer project.

Do not rebuild the site.
Do not change the visual layout.
Do not move or resize existing sections, text, images, cards, nav, footer, or page spacing.
Only adjust the specific behavior described below.
Do not duplicate components or leave unused layers.
After implementing, preview and verify the listed checks.
```

---

### Snippet: Hero / Header Preloader Trigger

```text
Hero/Header Visual, Digital, and Creative should use AuraPreloaderTransition.

- Visual → Visual Wide Preloader No Text → Visual page
- Digital → Digital Wide Preloader No Text → Digital page
- Creative → Creative Wide Preloader No Text → Creative page

Do not navigate instantly. Trigger the matching preloader first, hold for about 3.7 seconds, then route to the correct page.
```

---

### Snippet: Page 2 Card Portal Transition

```text
Page 2 service cards should not use the Hero preloaders.

When a Page 2 Visual/Digital/Creative card is clicked, use the clicked card’s own thumbnail/video as the transition visual.

Create a full-screen overlay:
- dark background rgba(5, 7, 12, 0.92)
- blurred full-screen duplicate of clicked media
- centered enlarged card using clicked media
- hold about 3 seconds
- subtle warp/vortex pulse near the end
- route to the matching page

Do not stretch the thumbnail edge-to-edge.
Do not change Page 2 layout or hover effects.
```

---

### Snippet: Blurred Preloader Edge Fix

```text
Remove the purple side border look.

Add a full-screen blurred duplicate of the same preloader image behind the main card:
- width: 100vw
- height: 100vh
- object-fit: cover
- scale: 1.08 to 1.15
- blur: 28px to 42px
- brightness: 0.45 to 0.6
- saturation: 0.85 to 0.95
- opacity: 0.75 to 0.9
- dark overlay: rgba(5, 7, 12, 0.35 to 0.55)

Keep the main card centered with no strong purple outline.
```

---

### Snippet: Page 2 Loop Mask

```text
Add loop masking to the Page 2 animated thumbnail videos.

If true frame freezing is possible:
- Hold/freeze last frame for 0.8–1.2s before restart.

If not possible, use overlay/brightness:
Dark overlay opacity:
0%: 0.00
65%: 0.02
82%: 0.08
94%: 0.16
100%: 0.00

Brightness:
0%–70%: brightness(1)
82%–94%: brightness(0.88–0.92)
100%: brightness(1)

Keep clipped inside the card.
Do not affect the whole page.
```

---

### Snippet: Hero Three-Dot Cadence

```text
Slow down the three-dot animation next to “Enter Your World.”

Total loop: 4.8s to 6s.
Inactive opacity: 0.25–0.35.
Active opacity: 0.75–0.9.
Each dot should brighten softly, hold briefly, then fade.
Add a 0.8s–1.2s pause before repeating.
No fast chase effect.
Do not move or resize the dots.
```

---

### Snippet: Runway Hero Video, Locked Text

```text
Use the provided Aura hero image as the exact source frame. Create a 10-second 16:9 cinematic website hero animation. Keep the composition, moon, mountains, rocks, water, reflections, colors, and centered AURA branding exactly the same.

Camera must be fully locked: no zoom, pan, tilt, shake, push-in, pull-back, reframing, or parallax. Keep the AURA logo, “VISUAL. DIGITAL. CREATIVE.” text, and three symbols completely frozen, sharp, readable, and unchanged. Do not move, warp, blur, flicker, duplicate, redraw, or distort any text/icons.

Only animate the atmosphere: soft purple/pink storm glow, gentle hidden lightning behind clouds, subtle cloud movement, faint cosmic shimmer, and natural water reflection shimmer. Premium, dark, polished, mysterious, not chaotic.

Negative: no text distortion, no camera movement, no aggressive lightning, no thick haze/fog, no new planets, birds, buildings, people, vehicles, cartoon style, neon oversaturation, abrupt cuts, or jumpy reset.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP 1: Adding a New Framer Animation Component with Claude Code

1. Tell Claude exactly which project is open.
2. Tell Claude what section/component to modify.
3. Tell Claude what not to touch.
4. Define component name.
5. Define layer order.
6. Define exact opacity/duration/blur/position values.
7. Require pointer-events disabled for visual overlays.
8. Require preview testing.
9. Ask Claude to confirm:
   - no layout shift
   - no duplicate component
   - no invisible overlay blocking clicks
   - animation visible in preview
   - component aligned at x:0, y:0 unless intentionally offset

---

### SOP 2: Building a Framer Preloader System

1. Decide if preloader belongs to Hero nav or page/card context.
2. Create reusable preloader component.
3. Define trigger functions:
   - `triggerVisualPreloader`
   - `triggerDigitalPreloader`
   - `triggerCreativePreloader`
4. Prevent immediate navigation.
5. Show overlay.
6. Animate in.
7. Hold for set duration.
8. Add final pulse/glitch/warp.
9. Navigate to correct route.
10. Clean up/unmount overlay after navigation.
11. Test every trigger source.

---

### SOP 3: Fixing Ugly Preloader Borders

1. Remove side panels and strong outlines.
2. Add same image as full-screen blurred background.
3. Darken and desaturate blurred layer.
4. Keep main image/card centered.
5. Add very subtle card border or none.
6. Keep text native and readable.
7. Preview on desktop and laptop.

---

### SOP 4: Page 2 Card Portal Transition

1. Keep Hero preloaders untouched.
2. Create `Page2CardPortalTransition`.
3. On Page 2 card click, capture clicked card type and media source.
4. Open full-screen overlay.
5. Use clicked media as blurred background.
6. Use clicked media as centered enlarged card.
7. Play/hold 3 seconds.
8. Add subtle warp/vortex pulse.
9. Navigate to matching page.
10. Do not break hover animations.

---

### SOP 5: Runway Prompting for Website Hero Assets

1. Attach exact source image.
2. Tell Runway what should animate.
3. Tell Runway what must stay frozen.
4. Use strict negative constraints.
5. Keep prompt under account character limit if needed.
6. Avoid explaining editing workflow to Runway.
7. Do not mention irrelevant context such as “I will slow it down later” unless needed.
8. For baked text, always include:
   - no text movement
   - no text distortion
   - no duplicate text
   - no flicker
   - no misspellings

---

### SOP 6: Claude Code Button Link Audit

1. Identify every clickable text element.
2. Assign destination:
   - Home/top
   - Visual page
   - Digital page
   - Creative page
   - About/Page 3
   - Contact/Page 4
   - External/social/legal placeholders
3. Add transparent hit areas if needed.
4. Add pointer cursor.
5. Confirm no overlay blocks clicks.
6. Test each link in Preview.

---

## 10. Future Agent Ideas

### Agent 1: Framer MCP Layout Auditor

Purpose:
Inspect Framer MCP changes and detect:

- weird offsets like `-300px`
- duplicate components
- overlays covering text
- broken z-index
- pointer-events issues
- layout shifts
- wrong parent frame

### Agent 2: Aura Animation Director

Purpose:
Generate strict animation prompts for:

- Runway
- Firefly
- native Framer effects
- preloader transitions
- hover effects

Rules:
Never generate images unless asked. Only write prompts.

### Agent 3: Preloader System Builder

Purpose:
Build reusable Framer preloader systems with:

- route trigger logic
- overlay cleanup
- media-specific visuals
- fallback behavior
- testing checklist

### Agent 4: Asset Folder Mapper

Purpose:
Read asset folder screenshots and convert them into:

- file inventory
- which files are actual backgrounds
- which files are references
- which files are animations/videos
- Framer-ready naming instructions

### Agent 5: Claude Code Prompt Compiler

Purpose:
Turn high-level design intent into precise Claude Code prompts with:

- exact colors
- exact dimensions
- exact component names
- exact timing
- exact layer order
- strict “do not touch” rules

---

## 11. Recommended Filename

`aura-framer-preloader-native-effects-runway-workflow.md`

---

## 12. Recommended Folder Inside Repo

`/01-framer-mcp-playbooks`

This belongs in the Framer MCP playbook folder because the core reusable value is how to direct Claude Code/MCP inside Framer to build preloaders, native effects, and transition logic without breaking layout.

Secondary useful tags:

- `/02-claude-code-prompts`
- `/03-image-asset-workflows`
- `/06-debugging-rules`
- `/07-aura-brand-systems`

---

## 13. Agent-Ready Summary

This chat produced a reusable workflow for building cinematic Framer websites with Claude Code/MCP. The main system is a two-part Aura preloader architecture: Hero/Header links use full cinematic preloaders, while Page 2 service cards use their own clicked thumbnail/video as a portal-style transition. Major reusable fixes include using blurred duplicate image backgrounds instead of ugly side bars, masking imperfect video loops with dark/brightness overlays, slowing dot animations with intentional cadence, and requiring strict layer/layout safety rules for Claude Code.

The most important debugging lessons are that Claude Code may place components incorrectly, native effects can be too visible or cheap unless specified numerically, and Runway is risky with baked text unless prompts strictly forbid camera movement and text distortion. The report should be saved as a Framer MCP playbook and reused as a prompt/rule set for future Aura-style builds.
