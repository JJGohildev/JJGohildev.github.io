# Jaydipsinh Gohil — portfolio website (standalone export)

Everything needed to host the site. No build step, no framework, no editor runtime —
`index.html` is plain HTML, CSS and JavaScript. Open it from any static host.

## Contents

```
index.html                     the whole site (HTML + CSS + JS)
favicon.svg                    JG favicon
robots.txt                     allows indexing, points to sitemap
sitemap.xml                    update the URL after you pick a domain
.nojekyll                      required for GitHub Pages
assets/
  portrait.mp4                 cursor-controlled portrait animation
  portrait.jpg                 poster / static portrait fallback
  Jaydipsinh_Gohil_Resume.pdf  resume download
  share-preview.png            1200×630 link preview image
  apple-touch-icon.png         iOS home-screen icon
  previews/*.png               six dashboard screenshots
```

## Deploy — GitHub Pages (free, recommended)

1. Create a public repository named **`JJGohildev.github.io`**.
2. Upload the **contents** of this folder to the repository root — `index.html`
   must sit at the top level, not inside a subfolder.
3. Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Wait ~1 minute. The site is live at **https://jjgohildev.github.io/**.

Any push updates the live site. Alternatively drag this folder onto
[app.netlify.com/drop](https://app.netlify.com/drop) or run `vercel` in it — both
give an instant `*.netlify.app` / `*.vercel.app` address with the same files.

## Optional — connect jaydipsinhgohil.com

A custom domain must be bought and pointed at the host; renaming anything in an
editor does not change the address.

1. Check availability and register the domain with any registrar
   (Namecheap, Porkbun, IONOS — roughly €10–15/year). **Do this yourself; nothing
   has been purchased.**
2. At the registrar's DNS panel add:
   - four `A` records for `@` → `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - one `CNAME` record for `www` → `jjgohildev.github.io`
3. In the repository: Settings → Pages → Custom domain → `jaydipsinhgohil.com` → Save.
   This creates a `CNAME` file in the repo.
4. Tick **Enforce HTTPS** once the certificate is issued (usually under an hour).
5. Update the four absolute URLs in `index.html` (`<link rel="canonical">`,
   `og:url`, `og:image`, `twitter:image`) and `sitemap.xml` from
   `https://jaydipsinhgohil.com/` to whatever address you settle on.

For Netlify/Vercel the steps are the same but the DNS values come from their
dashboard.

## Using it on a CV / applications

Put the final address on the CV and in the GitHub profile README. Direct links
that always work:

- Resume PDF: `https://<your-domain>/assets/Jaydipsinh_Gohil_Resume.pdf`
- Projects section: `https://<your-domain>/#projects`

## Notes

- The portrait animation runs on desktop with a mouse. Touch devices and anyone
  with "reduce motion" enabled get the still portrait, and the video is not
  downloaded for them.
- Open the site over `http://` or `https://` (a local server or a real host), not
  by double-clicking the file — `file://` blocks the video fetch and the clipboard API.
  A quick local server: `python3 -m http.server` inside this folder, then visit
  `http://localhost:8000`.
