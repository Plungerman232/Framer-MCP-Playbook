# Premium Framer Template Systems: ATA, Tinting, Preloader, GitHub Archiving, and Reference-Site Rebuild Rules

## 1. Chat Title / Topic

**Premium Small-Business Framer Template Workflow Using Framer MCP, Claude Code, Codex, GitHub, Cloudinary, and Reference-Site Forensics**

This chat covered reusable workflows for building premium Framer websites and template systems using Claude Code, Framer MCP, Codex, GitHub, Cloudinary, reference mockups, and partial website artifacts.

---

## 2. Main Problem Or Build Goal

Create reusable systems for turning conversations, visual references, Framer mockups, Codex audits, and Claude Code prompts into repeatable Framer build workflows.

Main projects covered:

1. **Athletes Training Athletes**
   - Premium sports performance training site.
   - Full viewport hero video.
   - Training-through-the-years slideshow.
   - Services.
   - Private/current-client booking process.
   - Foundation/family-tree athlete lineage section.
   - Alumni grid.

2. **Tinting Website**
   - Premium automotive tinting brand/showroom.
   - Not aggressively trying to attract new clients.
   - Built for brand presence, work showcase, Instagram/Facebook exposure, and exclusivity.
   - Owner is already backlogged, so the website should not create too much lead pressure.

3. **Preloader Template**
   - Inspired by ArchiZen’s premium loading effect.
   - Built from scratch in a separate Framer project named `preloader`.
   - Intended as a reusable small-business mini-template.

4. **Template Archiving**
   - Save prompts, design systems, page structures, asset links, and implementation notes into GitHub.
   - GitHub stores the blueprint, not the native Framer canvas state.

---

## 3. Tools Used

### Framer
Used as the native website builder. Concepts discussed:
- Native layers
- Frames
- Stacks
- Components
- Breakpoints
- Sticky/fixed nav
- Hero video placeholders
- Gallery sections
- Contact buttons
- Preloader effects
- Editable text
- Replaceable image/video placeholders

### Framer MCP
Used to allow Claude Code to manipulate Framer projects directly.

Key rule:
> Claude Code should build inside the intended Framer file/project only and should ask for broad permission up front before making many changes.

### Claude Code
Used as the implementation agent for Framer MCP tasks:
- Build Framer pages from long prompts.
- Rework existing Framer files.
- Create native Framer components.
- Replace lead-generation copy with exclusive brand-showcase copy.
- Save documentation locally.
- Prepare GitHub-ready folders.
- Push template archives to GitHub when user approves.

### Codex
Used to inspect and organize website artifacts.

Important finding:
- Initial Expel files were placeholder audits because the folder was empty.
- Later Expel files were useful forensic docs.
- The Expel artifact was a partial compiled Nuxt/Vue/Vite build, not clean source code.

### GitHub
Used to store reusable template prompts, page structures, design systems, and implementation notes.

Known details:
- GitHub username: `Plungerman232`
- Template repo URL: `https://github.com/Plungerman232/Framer-Templates.git`
- Local template folder: `C:\Users\Charl\framer-site-templates`
- Target playbook repo: `https://github.com/Plungerman232/Framer-MCP-Playbook`

### Cloudinary
Used to host visual mockup/reference images.

Important Cloudinary reference:
`https://res.cloudinary.com/drr7vuxzd/image/upload/v1780345972/ATA_Site_Layout_bg4nh4.png`

### Image Generation
Used to generate full-page site mockups. Download links were sometimes unreliable, so Cloudinary or direct upload is preferable for important references.

---

## 4. What Worked

### Full-page reference mockups worked well
Best workflow:
1. Generate or collect a full-page visual mockup.
2. Upload/host it.
3. Give Claude Code the image URL plus a detailed build prompt.
4. Tell Claude to build natively in Framer, not place the image as a flat screenshot.

### ATA structure became clear
Final ATA structure:
1. Full viewport hero video
2. Training-through-the-years slideshow
3. Services
4. How training works
5. Foundation section
6. ATA alumni grid
7. Contact

Positioning:
> ATA should feel like an athletic lineage and family development system, not a generic trainer website.

