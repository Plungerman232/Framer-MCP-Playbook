# Creative Umbrella Site — Framer Hero Animation, Claude Code, Runway, and Asset Workflow Report

## 1. Chat title / topic

**Creative Umbrella Site — Animated Aura Hero Page Using Framer, Claude Code, Runway, and Layered Still-Image Motion**

This chat focused on building the first hero page for a premium creative umbrella website called **AURA / Aura Creative**, including a cinematic sci-fi hero background, three clickable service cards, subtle “teleport / glitch / reality peel” animation, and a practical workflow using Claude Code, Framer, and generated image assets.

---

## 2. Main problem or build goal

The main goal was to create a **full-screen Framer hero page** for a creative umbrella website with three service paths:

- **Visual** — Photography & Visual Storytelling
- **Digital** — Web Design & Digital Experiences
- **Creative** — Creative Direction & Strategic Consulting

The original goal was to use Runway to create a 10-second animated hero video with:

- very slow lightning
- sunshower-style flicker
- page/rip-through-reality effect
- dimensional glitch / teleport effect
- no walking or character movement

Runway generated cool atmosphere, but repeatedly animated the model walking through water. Final decision: this should not be solved primarily with AI video. It should be built as a **Framer layered still-image animation** using Claude Code.

---

## 3. Tools used

### Framer

Final destination for the website. Used to import the generated `AuraAnimatedHero.tsx` code component and attach image assets through Framer property controls.

### Claude Code

Used to generate the Framer-ready React/TSX component.

Target file:

`AuraAnimatedHero.tsx`

### Framer MCP

Discussed as useful later, but not required before generating the code component. Final decision: get the component working first, then use MCP later for canvas/layer placement, resizing, and troubleshooting.

### Codex / local folder workflow

The user had Claude Code open locally and needed to make sure it was working from the correct project folder instead of `C:\WINDOWS\system32`.

Relevant folder shown:

`C:\Users\charlie - Personal\Desktop\Creative Umbrella\Site Design`

Earlier code path discussed:

`C:\Users\Charl\Documents\Codex\2026-05-04\files-mentioned-by-the-user-site`

### Runway

Used to test image-to-video generation. It created good lightning and atmosphere but failed by animating the model physically walking.

### Image generation

Used to generate:

- main hero background
- Visual card image
- Digital card image
- Creative card image

Important correction: the card images must be generated/exported as **three separate image files**, not one combined triptych.

### Cloudinary

Not directly used during this chat, but remains relevant for hosting final image assets as stable URLs for Framer.

### GitHub

The final report is intended for:

`https://github.com/Plungerman232/Framer-MCP-Playbook`

---

## 4. What worked

### Strong visual concept

The generated hero concept successfully established the mood:

- dark cinematic sci-fi
- purple/crimson lightning
- reflective water
- lone figure
- premium editorial hero layout
- three service cards at the bottom

### Separate service card direction

The final card asset direction became clear:

1. **Visual**
   - eye icon
   - portrait/cinematic background
   - “VISUAL”
   - “Photography & Visual Storytelling”
   - “ENTER”

2. **Digital**
   - globe/web icon
   - glowing portal/monolith background
   - “DIGITAL”
   - “Web Design & Digital Experiences”
   - “ENTER”

3. **Creative**
   - plus icon
   - cosmic orb/lightning background
   - “CREATIVE”
   - “Creative Direction & Strategic Consulting”
   - “ENTER”

### Claude Code generated the component

Claude Code successfully generated the page component after being run from the correct folder.

### Framer import worked

The user successfully imported the generated component into Framer.

### Best workflow was identified

The strongest final workflow is:

**Still image → Claude Code Framer component → layered CSS animation → Framer property controls → final page preview**

This is cheaper, cleaner, and more controllable than repeated Runway attempts.

---

## 5. What failed

### Runway made the model walk

Runway interpreted “teleport,” “dimensional drift,” and “displacement” as physical movement. Even when told “no walking,” it still animated the model walking faster.

### Multiple source images confused Runway

Using all three storyboard/source images encouraged Runway to create progression, movement, or transitions. This made the model move unnaturally.

Rule learned:

**Storyboard images should be style/motion references, not direct source frames for video generation.**

### Combined image outputs were not useful as Framer card assets

The user needed three individual card image files. Combined triptych outputs caused confusion and were not directly usable as clickable card backgrounds.

### Over-checking Claude Code wasted tokens

Having Claude review the entire generated file took longer and consumed unnecessary usage. Better workflow: import into Framer first, then only fix the exact error Framer gives.

### Earlier TSX/CSS structure problems

Earlier code failed because:

- CSS was floating outside a `const css = \`...\`` block
- the Nav component was cut off
- Framer needs one complete exported React component
- property controls need to be valid

---

## 6. Final decisions

