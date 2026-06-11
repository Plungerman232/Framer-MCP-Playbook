# Framer MCP Playbook Report

## 1. Chat Title / Topic

**Aura Creative Website Build Workflow, Claude Code Iteration System, Cloudinary Asset Pipeline, and Future AI Agent Architecture**

---

## 2. Main Problem or Build Goal

Build a premium Aura Creative / Aura Digital website using:

- Claude Code
- Framer
- Cloudinary
- ChatGPT

while minimizing manual work and creating a repeatable workflow that can eventually be delegated to AI agents.

The primary challenge was:

- Converting reference designs into Framer-compatible builds
- Managing image assets
- Iterating on layout accuracy
- Fixing image sizing/cropping issues
- Avoiding endless manual prompting cycles
- Building a future AI-agent workflow

---

## 3. Tools Used

### Design / Build

- Framer
- Framer Code Components
- Native Framer Layers

### AI

- ChatGPT
- Claude
- Claude Code

### Asset Hosting

- Cloudinary

### Future Tools Discussed

- Runway
- Codex
- MCP Workflows
- GitHub Repo Knowledge Base

---

## 4. What Worked

### A. Claude Code > Claude

Major finding:

Claude Code performs significantly better than standard Claude for:

- editing existing files
- making layout corrections
- working from screenshots
- updating React/TSX
- preserving context

Decision:

Use Claude Code as primary build engine.

### B. Cloudinary Asset Pipeline

Successful workflow:

1. Generate assets
2. Upload to Cloudinary
3. Use URLs directly in code

Example:

```ts
const heroImg = "https://res.cloudinary.com/..."
```

Instead of:

```ts
import heroImg from "./Hero.png"
```

Benefits:

- Eliminates Framer import issues
- Works across environments
- Easier for Claude Code

### C. Screenshot → Correction Prompt Workflow

Most effective workflow discovered:

1. Claude Code builds
2. Screenshot result
3. ChatGPT analyzes
4. Generate correction prompt
5. Claude Code amends

This consistently outperformed attempting to perfect builds in one prompt.

### D. Page-by-Page Build Strategy

Most successful process:

Build:

- Hero
- Then Page 2
- Then Page 3

instead of:

- entire site at once

Result:

Much cleaner iteration cycles.

---

## 5. What Failed

### A. Overly Generic AI Site Generation

Problem:

Claude frequently generated:

- SaaS layouts
- corporate agency layouts
- generic sections
- fake stats
- testimonials

Fix:

Explicitly forbid:

```text
Do not create a SaaS site.
Do not add fake statistics.
Do not add testimonials.
Do not redesign.
```

### B. Local Image Imports

Problem:

```ts
import hero from "./Hero.png"
```

Failed inside Framer workflows.

Fix:

Use Cloudinary URLs.

### C. Loose Responsive Instructions

Problem:

```text
Make it smaller.
Move it up.
Adjust spacing.
```

Produced inconsistent results.

Fix:

Provide exact measurements.

Example:

```text
Width: 270
Height: 128
Font size: 58
Letter spacing: 28
```

### D. Multiple Fixes Per Prompt

Problem:

Huge correction prompts often created new issues.

Example:

Fixing hero image positioning caused:

- model disappearance
- card cropping
- duplicate text

Fix:

One correction category at a time.

---

## 6. Final Decisions

### Website Build Philosophy

Never build entire site at once.

Always:

```text
Hero
→ Review
→ Fix

Page 2
→ Review
→ Fix

Page 3
→ Review
→ Fix
```

### Use Reference Images Aggressively

Reference images outperform written descriptions.

Preferred:

```text
Match this screenshot.
```

instead of:

```text
Create a cinematic premium layout.
```

### Cloudinary Is Source of Truth

Images should live in Cloudinary, not:

- local folders
- Framer uploads
- scattered assets

### Claude Code = Builder

Claude Code should:

- edit
- build
- refactor

ChatGPT should:

- direct
- critique
- QA
- create prompts

---

