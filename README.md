# Patricio Beltran — Portfolio

CEO-level personal portfolio site built as a zero-dependency SPA (Single Page Application). Deployed to GitHub Pages.

**Live site:** `https://prbeltran.github.io/portfolio`

---

## Stack

| Layer | Technology |
|-------|-----------|
| Framework | None — pure HTML/CSS/JS |
| Fonts | Bebas Neue + Outfit + Space Mono (Google Fonts) |
| Hosting | GitHub Pages |
| Routing | Hash-based SPA (`#home`, `#projects`, etc.) |
| Data | JavaScript arrays in `index.html` |
| Build step | None required |

---

## Repo Structure

```
portfolio/
├── index.html            ← Full application
├── README.md             ← This file
├── assets/
│   └── images/
│       ├── gallery/      ← Drop gallery photos here
│       └── photo.jpg     ← Add your profile photo here
└── docs/
    ├── CHANGELOG.md      ← Change history
    ├── ROADMAP.md        ← Planned features
    ├── IDEAS.md          ← Idea backlog
    ├── ARCHITECTURE.md   ← Technical deep-dive
    └── CONTENT_GUIDE.md  ← How to update content
```

---

## Deploy to GitHub Pages

1. Create a repo named `portfolio` on GitHub (or any name)
2. Push this folder to the `main` branch
3. Go to **Settings → Pages → Source: Deploy from branch → Branch: main / (root)**
4. Enable **Discussions** under Settings → Features (for project discussion boards)
5. Site is live at `https://yourusername.github.io/portfolio`

```bash
git init
git add .
git commit -m "Launch: CEO-level portfolio"
git remote add origin https://github.com/prbeltran/portfolio.git
git push -u origin main
```

---

## Updating Content

See **[docs/CONTENT_GUIDE.md](docs/CONTENT_GUIDE.md)** for step-by-step instructions on:
- Adding new projects
- Adding blog posts
- Uploading gallery images
- Adding project media files
- Enabling GitHub Discussions

---

## Sections

| Section | Description |
|---------|-------------|
| Home | Particle constellation hero + stats |
| About | Bio, skills, affiliations, photo |
| Research | Featured GRX-810 card + 3 research areas |
| Projects | 17 projects with filter by category + modals |
| Experience | Animated vertical timeline (5 roles) |
| Blog | 3 technical posts with modal reader |
| Gallery | Image grid (add photos to assets/images/gallery/) |
| Contact | Contact form + links + GitHub Discussions |

---

## Local Development

No server needed. Open `index.html` directly in any browser.

For live reload during editing:
```bash
npx serve .
# or
python3 -m http.server 8080
```

---

Built with precision and purpose — El Paso, TX.
