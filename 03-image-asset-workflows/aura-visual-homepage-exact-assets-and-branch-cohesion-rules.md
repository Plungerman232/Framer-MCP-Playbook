# Aura Visual Homepage + Aura Brand Cohesion — Image Asset Workflow & Sub-Brand Design Report

## 1. Chat Title / Topic

**Aura Visual Homepage Direction, Exact-Photo Mockup Workflow, and Aura Sub-Brand Cohesion Rules**

This chat focused on refining the **Aura Visual** homepage/button direction so it fits inside the broader **Aura Creative** brand universe while still feeling like its own distinct destination.

The conversation also produced important reusable rules about when to use AI image generation versus when to build exact layout composites with real images in Framer, HTML/CSS, Figma, or a manual design workflow.

---

## 2. Main Problem or Build Goal

The main build goal was to design the ideal **Aura Visual** hero/homepage and related umbrella-site button/card so it feels cohesive with the larger Aura Creative ecosystem.

The user wanted Aura Visual to:

- Feel like the **photography wing** of Aura Creative.
- Stay connected to the Aura universe without copying the exact dark chaotic atmosphere of the main umbrella homepage.
- Use a refined color scheme inspired by the newer Aura Visual mockup:
  - soft whitish gray
  - dusty mauve
  - muted orange
  - subtle purple/lavender
  - quiet warm red
- Include an editorial woman/model figure, but not make her too dark, harsh, or overly dramatic.
- Feel cinematic, premium, emotional, and somewhat “Star Wars-like.”
- Preserve the larger Aura family identity while feeling like a new place.

The major workflow problem was that AI image generation repeatedly **reinterpreted source photos** instead of placing the user’s original photos exactly. This created a need for a hard rule: if exact user-owned assets must remain unchanged, use Framer/HTML/CSS/manual composition, not generative image recreation.

---

## 3. Tools Used

### ChatGPT / Creative Direction

Used for:

- Brand strategy
- Aura Visual positioning
- Sub-brand hierarchy
- Homepage structure
- Button/card concepting
- Prompt creation
- Workflow correction after failed AI image attempts

### Image Generation

Used for:

- Early Aura Visual homepage concepts
- Aura Visual full-page mockup attempts
- Aura Visual button/card mockup
- Exploring mood, palette, and layout

Important limitation discovered:

- Image generation is useful for **style exploration**, but unreliable for preserving exact user-owned source images.

### Manual Composite / Layout Workflow

Used conceptually and once successfully for:

- Creating a layout mockup where the real source photos were placed instead of regenerated
- Preserving the original user images with only crop/scale/positioning

This became the recommended workflow for Framer/Claude implementation.

### Framer / Claude Code / MCP

No direct Framer MCP execution happened in this chat, but the chat created reusable instructions for Framer/Claude Code:

- Use real uploaded assets as image layers.
- Do not regenerate photos.
- Use image layers/cards with `object-fit: cover`.
- Use precise layout, spacing, and crop rules.
- Treat the Aura Creative homepage as the visual system anchor, but make branch pages distinct.

### GitHub / Repo Organization

The report is intended for:

`https://github.com/Plungerman232/Framer-MCP-Playbook`

Recommended placement:

`/03-image-asset-workflows`

Secondary relevance:

`/07-aura-brand-systems`

---

## 4. What Worked

### 4.1 The Aura Digital Page Established a Strong Sub-Brand Model

The Aura Digital concept worked because it felt like its own world while still belonging to Aura Creative.

Strong traits:

- canyon and reflective water environment
- purple/lavender/peach sunrise tone
- clean digital portfolio card layout
- elegant serif typography
- premium spacing
- structured web design grid
- less chaotic than the main Aura Creative homepage

This became the model for how Aura Visual should behave:

> Aura branch pages should feel like separate rooms inside the same mansion, not duplicates of the main portal.

---

### 4.2 Aura Visual Became Stronger When It Moved Away From the Dark Storm Look

The initial Aura Visual concepts were too close to the main Aura Creative homepage:

- too dark
- too chaotic
- too cosmic
- too fantasy-poster-like
- too dramatic for a photography page

The stronger direction was:

- quieter
- brighter
- soft red/orange/purple/gray
- editorial
- human
- photographic
- dreamy but still premium

Final working idea:

> Aura Visual should feel like a cinematic photography destination inside the Aura universe, not like the same dark portal with different text.

---

### 4.3 The Eye Icon Became the Correct Aura Visual Symbol

The user liked the eye emblem and wanted it retained.

Final rule:

