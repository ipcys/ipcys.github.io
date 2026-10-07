# Academic website — GitHub Pages

Three files, no build step: `index.html`, `styles.css`, `script.js`. This README covers hosting it for free on GitHub Pages and the main things to customize.

## 1. Host it on GitHub Pages

**Option A — personal/lab site at `yourusername.github.io`** (recommended if this is your main site)

1. Create a new repository on GitHub named exactly `yourusername.github.io` (replace with your actual GitHub username).
2. Upload `index.html`, `styles.css`, and `script.js` to the root of that repository (drag-and-drop on the GitHub web UI works, or use git — see below).
3. Go to the repo's **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
5. Wait 1–2 minutes, then visit `https://yourusername.github.io`.

**Option B — project site at `yourusername.github.io/lab-site`**

Same steps, but the repository can be named anything (e.g. `lab-site`), and the live URL will be `https://yourusername.github.io/lab-site`.

**Using git from the command line** (either option):

```bash
git init
git add index.html styles.css script.js
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

Then enable Pages as in step 3–4 above.

## 2. Use a university subdomain instead (optional)

Many departments will host a redirect or let you point a custom domain (e.g. `ferreira-lab.delacroix.edu`) at GitHub Pages:

1. Add a file named `CNAME` to the repo root containing just your domain, e.g. `ferreira-lab.delacroix.edu`.
2. Ask your department's IT to add a `CNAME` DNS record pointing that subdomain to `yourusername.github.io`.
3. In Settings → Pages, GitHub will confirm the custom domain automatically once DNS propagates.

## 3. About this version's content

This copy is customized for Sabrina C. Y. Ip's real, published research in computational rock mechanics (phase-field modeling of compaction bands, anisotropy in clay rocks, multiscale homogenization), sourced from her public Google Scholar/ResearchGate record, current postdoc position at UC Berkeley, and PhD work at Stanford under Ronaldo I. Borja.

**I could not verify a specific faculty appointment for her** — public records show her as a current postdoctoral scholar, with no confirmed institution or start date for a professorship. Anything that depends on that (the hero kicker, "Starting" field, office, program deadlines, funding availability, email address) is left as a bracketed placeholder like `[Confirm institution]` — search `index.html` for `[` to find every one and replace it with real, confirmed details before publishing. Publishing unverified claims about a real person's job title or institution could be misleading, so please don't leave these as-is.

## 4. What to customize before publishing

- **All placeholder content**: name, institution, dates, research descriptions, publication list, courses, and contact links currently describe a fictional example (Maya Ferreira / Delacroix University) — search the files for anything specific and replace it.
- **Photo**: the hero currently shows initials in a solid block instead of a real photo. Add an `<img>` tag with `src="photo.jpg"` in place of the `.hero-photo` div in `index.html`, and upload your photo alongside the other files.
- **Links**: the Google Scholar, GitHub, and CV links in the footer and publications section are placeholders (`href="#"`) — replace with real URLs, and add a real CV PDF to the repo if you link to one.
- **Favicon** (optional): add a `favicon.ico` to the root and link it in `<head>` with `<link rel="icon" href="favicon.ico">`.
- **Analytics** (optional): GitHub Pages doesn't include analytics by default. Plausible or GoAnalytics are privacy-respecting options if you want visit counts.

## 5. Local preview before publishing

From the folder containing the files:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` in a browser.

## Structure notes

- No frameworks or build tools — plain HTML/CSS/JS, so it will load fast and needs no maintenance.
- The layout is a single page with anchor-linked sections (`#research`, `#join`, `#publications`, `#teaching`, `#news`, `#contact`); the nav bar links to each.
- Responsive down to mobile, with a collapsible nav menu below 700px width.
- Respects `prefers-reduced-motion`.
