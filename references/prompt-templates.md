# AI Prompt Templates for Slidev Presentations

Ready-to-use prompt templates for generating presentations with any AI model.

## Template 1: Quick Presentation

```
Generate a Slidev Markdown presentation about [TOPIC].

Requirements:
- [N] slides
- Language: [LANGUAGE]
- Audience: [TECHNICAL/BUSINESS/GENERAL]
- Theme: [default/seriph/apple-basic/dracula]
- Include speaker notes

Output the complete slides.md content only, no explanation.
```

## Template 2: Tech Talk with Code

```
Create a Slidev presentation for a tech talk about [TOPIC].

Structure:
1. Cover slide with title "[TITLE]" and author "[NAME]"
2. Problem/Why slide — what pain point does this solve?
3. Overview slide — high-level architecture or concept
4. Code demo slide — show [LANGUAGE] code example
5. API/Usage slide — how to use it
6. Comparison slide — compare with alternatives (two-column layout)
7. Performance slide — benchmarks or metrics
8. Live demo slide — placeholder for live demo
9. Resources slide — links and documentation
10. Q&A slide

Rules:
- Use layout: image-right for code slides
- Add line highlighting with {N} syntax
- Include speaker notes for each slide
- Use fenced code blocks with language tags
- Theme: seriph

Output complete slides.md.
```

## Template 3: Business Pitch Deck

```
Generate a business pitch deck using Slidev about [COMPANY/PRODUCT].

Structure (12 slides):
1. Cover — company name + tagline
2. Problem — the market pain point (use layout: statement)
3. Market Size — TAM/SAM/SOM with big numbers
4. Solution — our product/service (layout: image-right)
5. How It Works — 3-step process
6. Demo — screenshot or mockup
7. Business Model — pricing tiers (two-column comparison)
8. Traction — key metrics and growth
9. Team — key team members
10. Competition — competitive landscape table
11. Ask — funding amount and use of funds
12. Contact — contact info + QR code

Style:
- Theme: default
- Clean, professional, data-driven
- Use large numbers for metrics
- Include a subtle background gradient

Output complete slides.md.
```

## Template 4: Tutorial/Workshop

```
Create a Slidev presentation for a hands-on workshop about [TOPIC].

Structure:
1. Cover — workshop title + instructor name
2. Agenda — table of contents with time estimates
3. Prerequisites — what attendees need installed
4. Concepts (2-3 slides) — key concepts with diagrams
5. Step 1 — first exercise with code example
6. Step 2 — second exercise
7. Step 3 — third exercise
8. Common Mistakes — troubleshooting tips
9. Resources — links to docs, repos, further reading
10. Exercise — practice problem for attendees
11. Solutions — answer reveal (use v-click)
12. Q&A

Rules:
- Use v-clicks for step-by-step reveals
- Code blocks should be copy-paste ready
- Include <!-- Speaker notes --> with talking points
- Add line numbers to code blocks
- Theme: apple-basic

Output complete slides.md.
```

## Template 5: Conference Lightning Talk

```
Generate a 5-minute lightning talk using Slidev about [TOPIC].

Constraints:
- Maximum 7 slides (1 minute per slide)
- Each slide: one BIG idea, minimal text
- Must start with a hook (surprising stat or question)
- Must end with a clear takeaway

Structure:
1. Hook — attention-grabbing opening
2. Context — why this matters
3. The Thing — the core concept/feature
4. Demo — code or visual example
5. Impact — real-world results
6. Takeaway — one sentence to remember
7. CTA — where to learn more

Style:
- Big fonts, minimal text per slide
- Use layout: statement for emphasis
- Theme: dracula (dark)
- Add dramatic pauses with v-click

Output complete slides.md.
```

## Template 6: Academic/Research Presentation

```
Create a Slidev presentation for an academic talk about [RESEARCH TOPIC].

Structure (15 slides):
1. Title slide — paper title, authors, affiliation
2. Motivation — why this research matters
3. Related Work — prior art (use comparison table)
4. Problem Statement — formal definition
5. Our Approach — methodology overview
6. Architecture — system/architecture diagram
7. Algorithm — pseudocode or algorithm block
8. Implementation — key technical decisions
9. Experimental Setup — dataset, metrics, baselines
10. Results — main findings (use tables/figures)
11. Results (cont.) — additional analysis
12. Discussion — implications and limitations
13. Future Work — next steps
14. Conclusion — summary of contributions
15. References — key citations

Rules:
- Formal academic tone
- Use LaTeX math: $E = mc^2$ (Slidev supports KaTeX)
- Include equation slides where appropriate
- Theme: default
- Speaker notes: detailed talking points

Output complete slides.md.
```

## Template 7: From Existing Content

```
Convert the following content into a Slidev presentation:

[PASTE YOUR CONTENT HERE — article, notes, outline, etc.]

Rules:
- One slide per key point
- Preserve all important information
- Add visual structure (layouts, headers, bullets)
- Include speaker notes summarizing each slide
- Theme: [default/seriph/apple-basic]
- Target: [N] slides

Output complete slides.md.
```

## Customization Tips

### Adding Your Brand

```
Generate the presentation with these brand colors:
- Primary: #3cffd0 (use for headings and accents)
- Secondary: #FFB800 (use for highlights)
- Background: #1d1d1f (dark mode)
- Text: #ffffff

Add this to the global style block:
<style>
:root { --slidev-theme-primary: #3cffd0; }
</style>
```

### Adding Chinese Font Support

```
In the frontmatter, add:
fonts:
  sans: 'Noto Sans SC, Inter'
  mono: 'Fira Code'

This ensures Chinese characters render correctly.
```
