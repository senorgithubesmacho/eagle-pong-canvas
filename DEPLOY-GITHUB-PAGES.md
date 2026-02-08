# Deploy Eagle Pong to GitHub Pages (for Canvas iframe)

Use this guide to get a **public** URL (no password) so the game works in a Canvas LMS iframe.

---

## What’s in this folder (ready to deploy)

- **index.html** – Eagle Pong game (single file, no build step)
- **OPA Mascot Head Large Banner Removed.png** – Ball image
- **.gitignore** – Ignores system junk (e.g. `.DS_Store`)

---

## Step 1: Initialize Git and make the first commit

In Terminal, from this project folder:

```bash
cd "/Users/ryan/Canvas Home Page"

git init
git add .
git commit -m "Add Eagle Pong for Canvas home page"
```

You only need to do this once per machine (or if you delete the `.git` folder).

---

## Step 2: Create a new public repository on GitHub

1. Go to **https://github.com/new**
2. Set **Repository name** (e.g. `eagle-pong-canvas` or `canvas-home-page`).
3. Set **Visibility** to **Public**.
4. **Do not** check “Add a README”, “Add .gitignore”, or “Choose a license” (you already have a local repo).
5. Click **Create repository**.

---

## Step 3: Connect your local repo and push

GitHub will show “push an existing repository from the command line.” Use your **actual repo URL** in place of `YOUR_USERNAME` and `YOUR_REPO` below.

```bash
cd "/Users/ryan/Canvas Home Page"

git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```

Example if your GitHub username is `jane` and repo is `eagle-pong-canvas`:

```bash
git remote add origin https://github.com/jane/eagle-pong-canvas.git
git branch -M main
git push -u origin main
```

---

## Step 4: Turn on GitHub Pages

1. Open your repo on GitHub (e.g. `https://github.com/YOUR_USERNAME/YOUR_REPO`).
2. Click **Settings** (top tab).
3. In the left sidebar, under **“Code and automation”**, click **Pages**.
4. Under **“Build and deployment”**:
   - **Source:** **Deploy from a branch**
   - **Branch:** choose **main** (or **master** if that’s what you use), folder **/ (root)**.
5. Click **Save**.
6. Wait 1–2 minutes. Refresh the Pages settings page; you’ll see something like:
   - **“Your site is live at https://YOUR_USERNAME.github.io/YOUR_REPO/”**

That URL is your **public** link (no password).

---

## Step 5: Use the link in Canvas

1. In Canvas, edit the course **Home** page (or the page where you want the game).
2. Switch to **HTML view** (e.g. “</>” or “Edit as HTML”).
3. Insert an iframe using your GitHub Pages URL:

```html
<iframe
  src="https://YOUR_USERNAME.github.io/YOUR_REPO/"
  width="660"
  height="460"
  style="border: 0; max-width: 100%;"
  title="Eagle Pong"
></iframe>
```

Replace `YOUR_USERNAME` and `YOUR_REPO` with your GitHub username and repository name. The game will load without a password and work inside the iframe.

---

## Updating the game later

After you change `index.html` or the image:

```bash
cd "/Users/ryan/Canvas Home Page"
git add .
git commit -m "Update Eagle Pong"
git push
```

GitHub Pages will update in a minute or two; refresh the Canvas page to see changes.
