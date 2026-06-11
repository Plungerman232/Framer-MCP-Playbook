# Aura Kinks — Aura Preloader + Visual Hero Asset Workflow Report

## 1. Chat Title / Topic

**Aura Kinks — Visual, Digital, and Creative Preloader Videos + Aura Visual Hero Image Direction**

This chat focused on building the visual asset system for the Aura website, especially the **Visual / Digital / Creative preloader transition videos** and the first concept pass for the **Aura Visual hero image**.

Primary project context:

- **Framer project:** `Aura TSX (copy 2)`
- **Website brand:** Aura Creative / Aura Visual / Aura Digital / Aura Creative
- **Working repo for documentation:** `https://github.com/Plungerman232/Framer-MCP-Playbook`
- **Main asset folder:** `Desktop → New Aura Hero → Color Graded`

---

## 2. Main Problem or Build Goal

The main goal was to create a consistent cinematic transition and visual identity system for Aura’s service pages.

The site already has a strong dark cosmic/canyon-based brand world. The next step was to make the individual service destinations feel connected but distinct:

- **Visual:** atmospheric, human, ethereal, wind, fashion/editorial energy
- **Digital:** glitchy, portal-like, sci-fi/data activation
- **Creative:** mysterious, light-up, subtle creative energy, less glitchy than Digital

The user wanted to build **4-second full-screen wide preloader animation videos** in Runway using the existing no-text preloader source images.

Important distinction:

- **Runway / Firefly / image tools:** used only when the user explicitly asks for image or video generation.
- **ChatGPT default role in this workflow:** prompt writer, creative director, Claude Code instruction generator, Framer/MCP systems organizer.

---

## 3. Tools Used

### Design / Build Tools

- **Framer**
  - Main website builder.
  - Working project: `Aura TSX (copy 2)`.
  - Used for hero page, service sections, preloaders, navigation, hover/click behavior, and page transitions.

- **Claude Code**
  - Used for implementation prompts and code-level changes.
  - Needs very specific instructions: exact sizes, timing, colors, layer order, what not to touch.

- **Framer MCP**
  - Used to connect Claude/agent workflows directly to Framer project structure.
  - Requires careful prompting to avoid Claude moving, duplicating, or rebuilding unintended layers.

- **Runway**
  - Intended for 4-second preloader animation videos.
  - Needs very strict negative prompts because it tends to over-animate, move the camera, morph faces, distort text, or add unwanted objects.

- **Firefly / Image Generation Tools**
  - Used or considered for image generation and image refinements.
  - Strong rule: do not generate unless explicitly requested.

- **Cloudinary**
  - Part of the broader Aura asset hosting workflow.
  - Useful for hosting generated image/video assets and passing stable URLs into Framer/Claude Code.

- **GitHub**
  - Final markdown documentation should be saved into:
    `https://github.com/Plungerman232/Framer-MCP-Playbook`

---

## 4. What Worked

### A. Separating actual source images from style-reference images worked

The correct asset logic is:

- **“No Text” images = actual Runway source frames / Framer backgrounds**
- **“Effect” images = style references only**

This prevents baked-in text or duplicated typography from polluting generated videos.

Correct source assets:

```text
Visual Wide Preloader No Text
Digital Wide Preloader No Text
Creative Wide Preloader No Text
```

Correct reference-only assets:

```text
Visual Preloader effect
Digital Preloader Effect
Creative preloader effect
```

### B. Visual preloader prompt direction worked conceptually

The Visual preloader should be:

- atmospheric
- elegant
- calm
- premium
- human but not overly dramatic
- slight head lift
- slow breath
- soft hair movement
- subtle fabric movement
- no camera movement
- no face/body distortion

This is the right creative lane for Aura Visual.

### C. Digital prompt direction worked conceptually

The Digital preloader direction was clearly separated from Visual:

- central magenta/purple portal activation
- data-rain particles
- thin holographic traces
- subtle scanlines
- micro-glitch pulses
- water reflection shimmer
- controlled sci-fi energy

