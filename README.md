# PinkPantheres Blog — How to Use

## File Structure

```
pinkpantheres/
├── index.html              ← Homepage (never edit this much)
├── resume.html             ← Resume page
├── assets/
│   ├── cat.png             ← Your logo
│   └── hridhyap_resume.pdf ← Your resume PDF
├── posts/
│   ├── manifest.json       ← THE FILE YOU EDIT TO ADD POSTS ← 
│   ├── android-malware-sdk/
│   │   └── index.html
│   ├── phishing-attribution/
│   │   └── index.html
│   └── memory-ransomware/
│       └── index.html
└── README.md
```

---

## Adding a New Blog Post (3 steps)

### Step 1 — Create a folder
Create a new folder inside `posts/` with a slug (no spaces, use hyphens):

```
posts/my-new-ctf-writeup/
```

### Step 2 — Copy the template
Copy any existing post's `index.html` into your new folder. Then edit:
- The `<title>` tag
- The `<meta name="description">` tag
- The `.post-meta` section (type, date, readtime)
- The `<h1 class="post-title">` 
- The `<p class="post-desc">`
- The `.post-tags` section
- All content inside `<article class="post-body">` — this is your post!

### Step 3 — Add it to manifest.json
Open `posts/manifest.json` and add an entry:

```json
{
  "slug": "my-new-ctf-writeup",
  "title": "My New CTF Writeup",
  "excerpt": "A short description shown on the homepage card.",
  "type": "ctf",
  "date": "2025-06-01",
  "readTime": "5 min read",
  "tags": ["ctf", "forensics", "stego"]
}
```

That's it. The homepage will show the new card automatically.

---

## Post Types & Colors

| type        | color  |
|-------------|--------|
| `forensics` | pink   |
| `ctf`       | cyan   |
| `osint`     | purple |
| `malware`   | orange |

---

## Adding Images to a Post

Put your images inside the post folder:
```
posts/my-new-post/
├── index.html
├── screenshot1.png
└── memory-dump.png
```

Then in your post HTML:
```html
<img src="screenshot1.png" alt="Description of image">
<p class="img-caption">Fig 1. What this shows</p>
```

---

## Callout Boxes (tip/warning/flag)

```html
<!-- Info / tip -->
<div class="callout">
  <div class="callout-label">// Note</div>
  <p>Some important note here.</p>
</div>

<!-- Warning -->
<div class="callout warn">
  <div class="callout-label">// Warning</div>
  <p>Something to watch out for.</p>
</div>

<!-- IOC / finding highlight -->
<div class="callout flag">
  <div class="callout-label">// IOC</div>
  <p>C2: <code>evil-domain.com</code></p>
</div>
```

---

## Deploying to GitHub Pages

1. Create a new repo: `github.com/pinkpantheres/pinkpantheres.github.io`
2. Push everything in this folder to the `main` branch
3. Go to repo Settings → Pages → Source: `main` / `/ (root)`
4. Your site is live at `https://pinkpantheres.github.io`

> **Important:** GitHub Pages serves static files. The manifest.json approach works perfectly — no server needed.

---

## Updating the Resume

Replace `assets/hridhyap_resume.pdf` with a new file of the same name. Done.
