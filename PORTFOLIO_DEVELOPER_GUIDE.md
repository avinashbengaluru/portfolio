# 🚀 Portfolio & Presentation Deck — Developer & Setup Guide

This guide contains everything you need to open, modify, authenticate, and deploy your portfolio website and presentation deck in another app (such as VS Code, Cursor, WebStorm, or on another machine).

---

## 📌 1. Live URLs & Repositories

| Property | URL |
| :--- | :--- |
| **Live Portfolio Page** | [https://avinashbengaluru.github.io/portfolio/portfolio.html](https://avinashbengaluru.github.io/portfolio/portfolio.html) |
| **Live 14-Slide Deck (Mobile)** | [https://avinashbengaluru.github.io/portfolio/mobile.html](https://avinashbengaluru.github.io/portfolio/mobile.html) |
| **Live Vercel Deck** | [https://billbuddy-deck.vercel.app](https://billbuddy-deck.vercel.app) |
| **Standalone Portfolio Repo** | [https://github.com/avinashbengaluru/portfolio](https://github.com/avinashbengaluru/portfolio) |
| **Case Studies Repo** | [https://github.com/avinashbengaluru/ai-product-case-studies](https://github.com/avinashbengaluru/ai-product-case-studies) |

---

## 📂 2. File Structure & What to Edit

All website files are contained inside `docs/demo/` (and synced to the standalone `portfolio` repository):

```text
portfolio/
├── portfolio.html              <-- Main AI & Analytics Portfolio Page (Avinash Immaneni)
├── mobile.html                 <-- 14-Slide Interactive Presentation Deck
├── index.html                  <-- Root page (mapped to mobile.html for Vercel)
├── GITHUB_PROFILE_README.md    <-- GitHub Profile README template
├── vercel.json                 <-- Vercel routing configuration
├── .github/
│   └── workflows/
│       └── deploy.yml          <-- GitHub Actions auto-deployment to GitHub Pages
└── assets/
    └── screenshots/
        ├── handwritten_ocr.jpg <-- Handwritten Doctor Note OCR modal screenshot
        ├── sales_analytics.jpg <-- Sales & purchase cost analytics screenshot
        ├── order_stepper.jpg   <-- 5-stage order progress stepper screenshot
        └── stock_search.jpg    <-- Fast stock search & dispatch drawer screenshot
```

---

## 🔐 3. Authentication & Git Setup

### Option A: Using GitHub CLI (`gh`) (Recommended)
If you have `gh` installed on your machine:
```bash
# 1. Login to your GitHub account
gh auth login

# 2. Clone the repository
git clone https://github.com/avinashbengaluru/portfolio.git
cd portfolio
```

### Option B: Using Personal Access Token (PAT)
1. Go to **[GitHub Settings ➔ Developer Settings ➔ Personal Access Tokens (Classic)](https://github.com/settings/tokens)**.
2. Click **Generate new token (classic)** with `repo` and `workflow` permissions.
3. Clone and authenticate:
```bash
git clone https://github.com/avinashbengaluru/portfolio.git
cd portfolio
```
When prompted for your password in git terminal/VS Code, paste your **Personal Access Token**.

### Option C: Using SSH
```bash
git clone git@github.com:avinashbengaluru/portfolio.git
cd portfolio
```

---

## 💻 4. Running & Previewing Locally

Because these are lightweight static HTML/CSS/JS files, you can preview them immediately without installing Node dependencies:

### Using Python (Built-in):
```bash
python -m http.server 3000
```
Then open in browser:
* **Portfolio:** [http://localhost:3000/portfolio.html](http://localhost:3000/portfolio.html)
* **Presentation Deck:** [http://localhost:3000/mobile.html](http://localhost:3000/mobile.html)

### Using VS Code / Cursor:
* Install the **Live Server** extension by Ritwick Dey.
* Right-click `portfolio.html` or `mobile.html` and select **"Open with Live Server"**.

---

## 🚀 5. How to Deploy Changes

Whenever you edit files in your editor, push them back to GitHub to update both GitHub Pages and Vercel automatically:

```bash
# 1. Stage modified files
git add .

# 2. Commit changes
git commit -m "Update portfolio sections"

# 3. Push to GitHub
git push origin main
```

### Automatic Deployments:
* **GitHub Pages:** Automatically triggers GitHub Actions (`deploy.yml`) and goes live in ~20 seconds at `https://avinashbengaluru.github.io/portfolio/`.
* **Vercel:** Automatically detects the push on `main` branch and deploys immediately to `https://billbuddy-deck.vercel.app`.

---

## ✏️ 6. Quick Customization Reference

* **Change Name / Bio / Title:**
  * Open `portfolio.html` and search for `<title>`, `<h1>Avinash Immaneni</h1>`, or `.avatar-badge`.
* **Add or Edit Presentation Slides:**
  * Open `mobile.html` and look for `<section class="m-slide" id="mslide...">`.
* **Replace Screenshots:**
  * Drop new JPG/PNG files into `assets/screenshots/` and update the `src="./assets/screenshots/..."` paths.