This gives Aura Digital its own identity without breaking the larger Aura world.

### D. Creative prompt direction worked conceptually

Creative was correctly positioned as:

- less glitchy than Digital
- more mysterious
- soft light-up effect
- lavender/pink/moonlit energy
- subtle particles
- gentle bloom
- creative spark / activation feeling

This keeps Creative distinct from Digital while still using the same canyon/cosmic environment.

### E. The Aura Visual hero image direction started strong

The generated wide hero composition had strong potential:

- full laptop-width 16:9 layout
- canyon/water world connected to Aura Digital and main Aura hero
- subject placed on the right
- open negative space on the left/center for web copy
- soft airy pink/lavender/bluish palette

The main issue was not composition. The issue was subject style.

### F. The creative-director correction was accurate

The first Aura Visual hero image made the woman look too real and slightly too “stoner/lifestyle poster.” The correct correction was:

- less photoreal
- more stylized
- closer to the Visual preloader girl’s aesthetic
- more editorial/fashion/ethereal
- cooler and more artistic
- less straight realism
- more premium website homepage energy

---

## 5. What Failed

### A. ChatGPT accidentally triggered image generation multiple times

The user repeatedly asked for prompt-writing and creative direction, but image generation was triggered unintentionally.

This is a major workflow failure.

Reusable rule:

```text
Do not generate images unless the user explicitly says to generate an image.
If the user asks for a prompt, instructions, creative direction, Runway prompt, Firefly prompt, Claude Code prompt, or Framer prompt, only provide text.
```

### B. The assistant confused “develop prompt” with “generate image”

When the user asked to “develop the preloader animation video prompt,” the correct output was a Runway prompt only.

The wrong behavior was triggering image generation.

### C. Sandbox image links had preview/display issues

After generation, the user opened a sandbox file link and saw nothing. A better asset handoff workflow is needed.

Reusable fix:

```text
When providing generated assets, give both PNG and JPG versions when possible.
Use a smaller JPG fallback because it opens more reliably in browser/chat previews.
```

### D. The first Visual hero generated subject looked too photoreal

The environment and framing were strong, but the subject did not fully match the Aura brand identity.

Problem:

- too realistic
- too lifestyle/still-photo
- not enough stylized Aura aesthetic
- slightly too sensual/stoner/poster-like
- less premium website homepage

Correct fix:

- semi-illustrated
- painterly/editorial
- ethereal clothing
- more stylized silhouette
- cooler, mysterious, high-end tone

### E. Runway requires strict restraint language

Runway often adds too much motion, especially when asked for atmosphere. Prompts must repeatedly control:

- no camera movement
- no zoom/pan/tilt
- no face distortion
- no body morphing
- no new text
- no new objects
- no aggressive glitch
- no strobe
- no oversaturation

---

## 6. Final Decisions

### A. Two separate preloader systems should remain

#### 1. Hero/Header Preloaders

Used when clicking:

- VISUAL
- DIGITAL
- CREATIVE

These use the full cinematic preloader images/videos.

Component idea:

```text
AuraPreloaderTransition
```

Behavior:

```text
Click header/hero Visual/Digital/Creative
→ show full cinematic preloader overlay for about 3.7–4 seconds
→ route to matching service page
```

#### 2. Page 2 Card Portal Transitions

Used when clicking service cards on Page 2.

Component idea:

```text
Page2CardPortalTransition
```

Behavior:

```text
Click Page 2 card
→ use clicked thumbnail/video as transition source
→ blurred/darkened full-screen duplicate background
→ centered enlarged card
→ hold around 3 seconds
→ subtle warp/vortex pulse
→ navigate to matching page
```

### B. Use no-text images as real sources

The preloader background should use:

```text
Visual Wide Preloader No Text
Digital Wide Preloader No Text
Creative Wide Preloader No Text
```

The effect images should not be used as the actual background unless specifically requested.

### C. Text should stay native/editable in Framer

