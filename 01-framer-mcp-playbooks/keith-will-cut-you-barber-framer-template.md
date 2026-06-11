# Keith Will Cut You — Solo Barber Website Template Build

## 1. Chat Title / Topic

**Keith Will Cut You — Framer MCP Solo Barber Website Template**

This chat focused on planning and preparing a simple, premium Framer website template for a one-man barber/home shop business called **Haircuts With Keith**, inside a Framer project named **“Keith will cut you.”**

---

## 2. Main Problem or Build Goal

The goal was to create a simple, clean, premium website layout for a solo barber who is temporarily operating out of a home/private shop.

The site needed to:

- Be simple enough for a one-man barber business.
- Use a strong visual hero section.
- Link directly to Booksy for booking.
- Promote Instagram as the main social proof/gallery channel.
- Display Booksy services, prices, reviews, and credibility.
- Work as a reusable Framer template.
- Be built first in **Desktop Large** inside Framer.
- Use placeholders first instead of importing final real photos/videos.

The user wanted Claude Code to connect to Framer MCP and recreate the generated website layout reference inside the Framer project.

---

## 3. Tools Used

### ChatGPT

Used for:

- Site strategy
- Layout planning
- Prompt writing
- Framer MCP build instructions
- Claude Code instructions
- System extraction for GitHub documentation

### Image Generation

Used to create a visual mockup/reference image for the barber homepage.

Generated concept included:

- Dark premium barber aesthetic
- Hero section
- Trust row
- About section
- Services/pricing
- Reviews
- Recent cuts gallery
- Booking CTA
- Footer

### Booksy

Used as the business information source.

Extracted details:

- Business name: **Haircuts With Keith**
- Location shown: **2966 Downing St, Jacksonville, 32205**
- Services/prices:
  - Haircut — $40 — 30 min
  - Haircut & beard — $60 — 45 min
  - House Calls — $80+ — 1 hr
  - Head Shaves w/ hot towels — $50 — 40 min
  - Beard Sculpting — $20 — 25 min
- Amenities:
  - Parking space
  - Wi-Fi
  - Credit cards accepted
- Reviews:
  - 5.0 rating
  - 6 reviews

### Cloudinary

Used to host the generated template reference image.

Reference URL:

```text
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png
```

### Framer MCP

Planned tool for building the layout directly in Framer.

Target project:

```text
Keith will cut you
```

Primary breakpoint/section:

```text
Desktop Large
```

### Claude Code

Planned agent for executing the build inside Framer through Framer MCP.

Claude Code was instructed to:

- Connect to Framer MCP.
- Confirm access to the project.
- Ask for full approval/access at the beginning.
- Build the Desktop Large version first.
- Use the Cloudinary mockup as visual reference.
- Use editable Framer frames, stacks, text, cards, buttons, and placeholders.
- Avoid importing final photos yet.

---

## 4. What Worked

### Simple Two-Page / One-Page Site Strategy

The best direction was to avoid overbuilding.

Recommended structure:

- Main one-page homepage/template
- Optional gallery/reviews page later
- Book Now button linking directly to Booksy
- Instagram button linking to his Instagram

This keeps the site appropriate for a solo barber instead of making it feel like a large franchise barbershop.

### Visual Reference Mockup Worked Well

A full desktop homepage mockup was generated and gave a clear visual direction.

The mockup successfully established:

- Dark modern style
- Blue accent color
- Strong hero layout
- Clear booking CTA
- Service cards
- Review cards
- Gallery preview
- Final CTA banner
- Footer structure

This became the primary reference for Claude Code and Framer MCP.

### Placeholder-First Build Strategy

The decision to **not use real photos yet** was correct.

Instead, Claude Code should build:

- Hero video/image placeholder
- About portrait placeholder
- Recent cut 1–6 placeholders

This keeps the Framer build clean and editable before adding real content.

### Desktop Large First

The build should start in **Desktop Large**.

Reason:

- Desktop is the clearest reference from the generated mockup.
- Layout, spacing, hierarchy, and section structure are easier to lock in first.
- Other breakpoints can inherit/adapt afterward.

### Full-Access Request at Start

