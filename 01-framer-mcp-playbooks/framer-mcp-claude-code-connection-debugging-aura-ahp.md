# Framer MCP Setup, Claude Code Connection Debugging, and Safe Framer Editing Workflow

## 1. Chat Title / Topic

**Framer MCP Setup — Claude Code + Framer MCP Connection Debugging for Aura Creative / AHP.tsx**

## 2. Main Problem or Build Goal

The goal was to connect **Claude Code** to the active **Framer MCP plugin** so Claude could inspect and edit the live Framer canvas directly instead of relying on screenshots.

The specific Framer project involved an **Aura Creative / Aura hero page** built mostly through one custom code component file, `AHP.tsx`. The user wanted Claude to inspect the canvas, understand the page structure, and later make precise hero-layout edits with actual Framer context.

Main pain point: Claude Code had the Framer MCP server configured, but the connection repeatedly failed because of stale URLs, wrong transport type, duplicate MCP server names, and session-restart timing.

## 3. Tools Used

- **Framer desktop / browser workspace**
- **Framer MCP plugin**
- **Claude Code**
- **Windows PowerShell**
- **Claude Code MCP commands**
- **Framer MCP URL from `mcp.unframer.co`**
- **AHP.tsx Framer code component**
- **Cloudinary-hosted image assets**
- **GitHub repo destination:** `https://github.com/Plungerman232/Framer-MCP-Playbook`

## 4. What Worked

### Successful MCP Connection

The final successful state showed:

```text
framer-mcp — connected — 22 tools
```

This confirmed Claude Code could access the Framer MCP toolset.

### Correct Transport

The working transport was:

```powershell
--transport http
```

The Framer MCP endpoint was not legacy SSE. It used **Streamable HTTP**, so using `--transport sse` caused failures.

### Correct Add Command

The working command pattern was:

```powershell
claude mcp add --transport http framer-mcp "FULL_FRAMER_MCP_URL"
```

### Correct Status Check

Inside Claude Code, the correct check was:

```text
/mcp
```

This showed whether the MCP server was actually available inside the current Claude Code session.

### Correct Fix for Broken Entry

The broken MCP entry was named:

```text
framer-mcp
```

So the correct removal command was:

```powershell
claude mcp remove framer-mcp
```

Removing only `framer` did not fix the issue because the failed entry was not named `framer`.

### Claude Code Eventually Inspected the Canvas

Once connected, Claude successfully called Framer MCP and summarized:

- One Framer page: `Home`
- Path: `/`
- Root desktop layout
- One main code component instance: `AuraDesktopHeroV2`
- Main code file: `AHP.tsx`
- Brand controls wired into the component
- Cloudinary-hosted hero and service-card images
- Three service buttons/cards: Visual, Digital, Creative
- Page/state navigation behavior
- No CMS collections
- No standalone reusable Framer components
- No design pages
- No global color/text styles

### Safe Working File Decision

Between the two similar Framer project tabs/files:

- `MCP Play`
- `Beloved Feature`

The better starting point was **MCP Play** because it appeared to be the safer connected testing copy. `Beloved Feature` should remain untouched as a backup/reference.

## 5. What Failed

### Wrong Transport: SSE

The command below caused connection issues:

```powershell
claude mcp add --transport sse framer-mcp "FULL_FRAMER_MCP_URL"
```

Claude later diagnosed that the Framer MCP endpoint required **HTTP / Streamable HTTP**, not legacy SSE.

### Duplicate / Stale Entries

At different points, both of these names were used:

```text
framer
framer-mcp
```

This created confusion. The actual failed entry was `framer-mcp`, so removing `framer` alone did not clear the broken connection.

### Restart Confusion

Claude Code MCP tools load at session startup. Adding the MCP server mid-session can make `claude mcp list` show the server as configured, but the active Claude Code chat may still not have the tools loaded yet.

This created the feeling that the connection “worked earlier,” then stopped after starting fresh.

### Pasting Raw MCP URL Into Claude Chat

Pasting the raw MCP URL directly into Claude Code caused Claude to ask what to do with the URL instead of automatically registering it.

Better pattern:

1. Add the MCP URL through PowerShell using `claude mcp add`.
2. Restart Claude Code.
3. Check `/mcp`.

### Running the Wrong Slash Command

The user accidentally typed:

```text
/claude-api
```

This was unrelated to Framer MCP and did not help.

Correct commands inside Claude Code were:

```text
/mcp
/exit
```

### Sharing the Full MCP URL Secret

The Framer MCP URL included a sensitive `secret=` parameter. The full URL was shared during debugging. This should be treated like a temporary session token.

Recommended action after setup/debugging: restart or refresh the Framer MCP plugin to rotate the secret.

## 6. Final Decisions