### Build only the hero first

Do not generate the entire website yet. First get the hero page working.

### Do not use Runway as the main solution

Runway is not the right tool when the subject must remain still. The desired effect is motion compositing, not AI video.

### Use Framer layered animation

The hero should use:

- still hero background
- ghost duplicate layer
- opacity flickers
- scanline/noise overlay
- subtle lightning overlay
- tiny horizontal displacement
- slow push-in
- card hover effects

### Use Claude Code before Framer MCP

Claude Code should generate the `AuraAnimatedHero.tsx` component first. Framer MCP should only be used later for direct Framer canvas/layer manipulation.

### Attach images through property controls

The component should expose these image controls:

- `heroBackground`
- `visualCardImage`
- `digitalCardImage`
- `creativeCardImage`

This keeps the component flexible inside Framer.

---

## 7. Reusable rules

1. **Do not use AI video generation when the subject must stay still.**  
   Use layered Framer animation instead.

2. **One video source image only.**  
   If testing Runway, use only the clean hero image as the video source.

3. **Do not feed multi-panel references directly into Runway.**  
   Runway may turn them into scene transitions or movement states.

4. **Generate service cards as separate files.**  
   Visual, Digital, and Creative must each be their own asset.

5. **Build the Framer code component first.**  
   Do not start with MCP before the component exists.

6. **Use Framer property controls for image assets.**  
   Avoid hardcoding image paths when the user needs to upload/select images in Framer.

7. **Preview in Framer before asking Claude for more edits.**  
   Fix actual errors, not imagined ones.

8. **Do not let Claude repeatedly rewrite the full file.**  
   Ask for small targeted fixes.

9. **Work from the correct project folder.**  
   Do not run Claude Code from `C:\WINDOWS\system32`.

10. **Premium motion is restrained motion.**  
   Less movement usually looks more expensive.

---

## 8. Reusable prompt snippets

### Claude Code prompt — Framer animated hero component

```text
Create a complete Framer-ready React/TSX code component named AuraAnimatedHero.tsx.

This is for my premium creative umbrella website called AURA / Aura Creative.

The goal is to build the full hero page only first, not the entire website.

Build it as a Framer Code Component using:
- React
- Framer property controls
- CSS animations inside the component
- no external packages unless Framer already supports them
- one complete export default component

The component should have image property controls for:
- heroBackground
- visualCardImage
- digitalCardImage
- creativeCardImage

Also add text property controls for:
- brandName default: AURA
- tagline default: Visual. Digital. Creative.
- visualTitle default: VISUAL
- visualSubtitle default: Photography & Visual Storytelling
- digitalTitle default: DIGITAL
- digitalSubtitle default: Web Design & Digital Experiences
- creativeTitle default: CREATIVE
- creativeSubtitle default: Creative Direction & Strategic Consulting

Layout:

Create a full-screen desktop hero page with a 16:9 / 1440px premium website feel.

The hero background should take up the full viewport:
- dark cinematic sci-fi landscape
- image fills the entire background
- background uses object-fit cover / background-size cover
- strong dark overlay gradient so text is readable
- should look premium, moody, cinematic, futuristic, ethereal

Top navigation:
- AURA wordmark top left
- small uppercase nav links across the top/right:
  Visual, Digital, Creative, About, Contact
- thin letter-spaced typography
- white/soft gray text
- transparent background

Center hero content:
- large centered AURA title
- small uppercase tagline underneath
- typography should feel editorial, premium, spaced out, cinematic
- do not make it look corporate or basic

Bottom cards:
Create three clickable cards across the bottom:
1. VISUAL
   - icon: eye
   - subtitle: Photography & Visual Storytelling
   - use visualCardImage as card background
2. DIGITAL
   - icon: globe/web
   - subtitle: Web Design & Digital Experiences
   - use digitalCardImage as card background
3. CREATIVE
   - icon: plus sign
   - subtitle: Creative Direction & Strategic Consulting
   - use creativeCardImage as card background

Each card should include:
- background image
- dark gradient overlay
- small icon at top
- title text
- subtitle text
- ENTER label
- rounded corners
- subtle border
- premium hover effect:
  - card lifts slightly
  - image slowly scales up
  - border/glow becomes slightly brighter
  - no cheesy effects

Animation goal:

Do NOT use AI video. Do NOT animate the person walking. This should feel like a living still poster.

Create layered CSS animation effects over the still hero background:
- very subtle slow background push-in
- very slow lightning flicker overlay
- subtle scanline/noise overlay
- ghost duplicate layer of the hero background with very low opacity
- tiny horizontal displacement flicker
- subtle dimensional glitch / phasing effect
- occasional soft light pulse in the sky
- everything should be restrained and premium

Important:
The central figure/model in the background should appear still. No walking, no arm movement, no body movement, no character animation. The animation should only be done through layered overlays, opacity, transforms, glitch masks, and subtle displacement.

The effect should feel like:
- a dark sci-fi album cover coming alive
- a premium creative studio hero section
- subtle dimensional phasing
- reality quietly glitching
- slow sunshower-style lightning flickers

Do NOT make it feel like:
- a trailer
- an action scene
- a video game intro
- an anime effect
- a loud VFX demo
- a cheap glitch effect

Technical requirements:
- The file must work as a Framer code component.
- Include addPropertyControls.
- Include all CSS inside the component file.
- Use inline SVG icons for eye, globe, and plus.
- Make sure the component exports default properly.
- Make sure there are no missing brackets or unfinished JSX.
- Make the component responsive enough for smaller screens, but prioritize desktop.
- Use a min-height of 100vh.
- Make sure the card section stays near the bottom of the hero.
- Use clean class names.
- Return the full complete TSX file and save it as AuraAnimatedHero.tsx in the current folder.
```

