# ⚡ CSS & CSS3 Quick-Reference Cheat Sheet

> **Goal:** One-pager with the **most-used** selectors, properties, and modern (CSS3) layout features.
> **Format:** Copy-paste snippets with **inline comments** and helpful “what you get” notes.

---

## 1️⃣ Anatomy of a Rule

```css
selector {            /* targets which elements */
  property: value;    /* declaration */
  /* multiple declarations allowed */
}
```

```css
h1 { color: #3366ff; }          /* all <h1> blue */
.box { padding: 1rem 2rem; }    /* class selector */
```

---

## 2️⃣ Selectors at a Glance

| Pattern            | Example               | Matches / Notes              |
| ------------------ | --------------------- | ---------------------------- |
| Type / Element     | `p`                   | `<p>`                        |
| Class              | `.card`               | elements with `class="card"` |
| ID                 | `#banner`             | element with `id="banner"`   |
| Descendant         | `.nav a`              | `<a>` inside `.nav`          |
| Child (`>`)        | `ul > li`             | direct children              |
| Sibling (`+`, `~`) | `h2 + p`              | first `<p>` after `<h2>`     |
| Attribute          | `input[type="email"]` | email fields                 |
| Pseudo-class       | `a:hover`             | link on hover                |
| Pseudo-element     | `p::first-line`       | first line of paragraph      |
| Grouping           | `h1, h2, h3`          | all these headings           |

**Tip:** Combine selectors for precision (`.card.highlight > h3:first-child{…}`).

---

## 3️⃣ Core Box Model

```css
.box {
  width: 200px;         /* content width  */
  padding: 10px 20px;   /* ↑↓ 10 ‖ ←→ 20  */
  border: 2px solid #333;
  margin: 1rem auto;    /* center block   */
  box-sizing: border-box; /* include border+padding in width */
}
```

*Set `box-sizing: border-box` globally to make layouts predictable.*

---

## 4️⃣ Colors & Units

```css
/* Hex, RGB, HSL */
color: #ff6b81;
color: rgb(255, 107, 129 / 0.8);   /* with alpha */
color: hsl(10 100% 64% / 0.8);

/* Absolute - px; Relative - em, rem, vw, % */
h1 { font-size: 2.5rem; }          /* 1 rem = root font-size */
.box { width: 50vw; }              /* 50 % of viewport width */
```

---

## 5️⃣ Typography Essentials

```css
body {
  font-family: "Inter", system-ui, sans-serif;
  line-height: 1.6;
  font-weight: 400;
}

h1 { text-transform: uppercase; }
p  { text-align: justify; }

a  { text-decoration: none; }
a:hover { text-decoration: underline; }
```

---

## 6️⃣ Layout Superpowers

### 6.1 Flexbox (1-Dimensional)

```css
.container {
  display: flex;              /* activate Flexbox */
  gap: 1rem;                  /* space between items */
  justify-content: space-between; /* main axis */
  align-items: center;        /* cross axis */
}

.item { flex: 1 1 200px; }    /* grow | shrink | basis */
```

| Shorthand  | Expands to                       |
| ---------- | -------------------------------- |
| `flex: 1;` | `flex: 1 1 0%;` *(fill equally)* |

### 6.2 CSS Grid (2-Dimensional)

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.item:nth-child(1) { grid-column: 1 / -1; }  /* span full row */
```

### 6.3 Positioning Cheatsheet

| Value      | Use-case / Effect                                                       |
| ---------- | ----------------------------------------------------------------------- |
| `relative` | Anchor for absolutely-pos children                                      |
| `absolute` | Takes element out of flow; coords relative to nearest positioned parent |
| `fixed`    | Viewport-pinned (sticky headers)                                        |
| `sticky`   | Scroll until threshold, then `fixed`                                    |

```css
.sticky {
  position: sticky;
  top: 0;           /* sticks after 0 px from top */
}
```

---

## 7️⃣ Backgrounds & Gradients

```css
.hero {
  background: url(hero.jpg) center/cover no-repeat;
}

.btn {
  background-image: linear-gradient(90deg, #4facfe, #00f2fe);
  border-radius: 9999px;
  color: #fff;
}
```

---

## 8️⃣ Transitions & Animations

```css
.card {
  transition: transform .3s ease, box-shadow .3s;
}
.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 20px rgba(0,0,0,.15);
}

/* Keyframes */
@keyframes spin {
  to { transform: rotate(360deg); }
}
.loader {
  animation: spin 1s linear infinite;
}
```

---

## 9️⃣ Media Queries (Responsive)

```css
/* Mobile-first base styles … */

@media (min-width: 768px) {      /* tablets & ↑ */
  .sidebar { display: block; }
}
@media (prefers-color-scheme: dark) {
  body { background:#111; color:#eee; }
}
```

---

## 🔟 Common Shorthands & Tricks

| Intent                          | Verbose                                                                     | Shorthand                        |
| ------------------------------- | --------------------------------------------------------------------------- | -------------------------------- |
| Margins (clockwise)             | `margin: 10px 10px 10px 10px;`                                              | `margin: 10px;`                  |
| Padding (top/left-right/bottom) | `padding: 10px 20px 10px 20px;`                                             | `padding: 10px 20px;`            |
| Center block horizontally       | `margin-left:auto; margin-right:auto;`                                      | `margin: 0 auto;`                |
| Border radius all corners       | `border-radius: 5px 5px 5px 5px;`                                           | `border-radius: 5px;`            |
| Font (family-size-line)         | `font-weight:400; font-size:1rem; line-height:1.5; font-family:sans-serif;` | `font: 400 1rem/1.5 sans-serif;` |

---

## 1️⃣1️⃣ Useful Utility Classes (Tailwind-style DIY)

```css
/* Create once – reuse everywhere */
.mt-1 { margin-top: .25rem; }
.text-center { text-align: center; }
.flex-center { display:flex; align-items:center; justify-content:center; }
.hidden { display:none !important; }
```

---

## 1️⃣2️⃣ Debug & Best Practices ✅

1. **Reset / Normalize** to kill default browser quirks (`*{margin:0;box-sizing:border-box}` or \[normalize.css]).
2. **Avoid fixed pixel heights**; use `min-height` or flex.
3. Use **rem / em** for scalable typography, `% / vw` for fluid layouts.
4. Keep specificity low – leverage **BEM** or utility classes to avoid `!important`.
5. Bundle & minify CSS for production; enable **`content-visibility`** or **lazy-loading images** for performance.

---