- Aura Visual = eye icon
- Remove camera/globe/star icon row from Aura Visual
- Keep the eye as the branch-specific symbol

This prevents Aura Visual from looking like the umbrella homepage’s three-branch selector.

---

### 4.4 Smaller Image Strips Worked Better Than Huge Photo Blocks

The user liked the idea of having images run across the lower part of the page, but not as a full gallery page.

Working direction:

- Aura Visual homepage should be one hero-style page.
- It can include a small curated image strip.
- It should not become a full gallery dump or a long photography portfolio page.
- Gallery should be linked, not fully displayed on the homepage.

Reusable rule:

> On Aura Visual, use a small preview strip as evidence of work, not a full gallery wall.

---

### 4.5 The Button/Card Direction Became Clear

The Aura Visual button for the umbrella homepage should not stay red/gray if the new Aura Visual page uses the softer canyon/sunset palette.

New button identity:

- soft orange sunset
- mauve/purple haze
- silvery gray
- warm red undertone
- editorial woman/model
- eye icon
- title: Visual
- subtitle: Photography & Visual Storytelling
- CTA: Enter

This button better aligns with the new Aura Visual world.

---

## 5. What Failed

### 5.1 AI Image Generation Failed to Preserve Exact Source Photos

The user explicitly asked for original source photos to be placed without editing.

Failures:

- The graduation model was re-created and visually changed.
- The Mercedes photo was replaced with a fake generated Mercedes scene.
- Faces, lighting, and environments were altered.
- The source photos were not preserved exactly.

Cause:

- Generative image tools tend to reinterpret reference images instead of compositing them pixel-faithfully.

Reusable rule:

> If the user says “use my actual source photos” or “do not edit them,” do not use image generation to place those photos. Use Framer, HTML/CSS, Figma, or a manual composite workflow.

---

### 5.2 Full Aura Visual Site Mockup Was Too Much

A full multi-section Aura Visual site was generated with:

- gallery section
- sessions/services section
- about section
- contact form
- footer
- many photos

This was incorrect because the user wanted a **single hero page**, similar to Aura Digital.

Final correction:

- Aura Visual should be one hero/landing page.
- It should not include a full gallery on the page.
- The homepage can link to Gallery, Services, Contact, etc., but should not display everything at once.

---

### 5.3 The Early Aura Visual Look Was Too Similar to the Umbrella Homepage

The main Aura Creative homepage should be the most intense, dark, atmospheric portal.

The branch pages should be:

- still cohesive
- still premium
- still Aura
- but different environments

The early Aura Visual versions were too dark and dramatic, which made them feel like duplicates of Aura Creative rather than a distinct Visual branch.

---

### 5.4 Too Many Generic Photography Website Elements Weakened the Aura Feel

Elements that felt too generic:

- large “Portraits / Graduations / Brands / Weddings” service blocks
- standard photography-site service layout
- huge gallery sections
- hard-sell booking layout
- basic photography portfolio structure

Better direction:

- premium portal
- hero-first
- eye icon
- subtle image strip
- soft editorial palette
- gallery as CTA, not full content dump

---

## 6. Final Decisions

### 6.1 Aura Creative Homepage Role

Aura Creative is the main umbrella portal.

It should stay:

- dark
- atmospheric
- cosmic
- mysterious
- intense
- storm-like
- mythic
- “enter the world” oriented

It is the gateway to the branches.

---

### 6.2 Aura Visual Role

Aura Visual is the photography branch.

It should feel:

- cinematic
- human
- emotional
- editorial
- softer than Aura Creative
- still premium and atmospheric
- less dark, less chaotic
- more grounded in imagery and story

Final concept:

> Aura Visual is photography through the Aura lens: images shaped through atmosphere, story, and emotion.

---

### 6.3 Aura Digital Role

Aura Digital is the web design / digital experiences branch.

It should feel:

- cleaner
- brighter
- structured
- canyon/water/dawn-like
- purple/lavender/peach
- architectural
- digital-world focused

Final concept:

> Aura Digital is the digital landscape wing of the Aura universe.

---

### 6.4 Branch Color System

Recommended color identities:

| Branch | Color Identity | Feeling |
|---|---|---|
| Aura Creative | black, violet, red lightning, cosmic storm | portal / umbrella world |
| Aura Visual | whitish gray, dusty mauve, quiet red, soft orange, muted purple | photography / emotion / cinematic portrait |
| Aura Digital | purple, lavender, peach, reflective water, dawn light | web design / digital landscape |
| Aura Creative Consulting | black, crimson, muted gold, violet, ember/orb | strategy / direction / idea formation |

