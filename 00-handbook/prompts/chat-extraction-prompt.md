# Chat Extraction Prompt

Use this in ChatGPT when extracting reusable material from old project chats.

```text
Read this project chat and extract the reusable Framer MCP / Claude Code / Codex / image asset knowledge into a clean markdown report.

Focus on:
1. repeated Framer MCP rules
2. repeated Claude Code rules
3. Codex and GitHub workflow rules
4. image, Cloudinary, upload, compression, and local file path rules
5. debugging rules and stop conditions
6. reusable prompt snippets
7. SOPs / workflows
8. future agent ideas
9. important Aura project context
10. exact file paths, URLs, project names, and tool behaviors

Do not just summarize the conversation. Extract the operational knowledge that future agents can reuse.

Preserve:
- exact prompts that worked
- exact paths
- exact URLs
- Framer project names
- Cloudinary links
- tool names
- mistakes and fixes
- stop conditions

Do not preserve:
- private secrets
- full MCP session URLs
- irrelevant small talk
- duplicate explanation unless it reveals a repeated rule

At the end, include:
- recommended filename in lowercase kebab-case
- recommended folder in the Framer-MCP-Playbook repo
- whether the content should become a rule, SOP, prompt snippet, project summary, brand note, or agent instruction
```

