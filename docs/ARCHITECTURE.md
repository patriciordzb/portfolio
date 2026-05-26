# Architecture

Technical documentation for the portfolio site.

---

## Overview

Single-file SPA (Single Page Application) with zero build step. Pure HTML + CSS + JavaScript.

```
portfolio/
├── index.html          ← Entire application (HTML + CSS + JS in one file)
├── README.md           ← Deployment guide and quick start
├── assets/
│   └── images/
│       ├── gallery/    ← Drop gallery photos here
│       └── photo.jpg   ← Profile photo (add manually)
└── docs/
    ├── ARCHITECTURE.md ← This file
    ├── CHANGELOG.md    ← Change history
    ├── IDEAS.md        ← Future ideas backlog
    ├── ROADMAP.md      ← Planned features
    └── CONTENT_GUIDE.md← How to update content
```

---

## Routing

Hash-based SPA routing. No server required — works on GitHub Pages.

```javascript
// Navigate to a section
go('projects')  // sets #projects in URL, shows that .page-section

// URL format
https://prbeltran.github.io/portfolio/#research
https://prbeltran.github.io/portfolio/#projects
```

Pages: `home` | `about` | `research` | `projects` | `experience` | `blog` | `gallery` | `contact`

---

## Data Model

All content lives in JS arrays at the bottom of `index.html`.

### Project Object
```javascript
{
  id:     'grx810',           // unique identifier (kebab-case)
  cat:    'research',         // 'research' | 'engineering' | 'software' | 'leadership'
  icon:   '🔬',              // emoji icon for card
  year:   '2024 – Present',  // display year string
  status: 'Active',           // 'Active' | 'Completed' | 'Published' | 'Proposed' | 'Delivered'
  inst:   'W.M. Keck Center / NASA',
  title:  'GRX-810 ODS Superalloy — NASA',
  desc:   'Short 1–2 line description for card view',
  full:   `Multi-paragraph full description for modal...`,
  tags:   ['L-PBF', 'NASA', 'EBSD'],  // shown in modal and on card
}
```

### Experience Object
```javascript
{
  date: '2024 – Present',
  role: 'Role Title',
  org:  'Organization Name',
  pts:  ['Bullet 1', 'Bullet 2', ...]
}
```

### Blog Object
```javascript
{
  id:      'b1',
  date:    'May 2025',
  title:   'Post Title',
  excerpt: 'Preview text shown on card',
  content: `Full post text with \n for paragraphs`
}
```

---

## Design System

### CSS Variables
```css
--bg:        #07070E    /* page background */
--surface:   #0F0F1E    /* card / modal background */
--surface2:  #161628    /* elevated surface */
--surface3:  #1E1E35    /* highest surface */
--border:    #1A1A30    /* subtle border */
--border2:   #252545    /* visible border */
--gold:      #D4A843    /* primary accent */
--gold-dim:  #7A5F20    /* muted gold for borders */
--gold-glow: rgba(212,168,67,.14)  /* gold ambient glow */
--sky:       #38C4F0    /* secondary accent (links, org names) */
--text:      #EDE9F4    /* primary text */
--text2:     #A0A0C0    /* secondary text */
--muted:     #4A4A70    /* labels, placeholders */
--green:     #22D3A4    /* success / active status */
```

### Fonts
- `Bebas Neue` — display headings, hero name, section titles
- `Outfit` — body text, descriptions, UI
- `Space Mono` — nav links, labels, technical metadata, monospaced code

### Animation System
- `.reveal` class + IntersectionObserver for scroll-triggered fade-up
- `@keyframes fadeUp` for hero elements (staggered with animation-delay)
- `@keyframes shimmerScan` for the research featured card top bar
- `@keyframes shimmerBar` for modal top gradient
- Canvas requestAnimationFrame loop for hero particle system

---

## Hero Canvas

Particle constellation system. Interactive — particles react to mouse proximity.

```javascript
// Tunable parameters
const n    = Math.min(Math.floor(W * H / 9500), 120) // particle count
const dist = 140  // connection distance (px)
const spd  = 0.3  // max particle speed
const mouseRadius = 100  // mouse interaction radius
```

---

## Deployment

GitHub Pages — push `main` branch, enable Pages in repo settings (root `/` directory).

No build step. No Node. No dependencies. Works offline.
