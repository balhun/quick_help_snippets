
# React + AOS (Animate On Scroll) Guide

Use **AOS (Animate On Scroll)** in React to animate elements as they scroll into view. Great for enhancing UI with subtle fade, zoom, or slide effects.

---

## ✅ 1. Install AOS

```bash
npm install aos --save
```

---

## ✅ 2. Import AOS in Your Component

```jsx
import React, { useEffect } from 'react';
import AOS from 'aos';
import 'aos/dist/aos.css'; // Import AOS styles

function MyComponent() {
  useEffect(() => {
    AOS.init({
      duration: 800, // animation duration (in ms)
      once: true,    // only animate once
    });
  }, []);

  return (
    <div>
      <h1 data-aos="fade-up">Welcome to Paragliding</h1>
      <p data-aos="fade-in">Soar above the clouds!</p>
      <div data-aos="zoom-in" className="card">
        Book Your Flight
      </div>
    </div>
  );
}

export default MyComponent;
```

---

## ✅ 3. Best Practices

- Initialize AOS only **once**, preferably in your top-level component (`App.js`, `Layout.js`, etc.).
- Add `data-aos="effect-name"` to any element you want to animate.

---

## ✅ 4. Refresh AOS When Dynamically Rendering Content

If you load data dynamically (e.g., from an API), you may need to refresh AOS:

```jsx
useEffect(() => {
  AOS.init();
  AOS.refresh();
}, [yourData]);
```

---

## ✨ Common AOS Effects

| Attribute             | Description             |
|----------------------|-------------------------|
| `fade-up`            | Fade in + slide up      |
| `fade-down`          | Fade in + slide down    |
| `fade-right`         | Fade in from right      |
| `fade-left`          | Fade in from left       |
| `zoom-in`            | Zoom into view          |
| `flip-left`          | Flip in from the left   |

Full list: [https://michalsnik.github.io/aos/](https://michalsnik.github.io/aos/)

---

## ✅ Great For

- Portfolio sections
- Cards and content blocks
- Landing page intros
- CTA elements

---

## 🛠️ Alternative Libraries (Advanced)

- **GSAP ScrollTrigger** – Advanced control with timelines.
- **Framer Motion** – React-native animation powerhouse.
- **IntersectionObserver API** – Vanilla JS way (manual control).
