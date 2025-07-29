---
category: "menu_navigation"
category_description: "Accessible menus and hierarchical navigation."
---

### Overview

Menus organise links and commands; hierarchical menus need clear structure and keyboard support. Use lists for simple nav and ARIA menu roles for complex menus.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Group menu items and submenus semantically.
- **2.1.1 Keyboard** (Level A) – Arrow keys navigate menus and submenus. ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **2.4.7 Focus Visible** (Level AA) – Menu items show visible focus. ([WCAG 2.4.7 – Focus Visible](https://www.w3.org/TR/WCAG21/#focus-visible))
- **3.2.3 Consistent Navigation** (Level AA) – Menu appears in the same order across pages. ([WCAG 3.2.3 – Consistent Navigation](https://www.w3.org/TR/WCAG21/#consistent-navigation))

### Technical guidance

* For simple nav, use a `<ul>` with `<li>` containing `<a>` links.  
* For complex menus, set `role="menubar"` on the root, `role="menuitem"` on each item and `role="menu"` on submenus; manage `aria-haspopup` and `aria-expanded`.  
* Support arrow key navigation according to orientation (horizontal or vertical) and provide Esc to close submenus.  
* Provide clear focus styling on each menu item; hide submenus when not active.

### Code example

#### Simple nav
```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/blog">Blog</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
```

#### Menu with submenu
```html
<ul role="menubar">
  <li role="none">
    <button role="menuitem" aria-haspopup="true" aria-expanded="false">Products</button>
    <ul role="menu" hidden>
      <li role="none"><a role="menuitem" href="/phones">Phones</a></li>
      <li role="none"><a role="menuitem" href="/tablets">Tablets</a></li>
    </ul>
  </li>
</ul>
```
