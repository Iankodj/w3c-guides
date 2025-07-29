---
category: "carousel"
category_description: "Make rotating carousels controllable and reduce motion."
---

### Overview

Carousels that automatically cycle through content can disorient users. Provide controls to pause and navigate slides and respect reduced motion preferences.

### Relevant WCAG 2.1 success criteria

- **2.2.2 Pause, Stop, Hide** (Level A) – Users can pause or stop auto-rotating slides. ([WCAG 2.2.2 – Pause, Stop, Hide](https://www.w3.org/TR/WCAG21/#pause-stop-hide))
- **2.3.3 Animation from Motion** (Level AA) – Users can disable motion animation.
- **2.4.3 Focus Order** (Level A) – Focus moves logically through slides and controls. ([WCAG 2.4.3 – Focus Order](https://www.w3.org/TR/WCAG21/#focus-order))

### Technical guidance

* Include previous, next and pause buttons accessible via keyboard and screen readers.  
* Disable auto-rotation by default or pause after one cycle; respect `prefers-reduced-motion`.  
* Announce slide changes using live regions or update the slide label.  
* Ensure focus does not get trapped in the carousel; allow users to navigate away easily.

### Code example

#### Carousel controls
```html
<div class="carousel">
  <button aria-label="Previous slide">❮</button>
  <button aria-label="Next slide">❯</button>
  <button aria-label="Pause slideshow">❚❚</button>
</div>
```