Do not bake preloader text into images/videos.

Text should be native Framer text:

```text
VISUAL
PHOTOGRAPHY & VISUAL STORYTELLING
ENTER
```

```text
DIGITAL
WEB DESIGN & DIGITAL EXPERIENCES
ENTER
```

```text
CREATIVE
CREATIVE DIRECTION & STRATEGIC CONSULTING
ENTER
```

### D. Purple side borders should be removed

The correct preloader edge solution is:

```text
full-screen blurred duplicate background
centered main card
soft shadow
subtle/no border
no strong purple outline
```

### E. Aura Visual hero image should match the canyon world but feel more editorial

The Visual page should share the Aura canyon/water language but use:

- softer colors
- more air
- more blush/pink/lavender/blue
- human subject as visual storytelling symbol
- stylized/painterly/editorial subject
- room for website UI and hero text

---

## 7. Reusable Rules

### Rule 1 — Image Generation Permission Rule

```text
Never generate an image unless the user explicitly asks for image generation.
If the user asks for a prompt, Runway prompt, Firefly prompt, Framer prompt, Claude Code prompt, or creative direction, only provide text.
```

### Rule 2 — Aura Asset Source Rule

```text
For Aura preloaders:
- “No Text” assets are real source images/backgrounds.
- “Effect” assets are style references only.
- Do not use effect-reference images as the final Framer background unless specifically asked.
```

### Rule 3 — Runway Camera Lock Rule

```text
Always tell Runway:
camera must stay completely locked.
No zoom, pan, tilt, push-in, pull-back, shake, parallax, reframing, or lens movement.
```

### Rule 4 — Runway Text Safety Rule

```text
If source image includes or relates to branding/text:
tell Runway not to add, move, warp, blur, flicker, duplicate, redraw, or distort text/icons.
```

### Rule 5 — Claude Code Precision Rule

```text
Never tell Claude Code vague instructions like “make it professional.”
Give exact dimensions, colors, timing, layer order, hover behavior, click behavior, routes, and what not to touch.
```

### Rule 6 — Framer Safety Rule

```text
Always tell Claude:
Do not rebuild the site.
Do not move unrelated sections.
Do not duplicate components.
Do not change unrelated styling.
Do not change layout unless explicitly requested.
Test desktop, tablet, phone, Preview/Play mode, hover, click, overlays, routes, and spacing.
```

### Rule 7 — Preloader Text Rule

```text
Preloader text should be native/editable in Framer, not baked into the image/video.
```

### Rule 8 — Website Hero Composition Rule

```text
For Aura hero images, preserve negative space for nav, title, subtitle, CTA buttons, and footer.
Do not fill the entire frame with subject/detail.
The image must work as a website background, not just as a poster.
```

### Rule 9 — Generated Asset Link Rule

```text
When handing off a generated image, provide a PNG and a smaller JPG fallback if possible.
If the sandbox preview fails, the JPG is usually safer for opening/downloading.
```

---

## 8. Reusable Prompt Snippets

## A. Runway Visual Preloader Prompt