1. Use **HTTP transport**, not SSE.
2. Use one consistent MCP server name: `framer-mcp`.
3. Remove broken entries before re-adding fresh URLs.
4. Always get a fresh Framer MCP URL after restarting the Framer MCP plugin.
5. Never publicly expose the full URL after `secret=`.
6. Use `/mcp` inside Claude Code to verify the tools are available.
7. Use `MCP Play` as the working/test project.
8. Preserve `Beloved Feature` as backup/reference.
9. Before editing, have Claude inspect and summarize `AHP.tsx`.
10. Do not allow broad edits until Claude confirms page/component/layer structure.

## 7. Reusable Rules

### Rule: Do Not Guess MCP Transport

If Framer MCP fails with SSE, test/add with HTTP:

```powershell
claude mcp add --transport http framer-mcp "FULL_FRAMER_MCP_URL"
```

### Rule: Remove the Exact Failed MCP Name

If `/mcp` shows:

```text
framer-mcp — failed
```

remove exactly:

```powershell
claude mcp remove framer-mcp
```

Do not remove a different name and assume it fixed the problem.

### Rule: MCP Tools Load at Claude Code Startup

After adding an MCP server, restart Claude Code before expecting the tools to appear.

### Rule: Use `/mcp` Before Re-Adding Anything

Before adding another MCP entry, always check:

```text
/mcp
```

This prevents duplicate stale configs.

### Rule: Never Share the Full MCP Secret Publicly

A Framer MCP URL may look like:

```text
https://mcp.unframer.co/mcp?id=PROJECT_ID&secret=PRIVATE_SECRET
```

Safe sharing format:

```text
https://mcp.unframer.co/mcp?id=REDACTED&secret=REDACTED
```

or:

```text
https://mcp.unframer.co/mcp?REDACTED
```

### Rule: Edit the Test Copy First

When two similar Framer versions exist, edit the connected/safe test file first and keep the preferred/reference version untouched.

## 8. Reusable Prompt Snippets

### Diagnose Framer MCP Setup

```text
I’m trying to connect Claude Code to the Framer MCP plugin.

Context:
- The Framer desktop app is open.
- The Framer MCP plugin is currently running inside Framer.
- I have the MCP URL available from the plugin.
- I do not know where the plugin is installed locally.
- Do not edit my website files yet.

Please diagnose the MCP setup on this computer. Check my Claude Code MCP config, list any existing MCP servers, identify duplicates or broken Framer entries, and tell me the exact next command I should run to connect to the active Framer MCP plugin. Ask me for the fresh Framer MCP URL only when you need it. Do not assume npm/framer-mcp unless you verify it.
```

### Inspect Framer Canvas Before Editing

```text
Use framer-mcp to inspect my current Framer canvas before making edits. Tell me what pages, components, frames, and key layers you can see.
```

### Read AHP.tsx Before Editing

```text
Read the AHP.tsx code file in full.
```

### Summarize Before Editing

```text
Before making edits, summarize how AHP.tsx controls the hero section, the three buttons, the page transitions, and the image positioning. Then tell me the safest way to edit only the hero page while preserving the other pages/sections.
```

### Hero-Only Safety Instruction

```text
Only edit the hero section in AHP.tsx. Preserve the service cards, page transitions, about section, footer, and all page 2/3 behavior. Do not rename layers, do not restructure unrelated sections, and do not touch Cloudinary image URLs unless I explicitly ask.
```

## 9. SOPs / Step-by-Step Workflows

## SOP 1: Clean Framer MCP Setup in Claude Code

### Step 1 — Open Framer First

Open the Framer project and make sure the Framer MCP plugin is running.

### Step 2 — Copy a Fresh MCP URL

Copy the full URL from the Framer MCP plugin.

Do not remove anything from the URL when using it locally.

### Step 3 — Remove Broken MCP Entries

In PowerShell:

```powershell
claude mcp remove framer
claude mcp remove framer-mcp
```

It is okay if one of them does not exist.

### Step 4 — Add Framer MCP with HTTP Transport

```powershell
claude mcp add --transport http framer-mcp "FULL_FRAMER_MCP_URL"
```

### Step 5 — Check MCP List

```powershell
claude mcp list
```

Desired result:

```text
framer-mcp — connected
```

### Step 6 — Start Claude Code Fresh

```powershell
claude
```

### Step 7 — Verify Inside Claude Code

```text
/mcp
```

Desired result:

```text
framer-mcp — connected — tools available
```

### Step 8 — Inspect Before Editing

```text
Use framer-mcp to inspect my current Framer canvas before making edits. Tell me what pages, components, frames, and key layers you can see.
```

## SOP 2: Handling Failed Framer MCP Connection

If `/mcp` shows failed:

```text
framer-mcp — failed
```

Do this:

```powershell
claude mcp remove framer-mcp
```

