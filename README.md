# HAISTRY — Website

The public site for **HAISTRY**, an AI-illustrated history brand. Static HTML pages hosted on Netlify. No build step, no framework — just plain HTML/CSS files.

---

## Pages

| File | Purpose | Live path |
|------|---------|-----------|
| `index.html` | Free sampler landing page — email signup that delivers the free sampler via Kit | `/` |
| `hub.html` | Link hub — the "everything in one place" page used as the Instagram bio link | `/hub.html` |
| `resources.html` | Affiliate resources — the books and tools behind the stories | `/resources.html` |

> If you rename the sampler page to `index.html`, it becomes the homepage (`/`). Keep whichever page you want as the front door named `index.html`.

---

## Design

All pages share one visual system so they read as a single site:

- **Background:** near-black `#0a0e14` with a faint blueprint grid
- **Accents:** antique gold `#c9a24a`, editorial blue `#4a7fd0`
- **Type:** serif display (Iowan Old Style / Palatino / Georgia fallback), monospace for small labels
- **Layout:** single centered column, card-based, fully responsive (mobile-first — most traffic is the Instagram bio link)

Each page is self-contained: all CSS is inline in a `<style>` block. No external stylesheets, no dependencies.

---

## Deploying to Netlify

### If this repo is connected to Netlify (recommended)
1. Commit and push changes to the main branch.
2. Netlify auto-detects the push and redeploys within a minute or two.
3. No build command needed — publish directory is the repo root.

### If deploying by drag-and-drop
1. Download / clone this repo as a folder.
2. Netlify dashboard → your site → **Deploys** → drag the whole folder onto the deploy area.
3. Each drag replaces the entire site, so always include every page in the folder.

**Netlify settings:** Build command = *(none)*. Publish directory = `/` (root).

---

## Before going live — placeholders to fill

Some links are intentionally left as placeholders. Search the files for `#PASTE`, `#EBOOK`, `#BUNDLE`, `#SCENES`, `#STORE`, `#RESOURCES`, `#CREATOR` and replace with real URLs.

### `hub.html`
- `#EBOOK-GUMROAD-LINK` — the ebook checkout
- `#BUNDLE-GUMROAD-LINK` — the Creator System bundle
- `#SCENES-GUMROAD-LINK` — Fifty Cinematic History Scenes
- `#STORE-GUMROAD-LINK` — Gumroad store / profile
- `#RESOURCES-PAGE-LINK` — the live URL of `resources.html` once deployed

### `resources.html`
- 14 × `#PASTE-AMAZON-LINK` — one Amazon affiliate link per book
- `#PASTE-ELEVENLABS-LINK` — ElevenLabs affiliate link
- `#CREATOR-SYSTEM-LINK` — the Creator System bundle

### `index.html` (sampler)
- The Kit form is embedded via `<script ... data-uid="ad32b06c50" ...>`. The form's fields, wording, and styling are configured **in Kit**, not here — editing the form in Kit updates the page automatically.

### All pages
- The footer Facebook link points to `facebook.com/historyaiillustration`. Update it once the correct/working Facebook URL is confirmed.

---

## The Kit form (sampler signup)

- The sampler page loads a Kit (ConvertKit) form by its embed script.
- **Form appearance, wording, fields, and the sampler delivery are all managed inside Kit** — not in this repo. To change how the form looks or what it says, edit the form in Kit; the page picks up changes automatically.
- Double opt-in is on: subscribers get a confirmation email, then the sampler PDF.

---

## Testing checklist before sharing a page

- [ ] Open the live URL in a private/incognito window (not cached).
- [ ] Sampler: enter a test email → confirm → the sampler PDF actually arrives.
- [ ] All buttons/links go to the right place (no `#PASTE` placeholders left).
- [ ] Looks right on a phone (most visitors arrive from the Instagram bio).

---

## Notes

- Keep the two audiences separate: history links (sampler, ebook, book recommendations) vs. creator links (the Creator System). The hub groups them into sections for this reason.
- Affiliate/Amazon links live only on `resources.html` (never in emails or PDFs — Amazon's terms).
- These are static files. There's no server, database, or secrets in this repo — safe to keep public.

---

*HAISTRY — AI-illustrated history.*