```text
Use the provided Visual preloader image as the exact source frame. Create a 4-second full-screen 16:9 cinematic website preloader video. The camera must stay completely locked in place: no zoom, no pan, no tilt, no push-in, no pull-back, no shake, no parallax, no reframing, and no lens movement. Preserve the exact composition, crop, lighting direction, colors, background, water, rocks, sky, subject pose, face, hair shape, clothing, and overall atmosphere.

The motion should be very subtle, elegant, premium, and atmospheric. The woman should feel alive, but barely moving. Add only a slow, natural breath-like motion: her chest and shoulders rise slightly, and her head lifts upward just a tiny amount, as if she is taking one calm deep breath. Keep the movement minimal and graceful, not dramatic. Her expression should stay serene and unchanged. Preserve her facial structure, identity, body shape, pose, and styling.

Add a soft natural breeze effect. Her loose hair strands can move gently and slowly, especially around the edges of the silhouette. The translucent fabric/clothing can shift very lightly as if wind is passing through it. Keep the wind soft and realistic, not strong. No whipping hair, no large cloth movement, no pose change.

Animate the environment subtly: faint warm pink/orange atmospheric glow, soft drifting dust or ember-like particles, gentle haze movement, very slight shimmer in the water reflection, and a calm cinematic sunset atmosphere. The sky can have a barely noticeable slow glow pulse, like warm light passing through clouds. The overall mood should feel mysterious, luxurious, cinematic, feminine, calm, and high-end.

This is for a premium website transition preloader, so the video should feel polished and controlled. Motion should be restrained and slow. Keep the first frame and last frame visually close so it can transition smoothly. Do not add any text, logos, symbols, graphics, borders, overlays, UI, or typography. Do not make it look like a music video or fantasy action scene. Do not over-animate.

Negative prompt: no camera movement, no zoom, no pan, no tilt, no shake, no push-in, no pull-back, no reframing, no face distortion, no facial morphing, no body morphing, no changing identity, no extra people, no new objects, no added text, no logo, no symbols, no harsh flashes, no aggressive lightning, no heavy glitch, no dramatic pose change, no strong wind, no whipping hair, no flying fabric, no cartoon style, no anime style, no plastic skin, no oversaturation, no blurry subject, no warped anatomy, no flickering face, no jump cuts, no chaotic motion.
```

## B. Runway Digital Preloader Prompt

```text
Use the provided Digital preloader image as the exact source frame. Create a 4-second full-screen 16:9 cinematic website preloader video. The camera must stay completely locked: no zoom, no pan, no tilt, no push-in, no pull-back, no shake, no parallax, no reframing, and no lens movement. Preserve the exact composition, crop, canyon landscape, water reflection, mountains, sky, color palette, lighting, and central glowing digital structure.

The animation should feel like a premium digital portal activating inside the landscape. Keep the movement controlled, elegant, and high-end, not chaotic. The central magenta/purple digital light column should slowly brighten and pulse, as if the portal is powering on. Add subtle vertical data-rain particles and thin holographic light traces rising and falling inside the glowing center. These details should feel integrated into the atmosphere, not pasted on top.

Add a refined glitch effect inspired by a cinematic sci-fi interface: very thin horizontal glitch streaks, tiny pixel fragments, faint chromatic separation near the edges, subtle scanline texture, and small digital particles flickering in the sky and water reflection. The glitch should be subtle and tasteful, only appearing in brief micro-pulses. Do not make the entire image glitch heavily. The landscape should remain stable and readable.

Animate the environment with slight atmospheric movement: faint haze drifting around the portal, soft shimmer in the water reflection, gentle glow bloom from the magenta light source, and barely noticeable cloud movement. The portal glow can reflect softly across the water, creating a slow pulse from center to bottom. Keep the mood mysterious, futuristic, luxurious, dark, cinematic, and immersive.

The motion should build gently over the 4 seconds: start calm, slowly increase the portal glow and digital particles, then finish with a subtle glitch pulse and light bloom as if the viewer is about to enter the Digital world. Keep the first and last frame visually close enough that the video can loop or transition smoothly. Do not add any text, logos, symbols, typography, UI, buttons, borders, or new objects.

Important restraint: Runway should keep this subtle. The animation should feel like a controlled luxury website transition, not a loud cyberpunk music video. Use micro-glitches, elegant light pulses, and atmospheric digital energy. No aggressive distortion.

Negative prompt: no camera movement, no zoom, no pan, no tilt, no shake, no push-in, no pull-back, no reframing, no heavy glitch, no chaotic distortion, no large screen tearing, no aggressive flashes, no full-image warping, no new buildings, no people, no vehicles, no birds, no added text, no logos, no symbols, no UI, no cartoon style, no anime style, no oversaturation, no neon overload, no blurry landscape, no jump cuts, no flickering entire frame, no random objects, no portal explosion, no camera shake, no rapid strobe, no harsh lightning.
```

