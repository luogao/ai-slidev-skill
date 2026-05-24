# AI + Slidev Skill 🎤

> An Agent Skill that teaches AI to generate professional presentations using [Slidev](https://github.com/slidevjs/slidev)

[![Skills](https://img.shields.io/badge/skills.sh-ai--slidev-blue)](https://www.skills.sh/luogao/ai-slidev-skill)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**One topic → One Markdown file → Beautiful slides. In under a minute.**

## What It Does

This skill teaches any AI agent (Claude Code, Codex, Cursor, GitHub Copilot, etc.) how to:

1. **Understand your topic** — Gather requirements or infer from context
2. **Generate Slidev Markdown** — Complete `slides.md` with layouts, code, speaker notes
3. **Choose the right theme** — Dark tech, corporate, or custom branded
4. **Export** — PDF, SPA, or PNG with one command

## Demo

🇨🇳 [中文文档](README_CN.md)

*A 30-second video showing: topic → AI generates Markdown → Slidev renders slides → PDF export*

**Video coming soon — stay tuned!**

## Quick Start

### Install the Skill

```bash
# Using the skills CLI
npx skills add https://github.com/luogao/ai-slidev-skill

# Or manually: copy the skill contents into your agent's skill directory
```

### Use with Your Agent

Just ask your AI agent:

> "Create a 10-slide presentation about React performance optimization"

The agent (with this skill loaded) will:
1. Generate a complete `slides.md` file
2. Help you set up the Slidev project
3. Preview and iterate
4. Export to PDF

### Manual Setup

```bash
# Create project
mkdir my-talk && cd my-talk
npm init slidev@latest

# Paste AI-generated content into slides.md
# Start dev server
npm run dev

# Export to PDF
npm run export
```

## What's Included

```
ai-slidev-skill/
├── SKILL.md                        # Core skill instructions
├── references/
│   ├── slidev-syntax.md            # Complete Slidev Markdown syntax
│   └── prompt-templates.md         # AI prompt templates for 7 scenarios
├── assets/
│   └── themes/                     # Pre-built theme configurations
│       ├── dark-tech.json          # Dark tech/developer theme
│       └── corporate.json          # Clean business theme
├── examples/
│   └── demo-slides.md              # Example presentation
└── README.md
```

## Prompt Templates

| Template | Best For |
|----------|----------|
| Quick Presentation | Any topic, fast generation |
| Tech Talk with Code | Developer presentations with live code |
| Business Pitch Deck | Startups, fundraising, product launches |
| Tutorial/Workshop | Hands-on teaching with exercises |
| Lightning Talk | 5-minute conference talks |
| Academic/Research | Paper presentations with math |
| From Existing Content | Convert articles/notes to slides |

## Compatible Agents

Works with any agent that supports the [Agent Skills spec](https://agentskills.io/specification):

- ✅ Claude Code
- ✅ OpenAI Codex
- ✅ Cursor
- ✅ GitHub Copilot
- ✅ Windsurf
- ✅ Cline
- ✅ Any agent with SKILL.md support

## Why Slidev?

| Feature | PowerPoint | Slidev |
|---------|-----------|--------|
| Format | `.pptx` binary | `.md` plain text |
| Version control | ❌ | ✅ Git-friendly |
| AI-generated | Hard to automate | Natural Markdown output |
| Code blocks | Ugly screenshots | Syntax-highlighted, live |
| Developer experience | GUI-only | CLI + hot reload |
| Theme ecosystem | Expensive | Free & open source |
| Export | Built-in | PDF / SPA / PNG |

## License

MIT © [luogao](https://github.com/luogao)
