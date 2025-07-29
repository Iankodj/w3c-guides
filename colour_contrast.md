---
category: "colour_contrast"
category_description: "Ensure sufficient contrast and do not rely solely on colour."
---

### Overview

Colour helps communicate, but relying on it alone excludes colour-blind users. Provide sufficient contrast for text and controls and support high-contrast modes.

### Relevant WCAG 2.1 success criteria

- **1.4.1 Use of Colour** (Level A) – Do not use colour as the only cue.
- **1.4.3 Contrast (Minimum)** (Level AA) – 4.5:1 ratio for normal text and 3:1 for large text. ([WCAG 1.4.3 – Contrast (Minimum)](https://www.w3.org/TR/WCAG21/#contrast-minimum))
- **1.4.11 Non-text Contrast** (Level AA) – 3:1 ratio for icons and controls. ([WCAG 1.4.11 – Non-text Contrast](https://www.w3.org/TR/WCAG21/#non-text-contrast))

### Technical guidance

* Pair colour cues with text or icons (e.g. red border plus error icon).  
* Verify contrast ratios using tools; adjust colours to meet 4.5:1 for body text.  
* Provide visible focus outlines with high contrast.  
* Offer alternative themes (dark, high contrast) while maintaining ratios.

### Code example

#### Error message with icon
```html
<label for="email">Email</label>
<input id="email" aria-invalid="true">
<span class="error" id="email-error">
  <svg aria-hidden="true">...</svg>
  Invalid email address.
</span>
```

#### High contrast button
```html
<button style="background:#004a99;color:#fff;outline:3px solid #ffbf47">Submit</button>
```
