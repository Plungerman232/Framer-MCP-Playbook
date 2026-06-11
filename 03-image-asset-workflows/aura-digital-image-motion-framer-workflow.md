# Aura Digital Image / Motion / Framer Build Workflow

## 1. Chat Title / Topic

**Aura Digital — Homepage Direction, Image Asset Creation, Runway Motion Testing, and Framer/Claude Code Implementation Rules**

This chat focused on developing the visual direction and asset workflow for the **Aura Digital** branch of the Aura Creative brand system. It covered homepage layout direction, AI-generated image concepts, Framer button/card behavior, Runway video prompting, Cloudinary asset usage, and when to move motion effects out of AI video generation and into Framer/Claude Code.

---

## 2. Main Problem or Build Goal

The goal was to build the **Aura Digital** website/page as a distinct sub-brand within the larger Aura Creative universe.

Aura Creative has three branches:

1. **Aura Visual** — photography and visual storytelling  
2. **Aura Digital** — web design and digital experiences  
3. **Aura Creative** — creative direction and strategic consulting  

The Aura Digital page needed to feel like a **digital architecture / web design wing** of the same cinematic Aura universe, not a generic web agency page.

The major build goals were:

- Create a homepage/page design for **Aura Digital**.
- Keep the same Aura universe: cinematic, atmospheric, premium, purple/magenta/orange storm energy.
- Differentiate Aura Digital from Aura Visual and Aura Creative.
- Build a 3x3 grid of website/design cards for digital projects.
- Create new Visual, Digital, and Creative buttons for the main Aura homepage.
- Preserve the existing Framer hover effect on the homepage cards.
- Use Cloudinary-hosted source images in Claude Code / Framer.
- Create AI motion card/video assets with Runway.
- Learn when Runway is useful and when Framer/Claude Code is safer.
- Avoid AI video tools deforming subjects or over-animating hero assets.

---

## 3. Tools Used

### Design / Web Build Tools

- **Framer**
  - Main website builder.
  - Existing site already had pages/sections and hover effects.
  - Needed Claude Code / MCP edits inside a copied Framer project.

- **Framer MCP**
  - Intended for letting Claude Code inspect and modify the Framer project.
  - Used conceptually for page replacement, component/card edits, and hover-effect preservation.

- **Claude Code**
  - Intended executor for Framer edits.
  - Needed highly specific instructions so it would only edit the first/home section and not touch other pages.

- **Codex**
  - Intended repo organizer / future automation helper.
  - Mentioned as a possible tool to organize markdown prompts and reports into the GitHub playbook repo.

- **GitHub**
  - Target repo: `https://github.com/Plungerman232/Framer-MCP-Playbook`
  - This chat report should become reusable documentation for the repo.

- **Cloudinary**
  - Used to host source images and video assets.
  - Cloudinary URLs were intended to be passed into Claude Code / Framer as image/video sources.

### AI Image / Video Tools

- **ChatGPT image generation**
  - Used to create Aura Digital backgrounds, homepage buttons, hero page concepts, and card imagery.

- **Runway**
  - Used for image-to-video motion tests.
  - Generated AI motion card loops and hero background attempts.
  - Problems appeared when Runway changed the subject, added unwanted camera movement, or made tornado-like motion.

- **Gemini 2.5 Flash**
  - Used as a helper to rewrite prompts for Runway.
  - Helpful for producing alternate prompt styles, but still required strong human art direction.

- **Adobe Firefly**
  - Discussed as a possible future tool.
  - Might be useful for safer, more controlled commercial visual generation and image-to-video work.

---

## 4. What Worked

### A. Aura Digital Direction

The strongest positioning became:

> **Aura Digital is not a web agency. It is the place where Aura turns brands into online worlds.**

The winning direction:

- Dark luxury web design.
- Digital spaces built through the Aura lens.
- More structured and interface-led than Aura Visual.
- Still cinematic, atmospheric, and premium.
- Less corporate SaaS, less cyberpunk, less generic agency.

Best headline direction:

> **Websites built like worlds.**

Best sub-brand description:

> **Web design & digital experiences.**

Best emotional direction:

> Aura Digital should feel like entering a curated design archive, digital gallery, or online-world concept chamber.

---

### B. 3x3 Aura Digital Page Layout

The 3x3 card/grid idea worked well.

The page should show multiple website concepts immediately instead of acting like a normal service page.

Recommended structure:

