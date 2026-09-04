# Price Technology Solutions — website

A simple, single-page site. No build tools needed — just plain HTML/CSS/JS.

## Files
- `index.html` — the page
- `styles.css` — all styling
- `script.js` — mobile menu + footer year
- `assets/` — your logo images
- `CNAME` — tells GitHub Pages to serve this site at `pricets.com`

## Before you deploy
Open `index.html` and replace the placeholder phone number
`(555) 123-4567` (it appears twice, and once in a `tel:` link) with your real one.

## Deploy with GitHub Pages

### 1. Create the repository
1. Go to [github.com/new](https://github.com/new).
2. Repository name: anything you like, e.g. `pricets-website`.
3. Set it to **Public** (required for free GitHub Pages).
4. Don't initialize with a README — you already have these files. Click **Create repository**.

### 2. Upload the files
Easiest way (no command line needed):
1. On your new repo's page, click **uploading an existing file**.
2. Drag in `index.html`, `styles.css`, `script.js`, `CNAME`, and the whole `assets` folder.
3. Scroll down, click **Commit changes**.

(If you prefer git on the command line instead:)
```bash
cd pricets
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/pricets-website.git
git push -u origin main
```

### 3. Turn on GitHub Pages
1. In your repo, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)`. Click **Save**.
4. GitHub will give you a URL like `https://YOUR-USERNAME.github.io/pricets-website` — wait a minute or two, then check it loads.

### 4. Point pricets.com at GitHub Pages
Go to wherever you bought `pricets.com` (GoDaddy, Namecheap, etc.) and edit its DNS records:

**Add these 4 A records** for the root domain (`@` or blank host):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**Add a CNAME record** for the `www` subdomain:
```
Host: www
Value: YOUR-USERNAME.github.io
```

DNS changes can take anywhere from a few minutes to a few hours to take effect.

### 5. Confirm the custom domain in GitHub
1. Back in **Settings → Pages**, under **Custom domain**, enter `pricets.com` and click **Save**.
   (The `CNAME` file you uploaded already does this automatically, but re-saving it here also triggers GitHub's SSL certificate for `https://`.)
2. Check **Enforce HTTPS** once it becomes available (may take a little while after DNS propagates).

That's it — `https://pricets.com` should serve the site.

## Making changes later
Edit any file directly on GitHub (pencil icon) or locally and push — the site rebuilds automatically within a minute of any commit to `main`.
