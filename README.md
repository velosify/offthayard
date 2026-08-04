# OffThaYard Tattooz — Website

A single-page static site for OffThaYard Tattooz. No build step, no dependencies — just static files you can host anywhere.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The whole landing page (HTML, CSS, and JS all in one file). |
| `hero.mp4` | Background video used in the hero section. |
| `poster.jpg` | Still frame shown before the video loads. |
| `404.html` | Custom "page not found" page. |
| `_headers` | Cloudflare Pages caching + security headers. |
| `.gitignore` | Keeps OS/editor junk out of the repo. |

Keep `index.html`, `hero.mp4`, and `poster.jpg` together — the page loads the media by relative filename.

## Before you go live — fill in the placeholders

The page ships with placeholder business details wrapped in double brackets, like `[[PHONE]]` and `[[BOOKING_URL]]`. Open `index.html`, do a find-and-replace for each token, and you're done. The full list is in the comment block at the top of `index.html`. Also swap the gallery images (they currently use random stock photos) for real photos of your work.

## Deploy: GitHub → Cloudflare Pages

### 1. Put this folder on GitHub
```bash
# from inside this folder
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/offthayard-tattooz.git
git push -u origin main
```
(Create the empty `offthayard-tattooz` repo on github.com first, then use its URL above.)

### 2. Connect it to Cloudflare Pages
1. Go to the Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
2. Pick your `offthayard-tattooz` repo.
3. Build settings — this is a plain static site, so:
   - **Framework preset:** `None`
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`  (the repo root, since `index.html` lives there)
4. Click **Save and Deploy**. Cloudflare gives you a live `*.pages.dev` URL in under a minute.

### 3. (Optional) Use your own domain
In the Pages project → **Custom domains** → **Set up a custom domain**, and follow the prompts. If your domain's DNS is already on Cloudflare, it wires up automatically.

## Updating the site later
Edit the files, commit, and push to `main` — Cloudflare Pages redeploys automatically on every push.
