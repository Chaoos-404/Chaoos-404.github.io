# Warm Palette Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Apply the supplied warm four-color scheme consistently to the existing personal website.

**Architecture:** Keep the current single-page HTML and its responsive layout unchanged. Replace the current dark-theme CSS color tokens with a warm palette and preserve existing interactive behavior, including sticky navigation and card hover motion.

**Tech Stack:** HTML5 and CSS3; no build tooling or runtime dependencies.

## Global Constraints

- Modify only `css/style.css`.
- Preserve all markup, content, JavaScript behavior, and responsive breakpoints.
- Use `#F7F2E5`, `#F97350`, `#FAD06C`, and `#B7AC9A` as the supplied palette.
- Use a near-black warm neutral for readable primary text.

---

### Task 1: Replace the dark visual system

**Files:**

- Modify: `css/style.css:11-85`
- Test: browser rendering of `index.html`

**Interfaces:**

- Consumes: Existing `body`, link, header, navigation, section, card, and footer selectors.
- Produces: A light warm color system with identical selector names and layout behavior.

- [ ] **Step 1: Add the CSS color system at the top of the stylesheet**

```css
:root {
  --coral: #f97350;
  --yellow: #fad06c;
  --cream: #f7f2e5;
  --taupe: #b7ac9a;
  --ink: #241e18;
  --surface: #fffdf8;
}
```

- [ ] **Step 2: Replace the existing dark colors with the defined system**

```css
body { background: var(--cream); color: var(--ink); }
a { color: var(--coral); }
a:hover { color: var(--ink); }
header { background: rgb(247 242 229 / 90%); border-bottom-color: var(--taupe); }
nav a { color: var(--ink); }
nav a:hover { color: var(--coral); }
.eyebrow, .intro, footer { color: #706657; }
section { border-bottom-color: var(--taupe); }
.project-card { background: var(--surface); border-color: var(--taupe); }
.project-card:hover { border-color: var(--coral); }
```

- [ ] **Step 3: Inspect the stylesheet for dark-theme hexadecimal values**

Run: `rg -n '#(0d1117|e6edf3|58a6ff|79c0ff|c9d1d9|30363d|21262d|161b22|8b949e)' css/style.css`

Expected: no output and exit status 1.

- [ ] **Step 4: Start a local static server and visually inspect the page**

Run: `python3 -m http.server 8000`

Open: `http://localhost:8000`

Expected: cream page background, readable dark primary text, coral links, taupe separators, and light project cards with coral hover borders.

- [ ] **Step 5: Verify the narrow-screen layout**

In a browser viewport at 700px wide or narrower, confirm navigation remains horizontally scrollable and project cards display in one column.

- [ ] **Step 6: Commit the stylesheet update**

```bash
git add css/style.css
git commit -m "Apply warm color palette"
```