## C. Runway Creative Preloader Prompt

```text
Use the provided Creative preloader image as the exact source frame. Create a 4-second full-screen 16:9 cinematic website preloader video. The camera must stay completely locked in place: no zoom, no pan, no tilt, no push-in, no pull-back, no shake, no parallax, no reframing, and no lens movement. Preserve the exact composition, crop, landscape, sky, moon/light source, mountains, water/reflections, central structure, colors, and overall dark cinematic atmosphere.

The animation should feel like a mysterious creative world slowly activating. This should be elegant, atmospheric, and premium — not glitchy, chaotic, or overly sci-fi. The main effect should be subtle illumination: soft lavender, pink, and moonlit energy gently brightening through the center of the scene, as if hidden creative energy is coming alive. The light should slowly pulse and breathe, not flash.

Add a refined “creative spark” feeling: faint glowing particles drifting slowly through the air, soft mist movement, gentle shimmer in the water reflection, and delicate light rays or aura lines appearing briefly around the central illuminated area. These should feel natural and cinematic, like magical atmosphere or creative inspiration forming inside the environment. The glow can slowly bloom outward, then settle back down.

The sky and background should have subtle movement only: barely noticeable cloud drift, soft atmospheric haze, and a gentle moonlit glow pulse. If there is a central portal, doorway, orb, or light source, make it feel like it is slowly charging with energy. The effect should feel like “entering the Creative world” — mysterious, luxurious, calm, artistic, and immersive.

The motion should build gently over the 4 seconds: begin quiet and still, slowly increase the glow and floating particles, then finish with a soft light bloom or aura pulse as if the transition is about to open. Keep the first frame and last frame visually close enough for a smooth website transition. The final pulse should be subtle, not explosive.

Do not add any text, logos, icons, symbols, typography, UI, borders, buttons, or new objects. Do not redesign the scene. Do not make it look like a fantasy battle, music video, cartoon, or heavy VFX scene. The animation should stay restrained and polished for a high-end website preloader.

Important restraint: keep all motion minimal and atmospheric. Runway should not overdo the effect. Use soft glow, subtle particles, slow haze, gentle reflection shimmer, and a quiet creative energy pulse. The scene should feel alive, but still premium and controlled.

Negative prompt: no camera movement, no zoom, no pan, no tilt, no shake, no push-in, no pull-back, no reframing, no heavy glitch, no aggressive lightning, no explosions, no strong flashes, no portal blast, no large warping, no added text, no logos, no symbols, no UI, no people, no vehicles, no birds, no new buildings, no cartoon style, no anime style, no oversaturation, no neon overload, no chaotic particles, no rapid strobe, no jump cuts, no blurry landscape, no distorted reflections, no full-image flicker, no dramatic scene changes, no random objects.
```

## D. Claude Code Prompt — Implement Hero/Header Preloaders

