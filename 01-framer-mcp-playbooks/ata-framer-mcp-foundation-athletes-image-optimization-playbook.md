# ATA Framer MCP Build — Foundation Athlete Cards, Image Optimization, Copy, Navigation, and Alumni Ordering

## 1. Chat Title / Topic

**ATA Pt. 2 — Athletes Training Athletes Framer Website Build System**

This chat focused on building and troubleshooting the **Athletes Training Athletes** website inside Framer using **Claude Code connected through the Framer MCP plugin**. The main work centered on the **Foundation Athletes / THE FIRST 10** card section, athlete image optimization, hover animation fixes, Coach Charlie Simmons Jr. copy, Home page navigation buttons, and ATA Alumni organization.

---

## 2. Main Problem or Build Goal

The user is building a premium, dark, athletic training brand website for **Athletes Training Athletes** in Framer.

Framer project name:

```txt
ATA copy
```

Main build goals:

1. Create a serious, high-trust athletic training website.
2. Build a polished **Foundation Athletes / THE FIRST 10** section with premium hover animations.
3. Replace full-size athlete photos with compressed web-optimized versions.
4. Fix athlete hover-image crops without disturbing the rest of the component.
5. Improve performance where specific cards load slowly or glitch.
6. Rewrite the **Coach Charlie Simmons Jr.** section to feel more specific and credible.
7. Make all Home page buttons and nav items usable.
8. Improve the **Training Built For Every Athlete** section.
9. Reorder **ATA Alumni** cards from oldest alumni to youngest/current athletes.

---

## 3. Tools Used

### Primary Tools

- **Framer**
  - Main website builder.
  - Project: `ATA copy`.
  - Used for layout, breakpoints, sections, code components, pages, and live preview.

- **Claude Code**
  - Used as the Framer implementation agent.
  - Connected to Framer through the **Framer MCP plugin**.
  - User copy/pasted precise prompts from ChatGPT into Claude Code.

- **Framer MCP Plugin**
  - Used to let Claude Code inspect and modify Framer layers/components.

- **Local Windows File System**
  - Main asset source folder:

```txt
C:\Users\Charl\Desktop\Ata\Copy Right\
```

  - Backup path if needed:

```txt
C:\Users\charleshockey3\Desktop\Ata\Copy Right\
```

- **Image compression workflow**
  - TinyJPG / TinyJPEG style compression.
  - Goal: reduce huge photos to web-optimized versions while preserving quality.

### Relevant Cloud / CDN Concept

- Framer/browser/CDN rendering can make huge files appear blurry, grainy, or slow.
- The fix was not always “use a higher quality image.”
- Often the fix was to use properly compressed and resized files.

---

## 4. What Worked

### A. Precise Claude Code Prompts Worked Best

The most successful prompts were short, specific, and scoped to one athlete, one section, or one exact image.

Effective prompt pattern:

```txt
Update only [athlete/card] in the Foundation Athletes / THE FIRST 10 code component.
Use the files from [folder path].
Replace only [main image / hover image 1 / hover image 2 / hover image 3].
Do not change card sizing, layout, animation, blur, hover spacing, typography, or any other athlete.
Confirm exactly what changed.
```

This worked because the Foundation Athlete cards were fragile code/component layers. Broad prompts risked changing the wrong card, layout, crop, hover logic, or animation.

---

### B. Compressed Images Improved Website Performance and Visual Quality

The workflow of creating smaller compressed files worked well for:

- Xavier Hutchinson
- Charlie Simmons III / CS3
- Camryn Simmons
- Tori Grambo

Recommended compression settings:

```txt
Card/profile images: 1000–1400 px wide
Hover/action images: 1400–1800 px wide
JPEG quality: 85–92%
Color profile: sRGB
File naming: Main Card Compressed, Hover Image 1 Compressed, etc.
```

Important discovery:

> Huge high-res images can look worse in Framer/browser/CDN because they get compressed/rendered poorly. A smaller optimized image can look sharper and load faster.

---

### C. Image Source Swaps Worked When Layout Was Protected

For Xavier, CS3, Camryn, and Tori, the right approach was:

1. Use the compressed image folder.
2. Replace only the image source.
3. Preserve crop, object-position, animation, card size, hover spacing, and layout.

Example: Xavier’s compressed folder was:

```txt
C:\Users\Charl\Desktop\Ata\Copy Right\X\x ata pics\X ATA Tiny\
```

Files used:

```txt
main 1_compressed_basic
Hov1_compressed_high
hov2_compressed_basic
Hover Image 3_compressed_high
```

---

### D. Hover Crop Fixes Worked Best Through Object Positioning

Because the athlete cards were code/component layers, many crop fixes had to happen inside the component using values like:

```txt
object-position
background-position
focal point
image positioning prop
```

The best prompt structure was:

```txt
Fix only [Athlete] Hover Image [#].
Do not replace the image source.
Only adjust object-position/background-position.
Move the visible subject [up/down] by about [10–15%].
Confirm the final positioning value.
```

---

### E. Coach Charlie Simmons Jr. Copy Became Much Stronger

The original Coach section felt generic. The revised version became more proof-based and specific.

Final preferred credential box:

```txt
1990 National Champion — Georgia Tech Football
Drafted by the Green Bay Packers
Played for the Hamilton Tiger-Cats
15+ years building next-level athletes
```

Final direction:

- Small eyebrow should say `COACH`, not `THE FOUNDATION`.
- Main heading should be `CHARLIE SIMMONS JR.`
- Copy should emphasize championship experience, professional football background, and athlete development.

---

### F. Button / Navigation Audit Was Necessary

The Home page had buttons and nav items that looked selected or highlighted blue, and some needed clickable behavior.

Useful button audit requirements:

- Nav items must scroll or link correctly.
- CTA buttons must link to the right section or page.
- Remove default blue active/selected link styling.
- Add `cursor: pointer`.
- Check z-index so overlays do not block clicks.
- Keep styling aligned with ATA brand: white text, dark background, muted gold hover/active accents.

---

### G. Alumni Ordering Should Be Based on Class Year, Not Displayed Age

The user wanted ATA Alumni organized from older alumni first to younger/current athletes last.

Best rule:

> Sort by graduation/class year or public roster class, but do not display age or graduation year on the cards.

Claude should research each athlete by:

- Name
- School
- Sport
- Roster bio
- Graduation/class year
- College eligibility year
- High school class year if available

Then Claude should provide a research summary before reordering.

---

## 5. What Failed

### A. Prompts That Mentioned the Wrong Image Caused Risk

One prompt accidentally told Claude to center or adjust **Tori’s main card image** when the actual issue was **Tori Hover Image 2**.

Rule:

> If only a hover image is wrong, explicitly say “Do not touch the main card image.”

---

### B. “Move Focal Point Up” Can Be Confusing

In image cropping, “move focal point up” and “move subject down” can mean opposite things depending on whether the code uses object-position, background-position, or Framer focal point controls.

Better wording:

```txt
Adjust the crop so the visible subject appears higher/lower inside the frame.
If using object-position/background-position, change only that value and confirm the final number.
```

---

### C. Some Copy Sounded Too Generic or Awkward

Bad / awkward line:

```txt
Professional football experience with the Hamilton Tiger-Cats
```

Reason it failed:

- It implied Hamilton was the only professional football experience.
- It ignored that Green Bay was also professional football.

Better line:

```txt
Played for the Hamilton Tiger-Cats
```

Bad / awkward line:

```txt
15+ years building next-level collision athletes
```

Reason it failed:

- Too niche.
- Sounded clunky and unnatural for the main Coach section.

Final line:

```txt
15+ years building next-level athletes
```

---

### D. Tori Card Glitch Suggested a Source or Preload Problem

Tori’s card stayed glitchy even after resizing and compression.

Likely causes:

1. One of Tori’s image sources still pointed to an old full-size file.
2. One hover image was still uncompressed.
3. Hover images loaded only when clicked/hovered.
4. Tori’s image source structure differed from other cards.
5. A heavy image was causing delayed animation.

Reusable diagnosis:

```txt
Inspect only Tori’s image sources.
Confirm every image uses the compressed file.
Compare Tori’s setup to smooth cards.
Preserve current crop values.
Preload hover images if needed.
Do not change animation design.
```

---

### E. Broad Layout Prompts Were Risky

Because Framer code components are sensitive, broad prompts like “fix this section” could accidentally affect:

- card sizing
- hover image placement
- blur/dim effect
- typography
- animation timing
- other athletes

Rule:

> Scope every Claude Code prompt tightly unless intentionally redesigning the full section.

---

## 6. Final Decisions

### Foundation Athletes / THE FIRST 10

Final behavior rules:

- Active card stays sharp.
- Other cards/background blur and dim.
- Three floating hover images appear above the active card.
- Hover images are absolute overlays and should not push layout down.
- Hover images should be same size.
- Hover images should have slight tasteful overlap only.
- Do not rebuild hover component unless absolutely necessary.
- Most future work should only replace image sources or adjust crop values.

### Image Workflow

Final image workflow:

1. Compress images before inserting into Framer.
2. Use clear naming.
3. Replace sources only.
4. Preserve layout and animation.
5. Check Live View after each athlete.
6. Fix crop through object-position/background-position only.

### Coach Section

Final Coach credential box:

```txt
1990 National Champion — Georgia Tech Football
Drafted by the Green Bay Packers
Played for the Hamilton Tiger-Cats
15+ years building next-level athletes
```

### Home Page Buttons

Final button/link direction:

- All nav and CTA buttons should be usable.
- Blue active/default link styling should be removed.
- Gold hover/active accents should be used instead.
- CTA routing should be consistent:
  - `START HERE` → `/contact`
  - `SEE THE FOUNDATION` → Foundation section
  - `TRAINING` → Training sections
  - `ALUMNI` → ATA Alumni
  - `CONTACT` → `/contact`

### Training Built For Every Athlete

Final direction:

Add more intentional service-card structure:

1. Youth Development
2. Speed & Movement
3. Strength & Power
4. Next-Level Preparation

CTA:

```txt
START TRAINING
```

Link:

```txt
/contact
```

### ATA Alumni

Final direction:

- Research each athlete publicly.
- Sort by older alumni first, younger/current athletes last.
- Do not display age or graduation year on cards.
- Ask Claude to provide research confidence levels before reordering.

---

## 7. Reusable Rules

### Rule 1 — Do Not Rebuild Working Components

If a hover component works, do not rebuild it.

```txt
Do not rebuild the hover component unless absolutely necessary.
Do not change animation logic unless specifically asked.
```

---

### Rule 2 — Protect Layout During Image Swaps

When replacing images:

```txt
Only replace image sources.
Do not change sizing, layout, crop, object-position, animation, typography, spacing, or other athletes.
```

---

### Rule 3 — Use Compressed Images for Framer Performance

For Framer image-heavy sections:

```txt
Use compressed, web-optimized images instead of huge original files.
Huge files can look grainy, blurry, or load slowly after browser/CDN rendering.
```

---

### Rule 4 — Fix Crops Inside Code Components

If the card is a code/component layer:

```txt
Fix crop/object-position inside the component code.
Do not try to drag native Framer image layers if the image is not a native layer.
```

---

### Rule 5 — One Athlete Per Prompt

For athlete card updates:

```txt
Update only one athlete per Claude Code prompt unless doing a planned full batch replacement.
```

---

### Rule 6 — Require Confirmation

Every Claude Code prompt should end with:

```txt
After updating, confirm exactly what changed.
```

For image work, require:

```txt
Confirm the exact image files connected.
```

For crop work, require:

```txt
Confirm the final object-position/background-position value.
```

---

### Rule 7 — Avoid Blue Link Styling

For premium dark Framer sites:

```txt
Remove default blue selected/active/link styling.
Use brand accent colors for hover and active states.
```

---

### Rule 8 — Research Before Reordering Data

For sortable people/card grids:

```txt
Research first, summarize confidence, then reorder.
Do not display internal research data unless requested.
```

---

## 8. Reusable Prompt Snippets

### A. Single Athlete Image Replacement Prompt