- **Top row:** basic reusable templates / lower-cost starter sites.
- **Middle row:** more creative custom sites using original photography, images, or video.
- **Bottom row:** AI video / Runway / AI motion / experimental web experiences.

This is better than generic service buttons like “Brand Site,” “Landing Page,” and “Portfolio,” because the page becomes a visual proof-of-work gallery instead of a normal agency sales page.

Reusable rule:

> For Aura Digital, the card grid should represent actual work or build categories, not generic navigation links.

---

### C. Aura Homepage Button System

The new Visual, Digital, and Creative button concepts worked well when treated as three separate portals inside the Aura universe.

The motion differentiation concept was strong:

- **Visual:** breeze, water shimmer, organic photographic motion.
- **Digital:** glitch, scanline, signal pulse, interface energy.
- **Creative:** ember, hidden-door glow, mystical/strategic reveal.

Reusable rule:

> The three Aura homepage buttons can share the same universe, but their motion language should differentiate the branches.

---

### D. Framer Hover Effect Preservation

The existing Framer hover effect on the buttons was already good. The correct strategy was not to rebuild it from scratch.

Reusable rule:

> Before replacing button/card images in Framer, inspect and preserve the existing hover effect. Reuse the same motion, lift, glow, scale, and transition timing on the new cards.

---

### E. Cloudinary Asset Workflow

Cloudinary worked as the asset source for:

- Hero images.
- Button images.
- Runway-generated videos.
- Placeholder/card images.

Reusable workflow:

1. Generate or finalize image/video asset.
2. Upload to Cloudinary.
3. Pass the Cloudinary URL to Claude Code.
4. Use the Cloudinary asset inside Framer.
5. Keep text/icons as Framer layers whenever possible instead of baking them into videos.

---

### F. Runway for Card-Level Motion

Runway worked better for abstract motion cards than for preserving complex subjects.

Best use cases:

- AI motion cloud card.
- Subtle animated background inside a card.
- Atmospheric motion where exact anatomy/identity does not matter.
- Abstract cloud, haze, light, and portal motion.

Reusable rule:

> Runway is useful for organic motion backgrounds, but text and UI should be layered in Framer afterward.

---

### G. Framer / CSS Overlay Motion

For the “Intelligence in Motion” hero image, Runway repeatedly changed the model/subject. The final decision was that Framer/Claude Code overlays are safer.

Best Framer approach:

- Keep the source image completely static.
- Do not animate the image layer.
- Add separate overlay layers:
  - drifting cloud haze
  - mist around waist/lower body
  - subtle light shimmer
  - background fog movement
- Use CSS/Framer animation loops.
- Keep opacity low and motion slow.

Reusable rule:

> If Runway keeps warping the subject, stop using video generation and recreate motion as Framer overlay effects.

---

## 5. What Failed

### A. Overly Futuristic Aura Digital Images

Some early Aura Digital mockups became too:

- futuristic
- dark
- cyberpunk
- mechanical
- purple/black-heavy
- generic tech-agency-looking

Fix:

- Lighten the palette.
- Add sunset tones: peach, pink, orange, lavender, mauve.
- Keep the Aura palette but make it more breathable and professional.
- Avoid heavy black backgrounds for sales-facing pages.

Reusable rule:

> Dark cinematic does not mean black-heavy. Aura Digital needs enough warmth and visual openness to feel premium and trustworthy.

---

### B. Backgrounds Competing With 3x3 Cards

Some image generations had too much detail behind the card grid.

Problem:

- Cards became hard to read.
- Page felt busy.
- Background overpowered the actual work previews.

Fix:

- Use a calmer atmospheric background.
- Keep the center/lower areas less busy.
- Give the cards breathing room and staggered placement.
- Avoid making the 3x3 grid look like a boring mechanical assembly line.

Reusable rule:

> If the card grid is the main content, the background must support it, not compete with it.

---

### C. Door / Portal Beam Looking Too Literal

Some Aura Digital background images had a visible door/portal that looked off-putting once the page layout was added.

Fix:

- Blend the beam into the atmosphere.
- Keep the glow but reduce the literal door shape.
- Make it feel like environmental light, not a physical door object.

Reusable rule:

> Portal energy is good; obvious fake portal doors can look cheesy.

---

### D. Text Placement Mistakes on Hero Images

Some generated hero overlays had:

