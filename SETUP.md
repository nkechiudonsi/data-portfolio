# How to Put This on GitHub

Follow these steps to publish your portfolio as a real GitHub repository with a live website.

---

## Step 1: Create a GitHub Account

If you don't have one:
1. Go to [github.com](https://github.com)
2. Click **Sign up**
3. Use `nkechi-udonsi` as your username (or similar)
4. Confirm your email

---

## Step 2: Create the Profile Repository

This is special — a repository with the same name as your username becomes your GitHub profile.

1. Click the **+** icon (top right) → **New repository**
2. Set **Repository name** to your exact username (e.g. `nkechi-udonsi`)
3. Tick **Public**
4. Tick **Add a README file**
5. Click **Create repository**
6. Replace the default README with the content from `README.md` in this folder

---

## Step 3: Create the Portfolio Repository

1. Click **+** → **New repository**
2. Name it: `data-portfolio` (or `nkechi-data-portfolio`)
3. Make it **Public**
4. **Do not** tick "Add a README" (you'll add the files yourself)
5. Click **Create repository**

---

## Step 4: Upload All Files

**Option A — GitHub web interface (no coding needed):**
1. Open your new repository on GitHub
2. Click **Add file** → **Upload files**
3. Drag and drop all the folders and files from this portfolio folder
4. Scroll down, write "Add portfolio files" in the commit message box
5. Click **Commit changes**

**Option B — Git command line:**
```bash
cd nkechi-portfolio
git init
git add .
git commit -m "Initial portfolio commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/data-portfolio.git
git push -u origin main
```

---

## Step 5: Enable GitHub Pages (Live Website)

This turns your `docs/index.html` into a real website at `https://YOUR-USERNAME.github.io/data-portfolio/`

1. Go to your repository on GitHub
2. Click **Settings** (top tab)
3. Scroll down to **Pages** (left menu)
4. Under **Source**, select **Deploy from a branch**
5. Set **Branch** to `main` and **Folder** to `/docs`
6. Click **Save**
7. Wait 1–2 minutes, then visit: `https://YOUR-USERNAME.github.io/data-portfolio/`

---

## Step 6: Add Your LinkedIn URL

Update the LinkedIn badge in `README.md` — replace the example URL with your real one:
```
https://www.linkedin.com/in/nkechi-udonsi-442b08231
```

---

## Step 7: Pin Repositories to Your Profile

1. Go to your GitHub profile page
2. Click **Customize your pins**
3. Select your portfolio repositories to feature them prominently

---

## Step 8: Add Your GitHub Link to LinkedIn

1. Go to your LinkedIn profile
2. Click **Edit** on your intro section
3. Add your GitHub URL: `https://github.com/YOUR-USERNAME`

---

## What the Repository Will Look Like

```
data-portfolio/
├── README.md                          ← Main portfolio page (shows on GitHub)
├── SETUP.md                           ← This file
├── docs/
│   └── index.html                     ← Live website (GitHub Pages)
├── data-analytics/
│   ├── sales-analysis/README.md
│   ├── me-dashboard/README.md
│   └── data-quality/README.md
├── ai-language-ops/
│   ├── annotation-study/README.md
│   ├── ai-eval-toolkit/README.md
│   └── metadata-analysis/README.md
└── technical-writing/
    ├── docs-portfolio/README.md
    └── data-docs/README.md
```

---

## Next Steps (Optional but Recommended)

| Action | Why |
|---|---|
| Add a Jupyter notebook to `data-quality/` | Shows real Python/data work |
| Add a `.csv` sample dataset | Gives employers something concrete to look at |
| Add a PDF writing sample to `technical-writing/` | Proves writing quality |
| Add your Upwork profile link | Links to verified client reviews |
| Upload a dashboard screenshot | Visual proof of Power BI / Tableau skills |

---

**Questions?** Feel free to reach out: nkechiudonsi77@gmail.com
