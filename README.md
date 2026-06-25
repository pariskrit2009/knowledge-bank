# 📚 Team TIL — Today I Learned

A running log of small, useful things our frontend & WordPress team picks up each week.
Born from our weekly knowledge-sharing sessions. One share, every week — captured here so it never gets lost.

> **The rule:** if it helped you, it can help someone else. Tips, fixes, tools, gotchas — all count.

---

## 🔍 How to find things

- **Search the whole repo:** press <kbd>t</kbd> on GitHub, or use the search bar at the top.
- **Ctrl/Cmd + F** on this page to find a keyword or a tag like `#wordpress`.
- **Browse by category** using the index below.
- Every entry is tagged. Tags are written as `#lowercase` so they're easy to search. Stick to the [approved tag list](#-tags) to keep search reliable.

---

## ✍️ How to add an entry (≈60 seconds)

Do this **live at the end of each session** — don't leave it as homework.

1. Click **Add file → Edit `README.md`** (or open a PR if you prefer review).
2. Copy the template below.
3. Paste it at the **top of the matching category section** (newest first).
4. Fill in the five fields, commit. Done.

### 📋 Entry template — copy this

```markdown
### <Short, specific title>

**Date:** YYYY-MM-DD · **By:** @your-username · **Tags:** `#tag1` `#tag2`

One or two sentences: what it is and why it's useful.

<!-- optional: a tiny code snippet -->
\`\`\`css
/* example */
\`\`\`

🔗 [Source / docs / PR](https://example.com)
```

**Keep it tight.** Title + two sentences + a link is the whole job. If you're writing paragraphs, link out instead.

---

## 🗂️ Categories

| Category | Count | Jump to |
|---|---|---|
| 🎨 CSS | 1 | [#css](#-css) |
| 🟦 JavaScript | 1 | [#javascript](#-javascript) |
| 🌐 WordPress | 1 | [#wordpress](#-wordpress) |
| ⚡ Performance | 0 | [#performance](#-performance) |
| 🛠️ Tooling & Editor | 1 | [#tooling--editor](#️-tooling--editor) |
| 🐛 Bug Fixes & Gotchas | 0 | [#bug-fixes--gotchas](#-bug-fixes--gotchas) |
| 🔀 Git & Workflow | 0 | [#git--workflow](#-git--workflow) |
| ♿ Accessibility | 0 | [#accessibility](#-accessibility) |

> Update the count when you add an entry — it's a quick health check on which areas we're learning in.

---

## 🏷️ Tags

Use these consistent tags so search and filtering stay reliable. Add a new one only when nothing fits, and add it to this list when you do.

`#css` `#scss` `#layout` `#javascript` `#react` `#wordpress` `#php` `#hooks` `#gutenberg` `#performance` `#tooling` `#vscode` `#git` `#accessibility` `#a11y` `#security` `#bug` `#workflow`

---

## 🎨 CSS

### `:where()` keeps specificity flat

**Date:** 2026-06-20 · **By:** @example-dev · **Tags:** `#css` `#layout`

Wrapping selectors in `:where()` gives them **zero specificity**, so base styles inside it are trivially easy to override later. Great for resets and component defaults.

```css
:where(.card) h2 { margin-top: 0; } /* easy to override anywhere */
```

🔗 [MDN: :where()](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)

---

## 🟦 JavaScript

### `structuredClone()` for deep copies

**Date:** 2026-06-20 · **By:** @example-dev · **Tags:** `#performance`

Built into modern browsers and Node — deep-clones objects without `JSON.parse(JSON.stringify(...))` hacks, and it handles Dates, Maps, and Sets correctly.

```js
const copy = structuredClone(original);
```

🔗 [MDN: structuredClone()](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)

---

## 🌐 WordPress

### Conditionally dequeue scripts you don't need

**Date:** 2026-06-20 · **By:** @example-dev · **Tags:** `#wordpress` `#performance` `#hooks`

A plugin was loading its JS on every page. Dequeuing it everywhere except where it's used shaved real weight off the homepage.

```php
add_action( 'wp_enqueue_scripts', function () {
    if ( ! is_page( 'contact' ) ) {
        wp_dequeue_script( 'some-plugin-script' );
    }
}, 100 );
```

🔗 [WP docs: wp_dequeue_script()](https://developer.wordpress.org/reference/functions/wp_dequeue_script/)

---

## ⚡ Performance

<!-- Add entries here, newest first -->

_No entries yet — be the first to add one._

---

## 🛠️ Tooling & Editor

### VS Code: edit all matches at once

**Date:** 2026-06-20 · **By:** @example-dev · **Tags:** `#tooling` `#vscode`

Select a word and press <kbd>Cmd/Ctrl + Shift + L</kbd> to put a cursor on **every** occurrence in the file at once. Faster than find-and-replace for quick renames.

🔗 [VS Code: multiple cursors](https://code.visualstudio.com/docs/editor/codebasics#_multiple-selections-multicursor)

---

## 🐛 Bug Fixes & Gotchas

<!-- Add entries here, newest first -->

_No entries yet — be the first to add one._

---

## 🔀 Git & Workflow

<!-- Add entries here, newest first -->

_No entries yet — be the first to add one._

---

## ♿ Accessibility

<!-- Add entries here, newest first -->

_No entries yet — be the first to add one._

---

<sub>Maintained by the frontend & WordPress team · Add yours after each weekly session 🎉</sub>