- “AURA” too far right.
- AURA covering the lightning bolt.
- Icon row sitting on the model’s head.
- Wrong “Enter your world” dots.
- Lower text too bright white instead of subtle gray.
- Footer not pinned to the very bottom.

Fix:

- Use the full reference homepage with buttons as the positioning guide.
- Use the clean hero image as the base.
- Add overlay text according to reference placement.
- Leave the bottom card space open if cards will be added later.
- Footer belongs at the bottom edge of the full page.

Reusable rule:

> For hero rebuilds, the clean no-text image is the base; reference images are for placement only.

---

### E. Runway Creating Tornadoes Instead of Subtle Cloud Motion

Multiple prompts accidentally caused Runway to generate:

- giant tornadoes
- vortex funnels
- huge storm subjects
- aimless cloud objects drifting away
- too much camera motion
- aggressive zooms

Cause:

- Words like “vortex,” “funnel,” “spiral,” “cloud formation,” and “main subject” made Runway latch onto one object.

Fix:

- Use simpler direction.
- Avoid words that imply tornado/vortex.
- Describe it as:
  - ambient cloud motion
  - smoky cloud-energy form
  - living cloud painting
  - subtle cloud drift
  - soft haze movement
- For hero videos, ask for almost no camera movement.

Reusable rule:

> For website hero backgrounds, prompt “animated painting,” not “scene animation.”

---

### F. Runway Warping the Intelligence Model

Runway repeatedly changed the model:

- turned body into glowing spaghetti-like linework
- changed pose/face
- animated the subject too much
- made the figure breathe or turn
- zoomed/panned too aggressively
- left clouds and lightning frozen

Attempts to fix with prompts still failed.

Final decision:

- Stop burning credits on Runway for this asset.
- Use Framer overlays instead.
- Keep the subject completely static.

Reusable rule:

> If the exact subject design matters, avoid AI video generation unless the tool has strong subject preservation controls.

---

## 6. Final Decisions

### Aura Digital Page

- Use a lighter, more sunset-toned version of the Aura palette.
- Use a 3x3 grid of website/project cards.
- Do not make the page a generic service page.
- Let the work previews carry the page.
- Keep the background atmospheric but less busy.
- Cards should be smaller, more spaced out, and slightly staggered.

### Aura Homepage

- Replace old homepage buttons with new Visual, Digital, and Creative button images.
- Keep the exact existing hover effect.
- Use the new hero image/text layout.
- Keep footer pinned at the bottom.
- Add subtle dark shelf/gradient behind bottom cards.

### Runway / Video

- Use Runway for abstract, non-subject card motion.
- Use simple Image-to-Video, not complex Workflow, for subtle background motion.
- Use low motion.
- Use short prompts when Runway over-interprets.
- Use 5 seconds first when credits are low.
- Extend only if the motion is working.

### Framer / Claude Code

- Use Framer/CSS overlays for motion when preserving a subject matters.
- Do not animate the base image layer.
- Add separate haze/mist/light layers.
- Keep text and icons in Framer, not baked into video.

---

## 7. Reusable Rules

### Framer / Claude Code Rules

1. **Do not touch unrelated pages.**
   If the task is the homepage, Claude Code must leave pages 2, 3, and 4 unchanged.

2. **Preserve existing hover effects.**
   Inspect the current card hover effect before deleting or replacing any button/card.

3. **Replace assets, not behavior.**
   When button images change, keep the existing interaction system unless explicitly redesigning.

4. **Use reference images only for layout.**
   The clean image is the base; the complete mockup is the placement guide.

5. **Keep text editable in Framer.**
   Do not bake important labels, nav, buttons, or CTA text into videos unless absolutely necessary.

6. **Never allow broad layer-renaming during visual edits.**
   Broad renaming can stall Claude/Framer MCP. Rename later in small batches.

7. **Use exact placement language.**
   Claude needs specific instructions: exact section, exact cards, exact behavior, exact pages not to touch.

---

### Image / Motion Rules

1. **Dark cinematic does not mean too black.**
   Use peach, lavender, orange, pink, mauve, and soft purple to keep the site premium and usable.

2. **Aura Digital should not look like SaaS or cyberpunk.**
   Avoid generic dashboard, blue neon tech, code rain, and overly mechanical layouts.

3. **Use motion as branch identity.**
   Visual = organic photographic movement.  
   Digital = signal/glitch/interface movement.  
   Creative = ember/reveal/portal movement.

