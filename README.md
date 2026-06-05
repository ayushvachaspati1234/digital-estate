# Heirloom — Landing Page

Static landing page for a **digital estate & access continuity** startup (dead-man switches, multi-party key escrow, legally-integrated access transfer for passwords, wallets, domains, SaaS admin rights). No build step, no dependencies — plain HTML/CSS/JS.

## Rebranding (company name / domain)

Edit the three values at the top of **`config.js`**:

```js
const BRAND = {
  companyName: "Heirloom",
  domain: "heirloom.example.com",
  contactEmail: "hello@heirloom.example.com"
};
```

Every occurrence of the company name, domain, and email in the page is injected from this file at load time. Nothing else needs to change.

## Deploy to GitHub Pages

1. Create a new GitHub repo and push this folder's contents to it:
   ```sh
   git init
   git add .
   git commit -m "Landing page"
   git remote add origin https://github.com/<user>/<repo>.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)`** → Save.
3. The site goes live at `https://<user>.github.io/<repo>/`.

For a custom domain, add it under **Settings → Pages → Custom domain** (GitHub creates a `CNAME` file) and point your DNS at GitHub Pages.

## Files

| File | Purpose |
|---|---|
| `index.html` | Page structure & copy |
| `style.css` | All styling (theme variables at top of file) |
| `config.js` | Brand config + injection script |

## Notes

- Theme: deep ink navy + antique gold with an **engraved-certificate hero** — the whole hero sits inside a gold double-rule frame; Spectral serif headings, roman-numeral steps (`--ink`, `--gold` in `style.css`).
- Hero visual is a pure HTML/CSS **estate vault card**: SEALED badge, armed dead-man-switch progress bar, and a 2-of-3 key-holder quorum list with "key held" chips.
- The email form shows a confirmation message client-side; wire it to Formspree, Buttondown, or your own endpoint to actually collect emails.
- Logo is an inline SVG key mark in `index.html` (nav + footer) — swap both `<svg class="logo-mark">` blocks to change it.
