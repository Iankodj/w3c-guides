---
category: "timing_movement_motion"
category_description: "Let users control timing and reduce movement that could cause harm."
---

### Overview

Time limits and auto-moving content can frustrate or exclude people with disabilities. Provide controls to extend time and pause or stop motion, and avoid content that flashes or moves unexpectedly.

### Relevant WCAG 2.1 success criteria

- **2.2.1 Timing Adjustable** (Level A) – Warn users of time limits and let them adjust or extend. ([WCAG 2.2.1 – Timing Adjustable](https://www.w3.org/TR/WCAG21/#timing-adjustable))
- **2.2.2 Pause, Stop, Hide** (Level A) – Users can pause, stop or hide moving or auto-updating content. ([WCAG 2.2.2 – Pause, Stop, Hide](https://www.w3.org/TR/WCAG21/#pause-stop-hide))
- **2.3.1 Three Flashes or Below** (Level A) – Content does not flash more than three times per second.
- **2.3.3 Animation from Motion** (Level AA) – Motion animation triggered by interaction can be disabled.

### Technical guidance

* Avoid or minimise time limits; allow users to extend sessions when necessary.  
* Provide controls (pause, next, previous) on carousels and auto-rotating content.  
* Do not include content that flashes quickly; abide by the three-flash rule.  
* Respect users’ `prefers-reduced-motion` setting and offer a toggle to reduce animations.

### Code example

#### Slideshow with pause
```html
<div class="slideshow">
  <button class="pause">Pause</button>
  <!-- slides here -->
</div>
<script>
  document.querySelector('.pause').addEventListener('click',()=>{
    // pause rotation logic
  });
</script>
```

#### Respect reduced motion
```html
<style>
@media (prefers-reduced-motion: reduce) {
  .spinner { animation: none; }
}
.spinner { animation: spin 1s linear infinite; }
</style>
<div class="spinner"></div>
```
