---
category: "non_text_content"
category_description: "Provide text alternatives for images, icons and non-text elements."
---

### Overview

Images, icons and other graphics must have equivalent text so that users who cannot see them can still understand their purpose. Avoid using images of text when real text will suffice and ensure icons and controls have sufficient contrast.

### Relevant WCAG 2.1 success criteria

- **1.1.1 Non-text Content** (Level A) – Supply text alternatives for non-text content.【755185167370695†L492-L544】
- **1.4.5 Images of Text** (Level AA) – Use text instead of images of text wherever possible.【755185167370695†L492-L544】
- **1.4.11 Non-text Contrast** (Level AA) – Provide 3:1 contrast ratio for icons and controls against adjacent colours.【755185167370695†L973-L990】

### Technical guidance

* Use `<img>` with a descriptive `alt` attribute for informative images.  
* Provide empty `alt=""` and `aria-hidden="true"` for decorative icons.  
* Avoid embedding text in images; use real HTML text so users can resize and adjust it.  
* Ensure icons and graphical controls meet a 3:1 contrast ratio against the background.

### Code example

#### Accessible image and decorative icon
```html
<!-- Informative image with alt text -->
<img src="/images/chart.png" alt="Sales chart showing Q1–Q4 growth">

<!-- Decorative icon hidden from assistive tech -->
<img src="/icons/star.svg" alt="" aria-hidden="true">
```

#### Replacing images of text with real text
```html
<!-- Avoid: <img src="sale.png" alt="Sale!"> -->
<h2>Sale!</h2>
<p>Up to 50% off.</p>
```