4. **Runway is not reliable for preserving exact subjects.**
   If the model/person/character must stay exact, use Framer overlays or a more controlled tool.

5. **Prompt ambient hero videos as animated paintings.**
   Avoid “vortex,” “funnel,” “tornado,” and “main subject” unless that is truly desired.

6. **Hero videos need less motion than card videos.**
   A hero background should be subtle, seamless, and readable behind text.

7. **For card videos, the motion must read at small size.**
   Keep the subject centered, simple, and not too wide.

---

## 8. Reusable Prompt Snippets

### A. Claude Code Prompt — Replace Homepage Only and Preserve Hover Effect

```text
I’m working in a copied Framer project. Rebuild ONLY the first/home page hero section using the new Cloudinary source images I provided.

Do not touch, edit, redesign, delete, or restructure the 2nd, 3rd, or 4th page/sections. Leave everything after the first homepage section exactly as-is.

Before deleting or rebuilding anything:
1. Inspect the current first-page button/card hover effect.
2. Save/reuse that exact hover behavior for the new Visual, Digital, and Creative cards.
3. Keep the same movement, glow, scale/lift, transition timing, and overall feel.

Use the clean no-text hero image as the base background.
Use the reference images only for placement.
Replace the old Visual, Digital, and Creative cards with the new card images.
Keep cards clickable.
Add the subtle darker shelf/gradient area behind the bottom cards.
Keep the footer pinned to the bottom of the page.
Do not generate new images.
Do not invent a new design direction.
```

---

### B. Claude Code Prompt — Static Image With Framer Motion Overlays

```text
Keep the source hero image completely static. Do not animate, scale, rotate, pan, zoom, or transform the image layer.

Add only separate animated overlay layers:
- very subtle drifting background haze
- soft cloud movement around the waist/lower body area
- low-opacity mist rising slowly upward
- optional faint light shimmer

Use CSS/Framer keyframes or motion properties with very low opacity, blur, and slow loop timing. The subject/model must remain unchanged. Do not use AI video for this effect.
```

---

### C. Runway Prompt — Subtle Hero Background Motion

```text
Animate this image as a premium cinematic website hero background. Keep the same exact composition, mood, and pastel color grading. Do not create a tornado, funnel, vortex, or single storm subject.

Create subtle elegant motion across the whole image: slow billowing clouds, soft drifting haze, gentle parallax depth, slight movement in the cloud ribbon, and faint warm light shifting through the clouds.

The camera movement should be extremely minimal because this is a homepage hero background. Use only a very slight smooth cinematic glide, almost imperceptible. No dramatic push-in, no orbiting, no shaky movement.

Keep the left and center areas visually open and readable for hero text and buttons. Make the animation loop naturally and seamlessly.

No tornado, no funnel, no vortex, no destructive storm, no giant central subject, no chaotic motion, no hard zoom-in, no excessive lightning, no people, no buildings, no text, no logos.
```

---

### D. Runway Prompt — Ultra-Safe Static Subject Hero

```text
Keep the camera completely locked with no camera movement at all. Do not move, redesign, or animate the subject. Keep the subject exactly as in the source image.

Only animate very subtle cloud movement in the background and slight soft cloud movement rising upward around the waist and lower body. Motion should be extremely minimal, calm, and seamless for a 5-second looping website hero background.
```

---

### E. Gemini Flash Prompt — Ask for Better Runway Direction