```txt
In the Framer project [PROJECT NAME], update only [ATHLETE NAME] in the [SECTION NAME] code/component.

Use the images from this folder:

[LOCAL FOLDER PATH]

Replace only these image sources:

- Main card image: [FILE NAME]
- Hover Image 1: [FILE NAME]
- Hover Image 2: [FILE NAME]
- Hover Image 3: [FILE NAME]

Do not change card sizing, layout, crop/object-position, animation, blur/dim effect, hover spacing, typography, or any other athlete.

After updating, confirm the exact image files that were connected.
```

---

### B. Hover Image Crop Fix Prompt

```txt
In the Framer project [PROJECT NAME], update only [ATHLETE NAME] Hover Image [NUMBER] in the [SECTION NAME] code/component.

Do not replace the image source.
Do not touch the main card image.
Do not change layout, sizing, spacing, animation, blur/dim effect, typography, or any other athlete.

Only adjust the crop/focal point/object-position/background-position so the visible subject appears [higher/lower] inside the hover frame by about [X]%.

After updating, confirm the exact positioning value that was changed.
```

---

### C. Swap Hover Image Order Prompt

```txt
In the Framer project [PROJECT NAME], update only [ATHLETE NAME] in the [SECTION NAME] code/component.

Simple image swap only:

- Make current Hover Image 1 become Hover Image 3
- Make current Hover Image 3 become Hover Image 1

Do not replace any other image sources.
Do not change the main card image.
Do not change layout, sizing, crop, object-position, animation, blur/dim effect, hover spacing, typography, or any other athlete.

After updating, confirm that Hover Image 1 and Hover Image 3 were swapped.
```

---

### D. Performance Diagnosis Prompt for One Glitchy Card

```txt
In the Framer project [PROJECT NAME], inspect only [ATHLETE NAME] in the [SECTION NAME] code/component.

Issue:
This is the only card that feels glitchy/laggy when clicked or hovered. The animation takes too long to load even though layout and sizing are correct.

Please diagnose and fix only this athlete’s image loading/performance.

Check the following:

1. Confirm the main card image and all 3 hover images are using compressed files.
2. Make sure none of the images are still connected to original full-size files, old URLs, or uncompressed versions.
3. Compare this athlete’s image setup to other cards that work smoothly.
4. If hover images only load when hover/click starts, preload the hover images inside the existing component.

Important:
- Do not change the animation design.
- Do not change card sizing, layout, hover image sizing, spacing, blur/dim effect, typography, or any other athlete.
- Preserve current crop/object-position settings.
- Only fix the image source/loading issue causing the glitch.

After fixing, confirm:
- the exact image files being used
- whether any old/uncompressed image source was still connected
- what change improved loading
```

---

### E. Coach Section Copy Update Prompt

```txt
In the Framer project [PROJECT NAME], update only the text in the Coach section.

Keep the layout, image, spacing, sizing, colors, button, and typography the same.

Set the small eyebrow text to:
COACH

Set the main heading to:
CHARLIE SIMMONS JR.

Set the credential box to:
1990 National Champion — Georgia Tech Football
Drafted by the Green Bay Packers
Played for the Hamilton Tiger-Cats
15+ years building next-level athletes

Do not change anything else on the page.

After updating, confirm the exact text changes made.
```

---

### F. Home Page Button / Link Audit Prompt

```txt
In the Framer project [PROJECT NAME], fix the Home page buttons and links.

Make sure every nav item and CTA button is clickable and routes or scrolls correctly.

Header nav:
- HOME → scroll/top of Home page
- TRAINING → scroll to Training sections
- THE FOUNDATION → scroll to Foundation Athletes / THE FIRST 10
- ALUMNI → scroll to ATA Alumni
- CONTACT → /contact
- START HERE → /contact

Hero CTA:
- SEE THE FOUNDATION → Foundation Athletes / THE FIRST 10

Remove any default blue active/selected/link styling.
No button or nav item should show bright blue text, blue outline, or blue active state.

Keep the ATA style:
- white text
- muted gold hover/active accents
- dark background
- premium athletic look

Make sure buttons have cursor: pointer.
Make sure clickable layers are above decorative overlays and are not blocked by z-index issues.

Do not change the overall layout unless needed to make buttons clickable.

After updating, confirm which buttons/links were fixed and what blue styling was removed.
```

