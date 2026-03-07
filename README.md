# saurabhtodi.in

Personal website for Saurabh Todi — Policy Analyst & Researcher.

## Deployment on GitHub Pages

1. Create a new repository on GitHub (e.g. `saurabhtodi.github.io` for user site, or any name for a project site).
2. Push all files in this folder to the `main` branch.
3. Go to **Settings → Pages** in your repository.
4. Under **Source**, select **Deploy from a branch** → `main` → `/ (root)` → **Save**.
5. Your site will be live at `https://<username>.github.io` within a few minutes.

### Custom Domain (saurabhtodi.in)

The `CNAME` file is already included and set to `saurabhtodi.in`. To connect it:

1. In your domain registrar's DNS settings, add these records:
   - **A records** (point to GitHub Pages IPs):
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - **CNAME record**: `www` → `<username>.github.io`
2. In GitHub repo **Settings → Pages → Custom domain**, enter `saurabhtodi.in` and save.
3. Check **Enforce HTTPS** once the DNS propagates (usually 24-48 hours).

## How to Update Content

### Adding a new opinion piece

Open `index.html` and find the `OPINION_PIECES` array near the top of the `<script>` tag. Add a new entry at the beginning:

```js
{ date: "Mar 2026", outlet: "Nature", title: "Your Article Title", url: "https://...", tier: "flagship" },
```

**Tier options:** `"flagship"` (top outlets — shows a dot marker), `"major"`, `"standard"`, `"featured"`.

### Adding a new research paper

Find the `RESEARCH` array and add an entry:

```js
{ date: "Mar 2026", publisher: "The Takshashila Institution", title: "Paper Title", url: "https://...", summary: "One-line summary." },
```

### Adding a new outlet icon

Find the `OUTLET_ICONS` object and add:

```js
"New Outlet Name": "their-domain.com",
```

The favicon is fetched automatically from Google's favicon service.

## File Structure

```
├── index.html     ← Entire site (single file, no build step)
├── CNAME          ← Custom domain config for GitHub Pages
├── .nojekyll      ← Tells GitHub Pages not to use Jekyll
└── README.md      ← This file
```

## Tech Stack

- **React 18** via CDN (no build tools required)
- **Babel Standalone** for in-browser JSX transpilation
- **Google Fonts** (Playfair Display, Source Sans 3, JetBrains Mono)
- **Google Favicon API** for publication icons

No `npm install`, no build step, no dependencies to manage. Just push and deploy.