```text
In the Framer project Aura TSX (copy 2), implement or refine the Hero/Header Visual, Digital, and Creative preloader transition system.

Do not rebuild the site. Do not move or resize unrelated sections. Do not duplicate components. Do not change Page 2 hover effects. Do not change unrelated typography, colors, spacing, or images.

Create/maintain a component named AuraPreloaderTransition.

This component should be triggered only by the Hero/Header VISUAL, DIGITAL, and CREATIVE links.

Use these assets as the actual preloader backgrounds:
- Visual Wide Preloader No Text
- Digital Wide Preloader No Text
- Creative Wide Preloader No Text

Do not use the effect-reference images as the real background. They are only style references.

Preloader behavior:
- Full-screen overlay
- Duration around 3.7–4.0 seconds
- Then route to the matching page
- VISUAL routes to Visual page
- DIGITAL routes to Digital page
- CREATIVE routes to Creative page

Preloader layout:
- Outer overlay: fixed full-screen 100vw/100vh
- Use a blurred duplicate of the same image as the background
- Background duplicate: object-fit cover, scale 1.08–1.15, blur 28–42px, brightness 0.45–0.6, saturation 0.85–0.95, opacity 0.75–0.9
- Add dark overlay rgba(5,7,12,0.35–0.55)
- Main card centered
- Main card width min(92vw, 1280px)
- Preserve image/video aspect ratio
- Border radius 14–18px
- Border rgba(255,255,255,0.08) or none
- Soft cinematic shadow
- Remove any strong purple side border/bar look

Text should be native/editable Framer text layered over the preloader:
VISUAL / PHOTOGRAPHY & VISUAL STORYTELLING / ENTER
DIGITAL / WEB DESIGN & DIGITAL EXPERIENCES / ENTER
CREATIVE / CREATIVE DIRECTION & STRATEGIC CONSULTING / ENTER

Text style:
- color #F4F1F8
- wide letter spacing
- large premium serif title
- small uppercase subtitle
- understated ENTER with thin underline/glow
- centered lower-middle/bottom of card

Test:
- Desktop/tablet/mobile
- Preview/Play mode
- Header links
- No duplicate preloaders
- No hidden overlay blocking clicks after transition
- No white gaps
- Routes work correctly
```

## E. Claude Code Prompt — Implement Page 2 Card Portal Transitions

```text
In Aura TSX (copy 2), implement a separate Page 2 card click transition system.

Do not use the Hero/Header Visual/Digital/Creative full-screen preloaders for Page 2 card clicks.

Create/maintain a separate component named Page2CardPortalTransition.

Page 2 cards:
- Visual card
- Digital card
- Creative card

Each Page 2 card should use its own clicked thumbnail/video as the transition source.

Do not replace Page 2 videos.
Do not change Page 2 layout.
Do not change Page 2 hover effects.
Do not stretch the thumbnail/video edge-to-edge in a low-quality way.

Transition layout:
- Full-screen fixed overlay
- Overlay background rgba(5,7,12,0.92)
- Use blurred/darkened duplicate of the clicked card media as full-screen background
- Background media object-fit cover
- Scale 1.15
- Blur 30–44px
- Brightness 0.35–0.5
- Saturation 0.8–0.95
- Opacity 0.7–0.85
- Add dark overlay rgba(5,7,12,0.35)

Main transition card:
- Centered
- Width min(78vw, 980px)
- Preserve original media aspect ratio
- Border radius 14px
- Overflow hidden
- Subtle border rgba(255,255,255,0.08)
- Soft cinematic shadow

Timing:
- 0–0.35s: overlay fades in, card opacity 0→1, card scale 0.96→1
- 0.35–2.35s: card holds/plays
- 2.35–3.0s: subtle warp/portal pulse, card scale 1→1.035, radial glow, a few thin horizontal streaks
- Navigate at the end

Optional text below card:
- VISUAL / DIGITAL / CREATIVE
- ENTERING
- Wide tracking
- rgba(244,241,248,0.72)
- Omit if it feels too busy

Testing:
- Click each Page 2 card
- Confirm it does not trigger the Hero preloader
- Confirm hover effects still work
- Confirm no layout shifts
- Confirm overlay disappears after route
- Confirm desktop/tablet/mobile behavior
```

## F. Aura Visual Hero Image Prompt Direction

```text
Create a full-width 16:9 laptop website hero image for the Aura Visual page.

The image should match the Aura Digital page and main Aura hero world: cinematic canyon landscape, reflective water, soft pastel pink/lavender/blush/blue atmosphere, elegant haze, high-end creative website mood.

Place a stylized woman on the right side of the composition, sitting on a rocky canyon/mountain ledge and looking out over the canyon. She should be turned sideways, one leg extended horizontally along the rock, the other leg bent upward with her forearm or elbow resting on the raised knee. She should feel calm, poised, mysterious, and editorial.

Leave generous negative space across the left and center for website hero text, nav, subtitle, and CTA buttons.

The woman should not look like a normal photoreal lifestyle model. Make her semi-illustrated, softly painterly, ethereal, and fashion-forward. Her styling should connect to the Aura Visual preloader girl: translucent layered fabric, cool artistic silhouette, wind-touched hair, refined visual storytelling energy.

The vibe should be cool, aesthetic, high-end, and professional as a website homepage — not stoner, not overly sensual, not a poster, not too realistic.

No text, no logos, no UI, no buttons, no borders.
```

