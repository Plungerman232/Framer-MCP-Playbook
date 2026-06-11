# Claude Code Rules

Use these rules when writing prompts for Claude Code or designing Claude Code-backed agents.

## Permission and bypass rules

1. Claude Code may request broad edit approval at the start of a long Framer MCP session.
2. Claude Code must not claim it can bypass Framer, MCP, operating system, or security approvals.
3. If approval is required and the user is away, Claude Code should ask up front before starting many edits.
4. If approval cannot be granted, Claude Code should work only on planning, prompts, documentation, or local files that are available.

Reusable permission wording:

```text
Before you make changes, ask me at the beginning for permission to make all necessary edits inside the target Framer project while I am away. Request full approval up front so you can complete the work without needing me to approve every small change.
```

## When Claude Code should continue without asking

Continue when:

- the task is clearly inside the approved project/page/section
- the requested change is specific and reversible
- source paths/URLs are provided and accessible
- the prompt explicitly says to preserve unrelated sections
- the next step is normal QA inside the agreed scope

Examples:

- replacing one image source in a named card
- adjusting one crop by a specified amount
- creating named parent frames and child layers for an approved page build
- checking links and hover states after a build

## When Claude Code should stop and ask

Stop and ask when:

- the project name does not match
- Framer MCP cannot inspect the target canvas
- the layer or component cannot be identified
- the prompt mentions conflicting files or image slots
- a requested change risks rebuilding a working component
- the same error repeats without new information
- the user-owned asset must remain exact but the available method changes it
- a permission, login, or connection block appears

## What Claude Code should report back

At the end of a session, Claude Code should report:

1. Target Framer project and page/section touched.
2. Exact layers/components changed.
3. Assets used, including local paths or Cloudinary URLs.
4. What was intentionally left untouched.
5. Before/after values for layout, crop, object-position, size, or spacing changes.
6. Any failed attempts and their likely cause.
7. QA performed: desktop, mobile, links, buttons, hover, images, loading, animation.
8. Remaining manual checks.
9. Recommended markdown report filename and repo folder.

## How to avoid looping on small problems

1. Use short correction prompts after the first build.
2. Fix one variable at a time.
3. Do not repeat a massive original prompt for a tiny alignment issue.
4. If two or three attempts fail, stop and summarize.
5. Switch strategy when the failure mode is clear: Cloudinary instead of local upload, native overlays instead of Runway, object-position instead of source replacement, manual Framer check instead of more MCP edits.

## Prompt shape that works

Use this structure:

```text
In the Framer project [PROJECT NAME], update only [PAGE/SECTION/LAYER].

Goal:
[Exact desired change.]

Use:
[Exact file path, folder, URL, or reference.]

Do not change:
- [protected section]
- [protected layout]
- [protected image/card]
- [protected animation]
- [protected typography]

Before finishing, report:
- what changed
- before/after values
- what stayed untouched
- any unresolved issues
```

