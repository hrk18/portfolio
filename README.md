# Hrithik Kumar Chorwar — Cybersecurity Portfolio

A hardened, single-page portfolio website with a pentester/terminal aesthetic. Built as a dependency-free static site (one `index.html`) so it deploys anywhere for free.

**Live:** `https://hrk18.github.io` (after deploy)

## Features

- Terminal/hacker themed dark UI with matrix rain, typing effect, and scroll reveals
- Fully responsive (mobile menu, fluid type)
- Sections: About, Skills, Experience, Projects, Certifications, Education, Contact
- Downloadable CV (`Hrithik_Chorwar_CV.pdf`)
- **Security hardened** (fitting for a security professional):
  - Content-Security-Policy via meta tag (no external scripts/trackers)
  - `X-Content-Type-Options: nosniff`, strict referrer policy
  - `frame-ancestors 'none'` (clickjacking protection)
  - Email/phone obfuscated and assembled at runtime (anti-scraping)
  - `/.well-known/security.txt` for responsible disclosure
  - All external links use `rel="noopener noreferrer"`
  - `prefers-reduced-motion` respected

## Files

```
index.html                       # the whole site (HTML + CSS + JS inline)
Hrithik_Chorwar_CV.pdf           # downloadable CV
robots.txt, sitemap.xml          # SEO
.nojekyll                        # tells Pages to serve files as-is
.well-known/security.txt         # security contact
.github/workflows/deploy.yml     # auto-deploy to GitHub Pages on push
```

## Deploy to GitHub Pages (free)

### Option A — automatic (recommended)
1. Create a repo named **`hrk18.github.io`** on GitHub (a user-site repo).
2. Push these files to the `main` branch (see commands below).
3. In the repo: **Settings → Pages → Build and deployment → Source = GitHub Actions**.
4. Done. Every push auto-deploys to `https://hrk18.github.io`.

### Option B — classic branch deploy
1. Create any repo (e.g. `portfolio`), push files to `main`.
2. **Settings → Pages → Source = Deploy from a branch → `main` / root**.
3. Site appears at `https://hrk18.github.io/portfolio`.

### Push commands
```bash
cd MyPortfolio
git init
git add .
git commit -m "feat: cybersecurity portfolio site"
git branch -M main
git remote add origin https://github.com/hrk18/hrk18.github.io.git
git push -u origin main
```

## Custom domain (optional, still free)
Add a file named `CNAME` containing your domain (e.g. `hrithik.dev`), then point a CNAME DNS record at `hrk18.github.io`. Update the URLs in `sitemap.xml`, `robots.txt`, and `security.txt`.

## Local preview
```bash
python3 -m http.server 8000   # then open http://localhost:8000
```
