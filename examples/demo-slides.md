---
theme: default
css: unocss
transition: slide-up
---

# AI + Slidev
Generate Professional Presentations with AI

<br>

One Markdown file → Beautiful slides

<br>

@luogao

---
layout: default
---

# Why AI + Slidev?

<div class="grid grid-cols-2 gap-8 mt-10">

<div>

### The Old Way
- Open PowerPoint
- Choose a template
- Write content slide by slide
- Adjust formatting manually
- **30+ minutes per deck**

</div>

<div>

### The AI + Slidev Way
- Describe your topic
- AI generates Markdown
- Slidev renders slides
- Auto-styled and formatted
- **Under 1 minute**

</div>

</div>

---
layout: default
---

# How It Works

<div class="mt-10 text-xl">

**Step 1:** Tell AI your topic  
> "Create a 10-slide deck about React performance"

**Step 2:** AI generates Slidev Markdown  
> Complete `slides.md` with layouts, code blocks, speaker notes

**Step 3:** Preview & Export  
> `npm run dev` → `npm run export` → Done!

</div>

---
layout: two-cols
---

# Example: Code Slides

Code blocks with syntax highlighting and line numbers:

<br>

- Auto-highlight with language tags
- Step-through with `{1|2-3|all}`
- Live Monaco editor for demos
- Copy-paste ready

::right::

```python {all|1-2|3-4|all}
import slidev

def present(topic):
    slides = ai.generate(topic)
    return slidev.render(slides)

present("My Awesome Talk")
```

---
layout: center
class: text-center
---

# Try It Yourself

<br>

```bash
npm init slidev@latest
```

<br>

**GitHub:** github.com/luogao/ai-slidev-skill

---
