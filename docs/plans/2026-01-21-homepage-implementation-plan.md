# Academic Homepage Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Build a single-screen bilingual academic homepage with a centered profile card.

**Architecture:** Static HTML with a single card layout and external CSS for typography, layout, and motion. No JavaScript; visual emphasis handled via CSS variables and animations.

**Tech Stack:** HTML, CSS (Google Fonts).

### Task 1: Create base HTML structure

**Files:**
- Create: `index.html`

**Step 1: Write the HTML skeleton**

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Mingjian Zhang | Research</title>
    <meta name="description" content="Mingjian Zhang - M.S. Student in Artificial Intelligence at BUPT. Research interests in AI, NLP, and LLM." />
    <link rel="stylesheet" href="styles.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@500;600&family=Work+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  </head>
  <body>
    <main class="page">
      <section class="card" aria-label="Profile">
        <header class="name-block">
          <h1 class="name-cn">[CN name]</h1>
          <p class="name-en">Mingjian Zhang</p>
        </header>
        <p class="title-cn">[CN title and affiliation]</p>
        <p class="title-en">M.S. Student in Artificial Intelligence, BUPT</p>
        <p class="keywords">Artificial Intelligence · NLP · LLM</p>
        <address class="contact">
          <a href="mailto:zhangmingjian2024@bupt.edu.cn">zhangmingjian2024@bupt.edu.cn</a>
        </address>
      </section>
    </main>
  </body>
</html>
```

**Step 2: Manual check**
Open `index.html` in a browser and confirm the card content renders with all lines present.

**Step 3: Commit**

```bash
git add index.html
git commit -m "Add homepage HTML structure"
```

### Task 2: Add global styles and card layout

**Files:**
- Create: `styles.css`

**Step 1: Define CSS variables and base layout**

```css
:root {
  --bg-1: #f6f1e7;
  --bg-2: #efe7d7;
  --ink: #1b1a16;
  --muted: #4a463d;
  --card: #fbf9f3;
  --border: #dfd7c6;
  --shadow: 0 18px 40px rgba(27, 26, 22, 0.12);
  --radius: 12px;
  --space-1: 10px;
  --space-2: 16px;
  --space-3: 28px;
  --space-4: 40px;
  --serif: "Cormorant Garamond", "Times New Roman", serif;
  --sans: "Work Sans", "Helvetica Neue", Arial, sans-serif;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  display: grid;
  place-items: center;
  padding: 32px 18px;
  color: var(--ink);
  background: radial-gradient(1200px 600px at 20% 10%, #fff7ea, transparent),
    linear-gradient(150deg, var(--bg-1), var(--bg-2));
  font-family: var(--sans);
}
```

**Step 2: Style the card and typography**

```css
.page {
  width: min(680px, 100%);
}

.card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: var(--space-4);
  box-shadow: var(--shadow);
  display: grid;
  gap: var(--space-2);
  animation: rise 700ms ease-out both;
}

.name-block {
  display: grid;
  gap: var(--space-1);
}

.name-cn {
  font-family: var(--serif);
  font-size: clamp(32px, 5vw, 46px);
  margin: 0;
  letter-spacing: 0.5px;
}

.name-en {
  font-size: 16px;
  margin: 0;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 0.16em;
}

.title-cn,
.title-en {
  margin: 0;
  font-size: 17px;
}

.title-en {
  color: var(--muted);
}

.keywords {
  margin: 0;
  font-size: 15px;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: var(--muted);
}

.contact {
  margin: 0;
  font-style: normal;
}

.contact a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1px solid var(--muted);
  padding-bottom: 2px;
}

.contact a:focus-visible {
  outline: 2px solid #2f4a7d;
  outline-offset: 4px;
}

@keyframes rise {
  from {
    opacity: 0;
    transform: translateY(16px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

**Step 3: Manual check**
Reload `index.html` and confirm the layout centers, text is legible on desktop and mobile widths, and the email link is visible with focus outline.

**Step 4: Commit**

```bash
git add styles.css
git commit -m "Add homepage styles"
```

### Task 3: Replace placeholders with final CN content

**Files:**
- Modify: `index.html`

**Step 1: Fill in Chinese name and title**
Replace `[CN name]` and `[CN title and affiliation]` with the provided values.

**Step 2: Manual check**
Reload `index.html` and verify bilingual layout alignment and spacing.

**Step 3: Commit**

```bash
git add index.html
git commit -m "Fill in bilingual profile content"
```

### Task 4: Verification

**Files:**
- None

**Step 1: Manual verification**
Open `index.html` at desktop and mobile widths and confirm:
- Card fits in viewport without overflow
- Fonts load and hierarchy feels correct
- Email link works (mailto)

**Step 2: Record status**
Note that there are no automated tests for this static page.
