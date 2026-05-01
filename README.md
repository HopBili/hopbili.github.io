# Hopbili — Consulting Website

**Live site:** [hopbili.ca](https://hopbili.ca)

A fully responsive, professional consulting website for Hopbili. Built as a static single-page site deployable directly to GitHub Pages — no build step required.

---

## Project Structure

```
hopbili/
├── index.html      # Complete website (HTML + CSS + JS)
└── README.md       # This file
```

---

## Deploy to GitHub Pages

### Option 1: Direct Upload (Easiest)

1. Create a new GitHub repository named `hopbili.ca` or `hopbili-website`
2. Upload `index.html` to the root of the repository
3. Go to **Settings → Pages**
4. Under **Source**, select **Deploy from a branch**
5. Choose `main` branch, `/ (root)` folder → click **Save**
6. Your site will be live at `https://yourusername.github.io/repo-name/`

### Option 2: Using Git CLI

```bash
git init
git add .
git commit -m "Initial commit: Hopbili website"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

Then enable GitHub Pages in repository Settings → Pages.

### Option 3: Custom Domain (hopbili.ca)

1. In your repository root, create a file named `CNAME` containing:
   ```
   hopbili.ca
   ```
2. In your domain registrar (e.g., Namecheap, GoDaddy), add these DNS records:
   ```
   A     @     185.199.108.153
   A     @     185.199.109.153
   A     @     185.199.110.153
   A     @     185.199.111.153
   CNAME www   YOUR_USERNAME.github.io
   ```
3. In GitHub Pages settings, enter `hopbili.ca` as your custom domain
4. Enable **Enforce HTTPS**

---

## Setting Up the Contact Form

### Option A: Formspree (Recommended — Free Plan Available)

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Create a new form and copy your Form ID (looks like `xabcdefg`)
3. In `index.html`, find this line:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID"
   ```
4. Replace `YOUR_FORM_ID` with your actual Form ID

### Option B: Mailto Fallback (Already Built In)

If you leave `YOUR_FORM_ID` unchanged, the form automatically falls back to opening the user's email client with a pre-filled message to `info@hopbili.ca`. No setup required.

---

## Customization

### Update LinkedIn URL
Search for `linkedin.com/company/hopbili` in `index.html` and replace with your actual LinkedIn URL.

### Update Colors
All colors are CSS variables at the top of the `<style>` block:
```css
--navy: #0d1f3c;
--teal: #0a7c6e;
--teal-light: #0d9e8c;
```

### Update Fonts
The site uses **Fraunces** (display) and **DM Sans** (body) from Google Fonts.
Change the `@import` link and font-family references to swap fonts.

---

## Technical Notes

- **No build step required** — pure HTML, CSS, JavaScript
- **No npm, Node.js, or CLI tools needed**
- **No paid dependencies**
- Google Fonts loaded via CDN
- Scroll reveal uses native `IntersectionObserver` API
- Form has Formspree + mailto dual fallback
- Fully accessible: semantic HTML, ARIA labels, keyboard navigable

---

*Built for Hopbili — data-driven consulting for businesses that want smarter systems.*