Since Framer MCP / Claude Code may need user approval to modify the project, the prompt correctly tells Claude Code to ask for full access/approval at the beginning.

Important limitation:

Claude Code can ask for full access upfront, but it cannot bypass Framer or MCP permission systems.

---

## 5. What Failed / Issues to Avoid

### Initial Phrase Ambiguity

The phrase **“Keith Will Cut You”** was initially interpreted as a meme/reference before the full barber context was provided.

Reusable lesson:

When a phrase sounds like a joke, title, brand name, or meme, ask/contextualize before assuming.

### Generated Mockups May Invent Details

The generated mockup included some placeholder/fake details such as:

- Example phone number
- Example Instagram handle
- Sample review names/text
- Placeholder gallery photos

These should not be treated as final truth unless confirmed.

Reusable rule:

Generated website mockups are design references, not reliable business data sources.

### Home Address Privacy Risk

Booksy displayed a street address, and the prompt included it in the footer.

Because this is a home/private shop, the exact address should only be published if Keith explicitly approves.

Safer alternative:

```text
Jacksonville, FL
Exact address sent after booking.
By appointment only.
```

Reusable rule:

For home-based service businesses, do not publish the full home address unless the owner explicitly approves it.

### Do Not Overbuild

A solo barber site does not need:

- Complex multi-page architecture
- Heavy animations
- Large blog system
- Full booking engine inside Framer
- Too many sections
- Excessive copy

The site should route bookings to Booksy and use Instagram for social proof.

---

## 6. Final Decisions

### Final Site Type

Build a **one-page Framer homepage template**.

Optional future pages:

- Gallery
- Reviews
- Contact / Info

But the first build should be one clean homepage.

### Final Project Target

Framer project:

```text
Keith will cut you
```

Primary working area:

```text
Desktop Large
```

### Final Visual Reference

Use this image as the main visual reference:

```text
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png
```

### Final Page Sections

1. Navbar
2. Hero
3. Trust / Info Row
4. About
5. Services & Pricing
6. Reviews
7. Recent Cuts / Gallery Preview
8. Final CTA Banner
9. Footer

### Final Design Direction

- Dark premium barber aesthetic
- Black / charcoal background
- White text
- Blue accent color
- Clean modern typography
- Rounded cards/buttons
- Simple one-man shop positioning
- Appointment-first
- Booksy-first
- Instagram-supported

---

## 7. Reusable Rules

### Rule 1 — Build Desktop First

For Framer MCP visual recreation projects, build the **Desktop Large** breakpoint first when the reference image is desktop-based.

Then adapt tablet/mobile after the main structure is correct.

### Rule 2 — Use Placeholders Before Assets

When the final photos/videos are not ready, build with clearly labeled placeholders.

Example placeholder names:

```text
Hero video/image placeholder
About portrait placeholder
Recent cut 1
Recent cut 2
Recent cut 3
Recent cut 4
Recent cut 5
Recent cut 6
```

### Rule 3 — Keep Solo-Service Websites Simple

For one-person service businesses, prioritize:

- Clear hero
- Booking CTA
- Services/pricing
- Reviews
- Gallery proof
- Contact/location
- Social link

Avoid unnecessary multi-page complexity.

### Rule 4 — Ask for MCP Permissions Upfront

If the user will be away, instruct Claude Code to request Framer MCP access/approval before starting.

Important phrasing:

```text
Ask me immediately for full access/approval to make changes throughout the project before you begin, because I will be away and cannot keep clicking approval buttons.
```

### Rule 5 — Do Not Bypass Approval Systems

Claude Code can request permissions upfront, but it cannot bypass Framer/MCP security or approval prompts.

### Rule 6 — Protect Home Business Privacy

For home-based service businesses, use general location language unless the owner approves public address display.

Recommended safer copy:

```text
Jacksonville, FL
Exact address sent after booking.
By appointment only.
```

### Rule 7 — Reference Images Are Direction, Not Data

Generated mockups are useful for visual hierarchy and style, but all business facts should be verified from the real source.

Use Booksy/owner-confirmed info for:

- Prices
- Address
- Phone number
- Instagram handle
- Reviews
- Policies

---

## 8. Reusable Prompt Snippets

