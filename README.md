# The Creative Leader

An interactive comic website hosted on GitHub Pages.

---

## How to Create the GitHub Repo & Deploy

### Step 1 — Create the repository

1. Go to [github.com](https://github.com) and sign in
2. Click the **+** icon (top right) → **New repository**
3. Name it something like `the-creative-leader`
4. Set it to **Public**
5. Leave everything else as default — do NOT tick "Add README"
6. Click **Create repository**

---

### Step 2 — Set up the folder structure on your computer

Create a folder on your computer with exactly this structure:

```
the-creative-leader/
├── index.html          ← rename index_v5.html to this
├── manifest.json
├── README.md
└── comics/
    ├── comics1.jpg
    ├── comics2.jpg     ← add more here as you create them
    └── ...
```

**Important:** The `comics/` folder must be inside the same folder as `index.html`.

---

### Step 3 — Upload to GitHub

**Option A — GitHub website (easiest):**

1. Open your new repo on github.com
2. Click **uploading an existing file** (or drag and drop)
3. Upload `index.html` and `manifest.json` first → click **Commit changes**
4. Click **Add file** → **Create new file**, type `comics/comics1.jpg` as the name
   — this creates the `comics/` folder automatically
5. Upload your comic JPEGs into the `comics/` folder one by one

**Option B — Git command line:**

```bash
cd the-creative-leader
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/the-creative-leader.git
git push -u origin main
```

---

### Step 4 — Enable GitHub Pages

1. Go to your repo on github.com
2. Click **Settings** (top tab)
3. In the left sidebar click **Pages**
4. Under **Source** select: **Deploy from a branch**
5. Under **Branch** select: **main** and **/ (root)**
6. Click **Save**
7. Wait ~60 seconds then visit:
   `https://YOUR_USERNAME.github.io/the-creative-leader/`

---

## How to Add New Comics

1. Create your comic as a JPEG (any name, e.g. `comics2.jpg`)
2. Upload it to the `comics/` folder in your GitHub repo
3. Open `manifest.json` and add the new entry:

```json
{
  "comics": [
    "comics/comics1.jpg",
    "comics/comics2.jpg",
    "comics/comics3.jpg"
  ]
}
```

4. Commit — the site updates automatically within seconds

---

## Comic Format Tips

- Each JPEG should be a **horizontal comic strip**
- Recommended dimensions: **1200×900px** or similar
- The comic displays at ~78% of the board area, centred
- Clicking the comic opens a fullscreen lightbox view
- On mobile: swipe left/right to navigate between comics

---

## Navigation

| Button | Action |
|--------|--------|
| ◀ yellow arrow | Previous comic |
| 💡 yellow bulb | Random comic |
| ▶ yellow arrow | Next comic |
| Swipe left | Next comic (mobile) |
| Swipe right | Previous comic (mobile) |
| Click comic | Expand fullscreen |
| Escape / click outside | Close fullscreen |

---

## Notes

- The site only works correctly when hosted (GitHub Pages or any web server)
- Opening `index.html` directly from your desktop will not load comics
  (browsers block `fetch()` on local files — this is expected)
- Always test by visiting your live GitHub Pages URL
