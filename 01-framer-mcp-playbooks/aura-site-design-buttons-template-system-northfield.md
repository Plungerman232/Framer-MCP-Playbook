# Aura Site Design and Buttons — Framer Template System, Asset Workflow, and Northfield Starter Site

## 1. Chat Title / Topic

**Aura Site Design and Buttons**

This chat focused on turning the Aura Digital visual concept into a real Framer/Claude Code build system: a 9-card template showcase, individual image asset workflows, AI/motion animation prompts, and the revised direction for Template #1, **Northfield**.

---

## 2. Main Problem or Build Goal

The main goal was to develop the Aura Digital page into a clickable demo-template system. The Aura Digital homepage has 9 placeholder cards. Each card should become a full demo website, not just a static image.

The business goal is to let Aura Digital show a range of web offerings:

- simple starter websites for local businesses
- standard service/business websites
- fuller growth websites
- creative/content-driven custom builds
- AI/motion/experimental web experiences

The first real build target became **Northfield**, originally treated like a minimal architecture site, but later corrected into a much more practical starter template for local service businesses such as barbershops, trainers, salons, photographers, wellness brands, consultants, and small studios.

Northfield should be the simplest top-row template: premium, clean, short, practical, and easy to customize.

---

## 3. Tools Used

### Framer

Framer is the main site-building tool. The user has a Framer project open with the Framer MCP connected.

Key preference:

- use native Framer layers whenever possible
- keep sites visually editable
- avoid making the whole website as one giant code component
- use code only for special effects or reusable interactions

### Claude Code

Claude Code is intended to operate Framer through the MCP. It should receive clear build prompts with exact page counts, image paths, section structures, and “do not build” constraints.

### Framer MCP

The Framer MCP should be used to create and edit Framer pages, components, sections, links, and image placements directly in the active Framer project.

### ChatGPT Image Generation

Used to generate template images, supporting website assets, and mockups. The most important lesson was that production assets need to be generated as individual PNG/JPEG files, not moodboards.

### Runway / Pika-style video prompts

Used for AI/motion animation direction. Prompts need to specify movement, camera behavior, loop length, energy flow, and negative constraints.

### GitHub

Target repo:

`https://github.com/Plungerman232/Framer-MCP-Playbook`

This report is intended to be saved in that repo.

### Cloudinary

Not actively used in this chat segment, but relevant to the broader Aura workflow for hosting image/video assets later.

### Codex

Not directly used in this segment, but the resulting report is intended to support future Codex/GitHub organization workflows.

---

## 4. What Worked

### 4.1 The 9-template system became clear

The Aura Digital page should function as a 9-card demo-site universe.

#### Top Row — Essential Templates

1. **Northfield — Starter / Essential Clarity Site**  
   Simplest local-service site. Best for barbershops, trainers, salons, photographers, wellness brands, consultants, and other small service businesses.

2. **Haven — Standard Service Site**  
   More developed business/service site with more pages, more structure, and more links.

3. **Vera — Premium Growth Site**  
   Fuller growth/business site with additional pages, features, testimonials, galleries, FAQs, and stronger brand structure.

#### Middle Row — Creative Custom Builds

4. **Saule & Co — Content / Video Brand Build**  
   Built around custom photo/video content and content capture.

5. **Wildsmart — Editorial Discovery Site**  
   Story-based, travel/editorial/discovery style.

6. **Aurelian — Signature Cinematic Brand Site**  
   Premium cinematic brand-experience site.

#### Bottom Row — AI / Motion / Experimental

7. **Lucid Labs — AI Motion Concept Site**  
   Cloud-motion, perception, generative visuals, animated hero.

8. **Echorame — Intelligence In Motion Site**  
   AI/human intelligence, neural systems, energy visuals.

9. **Nexus Studio — Experimental Interface Site**  
   Abstract glass portal/interface visuals, AI film/concepts/tooling energy.

---