### Framer MCP Full Build Prompt

```text
We are working inside my Framer project named “Keith will cut you.”

The page/template reference image is here:
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png

Before doing any work:
1. Connect to my Framer MCP.
2. Confirm that you can access the Framer project named “Keith will cut you.”
3. Ask me immediately for full access/approval to make changes throughout the project before you begin, because I will be away for some time and won’t be able to keep clicking approval buttons.
4. Once I approve full access, continue building without waiting for extra confirmations unless something is truly unclear.

Project goal:
Recreate the attached/reference barber website layout inside Framer as an editable template page.

Important:
- Work in the Desktop Large breakpoint/section first.
- The Desktop Large version is the priority.
- Once the Desktop Large layout is built correctly, make sure the structure can apply cleanly to the other breakpoints.
- Do not over-focus on mobile until the desktop version looks right.

Design reference:
Use the Cloudinary image URL as the main visual reference. Recreate the layout, spacing, dark premium style, section order, and overall visual hierarchy as closely as possible.

Business/site name:
Haircuts With Keith

Overall style:
- Premium dark barber website
- Black/charcoal background
- White text
- Blue accent color
- Clean modern typography
- Rounded cards and buttons
- Simple, polished, masculine, trustworthy
- Not a large barbershop site — this is a simple one-man private barber/home shop website

Do not add real photos yet.
Use editable placeholder blocks for images and videos. Label the placeholders clearly so I can replace them later.

Create this as a one-page homepage/template with these sections:

1. Navbar
- Left: scissors icon or simple placeholder icon + “Haircuts With Keith”
- Nav links: Home, Gallery, Reviews, Contact
- Right buttons:
  - Book Now
  - Instagram

2. Hero Section
- Large cinematic hero layout
- Use a large hero video/image placeholder on the right/background side
- Left text:
  “Clean cuts.
  Private barber
  experience.”
- Subtext:
  “A private, by-appointment barbershop in Jacksonville focused on quality, precision, and good vibes.”
- Buttons:
  - Book on Booksy
  - Text Keith
- Small rating row:
  “5.0 rating from 6 reviews” with five stars

3. Trust / Info Row
Create four horizontal info cards:
- 5.0 Rating / From 6 reviews
- Private Home Shop / One-on-one experience
- By Appointment / Your time. Your cut.
- Jacksonville, FL / Proudly local

4. About Section
Two-column layout:
- Left: image placeholder labeled “About portrait placeholder”
- Right:
  Small label: ABOUT KEITH
  Heading: “Your cut. My focus.”
  Body:
  “I’m Keith—an independent barber offering a private, by-appointment experience in my home shop in Jacksonville. No crowds, no distractions—just quality cuts, good conversation, and attention to detail.”

5. Services & Pricing
Create five service cards:
- Haircut — $40 — 30 min
- Haircut & beard — $60 — 45 min
- House Calls — $80+ — 1 hr
- Head Shaves w/ hot towels — $50 — 40 min
- Beard Sculpting — $20 — 25 min

Under the cards, add amenity row:
- Parking space
- Wi-Fi
- Credit cards accepted

6. Reviews Section
Left side:
- Big “5.0”
- Five stars
- “6 reviews”

Right side:
Create 3 review cards.

Card 1:
Name: Charlie
Text: “Great cut and even better experience. Professional, clean, and on time.”

Card 2:
Name: Marcus
Text: “Keith pays attention to detail and makes sure you leave looking fresh.”

Card 3:
Name: Derrick
Text: “Top-notch service in a relaxed environment. Highly recommend!”

Also include:
“View all reviews on Booksy”

7. Recent Cuts / Gallery Preview
- Section heading: RECENT CUTS
- Horizontal row/grid with 6 image placeholders
- Label them:
  - Recent cut 1
  - Recent cut 2
  - Recent cut 3
  - Recent cut 4
  - Recent cut 5
  - Recent cut 6

8. Final CTA Banner
Create a dark blue CTA block:
Heading:
“Ready to book with Keith?”

Subtext:
“Spots fill up fast. Book your appointment today.”

Buttons:
- Book on Booksy
- Follow on Instagram

9. Footer
Left:
“Haircuts With Keith”
“Private. Professional. Personal. Quality cuts in a relaxed, one-on-one setting.”

Middle:
CONTACT
“Text Keith: (904) 123-4567”
“Instagram: @haircutswithkeith”

Right:
LOCATION
“2966 Downing St”
“Jacksonville, 32205”
“By appointment only”

Build instructions:
- Use native Framer frames, stacks, text, buttons, cards, and placeholder image/video blocks.
- Keep everything editable.
- Name layers clearly:
  Navbar
  Hero
  Trust Row
  About
  Services
  Reviews
  Gallery Preview
  CTA
  Footer
- Avoid random absolute positioning unless absolutely necessary.
- Use stacks and frames so spacing is easy to adjust later.
- Keep the layout close to the reference image.
- Do not add extra sections.
- Do not import or generate real photos yet.
- Do not overcomplicate animations.
- Simple hover states for buttons/cards are okay, but the main priority is the static layout.

After building:
1. Tell me what you created.
2. Tell me which placeholders I should replace with photos/videos later.
3. Tell me anything that needs manual review inside Framer.
```