Key decision:
- Remove public schedule.
- Training is curated.
- Current clients receive private Google Calendar/booking access after onboarding.

### Tinting site improved after removing lead-gen energy
Initial tinting version looked good but felt too much like a normal lead-generation site.

Better positioning:
> Exclusive portfolio / digital showroom / social proof site.

Better tone:
- Best Tint in Jax? Ask Around.
- Clean Glass. Quiet Flex.
- Booked For A Reason.
- No Rush Jobs. No Messy Edges.
- The Work Speaks First.

### Rebuilding from scratch beat editing locked templates
For ArchiZen:
> Do not modify hard-to-edit template components. Use ArchiZen as visual inspiration and rebuild a simplified editable version from scratch.

### GitHub archiving worked
Recommended documentation folder model:

```text
framer-site-templates/
  Project-Name/
    README.md
    claude-build-prompt.md
    design-system.md
    page-structure.md
    asset-links.md
    implementation-notes.md
```

---

## 5. What Failed

### Empty repository audits were not useful
Codex initially produced audit files that only said the Expel repo was empty.

Rule:
> Do not treat placeholder audit docs as source files. First verify whether real website files, a live URL, screenshots, exported static assets, or design files exist.

### Compiled Nuxt/Vue/Vite artifacts should not be ported
The Expel files were useful as a forensic reference, not source code.

Problems:
- Partial compiled production build.
- Missing source tree.
- Missing CMS payloads.
- Missing physical images/videos/fonts.
- Missing many Vite chunks.
- Exact content copy not recoverable.

Rule:
> Use compiled artifacts as a blueprint for page types, component patterns, responsive behavior, and design clues. Do not port minified chunks into Framer.

### First tinting site was too template-like
Problems:
- Too much `Call Now`, `Book Tint`, `Ready To Tint?`
- Top stat cards made it feel like a lead funnel.
- Contact form was too prominent.
- It tried to attract customers even though the owner was already backlogged.

Fix:
- Reposition as exclusive showroom.
- Lead with gallery/work.
- Push Instagram/Facebook.
- Make contact subtle and availability-based.

### ChatGPT file links were unreliable
Workarounds:
- Host important images on Cloudinary.
- Upload directly to Claude/Framer.
- Save local copies manually.
- Use ZIP only if direct PNG link fails.

---

## 6. Final Decisions

### ATA
Build as a premium one-page athletic development site:
- Full viewport hero video
- Training through the years
- Services
- How training works
- Foundation/family tree
- Alumni grid
- Contact

### Tinting
Build as:
- Exclusive
- Portfolio-driven
- Social-first
- Not a sales funnel
- Cool, brand-building, and selective

Preferred sections:
1. Full viewport hero video
2. Work/Gallery
3. Instagram/Facebook exposure
4. Brand/personality section
5. Subtle availability/contact footer

### Preloader
The `preloader` Framer project should be:
- Inspired by ArchiZen
- Built from scratch
- Small-business friendly
- Minimal
- Premium
- Editable

### GitHub
Use GitHub to save:
- Prompts
- Design systems
- Page structures
- Asset links
- Claude Code implementation notes
- SOPs
- Troubleshooting rules

---

## 7. Reusable Rules

### Rule 1 — Native Framer Build
Always tell Claude:
> Build natively in Framer using real Framer layers, frames, stacks, components, text, images, buttons, and interactions. Do not place the mockup image as the site.

### Rule 2 — Reference Image
> Use the image as the visual/design reference only. Recreate the site natively with editable Framer components.

### Rule 3 — Permission For Long MCP Tasks
> Ask me for permission to make all necessary edits in the target Framer project while I am away, so you can complete the work without asking for approval on every small change.

### Rule 4 — Do Not Fight Locked Templates
> If a Framer template has hard-to-edit components, do not modify it directly. Use it as reference and rebuild a simplified editable version from scratch.

### Rule 5 — Match Business Intent
Classify the site first:
- Lead-generation
- Portfolio/showcase
- Social proof
- Booking funnel
- Brand presence
- Exclusive/private availability
- Existing-client portal

For backlogged businesses, avoid aggressive CTAs.

### Rule 6 — Private Booking
> Do not create public schedule or booking systems unless requested. Use current-client-only private booking/calendar access after onboarding.

