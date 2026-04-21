# El Post Pandémico — Website

A hand-built, magazine-style website for the monthly newsletter **El Post Pandémico**, hosted free on GitHub Pages. No command line needed — everything below is done in a browser.

---

## What's in this folder

```
website/
├── index.html                ← homepage: cover feature, editor's letter, article grid
├── style.css                 ← look & feel (fonts, colors, magazine layout)
├── articles/                 ← one HTML file per article
│   ├── nespoon.html
│   ├── rose-wylie.html
│   ├── dartagnan.html
│   ├── pelaez.html
│   └── ecos-del-tiempo.html
├── img/                      ← all photos used on the site (JPG)
│   ├── cover-earth-1.jpg ... cover-earth-3.jpg
│   ├── nespoon-hero.jpg, nespoon-1..6.jpg
│   ├── wylie-park-dogs.jpg, wylie-black-strap.jpg, ...
│   ├── dartagnan-church.jpg, dartagnan-statues.jpg, dartagnan-engraving.jpg
│   ├── pelaez-woodcut.jpg, pelaez-poster.jpg
│   └── ecos-painting.jpg
├── pdfs/
│   └── post-pandemico-229.pdf    ← archive copy of the original PDF (optional)
└── README.md                 ← this file
```

---

## Part 1 — Publish the site on GitHub Pages (one-time setup, ~10 min)

### Step 1. Create a GitHub account
1. Go to **https://github.com/signup**.
2. Use any email. Pick a username — it becomes part of the URL (e.g. `pelaez`).
3. Verify the email.

### Step 2. Create a new repository
1. Once logged in, click the **+** at the top-right → **New repository**.
2. **Repository name**: `post-pandemico` (lowercase, no spaces).
3. Set to **Public** (required for free GitHub Pages).
4. ✅ Check **"Add a README file"**.
5. Click **Create repository**.

### Step 3. Upload the site files
1. On the new repo page, click **Add file** → **Upload files**.
2. Open the `website` folder on your computer.
3. **Drag the *contents* of the `website` folder** (not the folder itself) into the browser: `index.html`, `style.css`, and the subfolders `articles`, `img`, `pdfs`.
   - GitHub preserves folder structure on drag-and-drop.
4. Scroll down, add a commit message like `Initial site`, click **Commit changes**.

### Step 4. Turn on GitHub Pages
1. In the repo, click **Settings** (top nav).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, select **Deploy from a branch**.
4. Under **Branch**, select **main** and folder **/ (root)**, then click **Save**.
5. Wait ~1–2 minutes. Refresh the Pages screen — a green box will show the live URL:
   ```
   https://<username>.github.io/post-pandemico/
   ```
6. That's it. Share this URL.

---

## Part 2 — Publish a new issue each month

Each month there's a new PDF with 3–5 articles. To put the issue on the site, do these three things from the repo page on github.com:

### A. Upload the images

Every article needs a hero image plus any inline photos. Rename them first on your computer using a simple, clear pattern like `nespoon-hero.jpg`, `wylie-1.jpg`, etc. — **lowercase, dashes, no accents, no spaces**.

1. In the repo, click into `img/` → **Add file** → **Upload files**.
2. Drag all the new images in.
3. Commit.

### B. Create one HTML page per article

The easiest way is to copy an existing article file and edit it:

1. In the repo, click into `articles/` → pick one of last month's files (say `nespoon.html`).
2. Click the pencil icon (**Edit this file**) → select all → copy.
3. Back in `articles/`, click **Add file** → **Create new file**.
4. Name it something short and URL-safe, like `new-article-slug.html`.
5. Paste the old article, then **replace**:
   - The page `<title>` and top `<h1>`
   - The `dek` (subtitle) and `byline`
   - The hero image filename + its alt text
   - The body paragraphs and any inline `<figure>` blocks
   - The `section` tag at top (e.g. "Arte", "Arqueología · Historia", etc.)
   - The issue number in the eyebrow (`Nº 229` → `Nº 230`)
6. Commit.

**Tip:** keep the outer structure (masthead, article-header, article-body, footer) exactly the same between articles. Only change the content inside.

### C. Rebuild the homepage for the new issue

Open `index.html` → pencil icon → edit, and change:

1. The **issue number and date** in the masthead eyebrow and the footer (`Nº 229 · Abril 2026` → `Nº 230 · Mayo 2026`).
2. The **cover feature** (`.cover-feature` section) — swap the images and change the headline/subhead to whatever the new issue's cover theme is.
3. The **editor's letter** (`.editor` section) — replace with the new month's text.
4. The **article grid** (`<ul class="articles">`) — one `<li class="article-card">` per article. For each one:
   - Change the `href` to the new article page
   - Change the `img` src + alt
   - Change the section, headline, dek, and byline
   - Pick a card size: `card-wide` (big, full width, for the lead article), `card-half` (medium, two per row), `card-third` (small, three per row)

Commit. The live site updates within ~1 minute.

### D. (Optional) Archive the PDF

If you want to keep a downloadable PDF version too:
1. Rename the new PDF to `post-pandemico-230.pdf` (lowercase, dashes, no accents).
2. Upload it to `pdfs/`.
3. Update the footer link in `index.html` to point to the new filename.

---

## Part 3 — Preview changes before committing

GitHub's edit screen has a **Preview** tab, but it only renders markdown, not HTML. To preview HTML changes before they go live:

- **Easiest:** open `index.html` or any `articles/xxx.html` by double-clicking it on your computer. It opens in your browser and looks just like the live site (fonts load from Google, so you need internet).

---

## Image tips

- **Format:** JPG. Keep file sizes under ~400 KB per image so the site stays fast.
- **Hero images** look best around **1600 × 900** pixels (landscape).
- **Inline figures** (right/left aligned in body text) work fine at **600–800 px** wide.
- **Cover feature circles** on the homepage are square/round and crop to circles — any roughly square image works.

---

## Optional — Custom domain

If you want a custom URL like `elpostpandemico.com`:
1. Buy the domain from any registrar (Namecheap, Porkbun, etc. — about $10–15/year).
2. In the repo → **Settings → Pages → Custom domain**, enter the domain.
3. At your registrar, add the DNS records GitHub shows you.
4. Check **Enforce HTTPS** once it's ready.

Full guide: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

---

## Troubleshooting

**An image is broken (shows the little "image missing" icon).**
The filename in the HTML must match the filename in `img/` *exactly*, including case. `nespoon-hero.jpg` is NOT the same file as `Nespoon-Hero.JPG`.

**A link goes to a 404.**
The article's `href` in `index.html` must exactly match the filename under `articles/`. Check for typos.

**Fonts look wrong.**
The site loads Playfair Display, EB Garamond, and Inter from Google Fonts. If you're offline, they fall back to generic serifs. That's fine — just keep going.

**The site shows 404 right after setup.**
GitHub Pages takes 1–3 minutes to build the first time. Refresh. If still broken after 5 minutes, check **Settings → Pages** shows the green "Your site is live" box.

**I messed up and want to revert.**
In the repo, click **Commits** (above the file list) → find a good version → click the `<>` icon → **Browse files** at that point. You can restore from there.

---

## Credits

Site design and setup by Claude (via Cowork). Issue 229 content by José A. Peláez and contributors.
