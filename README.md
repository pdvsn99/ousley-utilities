# ousley-utilities

Marketing site for **Ousley Utilities** — domestic energy connection management.

Live at **https://ousley.energy** (GitHub Pages, custom domain via `CNAME`).

## Structure

Static site, no build step. Everything is hand-written and self-contained.

| File | Purpose |
|---|---|
| `index.html` | The entire site — one page, inlined CSS and JS |
| `404.html` | Custom not-found page (GitHub Pages serves this automatically) |
| `CNAME` | Custom domain for GitHub Pages |
| `robots.txt` | Crawler directives + sitemap pointer |
| `sitemap.xml` | Single-URL sitemap |
| `social-card.png` | 1200×630 Open Graph / Twitter preview image |

> **Note:** the main file must be named `index.html`. GitHub Pages only treats
> `index.html` as a directory index — a file named `index` is not served.

## Deploying

Pushes to `main` publish automatically via GitHub Pages. There is nothing to build.

## DNS

For the apex domain `ousley.energy`, point A records at GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Add `www` as a `CNAME` to `<user>.github.io` if you want it to resolve too, then
enable **Enforce HTTPS** in the repository's Pages settings once the certificate
has been issued.

## Editing

- **Colours and type** live in the `:root` block at the top of the `<style>` tag.
- **Services** are `.service-row` blocks; each is an accordion.
- **FAQs** are `.faq-item` blocks. If you add, edit, or remove a question, update
  the `FAQPage` JSON-LD in `<head>` to match — Google will flag structured data
  that doesn't reflect the visible page.
- **Contact details** appear in three places: the contact section, the
  `ProfessionalService` JSON-LD, and the `404.html` footer link.

## Regenerating the social card

`social-card.png` was rendered from an HTML template at 1200×630. To change it,
recreate the artwork at that exact size and overwrite the file — the dimensions
are declared in the `og:image:width` / `og:image:height` meta tags.

## Known gaps

- The phone number and opening hours appear in the markup and in the structured
  data; keep them in sync.
- There is no enquiry form — contact is by email and phone only.
- No analytics is installed.