### Claude Code minimal Framer error-check prompt

```text
Review AuraAnimatedHero.tsx for Framer compatibility. Do not redesign it. Only fix errors that would prevent it from importing into Framer, including missing imports, TypeScript issues, broken JSX, property control issues, or invalid CSS syntax.
```

### Claude Code token-saving prompt

```text
Stop reviewing the whole file. Only check AuraAnimatedHero.tsx for import-breaking Framer errors and make minimal fixes.
```

### Runway system prompt, only if testing video again

```text
Create a cinematic desktop hero background animation for a premium creative studio website in 16:9 widescreen format.

Maintain the original composition of the source image:
a lone silhouetted figure standing in reflective water beneath massive cosmic storm clouds and subtle lightning.

The animation should feel atmospheric, immersive, emotional, dark, ethereal, cinematic, and premium — not like a trailer or action sequence.

Motion must remain extremely subtle:
- slow environmental drifting
- soft atmospheric cloud movement
- reflective water movement
- very slow sunshower style lightning flickers
- gentle lightning pulses through clouds
- slow dimensional displacement effect

A subtle reality peel effect slowly emerges through the center of the frame:
- paper ripping through reality
- slight horizontal displacement distortion
- ghost silhouette briefly appears behind the tear
- dimensional duplication effect
- slow teleportation drift
- elegant glitch artifacts

Camera movement should remain nearly static:
- extremely slow push-in only
- no cinematic sweeping
- no dramatic motion
- preserve original framing

The final result should feel like an expensive interactive website background for a futuristic creative brand.

Avoid:
fast motion, action scenes, aggressive lightning, explosions, dancing, anime effects, rapid cuts, chaotic movement, heavy morphing, trailer pacing, exaggerated VFX.
```

### Runway text prompt, only if testing video again

```text
slow cinematic dimensional displacement effect, lone figure standing in reflective water beneath cosmic lightning storm, subtle reality tearing effect through center of frame, atmospheric glitch distortion, ghost silhouette emerges briefly then fades, dimensional duplication, slow teleportation drift, very slow sunshower style lightning flickers, reflective water movement, dark ethereal sci-fi atmosphere, elegant and haunting, subtle paper tear effect through reality, premium cinematic desktop hero background
```

### Runway correction for unwanted walking

```text
The figure should remain almost completely still. No walking cycles, arm swinging, stepping, or realistic human movement. Motion should feel like suspended dimensional displacement and subtle glitch phasing rather than physical movement.
```

Important note: this still may not solve the issue. If Runway continues moving the model, stop using video generation and return to Framer layered animation.

---

## 9. SOPs / step-by-step workflows

### SOP 1 — Claude Code to Framer component workflow

1. Open the correct project folder.
2. Right-click inside the folder and choose **Open in Terminal**.
3. Start Claude Code from that folder.
4. Paste the `AuraAnimatedHero.tsx` prompt.
5. Allow Claude Code to create/edit files during the session.
6. Save the generated file as:

   `AuraAnimatedHero.tsx`

7. Do not ask for repeated full-file reviews.
8. Open Framer.
9. Import or paste the code component.
10. Drag the component onto the page.
11. Set:
   - Width: Fill
   - Height: 100vh or Fill
   - Position: top of page
12. Attach the four images through Framer property controls.
13. Preview.
14. Only then troubleshoot specific issues.

---

### SOP 2 — Framer import workflow

1. Open the Framer project.
2. Go to **Assets**.
3. Go to **Code**.
4. Add/import a code file.
5. Name it:

   `AuraAnimatedHero.tsx`

6. Paste/import the TSX code.
7. Save.
8. Return to canvas.
9. Insert the code component.
10. Select the component.
11. Attach:
   - hero background
   - Visual card image
   - Digital card image
   - Creative card image
12. Preview before making code changes.