### 4.2 The demo-sites-as-portfolio strategy worked

Until client work exists, the 9 demo sites can be shown as:

- Concept Builds
- Template Previews
- Aura Digital Demo Sites
- Selected Experiments

This lets Aura show quality and range without pretending the demos are client projects.

Reusable positioning:

> Choose a starting point. We’ll shape it around your brand, content, and goals.

This is stronger than saying “pick a template.”

---

### 4.3 Individual production assets worked better than moodboards

A recurring lesson was that image generation should create real website files, not reference boards.

Useful asset structure per template:

- hero image
- secondary/detail image
- about/process image
- service/feature image
- CTA/footer image
- optional gallery/detail image

Reusable rule:

> Moodboards are only references. Production assets must be individual files with no text, no borders, no UI labels, and no collage layout.

---

### 4.4 Animation prompts improved when made more active

The first animation prompts were too subtle. The AI/motion pages need more action, motion, and camera movement.

Better animation direction includes:

- camera glide
- forward push-in
- cloud billowing
- light pulses
- particles/sparks
- stronger vortex/tornado-style movement
- parallax depth
- visible energy flow

Ultra-short prompt that worked for low-credit animation:

> Forward camera glide following glowing horizon path, clouds billowing dynamically.

---

### 4.5 Archizen was useful as reference, but not as the final base

At first, **Archizen** seemed like a good free Framer template because it matched a minimal architecture look. After clarifying the actual business goal, it became clear that Archizen is too big for Template #1.

Problems:

- too many pages
- too many images
- too complex
- too architecture-portfolio oriented
- not right for a simple local-service starter site

Final decision:

> Do not force a full Framer marketplace template onto the first Aura Digital starter site. Build a lightweight preset layout system instead.

---

## 5. What Failed

### 5.1 Moodboards were generated when individual assets were needed

Several outputs were collages/moodboards when the user needed separate PNG/JPEG assets.

Why this failed:

- moodboards cannot be dropped directly into Framer sections
- text/UI overlays were unwanted
- cropping boards creates compromised files
- the user needed real assets, not presentation boards

Fix:

> Always specify: “Generate separate standalone images, no text, no UI, no collage, no borders, each image as its own PNG/JPEG.”

---

### 5.2 Cropping moodboards was not the correct fix

A moodboard was cropped into separate files, but the user wanted newly generated clean standalone assets. Cropping should only be used when specifically requested.

Rule:

> If the source is a moodboard, do not crop it as production unless the user asks. Regenerate each panel as a clean standalone image.

---

### 5.3 Northfield became too architecture-heavy at first

The initial direction made Northfield feel like a premium architecture portfolio. The corrected direction is a simple premium local-service starter site.

User’s corrected direction:

- simplest template in top row
- good for barbershop/local service use
- hero image/video
- services/booking
- contact/info
- no huge template
- no unnecessary pages

Lesson:

> Premium does not mean long or complex.

---

### 5.4 Free Framer templates may be too bloated

Free templates can help as references, but often contain too much structure for the actual Aura packages.

Better approach:

- use marketplace templates for inspiration only
- build Aura’s own preset Framer layouts
- control page count, section count, visual system, and complexity

---

### 5.5 Claude Code prompts must be exact

Vague prompts create poor builds. Claude Code needs explicit constraints.

Bad:

> Make it nicer and premium.

Better:

> Use native Framer layers. Build a 3-page local-service starter site. Create Home, Services/Booking, Contact. Use warm cream, soft charcoal, serif headlines, uppercase nav, thin borders, strong hero image/video, and subtle motion. Do not create extra pages.

---

## 6. Final Decisions

### 6.1 Northfield should be a starter local-service site

Northfield is the first and simplest Aura Digital template.

Best for:

- barbershops
- trainers
- salons
- photographers
- wellness brands
- consultants
- small contractors
- local service businesses

Core pages:

1. **Home**
2. **Services / Booking**
3. **Contact / Info**

