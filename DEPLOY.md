# Deploy VOTUM3 to GitHub Pages

This guide takes the website live on the public internet. Total time: about 10 minutes.

The contact form is already wired up to Formspree and submissions are landing in your inbox — no further setup needed there.

---

## Step 1 — Create the GitHub repository

1. Sign in (or sign up) at **https://github.com**
2. In the top-right corner, click the **+** icon → **New repository**
3. Fill in:
   - **Repository name:** `votum3` *(this becomes part of your URL — keep it short)*
   - **Description:** `VOTUM3 brand strategy studio website`
   - Visibility: **Public** *(required for free GitHub Pages)*
   - Tick **Add a README file** — we'll replace it in the next step
4. Click **Create repository**

## Step 2 — Upload the website files

1. On the repository page, click **Add file** → **Upload files**
2. Drag in all three files from the deployment folder:
   - `index.html`
   - `README.md` *(this replaces the default README)*
   - `DEPLOY.md` *(this guide — keeps it with the project for reference)*
3. Scroll down. Commit message: `Initial site upload`
4. Click **Commit changes**

> If GitHub asks whether to overwrite the existing `README.md`, say yes.

## Step 3 — Turn on GitHub Pages

1. Click the **Settings** tab at the top of the repository
2. In the left sidebar, click **Pages**
3. Under **Build and deployment** → **Source**, choose **Deploy from a branch**
4. Under **Branch**, choose **main**, folder **/ (root)**, then click **Save**
5. Wait about a minute, then refresh the Pages settings page. You'll see a green banner:

   > Your site is live at `https://yourusername.github.io/votum3/`

That's it. The site is live worldwide.

---

## Step 4 — (Optional) Use a custom domain

Right now your site sits at `https://yourusername.github.io/votum3/`. To use **votum3.io** or **votum3.com** instead:

### 4a. Buy the domain

If you don't already own it, buy it from any of:
- **Cloudflare Registrar** (sells domains at wholesale cost — cheapest long-term)
- **Namecheap** (easy interface, common choice)
- **Google Domains / Squarespace Domains**

Approximate prices:
- `.io` — £30–50 per year
- `.com` — £10–15 per year
- `.co.uk` — £8–12 per year

### 4b. Point the domain at GitHub Pages

In your domain registrar's DNS settings, add these records:

| Type  | Name | Value                       |
|-------|------|-----------------------------|
| A     | @    | 185.199.108.153             |
| A     | @    | 185.199.109.153             |
| A     | @    | 185.199.110.153             |
| A     | @    | 185.199.111.153             |
| CNAME | www  | `yourusername.github.io`    |

*(Replace `yourusername` with your actual GitHub username.)*

### 4c. Tell GitHub which domain to use

1. Back in your repository → **Settings** → **Pages**
2. Under **Custom domain**, type your domain (e.g. `votum3.io`) → **Save**
3. Once DNS has propagated (usually within an hour, can take up to 24), tick **Enforce HTTPS**

GitHub will automatically issue a free Let's Encrypt SSL certificate. The site will now be live at `https://votum3.io`.

### 4d. (Recommended) Add a CNAME file to the repo

To make the custom domain stick across re-deploys, create a file called `CNAME` (no extension) in your repository with just one line — your domain:

```
votum3.io
```

GitHub Pages reads this and keeps the custom domain configured even if the Pages settings reset.

---

## Updating the site later

To update any text, swap a project, fix a typo, etc:

**Option A — Edit on GitHub.com (easiest)**
1. Open the repository
2. Click `index.html`
3. Click the pencil icon (top-right of the file)
4. Make changes → scroll down → write a commit message → **Commit changes**
5. Wait ~1 minute. The live site updates automatically.

**Option B — Edit locally (more comfortable for larger changes)**
1. Install **GitHub Desktop** (https://desktop.github.com)
2. Clone the repository to your computer
3. Edit `index.html` in any text editor — VS Code recommended
4. In GitHub Desktop, write a commit message → commit → push origin
5. Live site updates within ~1 minute.

---

## Checklist

- [ ] GitHub account ready
- [ ] Repository `votum3` created, set to public
- [ ] Files uploaded: `index.html`, `README.md`, `DEPLOY.md`
- [ ] GitHub Pages turned on (Settings → Pages → main branch)
- [ ] Site is live at `https://yourusername.github.io/votum3/`
- [ ] (Optional) Custom domain bought
- [ ] (Optional) DNS records added at your registrar
- [ ] (Optional) Custom domain set in Pages settings
- [ ] (Optional) HTTPS enforced
- [ ] (Optional) `CNAME` file added to repository

---

## Common issues

**"My site shows a 404 after I turn on Pages."**
Wait 2–3 minutes — first deployment takes a moment. Hard-refresh the page (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows). Check that the file is named exactly `index.html` (lowercase).

**"My custom domain isn't loading."**
DNS propagation can take up to 24 hours. Check progress at **https://dnschecker.org** by entering your domain — when all global locations show the GitHub IPs, you're good.

**"The contact form sends to a Formspree page instead of staying on the site."**
This shouldn't happen — the form is set up to submit via AJAX and show the in-page thank-you message. If you ever see this, it means the JavaScript at the bottom of `index.html` got removed or broken. Restore from a working copy.

**"I want to take a Formspree submission off the limit."**
Formspree's free plan allows 50 submissions per month. Upgrade in your Formspree dashboard if needed — paid plans start at ~$10/month.

---

In Votum we trust.
