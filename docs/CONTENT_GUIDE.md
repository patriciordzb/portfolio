# Content Guide

How to update the portfolio without breaking anything.

---

## Adding a New Project

Open `index.html` and find the `const PROJECTS = [` array. Add a new object following this template:

```javascript
{ id:'your-id',          // unique kebab-case ID — no spaces
  cat:'research',        // 'research' | 'engineering' | 'software' | 'leadership'
  icon:'⚗️',             // pick an emoji that fits
  year:'2025',
  status:'Active',       // 'Active' | 'Completed' | 'Published' | 'Proposed' | 'Delivered'
  inst:'Institution Name',
  title:'Project Title — Organization',
  desc:'Short description for the card. One or two sentences max.',
  full:`Full description for the modal. Use line breaks for paragraphs.
  
  Can be multiple paragraphs. Will render as preformatted text in the modal.`,
  tags:['Tag1', 'Tag2', 'Tag3', 'Tag4', 'Tag5'],  // up to ~6 look best
},
```

---

## Adding a Blog Post

Find `const BLOG = [` in `index.html`. Add a new object:

```javascript
{ id:'b4',              // must be unique — increment from last entry
  date:'June 2025',
  title:'Your Post Title',
  excerpt:'Preview text shown on the blog card. Should hook the reader in 2–3 sentences.',
  content:`Full post text here.

Use a blank line between paragraphs — each non-empty line becomes a <p> tag.

Write as much as you want. The modal scrolls.`
},
```

---

## Updating Experience

Find `const EXPERIENCE = [` and add or edit entries:

```javascript
{ date:'2025 – Present',
  role:'Your Role Title',
  org:'Organization Name',
  pts:[
    'Accomplishment or responsibility — be specific and metric-driven',
    'Another bullet point',
  ]
},
```

---

## Adding Gallery Images

1. Drop your images into `assets/images/gallery/`
2. Open `index.html` and find the `<div class="gallery-placeholder">` section
3. Replace the `.gp-item` placeholder divs with:

```html
<img src="assets/images/gallery/your-photo.jpg" 
     alt="Caption describing the photo" 
     class="gallery-img" 
     style="width:100%;height:100%;object-fit:cover;border-radius:8px">
```

Recommended: 4 images per row on desktop (already set in CSS grid)

---

## Adding Your Profile Photo

1. Save your photo as `assets/images/photo.jpg`
2. Open `index.html`, find the `<div class="about-photo">` block
3. Replace the entire block with:

```html
<div class="about-photo" style="padding:0;overflow:hidden">
  <img src="assets/images/photo.jpg" 
       alt="Patricio Beltran" 
       style="width:100%;height:100%;object-fit:cover">
</div>
```

---

## Adding Media to Project Modals

In the PROJECTS array, add a `media` property:

```javascript
media: [
  { type:'link', label:'America Makes Dataset', url:'https://...' },
  { type:'video', label:'DED How-To Guide', url:'https://youtube.com/...' },
  { type:'pdf', label:'Download Report', url:'assets/projects/grx810/report.pdf' },
]
```

Then update the `openProject()` function in the script to render `p.media` in the `#m-media` div.

---

## Enabling GitHub Discussions

1. Go to your portfolio repo on GitHub
2. Settings → Features → check "Discussions"
3. The discussion links in each project modal and contact page will now work automatically

---

## Deploying Changes

```bash
git add .
git commit -m "Update: [what you changed]"
git push origin main
```

GitHub Pages deploys automatically within ~60 seconds.