### Rule 7 — Compiled Artifact
> Do not port minified Nuxt/Vue/Vite code. Use the artifact as a blueprint for components, page types, responsive patterns, integrations, and design references.

### Rule 8 — GitHub Archive
Every reusable build should save:
- `README.md`
- `claude-build-prompt.md`
- `design-system.md`
- `page-structure.md`
- `asset-links.md`
- `implementation-notes.md`

### Rule 9 — Sticky Header
- Fixed header: locked to the viewport top at all times.
- Sticky header: scrolls normally until it reaches top, then sticks.

---

## 8. Reusable Prompt Snippets

### Claude Code Permission

```text
Before you make changes, ask me at the beginning for permission to make all necessary edits inside the target Framer project while I am away. I need you to request full approval up front so you can complete the work without needing me to approve every small change.
```

### Native Framer Build

```text
Build this natively in Framer using real Framer layers, frames, stacks, components, text, images, buttons, and interactions. Do not place the reference image as a flat screenshot. Use the reference only as a visual guide.
```

### Reference-Only Template

```text
Do not edit or rebuild directly inside the reference template. Use it only as visual inspiration. Study the spacing, typography, preloader, motion, and premium feel, then recreate a simpler editable version from scratch in the target Framer project.
```

### Small-Business Premium Template

```text
Create a simplified premium small-business template inspired by high-end editorial sites, but make it much smaller and easier to reuse. This should work for local service businesses like tint shops, barbers, trainers, contractors, photographers, and boutique brands.
```

### Exclusive/Backlogged Business

```text
This business is already busy and does not need an aggressive lead-generation website. Shift the messaging from “book now / call now / get a quote” to “look at the work, follow the brand, and reach out for availability.” Make the site feel like an exclusive portfolio and digital showroom.
```

### No Public Booking

```text
Do not create a public upcoming sessions or public booking section. Training/work availability should happen after an initial conversation. Current clients may receive a private Google Calendar or booking link after onboarding.
```

### GitHub Archive

```text
Create a GitHub-ready archive folder for this Framer website project. Include README.md, claude-build-prompt.md, design-system.md, page-structure.md, asset-links.md, and implementation-notes.md. Save the full structure, styling rules, prompt, reference image URLs, implementation notes, and known manual Framer steps.
```

### Expel Artifact Interpretation

```text
Use the provided Expel forensic docs as a premium component/design reference only. Do not port the minified Nuxt/Vue/Vite chunks. Borrow inspiration from its hero video patterns, card grids, gallery sliders, CTA bands, review sections, responsive behavior, and header/footer structure, but build a smaller native Framer site from scratch.
```

---

## 9. SOPs / Step-By-Step Workflows

## SOP 1 — Build A Framer Site From A Visual Mockup

1. Generate or collect full-page reference image.
2. Upload it to Cloudinary or provide it directly to Claude Code.
3. Open target Framer project.
4. Start Framer MCP.
5. Give Claude:
   - target project name
   - reference image URL
   - section order
   - business positioning
   - copy/CTA rules
   - responsive requirements
6. Tell Claude to ask for full permission.
7. Tell Claude to build natively in Framer.
8. Ask Claude for final summary:
   - sections built
   - editable components
   - assets to replace
   - links still needed
   - responsive issues
9. Save prompt and notes to GitHub.

---

## SOP 2 — Save A Framer Template To GitHub

Folder structure:

```text
framer-site-templates/
  Project-Name/
    README.md
    claude-build-prompt.md
    design-system.md
    page-structure.md
    asset-links.md
    implementation-notes.md
```

Initial push:

```powershell
cd "C:\Users\Charl\framer-site-templates"
git remote add origin https://github.com/Plungerman232/Framer-Templates.git
git branch -M main
git push -u origin main
```

If remote already exists:

```powershell
cd "C:\Users\Charl\framer-site-templates"
git remote set-url origin https://github.com/Plungerman232/Framer-Templates.git
git branch -M main
git push -u origin main
```

Future updates:

```powershell
cd "C:\Users\Charl\framer-site-templates"
git add .
git commit -m "Update Framer template notes"
git push
```

---

## SOP 3 — Rebuild From A Complex Template Without Editing It

