# JoudPortfolio

Creative portfolio — AI filmmaking, 3D animation, character design and web.

---

## First-time setup (do this once)

### Step 1 — Install Node.js
Download from https://nodejs.org → click "LTS" → install it.
Open a terminal and check it worked:
```
node --version
```
You should see something like `v20.x.x`

---

### Step 2 — Clone your repo to your computer
```bash
git clone https://github.com/Juciferr/JoudPorfolio.git
cd JoudPorfolio
```

---

### Step 3 — Copy all the portfolio files in
Copy everything from the downloaded folder into your cloned repo folder.
Your folder should look like this:
```
JoudPorfolio/
├── src/
├── public/
├── .github/
├── package.json
├── astro.config.mjs
└── README.md
```

---

### Step 4 — Install dependencies
```bash
npm install
```

---

### Step 5 — Run the site locally to preview
```bash
npm run dev
```
Open http://localhost:4321 in your browser. You'll see your portfolio live.
Press Ctrl+C to stop.

---

### Step 6 — Enable GitHub Pages (one-time)
1. Go to https://github.com/Juciferr/JoudPorfolio/settings/pages
2. Under "Build and deployment" → Source → select **GitHub Actions**
3. Click Save

---

### Step 7 — Push everything live
```bash
git add .
git commit -m "Launch portfolio"
git push
```
Wait ~2 minutes. Your site is live at:
**https://juciferr.github.io/JoudPorfolio**

---

## Adding a new project (every time)

### Step 1 — Add your image
Drop the image into: `public/images/projects/your-project-name.webp`
(JPG is fine too — the GitHub Action will convert it automatically)

### Step 2 — Add the project data
Open `src/content/projects.json` and add a new entry:
```json
{
  "id": "your-project-name",
  "title": "Your Project Title",
  "category": "AI Film",
  "year": "2025",
  "description": "One or two sentences describing what this is.",
  "tags": ["Tool 1", "Tool 2"],
  "thumbnail": "/JoudPorfolio/images/projects/your-project-name.webp",
  "featured": true
}
```

### Step 3 — Push
```bash
git add .
git commit -m "Add project: Your Project Title"
git push
```
Done. Live in ~2 minutes.

---

## Updating your info

| What to change | Where to change it |
|---|---|
| Your name, bio, skills | `src/pages/about.astro` |
| Projects | `src/content/projects.json` |
| Your email | `src/pages/contact.astro` and `src/components/Footer.astro` |
| Social links | `src/components/Footer.astro` |
| Site URL | `astro.config.mjs` |

---

## What the automations do (happens automatically)

| Automation | When it runs | What it does |
|---|---|---|
| **Deploy** | Every push to main | Builds and publishes your site |
| **Image optimizer** | When you push images | Converts JPG/PNG to WebP, compresses |
| **Lighthouse** | On pull requests | Scores your site, comments results |

---

## Asset format guide

| Type | Format | Size |
|---|---|---|
| Project thumbnails | WebP or JPG | 1280×720 or 800×600 |
| Hero / portrait photo | WebP or JPG | Min 1200px wide |
| Logo / icons | SVG | N/A |
| Video showreel | MP4 H.264 | Under 30MB, 1080p |
| CV | PDF | Under 5MB |

**Free image converter:** https://squoosh.app — drag, convert to WebP, download.

---

## Folder structure

```
JoudPorfolio/
├── public/
│   ├── images/
│   │   ├── projects/     ← drop project thumbnails here
│   │   └── hero/         ← portrait photo goes here as portrait.webp
│   ├── favicon.svg
│   └── cv.pdf            ← optional: your CV
├── src/
│   ├── components/       ← Nav, Footer, ProjectCard
│   ├── content/
│   │   └── projects.json ← ALL project data lives here
│   ├── layouts/
│   │   └── BaseLayout.astro
│   └── pages/
│       ├── index.astro   ← homepage
│       ├── about.astro
│       ├── contact.astro
│       └── work/
│           └── index.astro
└── .github/
    └── workflows/        ← automations (don't touch these)
```

---

## Troubleshooting

**"npm: command not found"**
→ Node.js isn't installed. Go to nodejs.org and install it.

**"git: command not found"**
→ Git isn't installed. Go to git-scm.com and install it.

**Site shows 404**
→ Check Settings → Pages → Source is set to "GitHub Actions"

**Images not showing**
→ Check filenames match exactly (lowercase, hyphens, correct extension)

**Changes not appearing**
→ Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
