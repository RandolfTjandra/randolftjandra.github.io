# randolftjandra.github.io

This repository contains the Hugo project that builds https://randolftjandra.github.io/.

## Prerequisites
- Install the **extended** Hugo CLI (v0.114.0 or newer). On macOS you can run `brew install hugo`.
- Clone the repo with submodules so the theme is available: `git submodule update --init --recursive`.

## Local development
1. Start the live-reloading server (includes drafts):
   ```sh
   hugo server -D
   ```
2. Visit http://localhost:1313 to review changes. Hugo watches the project and refreshes the page automatically as you edit content or templates.

## Creating content
- Add a new post draft:
  ```sh
  hugo new posts/my-new-post/index.md
  ```
  This creates `content/posts/my-new-post/index.md` with front matter that sets `draft: true`. Add images or other assets alongside the `index.md` file in the same folder.
- While the post is still in progress leave `draft: true` (or add `publishDate` in the future). Run `hugo server -D` to preview drafts locally.
- When the post is ready to go live, set `draft: false` (or remove the line) and adjust `date`/`publishDate` as needed. Commit the content changes.
- Useful helpers:
  - `hugo list drafts` shows everything that is still marked as draft.
  - `hugo new posts/my-note.md` creates a single Markdown file instead of a bundle if you do not need extra assets.

## Publishing
1. (Optional) Build the site locally to verify the generated output:
   ```sh
   hugo --minify
   ```
   The static files land in `public/` and can be previewed locally.
2. Push your changes to the `main` branch. The GitHub Action in `.github/workflows/hugo.yml` builds the site and deploys it to GitHub Pages automatically.

## Project layout reminders
- `content/` – Markdown sources for posts and pages (`content/about`, `content/posts`, etc.).
- `static/` – Files copied verbatim into the final site (images, favicons, downloads).
- `themes/mini/` – Active theme; keep submodules updated with `git submodule update --remote --merge` when you want the latest theme release.

Feel free to add any project-specific tips here as your workflow evolves.