Core Home sections:

- hero image/video
- short brand intro
- services preview
- media/gallery strip
- booking CTA
- footer

Core Services/Booking sections:

- service list
- optional pricing or “starting at”
- booking button/link
- hours/location if needed

Core Contact/Info sections:

- contact form
- phone/email
- location
- socials
- optional map

---

### 6.2 Top row should scale by complexity

#### Template #1 — Starter Site

3 pages max:

- Home
- Services/Booking
- Contact/Info

#### Template #2 — Standard Site

4 pages:

- Home
- Services
- About
- Contact/Booking

#### Template #3 — Growth Site

5–6 pages:

- Home
- Services
- About
- Gallery/Work
- FAQ
- Contact/Booking

---

### 6.3 Aura Digital should use reusable preset Framer layouts

The best long-term workflow is to create:

- preset page layouts
- reusable Framer sections
- custom Framer components
- reusable effects
- consistent complexity tiers
- easy image/copy/client-brand swapping

This is better than searching for a new full Framer template every time.

---

### 6.4 Native Framer layers are preferred

Claude Code should be told:

- use Framer MCP
- use native Framer layers
- keep components visually editable
- avoid full code-component rebuilds
- use code only for special effects or reusable interactive components

---

### 6.5 Premium simplicity is the main design principle

Aura sites should feel:

- cinematic
- premium
- minimal
- elegant
- intentional
- not cluttered
- not generic SaaS
- not cheap-looking

Simple pages can still feel expensive with strong imagery, elegant typography, restrained copy, clean spacing, subtle motion, and a consistent color system.

---

## 7. Reusable Rules

### Rule 1 — Do not overbuild starter templates

The first template in any row should be intentionally small.

For Template #1, avoid:

- huge portfolios
- 10+ sections
- unnecessary CMS systems
- too many image slots
- multi-page agency layouts
- complex animations

---

### Rule 2 — Use marketplace templates only as references

Do not blindly build from full Framer Marketplace templates for simple local-business packages. Study the layout, extract what works, then rebuild a lighter Aura version.

---

### Rule 3 — Production image assets must be individual files

When generating assets:

- no moodboards
- no collage
- no text
- no fake UI
- no labels
- no borders
- no multi-panel layout

Each image should be a standalone PNG/JPEG ready for Framer.

---

### Rule 4 — Claude Code needs exact constraints

Always specify:

- page count
- page names
- section list
- image paths
- visual style
- what not to build
- native Framer layer preference
- desktop/tablet/mobile expectations

---

### Rule 5 — Aura templates scale left to right

Each row should increase in complexity:

- left = simplest
- middle = more developed
- right = most advanced in that category

Applies to Essential, Creative Custom, and AI/Motion rows.

---

### Rule 6 — Premium design can be short

A short site can still feel premium through:

- strong hero image/video
- elegant type
- restrained copy
- clean spacing
- thin dividers
- soft overlays
- strong CTA placement
- subtle motion

---

### Rule 7 — Animation prompts must define motion intensity

If animation is too subtle, increase:

- camera push
- glide
- parallax
- cloud movement
- energy flow
- light pulses
- particles
- environmental motion

Always include negatives to avoid flicker, warping, new objects, text, or color shifts.

---

## 8. Reusable Prompt Snippets

### 8.1 Claude Code Prompt — Build Northfield as a Lightweight Starter Site

