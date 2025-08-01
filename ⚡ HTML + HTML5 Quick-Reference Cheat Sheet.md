# ⚡ HTML + HTML5 Quick-Reference Cheat Sheet

> **Purpose:** Fast, one-page reminder of the most-used tags, attributes, and modern (HTML5) goodies.
> **Format:** Copy-paste snippets with **inline comments** explaining purpose and showing rendered result where helpful.

---

## 1️⃣ Boilerplate & Metadata

```html
<!DOCTYPE html>                          <!-- standards mode -->
<html lang="en">
<head>
  <meta charset="utf-8">                 <!-- UTF-8 -->
  <meta name="viewport"                  <!-- responsive -->
        content="width=device-width, initial-scale=1">
  <title>Page Title</title>
  <link rel="stylesheet" href="style.css"> <!-- external CSS -->
  <script defer src="app.js"></script>   <!-- non-blocking JS -->
</head>
<body>
  <!-- content … -->
</body>
</html>
```

*Always start with `<!DOCTYPE html>` to enable standards mode.*

---

## 2️⃣ Structure & Semantics

```html
<header>      <!-- page header / logo / nav -->
  <nav>
    <ul><li><a href="#main">Home</a></li></ul>
  </nav>
</header>

<main id="main">     <!-- primary content (only 1 per page) -->
  <article>          <!-- independent story -->
    <h1>Title</h1>
    <p>Paragraph text…</p>
  </article>

  <section>          <!-- thematic grouping -->
    <h2>Features</h2>
  </section>
</main>

<aside>Related links</aside>  <!-- complementary info -->
<footer>&copy; 2025</footer>   <!-- page footer -->
```

**Best practice:** Use semantic tags instead of generic `<div>` for SEO & accessibility.

---

## 3️⃣ Text & Inline Formatting

```html
<h1>Heading 1</h1>        <!-- H1–H6 hierarchy -->
<p>Regular text<br>Line-break.</p>
<strong>Bold</strong> / <em>Italic</em>   <!-- semantic emphasis -->
<code>let x = 1;</code>    <!-- inline code -->
<pre><code>multiline code block…</code></pre>
<blockquote cite="https://example.com">
  Quoted text…
</blockquote>
<hr>                      <!-- thematic break -->
```

---

## 4️⃣ Lists & Tables

```html
<ul> <li>Coffee</li> <li>Tea</li> </ul>     <!-- unordered -->
<ol start="3"> <li>Third</li> <li>Fourth</li> </ol> <!-- ordered -->
<dl> <dt>HTML</dt><dd>Markup language</dd> </dl>   <!-- definition -->

<table>
  <caption>Monthly Sales</caption>
  <thead><tr><th>Month</th><th>€</th></tr></thead>
  <tbody>
    <tr><td>Jan</td><td>1 000</td></tr>
    <tr><td>Feb</td><td>900</td></tr>
  </tbody>
  <tfoot><tr><td>Total</td><td>1 900</td></tr></tfoot>
</table>
```

*Use `<th scope="col|row">` for accessible headers.*

---

## 5️⃣ Links, Images & Media

```html
<a href="https://site.com" target="_blank" rel="noopener">
  Visit Site
</a>

<figure>
  <img src="pic.jpg" alt="Descriptive text">  <!-- alt = REQUIRED -->
  <figcaption>Figure 1: Caption.</figcaption>
</figure>

<!-- Responsive images -->
<picture>
  <source srcset="img.webp" type="image/webp">
  <img src="img.jpg" alt="Fallback">
</picture>

<!-- Audio / Video -->
<video controls width="320" poster="cover.jpg">
  <source src="clip.mp4" type="video/mp4">
  Your browser doesn’t support video.
</video>
```

---

## 6️⃣ Forms (HTML5 inputs highlighted)

