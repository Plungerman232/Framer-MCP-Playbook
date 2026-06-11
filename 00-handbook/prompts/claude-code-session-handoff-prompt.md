# Claude Code Session Handoff Prompt

Use this at the end of a Claude Code + Framer MCP session to create a clean report that can be saved into this repo.

```text
Summarize this full Claude Code / Framer MCP session as a GitHub-ready markdown report.

Preserve useful details:
- exact Framer project name
- pages, sections, layers, cards, and components touched
- local file paths
- Cloudinary URLs
- image/video asset names
- prompts that worked
- prompts or approaches that failed
- MCP connection issues
- permission issues
- layout values, crop values, object-position values, and before/after measurements
- any links, buttons, routes, or interactions changed

Organize the report with these sections:

1. Chat title / topic
2. Main problem or build goal
3. Tools used
4. What worked
5. What failed
6. Final decisions
7. Reusable rules
8. Reusable prompt snippets
9. SOPs / step-by-step workflows
10. Future agent ideas
11. Recommended filename
12. Recommended folder inside the repo
13. Agent-ready summary

Important:
- Do not invent details.
- Do not remove exact paths or URLs.
- Do not expose private MCP session URLs or secrets.
- If something is uncertain, mark it as uncertain.
- Recommend a lowercase kebab-case filename.
- Recommend one of these repo folders:
  /01-framer-mcp-playbooks
  /02-claude-code-prompts
  /03-image-asset-workflows
  /04-project-summaries
  /05-agent-instructions
  /06-debugging-rules
  /07-aura-brand-systems
  /08-reference-builds
  /09-inbox-unsorted
```

