---
category: "navigation_focus"
category_description: "Provide clear navigation and descriptive links and headings."
---

### Overview

Good navigation helps users find content quickly. Descriptive page titles, headings, link text and multiple ways to locate pages improve the user experience.

### Relevant WCAG 2.1 success criteria

- **2.4.2 Page Titled** (Level A) – Pages have descriptive titles. ([WCAG 2.4.2 – Page Titled](https://www.w3.org/TR/WCAG21/#page-titled))
- **2.4.4 Link Purpose** (Level A) – Link text describes its purpose.
- **2.4.5 Multiple Ways** (Level AA) – Offer more than one way to find pages. ([WCAG 2.4.5 – Multiple Ways](https://www.w3.org/TR/WCAG21/#multiple-ways))
- **2.4.6 Headings and Labels** (Level AA) – Headings and labels describe the content or purpose. ([WCAG 2.4.6 – Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels))
- **2.4.8 Location** (Level AAA) – Provide information about the user’s location (e.g. breadcrumbs). ([WCAG 2.4.8 – Location](https://www.w3.org/TR/WCAG21/#location))

### Technical guidance

* Use unique, descriptive titles and headings that match the topic or purpose.  
* Write meaningful link text; avoid “click here”.  
* Provide a search, site map or table of contents as alternative navigation.  
* Indicate the current location using breadcrumbs or `aria-current` on navigation links.

### Code example

#### Breadcrumb navigation
```html
<nav aria-label="Breadcrumb">
  <ol>
    <li><a href="/">Home</a></li>
    <li><a href="/articles">Articles</a></li>
    <li aria-current="page">Accessibility</li>
  </ol>
</nav>
```

#### Descriptive link
```html
<p>Read more about <a href="/a11y-testing">accessibility testing</a>.</p>
```