---

### 6.5 Aura Visual Hero Layout

Recommended Aura Visual homepage hero:

- actual Aura logo top-left
- nav top-right
- large `AURA VISUAL`
- eye icon
- subtitle: `PHOTOGRAPHY & VISUAL STORYTELLING`
- support line: `Images shaped through atmosphere, story, and emotion.`
- buttons:
  - `VIEW GALLERY`
  - `SERVICES`
- large editorial woman/model figure
- canyon/water/dawn-twilight environment
- four preview cards/panels max
- no long gallery section
- no lower service icon/category section

---

### 6.6 Aura Visual Umbrella Button

The Visual card/button on the main Aura Creative homepage should be updated to match the new Visual palette.

Recommended card text:

```md
VISUAL
PHOTOGRAPHY & VISUAL STORYTELLING
ENTER
```

Recommended visual traits:

- editorial female portrait
- canyon/water sunset atmosphere
- soft orange and mauve glow
- silvery gray haze
- muted purple shadows
- subtle glitch/film texture
- eye icon
- rounded premium card frame

---

## 7. Reusable Rules

### Rule 1 — Exact Source Photo Preservation

If a user says:

- “use my actual image”
- “do not edit the photo”
- “do not regenerate it”
- “I own this image”
- “place the real source image”

Then do **not** use image generation for that part.

Use:

- Framer image layers
- HTML/CSS image cards
- Figma placement
- manual Python/PIL composite
- direct asset placement with crop/scale only

Prompt rule:

```md
Use the provided images as real image layers. Do not recreate, redraw, relight, restyle, enhance, or replace them. Only crop, scale, and position them inside the layout.
```

---

### Rule 2 — Image Generation Is for Mood, Not Exact Assets

Image generation is acceptable for:

- exploring style
- moodboards
- atmospheric backgrounds
- fictional concept art
- button concept directions
- palette testing

Image generation is not reliable for:

- exact photo placement
- preserving faces
- preserving cars
- preserving logos
- preserving branded assets
- exact UI screenshots

---

### Rule 3 — Aura Branch Pages Should Feel Like New Places

The Aura Creative homepage is the main portal.

Each branch page should feel like a different destination:

```md
Aura Creative = the main universe / portal
Aura Visual = photography wing
Aura Digital = digital/web wing
Aura Creative Consulting = strategy/direction wing
```

Do not simply copy the same dark cosmic look across every page.

---

### Rule 4 — Aura Visual Is One Hero Page

Aura Visual should not become a full photography website on the front page.

Correct:

- one hero page
- main CTA to gallery
- secondary CTA to services/book
- optional 4-card or image strip preview
- clean branch identity

Incorrect:

- full gallery dump
- long service section
- multi-section photography template
- generic portfolio website layout

---

### Rule 5 — Gallery Is the Main Aura Visual CTA

For Aura Visual, the strongest CTA should usually be:

```md
VIEW GALLERY
```

or

```md
VIEW WORK
```

Booking matters, but the page should first invite visitors to see the work.

---

### Rule 6 — Do Not Make Visual Too Dark

Aura Visual should not be as dark/chaotic as Aura Creative.

Use:

- soft red
- pale gray
- mauve
- muted orange
- quiet purple
- cinematic haze

Avoid:

- heavy black storm
- extreme lightning
- overly dramatic fantasy model
- too much neon
- overly dark horror/sci-fi mood

---

### Rule 7 — Visual Card Should Use the Eye Emblem

For Aura Visual:

- keep the eye icon
- remove camera/globe/star branch icons
- do not use the umbrella homepage’s three-icon row

The eye becomes the Visual branch identity.

---

## 8. Reusable Prompt Snippets

### Prompt Snippet — Exact Asset Preservation

```md
Use the attached source images as real placed website image assets. Do not redraw, repaint, regenerate, relight, enhance, stylize, or replace them. Preserve the original subjects, faces, cars, lighting, and scene identity. Only crop, scale, and position the images inside the layout frames.
```

---

### Prompt Snippet — Aura Visual Hero Direction