---

### G. Alumni Research and Reorder Prompt

```txt
In the Framer project [PROJECT NAME], update only the ATA Alumni card section.

Goal:
Reorder the alumni cards from oldest alumni first to youngest/current athletes last.

Do not add age, graduation year, or research notes to the cards. This is only for organizing the order.

Process:
1. Read the current ATA Alumni card data from the section.
2. For each athlete, use their name, school, and sport from the existing card to research their public athlete bio/roster/profile.
3. Find the best available indicator of age/order:
   - college graduation year
   - roster class year
   - high school graduation/class year
   - current college eligibility year
   - public athlete bio dates if available
4. Use that information to estimate the correct order from oldest to youngest.
5. Before reordering, provide a quick research summary:
   - athlete name
   - school
   - sport
   - estimated class/graduation year or age-order clue
   - confidence level: high / medium / low
6. Then reorder the cards only.

Do not change:
- card design
- card sizing
- images
- names
- schools
- sports
- accolades
- typography
- spacing
- layout style
- footer/header
- any other section

After updating, confirm the final card order.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP 1 — Athlete Image Replacement in Framer Code Components

1. Confirm athlete name.
2. Confirm exact local folder path.
3. Confirm exact image files.
4. Use compressed files only.
5. Prompt Claude Code to replace sources only.
6. Explicitly protect:
   - layout
   - sizing
   - animation
   - crop/object-position
   - typography
   - other athletes
7. Ask Claude to confirm connected files.
8. Check Framer Live View.
9. Only then move to the next athlete.

---

### SOP 2 — Hover Image Crop Fix

1. Identify exact athlete and hover image number.
2. Determine whether visible subject needs to appear higher or lower.
3. Do not replace source.
4. Prompt Claude to adjust only object-position/background-position.
5. Ask Claude to confirm the exact value.
6. Check Live View.
7. If still off, request another 5–10% adjustment.

Important wording:

```txt
Move the visible subject higher/lower in the frame.
```

Avoid relying only on:

```txt
Move focal point up/down.
```

That can be interpreted backwards depending on the system.

---

### SOP 3 — Image Performance / Glitch Debugging

1. Identify the one card that glitches.
2. Confirm whether other cards work smoothly.
3. Inspect every source for that card.
4. Look for:
   - old full-size files
   - uncompressed images
   - old Cloudinary/CDN URLs
   - mismatched source structure
   - hover images lazy-loading too late
5. Preserve crop/object-position values.
6. Replace any bad source with compressed version.
7. Preload hover images if needed.
8. Do not change animation design unless source/preload fixes fail.

---

### SOP 4 — Coach Bio Copy Upgrade

1. Replace generic bio language with proof.
2. Use small eyebrow for section identity.
3. Use clean main heading.
4. Use credential box for quick authority.
5. Keep body paragraph short.
6. Avoid awkward claims or overexplaining.
7. Preserve layout unless text overflows.

Preferred Coach section structure:

```txt
COACH

CHARLIE SIMMONS JR.

1990 National Champion — Georgia Tech Football
Drafted by the Green Bay Packers
Played for the Hamilton Tiger-Cats
15+ years building next-level athletes