| Input type | Example snippet                                      | Note / Validation             |
| ---------- | ---------------------------------------------------- | ----------------------------- |
| **text**   | `<input type="text" name="user" required>`           | `required` enforces non-empty |
| **email**  | `<input type="email">`                               | checks for `@`                |
| **number** | `<input type="number" min="1" max="5" step="0.1">`   | numeric spinner               |
| **date**   | `<input type="date">`                                | OS date-picker                |
| **range**  | `<input type="range" min="0" max="100">`             | slider                        |
| **color**  | `<input type="color">`                               | color-picker                  |
| **file**   | `<input type="file" accept=".pdf,image/*" multiple>` | upload                        |

```html
<form action="/save" method="post">
  <fieldset>
    <legend>Profile</legend>
    <label>
      Name <input name="name" autocomplete="name">
    </label>
    <datalist id="cities">
      <option value="Cairo"><option value="Alexandria">
    </datalist>
    <input list="cities" name="city">
    <button type="submit">Send</button>
  </fieldset>
  <output id="score">0</output>
  <progress value="70" max="100"></progress>
</form>
```

**Tip:** Pair each input with a `<label>` for accessibility.

---

## 7️⃣ Interactive / Graphics Elements

```html
<details open>
  <summary>Click to toggle</summary>
  Hidden content…
</details>

<dialog id="dlg">
  <p>Modal message</p>
  <button onclick="dlg.close()">Close</button>
</dialog>
<script>document.getElementById('dlg').showModal();</script>

<canvas id="c" width="150" height="100"></canvas>
<script>
  var ctx = document.getElementById('c').getContext('2d');
  ctx.fillStyle = "salmon";
  ctx.fillRect(10,10,130,80);
</script>

<svg width="120" height="60">
  <rect width="120" height="60" fill="cornflowerblue"/>
  <text x="10" y="35" fill="#fff">SVG</text>
</svg>
```

---

## 8️⃣ Inline JS & Best-Practice Meta

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">   <!-- legacy -->
<meta name="description" content="Brief page summary">
<link rel="icon" href="favicon.svg" type="image/svg+xml">

<script>
  "use strict";                    // safer JS
  document.addEventListener("DOMContentLoaded", function () {
    // JS here runs after HTML parsed
  });
</script>
<noscript>Please enable JavaScript.</noscript>
```

---

## 9️⃣ Global Attributes & Data\*

| Attribute  | Purpose / Example                                    |
| ---------- | ---------------------------------------------------- |
| `id`       | Uniquely identify (`<div id="banner">`)              |
| `class`    | Style / select (`class="btn primary"`)               |
| `style`    | Inline CSS (`style="color:red"`)                     |
| `hidden`   | Boolean: hide element but keep in DOM                |
| `title`    | Tooltip text                                         |
| `tabindex` | Keyboard order                                       |
| `data-*`   | Custom data (`data-role="modal"`) retrievable via JS |

---

## 🔟 Accessibility & SEO Tips

1. **Always write `alt` text** for images (except purely decorative images with `alt=""`).
2. **Landmarks (`<header>`, `<nav>`, `<main>`, `<footer>`)** help screen-reader navigation.
3. **Use heading order (H1→H2→H3)**; never skip levels.
4. **Label controls** (`<label for="email">…`) or wrap input inside label.
5. **Language attribute** (`<html lang="en">`) for proper pronunciation & indexing.
6. **ARIA roles sparingly**—only when semantics lack (`role="button"` on a `<div>` etc.).

---

## ⚙️ Self-Closing vs Normal Tags

| Self-closing allowed                       | Must close                                      |
| ------------------------------------------ | ----------------------------------------------- |
| `<img>` `<input>` `<meta>` `<link>` `<br>` | `<script></script>` `<style></style>` `<a></a>` |

*(HTML5 allows omitting `/`, but `<img />` works too.)*

---

### 🔑 Golden Rules Recap

* **Use semantic tags** → better SEO, accessibility, maintainability.
* **Validate** with the **W3C HTML Validator** to catch typos & missing attributes.
* **Keep CSS & JS external** (`<link>`, `<script defer>`) for caching & clean markup.
* **Include `viewport` meta** for responsive sites.
* **Minimize inline styles**; prefer external or `<style>` blocks scoped with classes.

Pin this cheat-sheet near your editor 🔖—instant recall for everyday HTML & HTML5 essentials!