```text
We are working inside my Framer project with the Framer MCP connected.

Build Template #1 for Aura Digital.

Template name: Northfield
Template type: Starter Local Service Site

Do not use a large marketplace template structure. Do not create a huge multi-page architecture portfolio. This is the simplest Aura Digital package.

Use native Framer layers as much as possible. Avoid rebuilding the whole site as a code component unless absolutely necessary. I need this to remain editable inside Framer.

Build a small premium 3-page website:

1. Home
2. Services / Booking
3. Contact / Info

Design style:
- premium but simple
- warm cream / beige / soft charcoal
- elegant serif headlines
- small uppercase navigation
- thin borders
- strong image/video hero
- subtle motion
- lots of breathing room
- no generic SaaS look
- no clutter
- no bright blue buttons
- no random filler sections

Home page sections:
1. Hero with large image/video
2. Short brand intro
3. Services preview
4. Small gallery/media strip
5. Booking/contact CTA

Services / Booking page:
1. Service list
2. Optional pricing or “starting at”
3. Booking link/button
4. Hours/location block if relevant

Contact / Info page:
1. Contact form
2. Phone/email/socials
3. Location
4. Optional map
5. Final CTA

The design should feel like a premium starter website for a barbershop, trainer, photographer, salon, wellness brand, consultant, or small local service business.

Keep the result polished and realistic. This is a demo template that Aura Digital can show as its simplest package.
```

---

### 8.2 Claude Code Prompt — Native Framer Layer Preference

```text
Important Framer build instruction:

Use native Framer layers, frames, stacks, text layers, image layers, buttons, and components wherever possible.

Do not rebuild the entire site as one large custom React/code component.

Only use code components for specific reusable effects or interactions that cannot be done cleanly with native Framer.

The final result must remain visually editable inside Framer.
```

---

### 8.3 Image Generation Prompt — Individual Website Assets

```text
Generate separate standalone website image assets, not a moodboard.

No text, no UI, no borders, no labels, no collage, no mockup frame.

Each image should be its own clean PNG/JPEG-style asset ready to place directly into Framer.

Match this style:
premium, cinematic, warm, minimal, editorial, refined, soft light, elegant composition.

Create:
1. hero image
2. secondary/detail image
3. about/process image
4. CTA/footer image
```

---

### 8.4 Animation Prompt — Dynamic AI Motion

```text
Cinematic 5-second loop. Add strong fluid motion and visible energy flow. The glowing ribbon should surge forward through the clouds, twisting, curling, and pulsing with light as if alive. Surrounding clouds should billow and roll with layered parallax depth. Add drifting particles and tiny sparks. Camera should slowly glide forward with a subtle diagonal drift, creating the feeling of being pulled into the motion. Keep the original composition, colors, and atmosphere, but make it feel dynamic, immersive, and alive.

Negative prompt:
No text, no new objects, no random scene changes, no melting, no heavy flicker, no broken geometry, no dramatic color shifts.
```

---

### 8.5 Ultra-Short Animation Prompt