1. Open reference template in Framer.
2. Open/create separate target Framer project.
3. Tell Claude:
   - Reference project name
   - Target project name
   - Do not edit reference project
   - Build from scratch in target project
4. Identify what to borrow:
   - preloader
   - intro reveal
   - typography
   - spacing
   - editorial images
   - sticky/fixed header
   - smooth section pacing
5. Define smaller reusable structure:
   - preloader
   - header
   - hero
   - work/gallery
   - services
   - about/reputation
   - contact
   - footer
6. Build native editable components.
7. Save prompt and notes to GitHub.

---

## SOP 4 — Convert A Lead-Gen Site Into An Exclusive Portfolio Site

Remove or reduce:
- Book now
- Schedule today
- Get a quote
- Big top-page stat cards
- Large contact form
- Public availability calendars
- Urgency-based CTAs

Add or emphasize:
- Gallery/work showcase
- Brand personality
- Social links
- Word-of-mouth reputation
- Availability limited
- Message on Instagram
- Built off referrals
- Quality over volume

Better CTA language:
```text
View The Work
See The Gallery
Instagram
Message On Instagram
Availability Is Limited
```

Avoid:
```text
Book Now
Schedule Today
Get A Quote
Call Now
Ready To Tint Your Vehicle?
```

---

## SOP 5 — Use Codex Website Artifacts Correctly

1. Ask Codex to inventory the folder.
2. Verify whether it contains source or only compiled chunks.
3. If empty, treat output as placeholder audit only.
4. If compiled production files exist, extract:
   - component names
   - page types
   - CSS clues
   - responsive behavior
   - missing assets
   - integration clues
5. Do not ask Claude to port minified code.
6. Use findings as a Framer design/component blueprint.

---

## 10. Future Agent Ideas

### Agent 1 — Framer Template Archivist
Creates GitHub-ready documentation for completed Framer builds.

### Agent 2 — Reference Site Forensics Agent
Analyzes site artifacts, screenshots, or URLs and separates real source from compiled artifacts.

### Agent 3 — Business Intent Classifier
Classifies whether a site should be lead-gen, portfolio, social-proof, booking, brand presence, exclusive, or existing-client focused.

### Agent 4 — Framer Prompt Generator
Turns rough ideas into complete Claude Code Framer MCP prompts.

### Agent 5 — Small-Business Premium Template Builder
Creates reusable templates for tint shops, barbers, trainers, epoxy flooring, photographers, auto detailers, contractors, and boutique brands.

### Agent 6 — Framer QA Agent
Checks desktop/tablet/mobile layouts, sticky/fixed headers, scroll links, missing assets, overflow, CTA consistency, and component reuse.

---

## 11. Recommended Filename

```text
premium-small-business-framer-template-systems.md
```

---

## 12. Recommended Folder Inside The Repo

```text
/01-framer-mcp-playbooks
```

Secondary excerpt folders:
```text
/02-claude-code-prompts
/05-agent-instructions
/06-debugging-rules
/08-reference-builds
```

---

## 13. Agent-Ready Summary

This chat produced a reusable Framer MCP workflow for building premium small-business websites using Claude Code, visual references, Codex artifact audits, Cloudinary references, and GitHub documentation archives.

Key rules:
1. Build natively in Framer; never place a mockup image as the site.
2. Use complex templates like ArchiZen as reference only if components are hard to edit.
3. Ask Claude Code for full editing permission at the start of long Framer MCP tasks.
4. Use compiled Nuxt/Vue/Vite artifacts as forensic design/component references, not source code to port.
5. Match site structure to business intent.
6. For backlogged/exclusive businesses, avoid aggressive lead-generation language.
7. Save every reusable build as GitHub documentation.
8. Use Cloudinary or direct uploads for reliable image references.
9. Small-business templates should be simpler than full agency templates but keep premium effects like preloaders, sticky headers, editorial spacing, and smooth reveals.

---

## Final Save Instructions

File name:

```text
premium-small-business-framer-template-systems.md
```

Repo folder:

```text
/01-framer-mcp-playbooks
```

Classification:

```text
Primary: SOP
Secondary: Agent instruction + prompt snippet library
```
