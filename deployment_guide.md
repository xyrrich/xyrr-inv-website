# Xyrr Investments — Deployment Guide

## 1. Deploy to Vercel (Recommended — Free)

Vercel auto-detects static sites. Zero config needed.

**Steps:**
1. Push this repo to GitHub
2. Go to [vercel.com](https://vercel.com) and sign in with GitHub
3. Click **"Add New Project"** → select `xyrr-inv-website`
4. Vercel will detect it as a static site automatically
5. Click **Deploy** — the site will be live in ~30 seconds
6. You'll get a URL like `xyrr-inv-website.vercel.app`

**Redeployment:** Every push to `main` auto-deploys.

---

## 2. Deploy to GitHub Pages (Free)

**Steps:**
1. In your GitHub repo, go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose `main` branch and `/ (root)` folder
4. Click **Save**
5. Site will be live at `https://xyrrich.github.io/xyrr-inv-website/`

**Note:** If using a subfolder URL, asset paths may need adjusting. A custom domain avoids this.

---

## 3. Adding a Custom Domain

### On Vercel:
1. Go to your project → **Settings → Domains**
2. Add your domain (e.g., `xyrrinvestments.com`)
3. Update your domain's DNS:
   - **A Record:** `76.76.21.21`
   - **CNAME (www):** `cname.vercel-dns.com`
4. Vercel provisions SSL automatically

### On GitHub Pages:
1. Go to **Settings → Pages → Custom domain**
2. Enter your domain (e.g., `xyrrinvestments.com`)
3. Update DNS:
   - **A Records:** `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - **CNAME (www):** `xyrrich.github.io`
4. Check **Enforce HTTPS** once DNS propagates

### Domain registrars:
- Namecheap, Cloudflare, Google Domains, or GoDaddy all work fine
- Cloudflare is recommended for free SSL + CDN + DNS management

---

## 4. Backend Features to Add Next

### Priority 1 — Contact Form (Formspree)
- Sign up at [formspree.io](https://formspree.io) (free tier: 50 submissions/month)
- Replace the "Send Message" button with a `<form>` pointing to your Formspree endpoint
- Fields: Name, Email, Phone, Message
- No backend code needed — Formspree handles email delivery

### Priority 2 — Deal Inquiry Form
- Add a "Get Details" form per deal (or a shared modal)
- Capture: Buyer Name, Email, Phone, Which Deal
- Use Formspree or [Getform.io](https://getform.io) to collect submissions
- Tag each submission with the deal address for easy sorting

### Priority 3 — Buyers List Signup
- Add a "Join Our Buyers List" CTA section
- Collect: Name, Email, Phone, Markets of Interest, Budget Range
- Options for form backend:
  - **Formspree** — simplest, no code
  - **Airtable + Zapier** — auto-add to a spreadsheet/CRM
  - **Mailchimp** — if you want email marketing later

### Priority 4 — Deal Management (Future)
- Move deal data into a JSON file or headless CMS (Decap CMS is already in the AstroWind setup)
- Auto-generate deal cards from data
- Add a "SOLD" or "UNDER CONTRACT" badge to cards
- Archive closed deals to a separate page

---

## 5. Recommended Folder Structure (When the Site Grows)

```
xyrr-inv-website/
├── index.html              ← Main landing page (current)
├── deals/
│   ├── index.html          ← All deals listing page
│   └── 1220-pond-st.html   ← Individual deal detail pages
├── assets/
│   ├── css/
│   │   └── styles.css      ← Extracted from inline <style>
│   ├── images/
│   │   ├── deals/          ← Property photos
│   │   ├── logo.svg
│   │   └── og-image.jpg    ← Social media preview
│   └── fonts/              ← Self-hosted Inter (optional)
├── forms/
│   └── thank-you.html      ← Post-submission confirmation
├── legal/
│   ├── privacy.html
│   └── terms.html
├── design_system.md
├── deployment_guide.md
└── README.md
```

### When to migrate off pure HTML:
- **5+ pages** → Consider a static site generator (Astro is already set up in this repo)
- **Dynamic deal data** → Move deals to a JSON file or CMS
- **Buyer portal** → Add a backend (Node.js, Supabase, or Firebase)
- **For now** → Pure HTML is the fastest, cheapest, most reliable option

---

## Quick Checklist Before Going Live

- [ ] Replace placeholder email/phone with real contact info
- [ ] Add Google Analytics or Plausible for visitor tracking
- [ ] Add Open Graph meta tags for social media sharing
- [ ] Add a favicon (replace the default Astro one)
- [ ] Test on mobile devices
- [ ] Set up Formspree and wire up the contact form
- [ ] Register and connect custom domain
