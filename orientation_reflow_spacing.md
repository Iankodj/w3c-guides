---
category: "orientation_reflow_spacing"
category_description: "Support both orientations and let content reflow with zoom and spacing adjustments."
---

### Overview

Users may rotate their device or zoom in for readability. Content should reflow without horizontal scrolling, and text must be resizable with adjustable spacing.

### Relevant WCAG 2.1 success criteria

- **1.3.4 Orientation** (Level AA) – Do not restrict to a single orientation.【755185167370695†L703-L720】
- **1.4.10 Reflow** (Level AA) – Reflow content without two-dimensional scrolling at 320 CSS pixels width.【755185167370695†L942-L971】
- **1.4.4 Resize Text** (Level AA) – Text can be resized to 200% without loss of content.【755185167370695†L817-L825】
- **1.4.12 Text Spacing** (Level AA) – Custom spacing (line, letter, word) does not break layout.【755185167370695†L993-L1006】

### Technical guidance

* Use responsive design (flexbox, grid and media queries) and avoid fixed widths.  
* Allow orientation changes; avoid forcing portrait or landscape.  
* Define font sizes and spacing in relative units like `em` or `rem`.  
* Test with large zoom and increased line, word and letter spacing to ensure content remains usable.

### Code example

#### Responsive layout
```html
<style>
  .card { flex: 1 1 300px; margin: 1rem; }
  @media (max-width:600px) { .cards { flex-direction: column; } }
</style>
<div class="cards" style="display:flex;flex-wrap:wrap;">
  <div class="card">Card A</div>
  <div class="card">Card B</div>
</div>
```

#### Relative text sizes
```html
<style>
  body { font-size:1rem; line-height:1.5; }
  h1 { font-size:2rem; margin-bottom:1rem; }
</style>
<h1>Title</h1>
<p>Paragraph text scales proportionally when zoomed.</p>
```