### Placeholder-Only Follow-Up Prompt

```text
Use dark image placeholders for now. Label them:
- Hero video/image placeholder
- About portrait placeholder
- Recent cut 1
- Recent cut 2
- Recent cut 3
- Recent cut 4
- Recent cut 5
- Recent cut 6

Do not try to generate or import photos yet. I only want the page structure/template built cleanly first.
```

### Keep It Simple Correction Prompt

```text
Keep it simple. This is a one-page template for a solo barber, not a large barbershop website. The priority is matching the mockup layout, spacing, dark premium style, service cards, review cards, gallery placeholders, and strong booking CTA.
```

### Privacy-Safe Location Correction Prompt

```text
Because this is a home/private barber setup, do not publish the exact street address unless I confirm it is okay. Use:
“Jacksonville, FL”
“Exact address sent after booking”
“By appointment only”
for the public-facing location copy.
```

---

## 9. SOPs / Step-by-Step Workflows

## SOP 1 — Build a Framer Template from a Generated Reference Image

### Step 1 — Create or gather the reference

Use a generated mockup, screenshot, or Cloudinary-hosted image as the main reference.

Example:

```text
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png
```

### Step 2 — Confirm target Framer project

Identify the exact Framer project name.

Example:

```text
Keith will cut you
```

### Step 3 — Choose the primary breakpoint

Use the breakpoint that matches the reference.

For this project:

```text
Desktop Large
```

### Step 4 — Tell Claude Code to connect to Framer MCP

Claude Code should confirm MCP connection and project access before building.

### Step 5 — Ask for full approval upfront

If the user will be away, Claude Code should request full access before editing.

### Step 6 — Build with native Framer elements

Use:

- Frames
- Stacks
- Text
- Buttons
- Cards
- Placeholder blocks
- Icons where available

Avoid building as a flat image.

### Step 7 — Name layers clearly

Recommended section names:

```text
Navbar
Hero
Trust Row
About
Services
Reviews
Gallery Preview
CTA
Footer
```

### Step 8 — Use placeholders first

Add labeled placeholders for images and videos.

### Step 9 — Review desktop before adapting mobile

Do not start solving mobile until Desktop Large is visually correct.

### Step 10 — Replace placeholders later

After the structure is approved, swap in:

- Hero video
- Barber portrait
- Cut photos
- Client photos
- Instagram/Booksy links

---

## SOP 2 — Solo Barber Website Structure

### Recommended one-page order

```text
Navbar
Hero
Trust Row
About
Services & Pricing
Reviews
Recent Cuts
Booking CTA
Footer
```

### Required content

- Business name
- Short positioning statement
- Booking link
- Text/contact link
- Instagram link
- Services and prices
- Rating/reviews
- Recent work/gallery
- Location or appointment-area copy

### Best CTA hierarchy

Primary:

```text
Book on Booksy
```

Secondary:

```text
Text Keith
```

Social:

```text
Instagram
```

---

## SOP 3 — Turning Booksy Data Into Website Content

### Step 1 — Pull service names and prices

