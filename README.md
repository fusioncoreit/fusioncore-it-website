# FusionCore IT — Website

A static 4-page marketing site: Home, About, Services, Contact. No build step, no framework — plain HTML/CSS/JS.

## Structure

```
fusioncore-it-website/
├── index.html      Home
├── about.html       About
├── services.html    Services
├── contact.html      Contact (form)
├── css/style.css    All styling (colors, layout, components)
├── js/script.js     Mobile nav, scroll reveal, contact form handling
└── assets/          (empty — for future images/logo files)
```

## Before you go live

1. **Wire up the contact form.** It currently posts to a Formspree placeholder
   (`action="https://formspree.io/f/YOUR_FORM_ID"` in `contact.html`).
   - Sign up free at https://formspree.io, create a form, and swap `YOUR_FORM_ID`
     for your real form ID. Formspree emails submissions straight to your inbox
     (e.g. info@fusioncoreit.co.uk) — no server needed.
   - Alternatives: Netlify Forms (if hosting on Netlify, just add `netlify` and
     `data-netlify="true"` attributes to the `<form>`), or Getform, Web3Forms, etc.

2. **Update the domain references.** Replace `https://www.fusioncoreit.com/` in
   `index.html`'s `<meta property="og:url">` tag with your actual registered domain.

3. **Replace placeholder content:**
   - Stats on the homepage (`120+ Projects`, `98% Retention`, etc.) are illustrative — swap in real numbers.
   - "About" timeline entries are generic milestones — edit with your real company history.
   - Social links (`<div class="social-links">` in each footer) point to `#` — add your real LinkedIn/X URLs.

4. **Add a real logo (optional).** Right now the brand mark is a styled "F" letter
   (`.brand-mark` in `css/style.css`). Drop a logo file into `assets/` and swap the
   markup in each page's `<a class="brand">` if you'd rather use an image.

## Customizing the look

All colors, spacing, and the gradient theme are defined as CSS variables at the top
of `css/style.css` under `:root`. To change the accent colors, edit:

```css
--accent-cyan: #22d3ee;
--accent-violet: #a78bfa;
--accent-blue: #6366f1;
```

## Deploying

Since it's fully static, you can deploy it to any of these in minutes:

- **Netlify / Vercel**: drag-and-drop the folder in their dashboard, or connect a
  Git repo and deploy on push. Then point your domain's DNS at them (both have
  simple custom-domain instructions once the site is live).
- **GitHub Pages**: push this folder to a repo and enable Pages in repo settings.
- **Traditional hosting**: upload the whole folder via FTP/cPanel to your existing
  web host — no server-side requirements.

## Local preview

Just open `index.html` directly in a browser, or run a simple local server from
this folder for accurate relative paths:

```bash
# Python
python -m http.server 8000

# Node
npx serve .
```

Then visit `http://localhost:8000`.
