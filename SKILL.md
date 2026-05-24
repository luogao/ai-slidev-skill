---
name: ai-slidev
description: "Use this skill when the user wants to create a presentation, slides, deck, or PPT using AI + Slidev. Trigger when the user mentions making slides, creating a presentation, generating a deck, or asks about using AI to make PPTs. Works with any AI agent (Claude Code, Codex, Cursor, etc.) to generate Slidev Markdown presentations from a topic or outline. Covers: topic analysis, content generation, Slidev Markdown syntax, theme selection, speaker notes, code blocks, animations, and export to PDF."
license: MIT
---

# AI + Slidev: Generate Professional Presentations with AI

Create beautiful, developer-friendly presentations by combining AI with [Slidev](https://github.com/slidevjs/slidev) — the markdown-based slide framework.

## Quick Reference

| Task | Guide |
|------|-------|
| Generate a presentation | Follow the **Workflow** below |
| Slidev Markdown syntax | Read [references/slidev-syntax.md](references/slidev-syntax.md) |
| AI prompt templates | Read [references/prompt-templates.md](references/prompt-templates.md) |
| Theme configurations | Browse [assets/themes/](assets/themes/) |
| Example presentations | Browse [examples/](examples/) |

---

## Workflow

### 1. Gather Requirements

Ask the user (or infer from context):

- **Topic**: What is the presentation about?
- **Audience**: Technical? Business? General?
- **Length**: How many slides? (default: 10-15)
- **Language**: Output language (default: user's language)
- **Style**: Dark/light? Any brand colors?
- **Content**: Should it include code blocks? Charts? Images?

### 2. Generate Slidev Markdown

Use the AI to generate a complete Slidev Markdown file based on the requirements. Follow these rules:

#### Structure

A Slidev file is a single Markdown file with `---` as slide separators:

```markdown
---
theme: default
background: https://cover.sli.dev
class: text-center
---

# Your Title
Subtitle text

<br>

@Author Name

---
layout: default
---

# Second Slide

Content here...
```

#### Content Guidelines

- **Cover slide**: Title + subtitle + author. Use `text-center` class.
- **Agenda/TOC slide**: List of topics with icons or numbers.
- **Content slides**: One key idea per slide. Use short lines.
- **Code slides**: Use fenced code blocks with language tag. Add `line-numbers` if needed.
- **Image slides**: Use `<img>` or `![alt](url)` with layout positioning.
- **Comparison slides**: Use two-column layout with `<div class="flex gap-4">`.
- **Data slides**: Use large numbers for stats, simple tables for comparisons.
- **Closing slide**: Summary + call-to-action or Q&A prompt.

#### Slide Design Rules

- **One idea per slide** — never cram multiple topics
- **Max 6 bullet points** per slide — fewer is better
- **Short text** — each line should be readable at a glance
- **Visual hierarchy** — use `#` for slide title, `##` for sections, `###` for subsections
- **Speaker notes** — add `<!-- -->` comments below slide content for presenter reference

### 3. Choose a Theme

Pick from built-in themes or custom configurations:

| Theme | Best For | Config |
|-------|----------|--------|
| `default` | General purpose | Clean, Apple Keynote style |
| `seriph` | Corporate/Business | Professional, minimal |
| `apple-basic` | Tech talks | Apple-style, clean |
| `bricks` | Creative/Startups | Bold, modern |
| `dracula` | Dark theme talks | Dark purple, code-friendly |
| Custom | Brand-specific | See [assets/themes/](assets/themes/) |

Set theme in frontmatter: `theme: <name>`

### 4. Setup & Preview

```bash
# Create project
mkdir my-presentation && cd my-presentation

# Initialize Slidev
npm init slidev@latest

# Place generated slides.md as slides.md (the default entry)
# Or reference your file in package.json

# Start dev server with hot reload
npm run dev

# Export to PDF
npm run export

# Export to SPA (hosted presentation)
npm run build
```

### 5. Iterate

- Preview in browser at `http://localhost:3030`
- Adjust content, layout, and styling based on preview
- Add animations with `<v-click>` and `<Transition>` if needed
- Fine-tune with per-slide CSS using `<style>` blocks

---

## Slidev Markdown Quick Syntax

```
# Slide separator
---

# Frontmatter (first slide only, optional for others)
---
theme: default
layout: cover
background: https://image.url
class: text-center
---

# Layouts available
layout: cover        # Full-screen title
layout: intro        # Introduction page
layout: default      # Standard content
layout: center       # Centered content
layout: fact         # Big quote/fact
layout: statement    # Bold statement
layout: two-cols     # Two columns
layout: two-cols-header  # Two columns with header
layout: image        # Image with side content
layout: image-right  # Content left, image right
layout: image-left   # Image left, content right
layout: section      # Section divider
layout: quote        # Quote block
layout: none         # No default styling

# Features
<!-- Speaker notes -->
[Link text](url)     # Links
![Image](url)        # Images
`inline code`        # Inline code
```language          # Code blocks with syntax highlighting
<v-click>           # Click animations
<Transition>        # Vue transitions
<div class="...">   # Custom CSS classes (Tailwind/UnoCSS)

# Slot annotations (for two-col layouts)
::left::
Left column content
::right::
Right column content
::

# Page transition
transition: slide-up  # slide-up, slide-down, slide-left, slide-right, fade, fade-out
```

For complete syntax, see [references/slidev-syntax.md](references/slidev-syntax.md).

---

## Prompt Templates

When generating presentations, use these prompt patterns:

### Basic generation prompt
```
Generate a Slidev Markdown presentation about [TOPIC].
Requirements:
- [N] slides, [LANGUAGE]
- Audience: [TECHNICAL/BUSINESS/GENERAL]
- Theme: [THEME_NAME]
- Include: [CODE_BLOCKS/IMAGES/CHARTS]
- Style: [DARK/LIGHT]

Output only the complete Markdown content, ready to use as slides.md.
```

### Advanced with outline
```
First, create a slide outline for a presentation about [TOPIC].
Then generate the full Slidev Markdown.

Outline format:
1. Cover: [title]
2. [Section]: [key points]
...

After confirming the outline, generate the complete slides.md.
```

See [references/prompt-templates.md](references/prompt-templates.md) for more templates.

---

## Export Options

```bash
# PDF (one page per slide)
npm run export

# PDF with presenter notes
npm run export -- --with-notes

# Portable SPA (single HTML file)
npm run build

# PNG slides
npm run export -- --format png
```

---

## Tips & Pitfalls

1. **Always start with `---` frontmatter** — Slidev needs the first block to be YAML frontmatter
2. **Don't use HTML slide breaks inside code blocks** — `---` inside fenced code won't create new slides
3. **Use `layout: two-cols` with `::left::` / `::right::`** — not raw HTML columns
4. **Speaker notes go after the slide content** — use `<!-- Your notes -->` at the bottom of each slide
5. **Code blocks auto-highlight** — just specify the language: ` ```python ` 
6. **Tailwind/UnoCSS classes work** — use `class="text-center mt-10"` freely
7. **Images can be URLs** — Slidev fetches remote images automatically
8. **Export requires Playwright** — if `npm run export` fails: `npx playwright install chromium`
9. **Chinese/Unicode support** — add `fonts: sans: ['Noto Sans SC']` in frontmatter if needed
10. **Global components** — Vue components in `components/` folder are auto-registered
11. **Force `colorSchema: light` on dark themes** — macOS dark mode causes Slidev to auto-switch colors, making custom dark backgrounds' text invisible. Always add `colorSchema: light` in frontmatter when using dark backgrounds.
12. **No nested code blocks** — Never use ` ``` ` inside another fenced code block (e.g. ` ````markdown `). Slidev does not support nested fences. If you need to show code examples on a code slide, use screenshots, HTML `<pre><code>` entities, or put each code snippet in a separate non-nested fenced block.

---

## File References

When generating a presentation, you may optionally read:

- [references/slidev-syntax.md](references/slidev-syntax.md) — Complete Slidev Markdown syntax reference
- [references/prompt-templates.md](references/prompt-templates.md) — AI prompt templates for different presentation types
- [assets/themes/](assets/themes/) — Pre-built theme configurations
- [examples/](examples/) — Example Slidev presentations
