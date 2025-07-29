---
category: "pointer_gesture_inputs"
category_description: "Make pointer and touch interactions accessible and provide alternatives."
---

### Overview

Gestures such as swiping or multi-finger movements must have simple alternatives. Users should be able to cancel actions and control motion activation; target sizes should be large enough for accurate interaction.

### Relevant WCAG 2.1 success criteria

- **2.5.1 Pointer Gestures** (Level A) – Provide single-pointer alternatives to complex gestures.【755185167370695†L1472-L1502】
- **2.5.2 Pointer Cancellation** (Level A) – Allow users to abort pointer actions before completion.【755185167370695†L1472-L1502】
- **2.5.3 Label in Name** (Level A) – Accessible name contains the visible label text.【755185167370695†L1516-L1529】
- **2.5.4 Motion Actuation** (Level A) – Provide alternative to device motion activation and let users disable it.【755185167370695†L1472-L1502】
- **2.5.5 Target Size** (Level AAA) – Targets are at least 44×44 CSS pixels.【755185167370695†L1472-L1502】

### Technical guidance

* Avoid requiring multi-finger gestures; offer buttons or single taps.  
* Do not activate actions on touchstart; wait until pointerup so users can cancel.  
* Make sure the accessible name includes the visible label (e.g. a button labelled “Send” must have the same accessible name).  
* Provide on-screen controls when device motion triggers actions and allow motion activation to be turned off.  
* Make interactive targets at least 44×44px with spacing between them.

### Code example

#### Button with matching name
```html
<button aria-label="Add item">Add item</button>
```

#### Swipe alternative
```html
<div class="item">
  <span>Task 1</span>
  <button class="delete">Delete</button>
</div>
<script>
  document.querySelector('.delete').addEventListener('click',()=>{
    // delete item
  });
</script>
```