---

## 9. SOPs / Step-by-Step Workflows

## SOP 1 — Creating Aura Preloader Videos in Runway

1. Choose the correct no-text source image:
   - `Visual Wide Preloader No Text`
   - `Digital Wide Preloader No Text`
   - `Creative Wide Preloader No Text`

2. Use the effect image only as a visual reference:
   - `Visual Preloader effect`
   - `Digital Preloader Effect`
   - `Creative preloader effect`

3. Paste the matching Runway prompt.

4. Set video length:
   - 4 seconds
   - 16:9
   - full-screen wide

5. Check first output for:
   - no camera movement
   - no added text
   - no face/body distortion
   - no harsh flashes
   - no unwanted new objects
   - no warped landscape
   - usable first/last frame

6. Export the best version.

7. Upload final MP4/WebM to Cloudinary.

8. Copy stable Cloudinary URL.

9. Give URL to Claude Code for Framer implementation.

10. Test in Framer Preview.

---

## SOP 2 — Framer Preloader Implementation

1. Confirm assets are uploaded/available:
   - image/video URLs
   - Cloudinary links if external

2. Implement `AuraPreloaderTransition` for hero/header links only.

3. Implement `Page2CardPortalTransition` for Page 2 service cards only.

4. Keep systems separate.

5. Use native Framer text for preloader labels.

6. Use blurred duplicate background to avoid ugly side borders.

7. Test:
   - Visual link
   - Digital link
   - Creative link
   - About scroll
   - Contact scroll
   - footer links
   - Page 2 card clicks
   - Page 2 hover states
   - mobile/tablet/desktop

8. Inspect for:
   - hidden overlays blocking clicks
   - duplicate text
   - duplicate preloaders
   - white gaps
   - route failure
   - layout shift

---

## SOP 3 — Claude Code Prompting for Framer MCP

1. State the project name first:
   ```text
   Framer project: Aura TSX (copy 2)
   ```

2. State exact scope:
   ```text
   Only edit the preloader transition system.
   ```

3. State what not to touch:
   ```text
   Do not rebuild the site.
   Do not move unrelated sections.
   Do not change Page 2 layout.
   Do not duplicate components.
   ```

4. Give component names:
   ```text
   AuraPreloaderTransition
   Page2CardPortalTransition
   ```

5. Give exact dimensions, colors, timing, and routes.

6. Give test checklist.

7. Ask Claude to report what it changed.

---

## SOP 4 — Generated Hero Image Refinement

1. Generate or select a base hero image only when explicitly asked.

2. Evaluate as a website background, not just an artwork.

3. Check:
   - Is there negative space for UI?
   - Does the subject match brand style?
   - Is the image too photoreal?
   - Is the vibe too sensual, poster-like, or lifestyle?
   - Does it match Aura Digital / Aura main world?

4. If subject is wrong, refine the subject without destroying the composition:
   - less photoreal
   - more stylized
   - more editorial
   - more ethereal
   - more fashion-forward
   - more premium website mood

5. Export both:
   - PNG master
   - compressed JPG fallback

6. Upload final asset to Cloudinary for Framer use.

---

## 10. Future Agent Ideas

## A. Aura Asset Librarian Agent

Purpose:

- Organize all Aura assets by page, usage, source/reference status, and final Framer/Cloudinary URL.

Responsibilities:

- Detect “No Text” vs “Effect” assets.
- Create a `manifest.md` or `assets.json`.
- Store:
  - filename
  - source location
  - final Cloudinary URL
  - intended page/component
  - source/reference/final status
  - notes