## 7. Reusable Rules

### Rule 1

Never ask Claude Code to redesign.

Always say:

```text
Amend the current version.
Do not redesign from scratch.
```

### Rule 2

Fix one category at a time.

Good:

```text
Fix hero positioning only.
```

Bad:

```text
Fix hero, footer, cards, spacing, mobile, and animations.
```

### Rule 3

Use Cloudinary URLs.

Never rely on local image imports.

### Rule 4

Screenshot before every correction pass.

Visual review is mandatory.

### Rule 5

Desktop first.

Target:

```text
Desktop LG 1440
```

before mobile.

---

## 8. Reusable Prompt Snippets

### Snippet: Prevent Redesign

```text
Do not redesign from scratch.

Amend the current version.

Keep the existing layout and concept.

Only fix the issues listed below.
```

### Snippet: Hero Position Fix

```text
Move the hero artwork upward.

The model should remain visible above the cards.

Avoid extreme translateY values.

Use object-position adjustments instead.
```

### Snippet: Cloudinary Conversion

```text
Replace all local image imports with Cloudinary URLs.

Use string constants instead of file imports.

Do not alter layout or styling.
```

### Snippet: Card Image Fix

```text
The artwork should fill the card.

Do not crop the bottom text.

Adjust aspect ratio before changing image fit.
```

---

## 9. SOPs / Step-by-Step Workflows

### SOP: Website Build Cycle

1. Create reference layout.
2. Gather assets.
3. Upload assets to Cloudinary.
4. Generate initial Claude Code build.
5. Preview in Framer.
6. Screenshot Hero, Page 2, and Page 3.
7. Analyze screenshots.
8. Create correction prompt.
9. Apply correction.
10. Repeat.

### SOP: Asset Pipeline

```text
Generate
↓
Upload to Cloudinary
↓
Store URL in master asset sheet
↓
Use in Claude Code
↓
Deploy in Framer
```

---

## 10. Future Agent Ideas

### Agent 1: Creative Director

Responsibilities:

- moodboards
- references
- layouts
- visual direction

Input:

```text
Idea
```

Output:

```text
Creative Brief
```

### Agent 2: Build Manager

Responsibilities:

- Claude Code prompts
- screenshot reviews
- correction passes

Input:

```text
Screenshot
```

Output:

```text
Correction Prompt
```

### Agent 3: Asset Manager

Responsibilities:

- Cloudinary
- image naming
- Runway prompts
- asset mapping

Input:

```text
New Asset
```

Output:

```text
Production-ready URL
```

---

## 11. Recommended Filename

```text
aura-creative-claude-code-cloudinary-agent-workflow.md
```

---

## 12. Recommended Folder

```text
/01-framer-mcp-playbooks
```

Reason:

This is primarily a reusable website-building workflow and Claude Code playbook.

---

## 13. Agent-Ready Summary

This document should become the foundation for an Aura Creative website production system.

Core architecture:

```text
ChatGPT
    ↓
Creative Direction

Claude Code
    ↓
Implementation

Cloudinary
    ↓
Asset Hosting

Framer
    ↓
Visual Assembly
```

Future AI Agent Structure:

```text
Creative Director Agent
    ↓
Build Manager Agent
    ↓
Asset Manager Agent
```

Each build follows:

```text
Reference
→ Assets
→ Claude Code Build
→ Screenshot
→ Correction Prompt
→ Repeat
```

Never redesign.

Always amend.

Always review screenshots.

Always use Cloudinary URLs.

Always fix one category of issue at a time.

---

## Final Repository Placement

**Filename**

```text
aura-creative-claude-code-cloudinary-agent-workflow.md
```

**Folder**

```text
/01-framer-mcp-playbooks
```

**Classification**

Primary: SOP

Secondary: Agent Instruction

Additional Tags:

- Reusable Rules
- Prompt Snippets
- Claude Code Workflow
- Cloudinary Workflow
- Framer Build Workflow

This is not just a project summary. It is a repeatable operating system for future Aura Creative website builds.
