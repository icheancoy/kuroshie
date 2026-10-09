# Ichsan Andrian — portfolio

Single-page portfolio built from my CV. Plain HTML and CSS in one file, no build step, no framework, no tracking.

**Live:** https://icheancoy.github.io/kuroshie/

## What's here

```
index.html                  the whole page
assets/CV_IchsanAndrian.pdf CV generated from the same content
.nojekyll                   tells GitHub Pages to serve files as-is
```

## Running it locally

Open `index.html` in a browser. That is the entire setup.

To serve it over HTTP instead:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Editing

All styles are in the `<style>` block at the top of `index.html`, driven by CSS variables. The two themes (`paper` and `phosphor`) are defined in `:root` and `[data-theme="phosphor"]`. The theme toggle in the sidebar stores the choice in `localStorage`.

Sections are plain `<section>` elements in document order. Adding one means adding a matching entry to the `<nav>` list so it shows up in the sidebar index.

## Deploying to GitHub Pages

The repository does not exist yet. Create it first (empty, no README, no .gitignore), then push.

Using the GitHub CLI:

```bash
gh auth login
gh repo create icheancoy/kuroshie --public --source . --remote origin --push
```

Or by hand:

```bash
git init
git add .
git commit -m "Add portfolio"
git branch -M main
git remote add origin https://github.com/icheancoy/kuroshie.git
git push -u origin main
```

Switching to SSH later:

```bash
git remote set-url origin git@github.com:icheancoy/kuroshie.git
```

Then in the repository settings: **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.

The page lands at `https://icheancoy.github.io/kuroshie/` within a minute or two.