Coach Charlie Simmons Jr. brings championship-level experience and over 15 years of athlete development to ATA. His training is built for serious athletes who want to move better, compete harder, and prepare their bodies for the physical demands of the next level.
```

---

### SOP 5 — Home Page CTA / Nav Link Audit

1. List every nav item and CTA.
2. Define exact destination for each.
3. Fix routes/scroll anchors.
4. Remove blue browser/default active styling.
5. Add brand-consistent hover state.
6. Check cursor pointer.
7. Check z-index/overlay click blocking.
8. Test desktop, tablet, and mobile.

---

### SOP 6 — Alumni Grid Ordering

1. Extract current card names, schools, and sports.
2. Research public roster/bio pages.
3. Determine class/graduation order.
4. Mark confidence level.
5. Sort oldest to youngest.
6. Do not display age or class year unless specifically requested.
7. Preserve card design and all existing visible content.

---

## 10. Future Agent Ideas

### A. Framer Image Source Auditor Agent

Purpose:

- Inspect all Framer image sources.
- Identify uncompressed files.
- Find old Cloudinary/CDN URLs.
- Compare image sizes.
- Flag performance risks.

Useful command:

```txt
Audit every image source in this Framer project and report which ones are local compressed assets, which are old/uncompressed files, and which are external URLs.
```

---

### B. Hover Card QA Agent

Purpose:

- Inspect every athlete hover card.
- Check that each card has:
  - main image
  - 3 hover images
  - correct image order
  - no missing source
  - no layout shift
  - no animation mismatch
  - no incorrect z-index

---

### C. Framer Button Link QA Agent

Purpose:

- Click-test all nav and CTA items.
- Remove default blue styling.
- Check mobile nav behavior.
- Confirm anchors/routes.

---

### D. Alumni Research Sort Agent

Purpose:

- Research athlete cards by name/school/sport.
- Determine class/graduation order.
- Provide confidence levels.
- Reorder card data without changing visible content.

---

### E. Copy Consistency Agent

Purpose:

- Scan site copy for generic, awkward, or off-brand phrases.
- Keep tone:
  - premium
  - serious
  - athletic
  - proof-based
  - not gimmicky
  - not salesy

---

### F. Framer Breakpoint QA Agent

Purpose:

- Check desktop, tablet, and mobile layouts.
- Confirm sections remain aligned.
- Confirm hover/CTA behavior works on responsive breakpoints.
- Confirm no hidden horizontal overflow.

---

## 11. Recommended Filename

```txt
ata-framer-mcp-foundation-athletes-image-optimization-playbook.md
```

---

## 12. Recommended Folder Inside the Repo

Recommended repo folder:

```txt
/01-framer-mcp-playbooks
```

Reason:

This report is broader than a single prompt snippet. It documents a full Framer MCP workflow involving Claude Code prompting, image asset handling, hover card troubleshooting, copy improvements, button fixes, and alumni data organization.

Secondary useful folder if splitting later:

```txt
/03-image-asset-workflows
```

for the image compression and source-swap SOPs.

---

## 13. Agent-Ready Summary

This chat documents a reusable Framer MCP workflow for building the **Athletes Training Athletes** website in Framer using Claude Code.

The key system is to treat Framer code components as fragile production components. Do not ask Claude Code to broadly “fix” sections unless a full redesign is intended. Instead, scope each command to one athlete, one image source, one crop value, one text block, or one button group.

The **Foundation Athletes / THE FIRST 10** card system should not be rebuilt. It already has the correct core behavior: active card stays sharp, background/cards dim and blur, and three floating hover images appear above the active card. Future work should mostly replace compressed image sources or adjust object-position/background-position values.

Image performance issues were solved by compressing large originals before using them in Framer. Huge images can appear blurry, grainy, or laggy after Framer/browser/CDN rendering. Use web-optimized images, clear labels, and require Claude Code to confirm exact connected files.

For crop fixes, use code/component-level object-position or background-position changes. Prompts must state whether the visible subject should appear higher or lower in the frame. Always protect layout, sizing, animation, typography, and other athletes.

For copy, the Coach Charlie Simmons Jr. section should be proof-based and specific. Final credential box should read: 1990 National Champion — Georgia Tech Football; Drafted by the Green Bay Packers; Played for the Hamilton Tiger-Cats; 15+ years building next-level athletes.

For Home page QA, every nav item and CTA must be clickable, default blue link styling must be removed, brand-consistent gold hover/active states should be used, and z-index overlays must not block clicks.

For ATA Alumni, use public athlete bios/rosters to sort by class/graduation year from oldest alumni to youngest/current athletes. Do not display age or graduation year on cards unless specifically requested. Require a research summary and confidence level before reordering.

This should become a reusable **Framer MCP SOP + Claude Code prompt snippet collection + debugging rule set**.
