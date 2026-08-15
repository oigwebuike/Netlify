# HAISTRY — Website

The public site for **HAISTRY**, an AI-illustrated history brand. Static HTML pages hosted on Netlify. No build step, no framework — just plain HTML/CSS files.

---

## Pages

| File | Purpose | Live path |
|------|---------|-----------|
| `index.html` | Link hub — the front door, "everything in one place" | `/` |
| `sampler.html` | Free sampler landing page — email signup that delivers the free sampler via Kit | `/sampler` |
| `resources.html` | Affiliate resources — the books and tools behind the stories | `/resources` |

The hub is the homepage. The sampler is reached from the **Start Here** card at the
top of the hub, and from the closing CTA on `resources.html` — both link to `/sampler`.
The sampler's masthead links back to `/`.

> Whichever page you want as the front door must be the one named `index.html`.

### Redirects

`_redirects` (Netlify) keeps old links alive:

| Old URL | Goes to | Why |
|---------|---------|-----|
| `/hub`, `/hub.html` | `/` | The hub used to live at `/hub` — **that URL is the Instagram bio link**, so it must keep resolving. |

The sampler used to be the homepage; anyone with that link now lands on the hub,
which is intended.

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

Most links are already live. What's filled and what still needs a real URL:

### `index.html` (hub) — ✅ done
All Gumroad links (ebook, bundle, scenes, store) are live, the resources card
links to `resources.html`, and the Start Here card links to `/sampler`.

### `resources.html` — ⚠️ affiliate links still needed
- 14 × `#PASTE-AMAZON-LINK` — one Amazon affiliate link per book
- `#PASTE-ELEVENLABS-LINK` — ElevenLabs affiliate link
- ✅ the Creator System link is live

### `sampler.html` — ✅ done
Both signup forms post natively to the Kit form endpoint (see below).

### All pages — ✅ done
Footer social links point to Instagram `@historyaiillustration` and the
current Facebook page URL.

---

## The Kit form (sampler signup)

The sampler page posts email signups **directly to the Kit form endpoint** —
a plain HTML form, no JavaScript embed, so it works even with JS disabled:

```html
<form action="https://app.kit.com/forms/9481638/subscriptions" method="post" target="_blank">
  <input name="email_address" type="email" required>
</form>
```

- The form's *appearance and wording* live in this repo (inline CSS/HTML).
- The *delivery* lives in Kit: the sampler PDF is sent by the form's
  **incentive email** (Kit → the form → Settings → Incentive). The PDF is not
  in this repo.
- Double opt-in is on: subscribers get a confirmation email first, then the
  sampler PDF after confirming.
- **Kit will not re-send the incentive email to an already-confirmed
  address.** To test repeatedly, delete the test subscriber in Kit
  (Grow → Subscribers) or use plus-aliases (`you+test1@gmail.com`).

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
