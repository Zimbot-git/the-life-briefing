# GitHub Pages Deploy Guide
## Migrating peteschuil.live from Netlify to GitHub Pages

---

## 1. Repository Setup

### Create the GitHub repository

1. Go to [github.com](https://github.com) and sign in.
2. Click **New repository** (top-right **+** menu).
3. Set:
   - **Repository name:** `peteschuil.live` (or `the-life-briefing`)
   - **Visibility:** Public *(GitHub Pages requires public repos on the free plan)*
   - **Do not** initialise with a README — you already have the files.
4. Click **Create repository**.

### Push your local files

```bash
cd /path/to/the-life-briefing    # your local repo root

git init                          # skip if already a git repo
git add .
git commit -m "Initial deploy — migrate from Netlify to GitHub Pages"

git remote add origin https://github.com/YOUR_USERNAME/peteschuil.live.git
git branch -M main
git push -u origin main
```

---

## 2. Enable GitHub Pages

1. In your repository on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment**:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` | **Folder:** `/ (root)`
3. Click **Save**.

GitHub will publish your site and show a URL like:
`https://YOUR_USERNAME.github.io/peteschuil.live/`

Wait ~60 seconds for the first build to complete.

---

## 3. Add Your Images

Before pushing (or in a subsequent commit), make sure these two files are in the `images/` folder:

```
images/
  tlb-hero-image-web.png      ✅ already present
  tvfmo-book-cover-web.png    ← add this file
  plc-book-cover-web.png      ← add this file
```

```bash
# Copy your book cover files into the images folder, then:
git add images/tvfmo-book-cover-web.png images/plc-book-cover-web.png
git commit -m "Add book cover images"
git push
```

---

## 4. Custom Domain — Namecheap → GitHub Pages

### Step A: Add the custom domain in GitHub

1. In **Settings → Pages → Custom domain**, enter:
   ```
   peteschuil.live
   ```
2. Click **Save**. GitHub creates a `CNAME` file in your repo automatically.
3. Check **Enforce HTTPS** (available ~24 hours after DNS propagates).

### Step B: Update DNS records in Namecheap

Log in to Namecheap → **Domain List** → click **Manage** next to `peteschuil.live` → **Advanced DNS** tab.

#### Delete or replace old Netlify records

Remove any `A`, `ALIAS`, or `CNAME` records that point to Netlify (e.g. `*.netlify.app` or Netlify IP addresses).

#### Add GitHub Pages A records (apex domain)

Create four `A` records for the **root/apex domain** (`@`):

| Type | Host | Value             | TTL        |
|------|------|-------------------|------------|
| A    | @    | 185.199.108.153   | Automatic  |
| A    | @    | 185.199.109.153   | Automatic  |
| A    | @    | 185.199.110.153   | Automatic  |
| A    | @    | 185.199.111.153   | Automatic  |

#### Add CNAME record (www subdomain)

| Type  | Host | Value                              | TTL        |
|-------|------|------------------------------------|------------|
| CNAME | www  | YOUR_USERNAME.github.io            | Automatic  |

> Replace `YOUR_USERNAME` with your actual GitHub username.

#### (Optional) AAAA records for IPv6

| Type  | Host | Value                        | TTL       |
|-------|------|------------------------------|-----------|
| AAAA  | @    | 2606:50c0:8000::153          | Automatic |
| AAAA  | @    | 2606:50c0:8001::153          | Automatic |
| AAAA  | @    | 2606:50c0:8002::153          | Automatic |
| AAAA  | @    | 2606:50c0:8003::153          | Automatic |

---

## 5. DNS Propagation & HTTPS

- DNS changes typically propagate within **5–30 minutes**, but can take up to 48 hours globally.
- Once propagated, GitHub Pages will automatically provision a **free Let's Encrypt TLS certificate**.
- Enable **Enforce HTTPS** in Settings → Pages once the certificate is issued.

### Verify DNS is correct

```bash
# Should return GitHub's IPs (185.199.108-111.153)
dig peteschuil.live +noall +answer

# Should resolve to YOUR_USERNAME.github.io
dig www.peteschuil.live +noall +answer
```

---

## 6. Remove from Netlify (after DNS is live)

Once `peteschuil.live` resolves correctly to GitHub Pages:

1. Log in to Netlify → select your site → **Site settings → General → Danger zone → Delete this site**.
2. Alternatively just leave it; it won't serve traffic once DNS no longer points to it.

---

## 7. Keeping the Site Updated

Any future changes are a simple push:

```bash
git add -A
git commit -m "Describe your changes"
git push
```

GitHub Pages re-deploys automatically within ~60 seconds of each push to `main`.

---

## File Structure Reference

```
peteschuil.live/           ← repository root (served as site root)
├── index.html
├── og-image.png
├── pete-portrait.jpg
├── CNAME                  ← auto-created by GitHub (contains: peteschuil.live)
└── images/
    ├── tlb-hero-image-web.png
    ├── tvfmo-book-cover-web.png
    └── plc-book-cover-web.png
```