Then restart the Framer MCP plugin, copy a fresh URL, and re-add:

```powershell
claude mcp add --transport http framer-mcp "FULL_FRESH_FRAMER_MCP_URL"
```

Then:

```powershell
claude mcp list
claude
```

Inside Claude Code:

```text
/mcp
```

## SOP 3: Safe Editing Workflow for AHP.tsx

1. Connect Framer MCP.
2. Verify `/mcp` shows `framer-mcp — connected`.
3. Ask Claude to inspect the canvas.
4. Ask Claude to read `AHP.tsx` in full.
5. Ask Claude to summarize how the hero, cards, transitions, image positioning, and footer work.
6. Only then provide a targeted edit prompt.
7. Restrict edits to one area at a time.
8. Use the test Framer project/file first.
9. Compare against the backup/reference project.
10. Do not allow broad layer renaming or unrelated code cleanup during visual edits.

## SOP 4: Redacting Framer MCP URL

Original style:

```text
https://mcp.unframer.co/mcp?id=PROJECT_ID&secret=PRIVATE_SECRET
```

For screenshots/messages:

```text
https://mcp.unframer.co/mcp?id=REDACTED&secret=REDACTED
```

or:

```text
https://mcp.unframer.co/mcp?REDACTED
```

For local Claude Code setup, use the full URL exactly as Framer provides it.

## 10. Future Agent Ideas

### Agent Idea 1: Framer MCP Setup Doctor

A small agent that:

- Checks `claude mcp list`
- Detects stale/failed Framer entries
- Removes duplicates
- Asks for a fresh MCP URL
- Adds it with HTTP transport
- Verifies `/mcp` availability
- Warns if the token was exposed

### Agent Idea 2: Framer Code Component Inspector

A Claude/Codex-style agent that:

- Reads the active Framer canvas
- Finds the code component file
- Summarizes prop controls
- Summarizes animation/state logic
- Identifies safe edit zones
- Outputs “do not touch” sections before edits

### Agent Idea 3: Aura Hero Layout Precision Agent

A layout-focused agent for Aura Creative pages that:

- Compares current hero layout against a reference screenshot
- Outputs exact pixel/percentage placement instructions
- Adjusts card sizing, hero image position, typography, nav, footer, and scroll text
- Avoids vague prompts like “make it smaller”
- Uses numbers: widths, heights, gaps, top offsets, bottom offsets, z-index, opacity

### Agent Idea 4: MCP Token Hygiene Agent

A safety helper that:

- Detects exposed `secret=` URLs in chat/logs
- Reminds the user to restart the Framer MCP plugin
- Converts URLs into redacted examples for documentation

## 11. Recommended Filename

```text
framer-mcp-claude-code-connection-debugging-aura-ahp.md
```

## 12. Recommended Folder Inside the Repo

```text
/01-framer-mcp-playbooks
```

Secondary possible location:

```text
/06-debugging-rules
```

But the best primary folder is `/01-framer-mcp-playbooks` because this chat became a full connection/setup playbook.

## 13. Agent-Ready Summary

This chat documents a successful Framer MCP + Claude Code setup after repeated connection failures. The key issue was that the Framer MCP endpoint needed `--transport http`, not `--transport sse`. Claude Code showed a stale failed entry named `framer-mcp`, so the fix was to remove that exact entry, restart the Framer MCP plugin, copy a fresh full URL, and re-add it with HTTP transport. After restarting Claude Code, `/mcp` showed `framer-mcp — connected — 22 tools`.

Once connected, Claude could inspect the Framer canvas and identify a single-page Aura Creative project using one main code component, `AuraDesktopHeroV2`, powered by `AHP.tsx`. The component controlled the hero, Cloudinary images, three service cards, page transitions, and about/footer sections. The safest editing path is to work in the `MCP Play` copy first, keep `Beloved Feature` untouched as a backup, read `AHP.tsx` in full, summarize its structure, and then make narrow hero-only edits without touching unrelated pages, transitions, cards, or Cloudinary URLs.

## Final Classification

### Exact Markdown Filename

```text
framer-mcp-claude-code-connection-debugging-aura-ahp.md
```

### Exact Repo Folder

```text
/01-framer-mcp-playbooks
```

### Should This Become a Rule, SOP, Prompt Snippet, Project Summary, or Agent Instruction?

This should become **all four**, but its primary form should be an **SOP**.

Recommended breakdown:

- **SOP:** Full Framer MCP setup and recovery workflow.
- **Rule:** Always use HTTP transport for this Framer MCP endpoint; verify with `/mcp`; remove exact failed entry names.
- **Prompt snippet:** Reusable Claude Code diagnostic and canvas-inspection prompts.
- **Agent instruction:** Future agents must inspect `AHP.tsx` and Framer canvas before editing and must avoid broad unrelated changes.
