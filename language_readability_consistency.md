---
category: "language_readability_consistency"
category_description: "Specify language, explain abbreviations and keep navigation consistent."
---

### Overview

Setting the correct language and providing definitions or expansions for jargon and abbreviations helps users understand your content. Consistent navigation and predictable interactions build trust and reduce cognitive load.

### Relevant WCAG 2.1 success criteria

- **3.1.1 Language of Page** (Level A) – Specify the page’s primary language. ([WCAG 3.1.1 – Language of Page](https://www.w3.org/TR/WCAG21/#language-of-page))
- **3.1.4 Abbreviations** (Level AAA) – Provide expansions for abbreviations on first use. ([WCAG 3.1.4 – Abbreviations](https://www.w3.org/TR/WCAG21/#abbreviations))
- **3.2.3 Consistent Navigation** (Level AA) – Navigation mechanisms appear in the same order across pages. ([WCAG 3.2.3 – Consistent Navigation](https://www.w3.org/TR/WCAG21/#consistent-navigation))
- **3.2.4 Consistent Identification** (Level AA) – Components with the same function are identified consistently. ([WCAG 3.2.4 – Consistent Identification](https://www.w3.org/TR/WCAG21/#consistent-identification))
- **3.2.1 On Focus** (Level A) – Focusing on an element does not change context unexpectedly. ([WCAG 3.2.1 – On Focus](https://www.w3.org/TR/WCAG21/#on-focus))

### Technical guidance

* Set the `lang` attribute on the `<html>` element and wrap passages in different languages in elements with their own `lang`.  
* Define abbreviations using `<abbr title="...">` so screen readers can announce the full term.  
* Keep navigation menus and global controls in the same order on every page.  
* Do not trigger page changes or submit forms on focus or input events without user confirmation.

### Code example

#### Language and abbreviation
```html
<p lang="en">We work with the <abbr title="World Health Organization">WHO</abbr>.</p>
<p lang="es">Bienvenido a nuestro sitio.</p>
```

#### Consistent navigation example
```html
<nav>
  <ul>
    <li><a href="/home">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
<!-- The same order appears on other pages -->
```