---

### SOP 3 — Still-image hero animation workflow

1. Use the still hero image as the base background.
2. Add a dark gradient overlay for readability.
3. Duplicate the hero background as a ghost layer.
4. Set ghost layer opacity very low.
5. Animate ghost layer with:
   - tiny X movement
   - opacity flicker
   - slow timing
6. Add scanline/noise overlay.
7. Animate scanline/noise opacity subtly.
8. Add lightning/light pulse overlay.
9. Animate the light pulse slowly and irregularly.
10. Add slow background push-in.
11. Keep the model visually still.
12. Test at desktop size.
13. Reduce motion if it feels cheap.

---

### SOP 4 — Runway cost-control workflow

1. Only use Runway when actual video motion is required.
2. Use one clean hero image as source.
3. Do not use three-panel images as video source.
4. Set motion strength low.
5. Use nearly static camera.
6. Explicitly prohibit walking and arm movement.
7. Stop after 1–2 bad generations.
8. Move to Framer/CSS animation if the subject keeps moving.

---

### SOP 5 — Image asset workflow

1. Generate four separate files:
   - hero background
   - Visual card
   - Digital card
   - Creative card
2. Keep the hero image widescreen.
3. Keep cards individual.
4. Each card should include:
   - icon
   - title
   - subtitle
   - Enter label
   - dark cinematic background
5. Upload directly into Framer or host on Cloudinary.
6. Attach assets through Framer property controls.

---

## 10. Future agent ideas

### Framer Hero Animation Agent

Takes one still hero image and creates a Framer component with:

- background push-in
- lightning flicker
- scanlines
- ghost duplicate
- subtle glitch displacement
- card hover states

### Framer MCP Placement Agent

Connects after the component is imported and:

- places component on the page
- sets fill width and 100vh height
- adjusts z-index
- aligns bottom cards
- checks responsiveness

### Runway Cost-Control Agent

Prevents wasted generations by deciding whether an effect should be made in:

- Runway
- Framer/CSS
- Premiere
- Photoshop
- Claude Code

### Asset Separation Agent

Takes a combined visual direction and outputs separate prompts/assets for:

- hero background
- Visual card
- Digital card
- Creative card

### Framer Error Fix Agent

Accepts the exact Framer error and edits only the minimum required lines in the TSX file.

---

## 11. Recommended filename

`aura-animated-hero-framer-claude-code-runway-workflow.md`

---

## 12. Recommended folder inside the repo

`/01-framer-mcp-playbooks`

Secondary possible folder:

`/02-claude-code-prompts`

Best choice:

`/01-framer-mcp-playbooks`

Reason: this is primarily a workflow/playbook for building a cinematic Framer hero using Claude Code, assets, and optional MCP.

---

## 13. Agent-ready summary

The user is building a premium AURA Creative umbrella website in Framer. The hero page should have a dark cinematic sci-fi background, a lone still figure in reflective water, subtle purple/crimson lightning, and three clickable cards for Visual, Digital, and Creative.

The user initially tried using Runway to create a 10-second animated hero video. Runway created strong atmosphere but repeatedly made the model walk through the water, which was not desired. The correct solution is not AI video generation. It is layered still-image motion inside Framer.

Claude Code should generate a Framer-ready `AuraAnimatedHero.tsx` code component. The component should expose image property controls for the hero background and three card images. It should use CSS animations for subtle background push-in, lightning flicker, scanlines/noise, ghost duplication, and tiny glitch displacement. The model should remain visually still.

Framer MCP should not be the first step. First generate and import the code component. Then use MCP later only for canvas placement, layer manipulation, spacing, or troubleshooting.

The final build process is:

1. Generate separate assets.
2. Create `AuraAnimatedHero.tsx` with Claude Code.
3. Import the component into Framer.
4. Attach images through property controls.
5. Preview.
6. Fix only specific errors.
7. Use MCP later if needed.

Key rule: if the subject must stay still, do not keep spending Runway credits trying to force video models to stop moving. Use layered Framer animation instead.

---

# Final placement instructions

## What to name the markdown file

`aura-animated-hero-framer-claude-code-runway-workflow.md`

## Which folder in `Framer-MCP-Playbook` it should go into

`/01-framer-mcp-playbooks`

## Whether this should become a rule, SOP, prompt snippet, or agent instruction

This should become **all four**:

- **Rule:** Do not use AI video when the subject must remain still; use layered Framer motion instead.
- **SOP:** Claude Code → Framer Code Component → Framer import → property controls → targeted fixes.
- **Prompt snippet:** Save the `AuraAnimatedHero.tsx` Claude Code prompt as a reusable prompt.
- **Agent instruction:** Future agents should build the component first, avoid premature MCP use, avoid full-file rewrites, and only use MCP after import/layout testing.