```text
I’m using this image as a small website card background on my homepage. It needs to represent AI motion. It should feel clean, cinematic, premium, and readable inside a card, not like a full-screen storm scene.

Please direct the Runway animation in a simple way: subtle AI-generated motion, soft pastel cloud movement, a focused smoky cloud-current traveling through the frame, and very subtle cloud lightning flickers in the background.

Keep the exact peach, pink, lavender, mauve, and soft orange color grading. The motion should be intentional, smooth, and loopable. Do not create a giant tornado, disaster storm, or random object flying away.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP 1 — Replacing Aura Homepage Buttons in Framer

1. Duplicate the Framer project before editing.
2. Upload finalized button images to Cloudinary.
3. Give Claude Code all Cloudinary URLs and reference images.
4. Tell Claude Code to inspect the current homepage button hover effect.
5. Tell Claude Code to preserve that hover effect exactly.
6. Replace only the three card images:
   - Visual
   - Digital
   - Creative
7. Keep existing links or map them to the correct pages.
8. Keep all other pages unchanged.
9. Check desktop breakpoint first.
10. Only then check responsiveness.

---

### SOP 2 — Creating Aura Digital Page Assets

1. Define the page structure:
   - top row = basic templates
   - middle row = creative custom sites
   - bottom row = AI/video/motion sites
2. Generate or design each card as a project preview, not a generic service link.
3. Keep color grading consistent:
   - peach
   - pink
   - lavender
   - mauve
   - soft orange
   - gentle purple
4. Avoid making all three rows look like similar AI cloud scenes.
5. Upload finalized images/videos to Cloudinary.
6. Use Framer text overlays for titles/labels when possible.
7. Add hover effects in Framer, not baked into images.

---

### SOP 3 — Testing Runway Motion Without Burning Credits

1. Start with a 5-second test.
2. Use simple Image-to-Video, not Workflow, for subtle website backgrounds.
3. Use low motion strength.
4. Keep prompts short if the model overreacts.
5. Avoid words like:
   - tornado
   - funnel
   - vortex
   - spiral
   - huge formation
6. If subject preservation fails twice, stop using Runway.
7. Move the effect into Framer overlays instead.

---

### SOP 4 — Framer Overlay Animation Instead of AI Video

Use this when the source image must stay exact.

1. Add the still image as the locked base layer.
2. Do not animate the base image.
3. Add background haze overlay.
4. Add masked waist/lower-body cloud overlay.
5. Animate overlays slowly using CSS/Framer motion.
6. Use low opacity and blur.
7. Loop over 10–20 seconds.
8. Keep motion subtle enough for hero text readability.

---

## 10. Future Agent Ideas

### Agent 1 — Aura Framer Page Rebuilder

Purpose:

- Inspect a Framer page.
- Identify existing sections.
- Preserve hover effects.
- Replace only the requested page/section.
- Refuse to touch unrelated pages unless explicitly authorized.

Core rules:

- Always inspect before changing.
- Preserve working interactions.
- Use Cloudinary assets exactly.
- Do not rename layers broadly during visual edits.

---

### Agent 2 — Aura Asset Librarian

Purpose:

- Track all Aura images/videos.
- Store filename, Cloudinary URL, use case, page, and version.
- Mark assets as:
  - hero
  - card
  - button
  - video background
  - reference only
  - deprecated

---

### Agent 3 — Runway Prompt Director

Purpose:

- Convert creative direction into short Runway prompts.
- Avoid overprompting.
- Select whether to use Image-to-Video, Workflow, or Framer overlays.
- Detect risky cases where subject preservation will likely fail.

---

### Agent 4 — Aura Motion System Agent

Purpose:

- Define motion language per Aura branch:
  - Visual = organic photographic movement
  - Digital = signal/glitch/interface movement
  - Creative = ember/reveal/portal movement
- Generate Framer/CSS overlay instructions for each.

---

## 11. Recommended Filename

`aura-digital-image-motion-framer-workflow.md`

---

## 12. Recommended Folder Inside the Repo

`/03-image-asset-workflows`

Reason:

This chat is primarily about the reusable workflow for generating, refining, hosting, animating, and implementing image/video assets for Aura Digital and Aura homepage cards. It also includes Claude Code / Framer implementation rules, but the center of gravity is the image and motion asset pipeline.

---

## 13. Agent-Ready Summary

Aura Digital is the web design / digital experiences branch of Aura Creative. It should feel like a premium cinematic digital gallery, not a generic web agency or SaaS page. Use the Aura universe color palette, but lighten it with peach, pink, orange, lavender, mauve, and soft purple so it feels professional and usable.

The Aura Digital page should use a 3x3 card grid: top row for basic reusable templates, middle row for creative custom sites, and bottom row for AI/video/motion concepts. Cards should represent real work/project categories, not generic service links.

For Framer/Claude Code work, edit only the requested page/section. Preserve the existing button hover effects before replacing card images. Use Cloudinary URLs for assets. Keep text/icons as Framer layers when possible.

Runway is useful for abstract motion cards and atmospheric videos, but unreliable when exact subject preservation matters. If Runway warps the subject, stop using AI video and instead use Framer/CSS overlay layers on top of a static image. For hero videos, use subtle ambient motion, not big cinematic action. For card videos, make motion readable at small size.

Final implementation rule: use AI video for abstract atmosphere; use Framer overlays for controlled, professional website motion when the source image must stay exact.