```md
Create a single 16:9 Aura Visual homepage hero mockup. This is only one hero/landing page, not a full website.

Aura Visual is the photography branch of Aura Creative. It should feel like a new place inside the Aura universe: cinematic, editorial, emotional, and premium, but calmer and brighter than the main Aura Creative homepage.

Use a soft canyon/water/twilight environment with whitish gray haze, muted orange glow, dusty mauve, subtle purple, and quiet warm red. Include a refined editorial woman/model figure, but do not make her too dark, harsh, or overly dramatic.

Layout:
- actual Aura logo top-left
- small uppercase nav top-right
- large title: AURA VISUAL
- eye icon
- subtitle: PHOTOGRAPHY & VISUAL STORYTELLING
- support line: Images shaped through atmosphere, story, and emotion.
- buttons: VIEW GALLERY and SERVICES
- 4 refined visual preview cards max
- no full gallery section
- no lower service category block
```

---

### Prompt Snippet — Aura Visual Umbrella Button

```md
Create one standalone navigation card/button image for the Aura Creative umbrella homepage.

This card represents Aura Visual.

Use the new Aura Visual color system:
soft whitish gray, dusty mauve, muted orange glow, subtle purple/lavender, and a quiet warm red undertone.

The card should feel cinematic, premium, editorial, and slightly Star Wars-like, but not too dark or too dramatic. Feature a soft editorial female portrait with canyon/water atmosphere and subtle refined glitch texture.

Text:
VISUAL
PHOTOGRAPHY & VISUAL STORYTELLING
ENTER

Include the eye icon as the Visual symbol.

This is only one button/card image, not a full page.
```

---

### Prompt Snippet — Aura Ecosystem Cohesion

