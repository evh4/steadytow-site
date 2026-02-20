# SteadyTow Website

Static website for steadytow.app, hosted on GitHub Pages.

## Files

```
├── index.html      # Landing page
├── privacy.html    # Privacy Policy (App Store required)
├── terms.html      # Terms of Use (App Store required)
├── support.html    # Support/FAQ (App Store required)
├── 404.html        # Custom 404 page
├── CNAME           # Custom domain config
└── README.md       # This file
```

## Deployment

### Step 1: Create GitHub Repository

```bash
# Create new repo (or use existing steadytow repo)
gh repo create steadytow-site --public

# Or create at github.com/new
```

### Step 2: Push Files

```bash
cd steadytow-site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin git@github.com:evh4/steadytow-site.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to **github.com/evh4/steadytow-site/settings/pages**
2. Under "Source", select **Deploy from a branch**
3. Select **main** branch, **/ (root)** folder
4. Click **Save**

GitHub will deploy within ~60 seconds.

### Step 4: Configure Custom Domain

#### In GitHub:
1. Still in Settings > Pages
2. Under "Custom domain", enter `steadytow.app`
3. Click **Save**
4. Check "Enforce HTTPS" (may take a few minutes to appear)

#### In Squarespace DNS:

Go to **Squarespace > Domains > steadytow.app > DNS Settings**

Delete any existing A records and CNAME records pointing to Squarespace, then add:

**A Records** (point to GitHub Pages):
```
Type: A
Host: @
Value: 185.199.108.153

Type: A
Host: @
Value: 185.199.109.153

Type: A
Host: @
Value: 185.199.110.153

Type: A
Host: @
Value: 185.199.111.153
```

**CNAME Record** (for www subdomain):
```
Type: CNAME
Host: www
Value: evh4.github.io
```

DNS propagation takes 15-60 minutes.

### Step 5: Verify

- [ ] https://steadytow.app loads the landing page
- [ ] https://steadytow.app/privacy loads Privacy Policy
- [ ] https://steadytow.app/terms loads Terms of Use
- [ ] https://steadytow.app/support loads Support page
- [ ] https://www.steadytow.app redirects to steadytow.app
- [ ] All pages have HTTPS (lock icon)
- [ ] Random URL shows custom 404 page

## App Store Connect

Use these URLs when submitting:

| Field | URL |
|-------|-----|
| Privacy Policy URL | `https://steadytow.app/privacy` |
| Support URL | `https://steadytow.app/support` |
| Marketing URL | `https://steadytow.app` |

## Making Changes

Edit files locally, then:

```bash
git add .
git commit -m "Update description"
git push
```

GitHub Pages auto-deploys on push (~30-60 seconds).

## Email Setup

GitHub Pages doesn't handle email. Keep using Squarespace or ImprovMX for `support@steadytow.app` forwarding — this is independent of where the website is hosted.

---

© 2026 Neptune Industries, LLC