## B. Framer Transition QA Agent

Purpose:

- Test preloader and transition behavior after Claude Code edits.

Checklist:

- no hidden overlays
- no white gaps
- correct routes
- correct duration
- hover effects preserved
- mobile/tablet/desktop usable
- Page 2 card transitions separate from Hero preloaders

## C. Runway Prompt Compression Agent

Purpose:

- Convert full 5000-character creative prompts into 1000-character Runway-safe versions.

Rules:

- preserve camera lock
- preserve negative prompt
- preserve subject identity/style restraint
- preserve key motion directions
- remove fluff

## D. Cloudinary Upload + URL Agent

Purpose:

- Upload final exported images/videos.
- Generate stable URLs for Framer.
- Create folder naming system:
  ```text
  aura/preloaders/visual/
  aura/preloaders/digital/
  aura/preloaders/creative/
  aura/heroes/visual/
  ```

## E. Claude Code Framer Safety Agent

Purpose:

- Before any Framer MCP change, inject safety rules:
  - do not rebuild
  - do not move unrelated sections
  - preserve breakpoints
  - preserve hover/click
  - test preview
  - report changes

---

## 11. Recommended Filename

```text
aura-preloader-visual-hero-asset-workflow.md
```

---

## 12. Recommended Folder Inside Repo

```text
/03-image-asset-workflows
```

Reason:

This chat is primarily about image/video generation workflow, Runway preloader prompts, visual asset direction, and website hero asset refinement. It also contains Framer/Claude implementation rules, but the core reusable value is the asset workflow.

Secondary possible folder:

```text
/07-aura-brand-systems
```

Use this secondary folder only if creating a duplicate brand-system reference later.

---

## 13. Agent-Ready Summary

This chat established the Aura preloader and hero asset workflow. The Aura website uses a cinematic canyon/cosmic visual system with service-specific identities: Visual is atmospheric and editorial, Digital is glitch/portal/data-driven, and Creative is subtle light-up creative energy. For preloaders, always use the “Wide Preloader No Text” images as source assets and use the “Effect” images only as style references. Hero/Header Visual/Digital/Creative clicks should use full cinematic `AuraPreloaderTransition` overlays. Page 2 service card clicks should use a separate `Page2CardPortalTransition` based on the clicked thumbnail/video, with a blurred background duplicate, centered enlarged card, 3-second hold, and subtle warp pulse. Preloader text must remain native/editable in Framer. Purple side borders should be replaced by blurred full-screen image extensions.

The major workflow rule is that ChatGPT should not generate images unless the user explicitly asks for image generation. If the user asks for a Runway, Firefly, Framer, or Claude Code prompt, provide text only. Claude Code prompts must be exact and include colors, dimensions, timing, component names, route behavior, and explicit “do not touch” rules. Runway prompts must strongly lock camera movement and prevent text distortion, face morphing, body morphing, new objects, aggressive flashes, and over-animation.

The Aura Visual hero direction should match the canyon/water world of Aura Digital and the main Aura hero while feeling softer, more editorial, and more Visual-focused. The subject should be stylized/semi-illustrated rather than photoreal, sitting on a canyon ledge on the right with negative space left/center for web UI. The mood should be cool, aesthetic, premium, and professional — not stoner, not overly realistic, not poster-like.

---

# Final Filing Decision

## Name the markdown file:

```text
aura-preloader-visual-hero-asset-workflow.md
```

## Put it in this folder:

```text
/03-image-asset-workflows
```

## This should become:

```text
SOP + prompt snippet + agent instruction
```

Breakdown:

- **SOP** because it defines repeatable workflows for Runway, Framer preloaders, Cloudinary handoff, and Claude Code implementation.
- **Prompt snippet** because it contains reusable Visual/Digital/Creative Runway prompts and Claude Code prompts.
- **Agent instruction** because the “do not generate images unless explicitly requested” rule and Claude Code safety rules should be enforced across future agents.