Use Booksy as the source of truth for services.

### Step 2 — Pull rating/review count

Use Booksy rating as credibility proof.

### Step 3 — Pull amenities

Use amenities to create a quick trust row or small icons.

### Step 4 — Verify public-facing contact/location

Do not automatically publish private home shop addresses without owner confirmation.

### Step 5 — Link booking buttons to Booksy

Do not recreate booking flow in Framer unless specifically needed.

---

## 10. Future Agent Ideas

### Agent 1 — Framer MCP Template Builder Agent

Purpose:

Build editable Framer pages from reference images.

Responsibilities:

- Confirm project name
- Confirm breakpoint
- Request full access
- Build native Framer structure
- Name layers properly
- Use placeholders
- Summarize created sections

### Agent 2 — Local Service Website Copy Agent

Purpose:

Convert Booksy/Google/Instagram info into clean website copy.

Responsibilities:

- Extract services
- Extract pricing
- Write hero copy
- Write about section
- Write CTA copy
- Create privacy-safe location copy
- Avoid fake claims

### Agent 3 — Placeholder-to-Asset Replacement Agent

Purpose:

After template structure is complete, replace placeholders with final photos/videos.

Responsibilities:

- Match each asset to the correct placeholder
- Crop consistently
- Preserve layout
- Optimize images
- Use Cloudinary URLs if available
- Keep mobile crops safe

### Agent 4 — Home Business Privacy Review Agent

Purpose:

Review local-service websites for privacy risks.

Responsibilities:

- Flag exact home addresses
- Suggest “address sent after booking”
- Check exposed phone numbers
- Check maps embeds
- Confirm owner approval before publishing sensitive details

### Agent 5 — Framer Breakpoint Cleanup Agent

Purpose:

After Desktop Large is built, adapt the page to tablet/mobile.

Responsibilities:

- Stack hero correctly
- Compress service cards
- Convert horizontal galleries to swipe/stack
- Keep CTAs visible
- Fix overflowing text
- Preserve spacing and readability

---

## 11. Recommended Filename

```text
keith-will-cut-you-barber-framer-template.md
```

---

## 12. Recommended Folder Inside the Repo

Recommended folder:

```text
/01-framer-mcp-playbooks
```

Reason:

This is primarily a Framer MCP build workflow/playbook, not just a prompt snippet. It includes project setup, visual reference handling, Claude Code instructions, permission handling, and reusable build rules.

Secondary possible folder:

```text
/02-claude-code-prompts
```

But the best fit is:

```text
/01-framer-mcp-playbooks
```

---

## 13. Agent-Ready Summary

Build an editable one-page Framer template for a solo barber business called **Haircuts With Keith** inside the Framer project **“Keith will cut you.”**

Use this Cloudinary-hosted mockup as the visual reference:

```text
https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png
```

Work in **Desktop Large** first.

Claude Code should connect through Framer MCP, confirm access to the correct project, and ask the user for full approval before beginning because the user may be away and unable to keep approving prompts.

The page should be a simple, premium dark barber homepage with blue accents and these sections:

```text
Navbar
Hero
Trust Row
About
Services & Pricing
Reviews
Recent Cuts / Gallery Preview
Final CTA
Footer
```

Use placeholders only for now. Do not import final photos/videos yet.

Use real service/pricing data from Booksy:

```text
Haircut — $40 — 30 min
Haircut & beard — $60 — 45 min
House Calls — $80+ — 1 hr
Head Shaves w/ hot towels — $50 — 40 min
Beard Sculpting — $20 — 25 min
```

Use the 5.0 rating and 6-review proof point from Booksy.

Keep the site simple and appointment-focused. Primary CTA should be **Book on Booksy**. Secondary CTAs can be **Text Keith** and **Instagram**.

Important privacy rule: because this is a home/private shop, avoid publishing the exact home address unless Keith approves it. Safer public copy is:

```text
Jacksonville, FL
Exact address sent after booking.
By appointment only.
```

This report should be saved as:

```text
/01-framer-mcp-playbooks/keith-will-cut-you-barber-framer-template.md
```

Classification:

```text
SOP + Prompt Snippet + Agent Instruction
```
