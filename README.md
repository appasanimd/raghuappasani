# Dr. Raghu Appasani, MD — Website

A single-page, fully self-contained website. Everything (HTML, CSS, fonts,
images) is inlined into `index.html`, so there are **no build steps and no
external dependencies** — just static files you can host anywhere.

## Files

| File           | Purpose                                                            |
| -------------- | ----------------------------------------------------------------- |
| `index.html`   | The entire website, self-contained. This is all you strictly need. |
| `sitemap.xml`  | Helps search engines crawl the site.                              |
| `robots.txt`   | Tells crawlers they're welcome and points to the sitemap.         |
| `.nojekyll`    | Tells GitHub Pages to serve files as-is (no Jekyll processing).   |
| `CNAME`        | (Optional) add this if you use a custom domain — see below.       |

## Deploy with GitHub Pages (free, ~3 minutes)

1. Create a new repository on GitHub (e.g. `raghu-website`).
2. Upload every file in this folder to the repo root
   (drag-and-drop into GitHub's "Add file → Upload files", or `git push`).
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Set the branch to `main` and the folder to `/ (root)`, then **Save**.
6. Wait ~1 minute. Your site is live at
   `https://<your-username>.github.io/<repo-name>/`.

### Command line alternative

```bash
git init
git add .
git commit -m "Launch site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then enable Pages as in steps 3–6 above.

## Custom domain (e.g. raghuappasani.com)

1. Create a file named `CNAME` (no extension) in the repo root containing one
   line — your domain:
   ```
   raghuappasani.com
   ```
2. At your domain registrar, point the domain at GitHub Pages:
   - **Apex domain** (`raghuappasani.com`): add four `A` records to
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
   - **www subdomain**: add a `CNAME` record pointing to
     `<your-username>.github.io`.
3. In **Settings → Pages**, enter the custom domain and enable
   **Enforce HTTPS**.

## Before you go live — update the domain in the SEO tags

The SEO/social tags and structured data currently reference
`https://raghuappasani.com/`. If you deploy to a different URL, update these so
search engines and link previews use the correct address. They live in the
`<head>` of the **source** file (`Raghu Appasani.dc.html`) — search for
`raghuappasani.com` and replace, then re-export. The same domain also appears in
`sitemap.xml` and `robots.txt` in this folder (safe to edit directly).

## What's included for SEO

- Descriptive `<title>` and meta description
- Open Graph + Twitter Card tags (rich link previews)
- JSON-LD `Person` structured data (name, role, education, social profiles)
- Canonical URL, favicon, `sitemap.xml`, `robots.txt`

## Editing later

Don't hand-edit `index.html` — it's compiled output. Edit the source design and
re-export the self-contained file.
