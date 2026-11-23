# LexFolio — thelexfolio.in

Static one-page website for LexFolio. No build step, no framework: Vercel serves these files exactly as they are.

**Preview anywhere:** `index.html` is fully self-contained — styles, script, textures and the founder photo are built into the file. Open it on its own (double-click on a laptop, or send just that file to a phone and open it) and it renders exactly like the live site. Fonts need an internet connection.

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole landing page: copy, styles, responsive layout, mobile menu, parallax, founder photo |
| `assets/og-image.jpg` | Preview image shown when the link is shared on WhatsApp, LinkedIn etc. |
| `favicon.svg`, `favicon.ico`, `apple-touch-icon.png` | Browser tab and home-screen icons |
| `404.html` | Page shown for a wrong URL |
| `robots.txt`, `sitemap.xml` | Help Google find and index the site |
| `vercel.json` | Clean URLs, caching and security headers |

Push **every file and the `assets` folder**, keeping this exact structure at the root of the repository (`index.html` must sit at the top level, not inside a sub-folder).

## 1. Put the files on GitHub

**Easiest (browser):** open your repository on github.com → **Add file → Upload files** → drag in everything from this folder, including the `assets` folder → **Commit changes**.

**Or with git:**

```bash
cd lexfolio-site
git init
git add .
git commit -m "LexFolio website"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

## 2. Deploy on Vercel

1. vercel.com → **Add New… → Project** → import the GitHub repository.
2. **Framework Preset:** `Other`. Leave **Build Command** and **Output Directory** empty, and **Root Directory** as `./`.
3. Click **Deploy**. You'll get a `*.vercel.app` link to check the site.

Every later `git push` (or GitHub upload) to `main` redeploys automatically.

## 3. Connect thelexfolio.in

1. In the Vercel project: **Settings → Domains** → add `thelexfolio.in`, then add `www.thelexfolio.in` and set it to **redirect** to `thelexfolio.in`.
2. At the company where you bought the domain, open **DNS settings** and add exactly the records Vercel shows on each domain card. Typically:

| Type | Name / Host | Value |
|---|---|---|
| `A` | `@` | `76.76.21.21` (or the value on your Vercel domain card) |
| `CNAME` | `www` | the target shown on the Vercel domain card |

3. Delete any old `A`, `AAAA` or `CNAME` records on `@` and `www` that point elsewhere (registrars often add a parking page by default). Leave `MX`/`TXT` email records alone.
4. Wait for DNS to update (usually minutes, up to 24–48 hours). Vercel issues the HTTPS certificate automatically once the domain card turns green.

## Editing later

- **WhatsApp number:** search `wa.me/919582911540` in `index.html` (it appears on every chat button).
- **Founder photo:** it is embedded inside `index.html`; send a new 4:5 portrait to have the file regenerated.
- **Text:** edit directly in `index.html`; English and Hindi lines sit next to each other.

## Compliance lines (keep on the site)

The footer carries the AMFI distributor registration (ARN-113045), the standard mutual fund risk disclaimer and the commission disclosure. Keep them if the page is edited.