```text
Forward camera glide following glowing horizon path, clouds billowing dynamically.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP 1 — Creating a New Aura Digital Template Demo Site

1. Identify which of the 9 template cards is being developed.
2. Confirm its category: Essential, Creative Custom, or AI/Motion.
3. Define the complexity level: left = simple, middle = moderate, right = advanced.
4. Define page count before building.
5. Define exact pages.
6. Generate or collect individual assets.
7. Place assets into a clearly named local folder.
8. Give Claude Code exact local image paths.
9. Instruct Claude Code to use native Framer layers.
10. Build desktop first.
11. Adjust tablet and mobile.
12. Test navigation and links.
13. Save reusable sections/components into the internal Aura layout system.
14. Document the prompt and decisions in the Framer-MCP-Playbook repo.

---

### SOP 2 — Building the Top Row Essential Templates

#### Template #1 — Starter Site

Pages:

- Home
- Services/Booking
- Contact/Info

Sections:

- hero
- intro
- service preview
- gallery/media strip
- booking CTA
- footer

#### Template #2 — Standard Site

Pages:

- Home
- Services
- About
- Contact/Booking

Add:

- testimonials
- stronger about section
- expanded services
- more image slots

#### Template #3 — Growth Site

Pages:

- Home
- Services
- About
- Gallery/Work
- FAQ
- Contact/Booking

Add:

- service detail sections
- FAQ
- gallery/work
- testimonials
- lead capture

---

### SOP 3 — Image Asset Generation for Framer Sites

1. Generate a reference/moodboard only if needed.
2. After direction is approved, generate production assets separately.
3. Each asset must be standalone.
4. Avoid embedded text and fake UI.
5. Name files clearly: `hero.png`, `pic-2-detail.png`, `pic-3-process.png`, `pic-4-cta.png`.
6. Put them in a local template folder.
7. Use full Windows paths when giving Claude Code instructions.
8. Do not crop moodboards unless explicitly requested.
9. Store final assets in Cloudinary later if hosted links are needed.

---

### SOP 4 — Claude Code / Framer MCP Build Workflow

1. Open the correct Framer project.
2. Confirm MCP is connected.
3. Tell Claude Code the project name.
4. Tell it whether to use an existing template or build from scratch.
5. Always specify native Framer layers.
6. Provide local image file paths.
7. Give the page structure.
8. Give exact section structure.
9. Give visual rules.
10. Give “do not” rules.
11. Ask it to build desktop first.
12. Ask it to check tablet/mobile after desktop.
13. Review visually.
14. Send one correction prompt at a time.
15. Avoid asking Claude to rebuild everything unless necessary.

---

## 10. Future Agent Ideas

### Agent 1 — Aura Template Architect

Defines each Aura Digital template, page count, section structure, and complexity tier.

### Agent 2 — Framer Native Layer Builder

Turns prompts into native Framer layer structures while avoiding unnecessary code-component builds.

### Agent 3 — Aura Asset Director

Generates consistent asset prompts, ensures individual files, avoids moodboard mistakes, and organizes names/paths.

### Agent 4 — Animation Prompt Specialist

Creates Runway/Pika prompts, tunes motion intensity, writes short prompts when credits are limited, and includes negative prompts.

### Agent 5 — Template Package Builder

Turns demo sites into sellable Aura Digital packages with included pages, client use cases, and upsell paths.

### Agent 6 — Framer QA Agent

Checks responsiveness, navigation, CTA links, spacing, consistency, and whether a build feels cheap/generic.

---

## 11. Recommended Filename

`aura-site-design-buttons-template-system-northfield.md`

---

## 12. Recommended Folder Inside the Repo

`/01-framer-mcp-playbooks`

This belongs in the Framer MCP playbooks folder because the core value is the workflow for turning Aura Digital template cards into real Framer demo sites using Claude Code and the Framer MCP.

Secondary relevant folder:

`/03-image-asset-workflows`

If only one folder is used, choose:

`/01-framer-mcp-playbooks`

---

## 13. Agent-Ready Summary

Aura Digital uses a 9-card template showcase. Each card should become a full clickable demo website. The system is divided into three rows: Essential, Creative Custom, and AI/Motion. Each row increases in complexity from left to right.

The first template, Northfield, should not be built as a large architecture portfolio. It should become a small premium local-service starter site suitable for a barbershop, trainer, photographer, salon, wellness brand, consultant, or small business. The correct structure is 3 pages max: Home, Services/Booking, and Contact/Info.

Do not rely on bloated Framer Marketplace templates for the starter package. Use marketplace templates only as references. Build a lightweight native Framer layout system instead. Claude Code should use the Framer MCP and native Framer layers wherever possible, keeping everything visually editable. Use code components only for special effects.

Image generation must produce individual standalone website assets, not moodboards. Production assets should have no text, no UI, no collage, no borders, and no labels. Moodboards are allowed only as reference images.

For animation, AI/motion templates need more dynamic prompts than subtle loops. Include camera glide, forward push, cloud billowing, energy flow, pulsing light, particles, and negative prompts to prevent flicker, warping, text, or random objects.

The most important strategic decision is that Aura Digital should build its own reusable Framer preset layout system instead of forcing every client/demo into full external templates. The design principle is premium simplicity: short, clean, cinematic sites with strong imagery, elegant type, and intentional spacing.
