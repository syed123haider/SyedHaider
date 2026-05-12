# Personal Website

A clean, editorial-style personal website built for a techno-economic analyst / technology commercialization expert. Built with vanilla HTML, CSS, and a small amount of JavaScript — no build step, no framework, no dependencies. Designed to host directly on GitHub Pages and grow with you over time.

---

## Table of Contents

1. [Folder Structure](#folder-structure)
2. [Quick Start — Hosting on GitHub Pages](#quick-start--hosting-on-github-pages)
3. [Customizing the Site](#customizing-the-site)
4. [Adding New Content](#adding-new-content)
5. [Connecting the Contact Form](#connecting-the-contact-form)
6. [Custom Domain (optional)](#custom-domain-optional)
7. [Design Notes](#design-notes)

---

## Folder Structure

```
website/
├── index.html                  ← Home page
├── about.html                  ← About page
├── insights.html               ← Insights listing (with category filter)
├── insights/
│   └── sample-post.html        ← Template for individual posts
├── frameworks.html             ← Frameworks overview
├── frameworks/
│   ├── technology-investment-readiness.html
│   ├── pilot-success.html
│   ├── deeptech-commercialization.html
│   └── techno-economic.html
├── white-papers.html           ← White papers list
├── resources.html              ← Resources page
├── contact.html                ← Contact page
│
├── css/
│   └── styles.css              ← All styling (single file)
├── js/
│   └── main.js                 ← Nav toggle, filter, form
│
├── assets/
│   ├── images/                 ← Profile photo, post images
│   └── papers/                 ← PDF downloads
│
├── .nojekyll                   ← Tells GitHub Pages: serve raw files
└── README.md                   ← This file
```

---

## Quick Start — Hosting on GitHub Pages

GitHub Pages serves static HTML for free from any public repository. Here's the fastest path from these files to a live site:

### 1. Create a GitHub repository

Go to [github.com/new](https://github.com/new). For the cleanest URL, name the repo:

```
yourusername.github.io
```

(Replace `yourusername` with your actual GitHub username.) Setting the repo name this way means your site will live at `https://yourusername.github.io` directly. Set the repository to **Public**.

### 2. Upload the files

You have two options:

**Option A — Web Upload (no command line needed):**
1. On the new repo page, click **"uploading an existing file"**.
2. Drag and drop every file and folder from this project into the upload area.
3. Scroll to the bottom, write a commit message like "Initial site", click **Commit changes**.

**Option B — Git (if you're comfortable with the command line):**
```bash
cd path/to/website
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. In your repo on GitHub, go to **Settings → Pages** (in the left sidebar).
2. Under **"Build and deployment"**, set **Source** to **"Deploy from a branch"**.
3. Set **Branch** to `main` and folder to `/ (root)`. Click **Save**.
4. Wait 1–2 minutes. Your site will be live at `https://yourusername.github.io`.

If you used a different repo name (not `yourusername.github.io`), your site URL will be `https://yourusername.github.io/your-repo-name/`.

### 4. Verify

Visit the URL. Click through every page to make sure nothing is broken. If you see a 404 or blank page:
- Check that `.nojekyll` is in the root (this file disables Jekyll processing, which can break paths).
- Wait another 2–3 minutes — GitHub Pages can take a moment to build.

---

## Customizing the Site

Before publishing, replace placeholder content. The site uses `Your Name` as a placeholder everywhere — search and replace this with your actual name.

### Step 1 — Global find and replace

In your text editor (VS Code, Sublime, Notepad++), do a project-wide find-and-replace:

| Find | Replace with |
|---|---|
| `Your Name` | Your actual name |
| `hello@yourdomain.com` | Your real email |
| `https://linkedin.com` | Your LinkedIn URL |
| `https://twitter.com` | Your X / Twitter URL |
| `https://scholar.google.com` | Your Google Scholar URL |
| `/in/yourname` | Your LinkedIn handle |
| `@yourhandle` | Your X / Twitter handle |
| `Your City · GMT+3` | Your city and timezone |
| `© 2025 Your Name` | Update year as needed |

### Step 2 — Update About page

Open `about.html` and replace the placeholder bio sections (anything marked with `[brackets]` or that says "Replace this with...") with your actual background, focus areas, education, and experience.

### Step 3 — Update home page hero

Open `index.html` and tune the hero headline and lead paragraph to your specific positioning. The current text is:

> Translating *deeptech* into deployable capital, infrastructure, and impact.

Make it yours.

### Step 4 — Add a profile photo (optional)

1. Save a photo as `assets/images/profile.jpg` (square, ~600×600px).
2. In `about.html`, add `<img src="assets/images/profile.jpg" alt="Your Name" style="border-radius: 50%; max-width: 220px; margin-bottom: 2rem;">` inside the `.about-sidebar` div, before the first `<h4>`.

### Step 5 — Update favicon (optional)

To add a browser tab icon: place a `favicon.ico` (or `favicon.png`) in the root, then add this line inside every page's `<head>`:
```html
<link rel="icon" href="favicon.ico" type="image/x-icon">
```

---

## Adding New Content

The site is designed so you can grow it by copying existing files and editing them. No build step, no framework — just HTML.

### Adding a new Insight post

1. **Copy the template:** Duplicate `insights/sample-post.html` and rename it to something descriptive — e.g., `insights/hydrogen-foak-economics.html`.
2. **Edit the new file:**
   - Update `<title>` and `<meta name="description">`.
   - Update the `post-meta` block (category, read time, date).
   - Update the `<h1>` and lead paragraph.
   - Write the article body inside `<article class="post-content">`.
3. **List it on the Insights page:** Open `insights.html` and copy one of the existing `<a class="insight-card">…</a>` blocks. Paste a new copy and update:
   - `href` to point to your new post
   - `data-category` to the matching category slug:
     - `technology-deep-dive`
     - `techno-economic-analysis`
     - `scaleup-commercialization`
     - `investment-strategy`
   - The `<span class="category">`, `<h3>`, description, and `<span class="meta">`.
4. **(Optional) Add to home page:** Open `index.html` and add the same card to the latest-insights grid (keeping it to the most recent 3).

### Adding a new Framework

1. Duplicate one of the framework files in `frameworks/` (e.g., `technology-investment-readiness.html`).
2. Rename and edit as above.
3. Open `frameworks.html` and copy one of the existing `<a class="framework-row">` blocks. Update the number, link, title, and description.

### Adding a new White Paper

1. Save the PDF to `assets/papers/your-paper-name.pdf`.
2. Open `white-papers.html` and copy one of the existing `<a class="paper-item">` blocks. Update date, title, description, and `href` to point to the PDF.

### Adding a new Resource

1. Open `resources.html`.
2. Find the appropriate `<div class="resource-group">` (Tools & Templates, Datasets, or Curated Reading).
3. Copy one of the existing `<a class="resource-card">` blocks. Update the type, title, description, and `href`.

### Adding a new section / page

If you want a whole new top-level page (e.g., "Speaking", "Press"):

1. Duplicate any existing page (e.g., `resources.html`) and rename it.
2. Edit the content.
3. Add the link to the `<ul class="nav-links">` in every page's nav, and to the footer links.

---

## Connecting the Contact Form

The contact form currently shows an alert when submitted — it does not actually email you. To make it functional, you have three easy options:

### Option 1 — Formspree (easiest, free tier available)

1. Sign up at [formspree.io](https://formspree.io).
2. Create a new form. Formspree gives you a URL like `https://formspree.io/f/xyzabc123`.
3. Open `contact.html`. Find the `<form>` tag and update it:
   ```html
   <form class="contact-form" id="contact-form"
         action="https://formspree.io/f/xyzabc123"
         method="POST">
   ```
4. Open `js/main.js`. Delete or comment out the contact form `addEventListener` block (the one that calls `alert(...)`). Formspree will handle submissions natively.

### Option 2 — Netlify Forms (free if you host on Netlify instead)

If you switch hosting from GitHub Pages to Netlify, just add `netlify` to the form tag:
```html
<form class="contact-form" id="contact-form" name="contact" method="POST" netlify>
```

### Option 3 — Plain mailto:

Replace the form with a styled mailto link if you'd rather skip the form entirely. The direct email is already displayed in the left column of the Contact page.

---

## Custom Domain (optional)

If you own a domain (e.g., `yourname.com`) and want to use it instead of `yourusername.github.io`:

1. In your domain registrar (GoDaddy, Namecheap, etc.), add these DNS records:
   - `A` record `@` → `185.199.108.153`
   - `A` record `@` → `185.199.109.153`
   - `A` record `@` → `185.199.110.153`
   - `A` record `@` → `185.199.111.153`
   - `CNAME` record `www` → `yourusername.github.io`
2. Create a file in the repo root called `CNAME` (no extension) containing just your domain on one line:
   ```
   yourname.com
   ```
3. In GitHub: Settings → Pages → Custom domain → enter your domain → Save → check "Enforce HTTPS".
4. Wait up to an hour for DNS to propagate.

---

## Design Notes

If you want to tweak the aesthetic:

- **Colors:** All colors are CSS variables at the top of `css/styles.css`. Change `--paper` (background), `--ink` (text), and `--accent` (the rust/terracotta accent) to retheme the whole site instantly.
- **Fonts:** Loaded from Google Fonts in each HTML head. Current pairing is Fraunces (display serif) + DM Sans (body sans) + JetBrains Mono (mono accents). Change the Google Fonts URL and the `--font-display`, `--font-body`, `--font-mono` variables to swap.
- **Spacing:** Spacing scale is also in CSS variables. Adjust `--space-*` tokens for tighter or looser layout.
- **Animations:** Subtle fade-up reveals on scroll. Disable by removing the `.reveal` class from elements, or by deleting the IntersectionObserver block in `js/main.js`.

---

## Tips for Growing the Site

- **Write in markdown first, convert later.** Drafting posts in markdown and pasting in the HTML is faster than writing raw HTML.
- **Keep insights short and frequent at first.** A 600–1000 word post on a specific question publishes faster than a 3,000-word essay you never finish.
- **Repurpose advisory work.** Every diligence memo, TEA review, or strategy document you write for clients is the seed of a 70%-anonymized public post. The act of generalizing usually improves the underlying thinking.
- **Date-stamp everything.** Readers and search engines both reward freshness. Update the "Latest" sections regularly.
- **Backup before you experiment.** Before any major change, commit and push (or download a zip from GitHub). Reverting is easy if you have the previous state.

---

## Questions / Issues

If something breaks or you want to extend the site in a direction not covered here, the structure is simple enough that any LLM (Claude, ChatGPT, Cursor) can help you modify it — just paste the relevant HTML or CSS and describe what you want to change.

Built to last. Built to grow. Have at it.