```md
Treat Aura Creative as the main umbrella world. Each branch page should feel like a new destination inside the same universe, not a duplicate of the homepage.

Aura Creative: dark cosmic portal, storm, mystery, umbrella brand.
Aura Visual: cinematic photography, human emotion, soft red/gray/orange/purple, eye emblem.
Aura Digital: web design and digital experiences, purple/lavender/peach canyon-water digital landscape.
Aura Creative Consulting: strategy and direction, abstract orb/eclipses, crimson/gold/violet, idea formation.

Keep typography, spacing, nav style, card framing, and premium atmosphere consistent across the system.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP 1 — Creating an Aura Branch Page Mockup

1. Identify the branch:
   - Visual
   - Digital
   - Creative/Consulting

2. Define the branch role:
   - What does this page do?
   - What should the visitor feel?
   - What action should they take?

3. Pull from the Aura Creative system:
   - logo placement
   - nav style
   - elegant serif title
   - small uppercase labels
   - cinematic landscape/world
   - premium spacing

4. Give the branch its own environment:
   - Visual = editorial photography world
   - Digital = digital canyon/water world
   - Creative = strategic/abstract idea world

5. Keep the page focused:
   - one hero page
   - one main CTA
   - one secondary CTA
   - small supporting preview only

6. Avoid generic template sections unless specifically needed.

7. Generate style mockups first.

8. If exact source assets are required, switch to manual layout or Framer implementation.

---

### SOP 2 — Exact Photo Layout in Framer / HTML / Claude Code

Use this when user-owned images must stay unchanged.

1. Import/upload the user’s actual image files.

2. Place them as image layers/cards.

3. Use:

```css
object-fit: cover;
object-position: center;
```

4. Adjust per image:
   - Mercedes: set object-position so car is centered and not cut off.
   - Portraits: keep faces visible and not overly cropped.
   - Wide photos: crop horizontally for hero/card shape.

5. Add overlays separately:
   - gradient overlay
   - text overlay
   - border
   - hover state
   - shadow

6. Do not bake text into the photo if the site is being built in Framer.

7. Keep images editable as independent assets.

8. Build final layout in Framer or HTML/CSS, not through AI-generated image recreation.

---

### SOP 3 — Updating Umbrella Homepage Buttons

1. Confirm each branch page’s final visual identity.

2. Create one button/card per branch:
   - Visual
   - Digital
   - Creative

3. Make them visually distinct but system-consistent.

4. Match each button to its destination page:
   - Visual button should preview Aura Visual’s soft cinematic photography palette.
   - Digital button should preview Aura Digital’s purple canyon/digital-world palette.
   - Creative button should preview strategy/idea/orb/eclipse energy.

5. Keep all cards consistent in:
   - dimensions
   - border radius
   - typography
   - CTA placement
   - hover potential

6. Update the umbrella homepage buttons only after branch visual identities are locked.

---

## 10. Future Agent Ideas

### Agent 1 — Aura Brand System Guardian

Purpose:

- Keeps all Aura pages visually cohesive.
- Checks whether a new page/card follows the correct branch identity.
- Prevents Aura Visual, Digital, and Creative from becoming too similar.

Inputs:

- current page mockup
- branch type
- intended CTA
- existing Aura Creative reference

Outputs:

- consistency score
- what to keep
- what to change
- exact layout corrections
- color alignment notes

---

### Agent 2 — Exact Asset Placement Agent

Purpose:

- Builds mockups using real uploaded photos without regenerating them.
- Creates Framer/HTML/CSS/PIL-based composites.
- Prevents AI from changing faces, cars, or logos.

Rules:

- Never redraw user photos.
- Use real image layers.
- Only crop/scale/position.
- Preserve asset identity.

---

### Agent 3 — Framer MCP Precision Layout Agent

Purpose:

- Takes a visual mockup and converts it into precise Framer instructions.
- Provides exact spacing, sizes, layout hierarchy, and object-fit rules.

Outputs:

- section structure
- frame sizes
- card dimensions
- gap values
- font sizes
- object-position instructions
- mobile rules

---

### Agent 4 — Aura Button/Card Generator Agent

Purpose:

- Generates or directs the creation of branch cards for the umbrella homepage.
- Ensures each button accurately represents its destination page.

Branch card outputs:

- Visual card
- Digital card
- Creative card

---

## 11. Recommended Filename

```md
aura-visual-homepage-exact-assets-and-branch-cohesion-rules.md
```

---

## 12. Recommended Folder Inside the Repo

Primary folder:

```md
/03-image-asset-workflows
```

Secondary relevant folder:

```md
/07-aura-brand-systems
```

Best placement:

```md
/03-image-asset-workflows/aura-visual-homepage-exact-assets-and-branch-cohesion-rules.md
```

Reason:

The most reusable lesson from this chat is the difference between **AI-generated style exploration** and **exact real-asset placement** for Framer/web builds.

---

## 13. Agent-Ready Summary

Aura Visual is the photography branch of Aura Creative. The main Aura Creative homepage should remain the darkest, most intense, cosmic/storm-like portal. Aura Visual should feel like a new destination within the same universe: cinematic, editorial, human, emotional, and premium, but calmer and brighter than the umbrella page.

The final Aura Visual direction should use a soft canyon/water/twilight world with whitish gray haze, dusty mauve, muted orange glow, subtle purple, and quiet warm red. It should include a refined editorial woman/model figure, the eye icon, the title “AURA VISUAL,” the subtitle “PHOTOGRAPHY & VISUAL STORYTELLING,” and hero CTAs like “VIEW GALLERY” and “SERVICES.” It should be one hero-style page, not a full gallery website. The page can include a small set of preview cards, but it should not display the entire gallery or a long services section.

The biggest workflow lesson is that AI image generation repeatedly failed to preserve the user’s exact source photos. It changed faces, lighting, scenes, and even replaced the Mercedes image. Therefore, when exact source assets are required, do not use AI image generation. Use Framer, HTML/CSS, Figma, or manual composite workflows where the user’s real images are placed as actual image layers and only cropped/scaled/positioned.

For Framer or Claude Code, the rule is: import the real images, place them as image layers, use object-fit/object-position, and add overlays/text separately. Do not regenerate, stylize, enhance, relight, or replace user-owned photos.

The Aura Visual umbrella homepage button should also be updated to match the new Visual color scheme. It should use the eye icon, soft editorial portrait energy, canyon/water atmosphere, mauve/orange/purple/gray palette, and text: “VISUAL,” “PHOTOGRAPHY & VISUAL STORYTELLING,” “ENTER.”

---

# Final Classification

## Exact Markdown File Name

```md
aura-visual-homepage-exact-assets-and-branch-cohesion-rules.md
```

## Exact Repo Folder

```md
/03-image-asset-workflows
```

## Should This Become a Rule, SOP, Prompt Snippet, or Agent Instruction?

This should become **all four**, but the primary classification is:

```md
Rule + SOP
```

### Primary Rule

```md
When exact user-owned source images must be preserved, do not use AI image generation. Use Framer/HTML/CSS/Figma/manual composition with the original files as real image layers.
```

### Primary SOP

```md
Exact Photo Layout in Framer / HTML / Claude Code
```

### Also Save As Prompt Snippet

```md
Use the attached source images as real placed website image assets. Do not redraw, repaint, regenerate, relight, enhance, stylize, or replace them. Preserve the original subjects, faces, cars, lighting, and scene identity. Only crop, scale, and position the images inside the layout frames.
```

### Also Save As Agent Instruction

```md
Before generating mockups for Aura web builds, ask whether uploaded photos must be preserved exactly. If yes, switch to exact asset placement workflow and avoid image generation for those assets.
```
