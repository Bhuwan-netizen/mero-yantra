# Mero Yantra Technologies — Website

A single-page company website, built as one self-contained `index.html`.
Everything (CSS, JavaScript, and the logo images) is embedded in that one
file, so it works by double-clicking it locally and by uploading it to any
host — no build step, no dependencies.

---

## Files

| File | What it is |
|---|---|
| `index.html` | **The website.** This is the only file you need to publish. |
| `assets/logo-mark.png` | Just the "MY" monogram, transparent background |
| `assets/logo-full.png` | Full logo, transparent background |
| `assets/logo-full-light.png` | Full logo in white/red, for dark backgrounds |
| `assets/mark-light.png` | Monogram in white/red, for dark backgrounds |

The `assets/` folder is a bonus — the site does not need it, since the logos
are already embedded inside `index.html`. Keep it for your business cards,
social profiles, invoices and email signatures.

---

## ⚠️ Placeholders you must replace before going live

I did not have your real contact details, so the following are stand-ins.
Open `index.html` in any text editor (Notepad++, VS Code) and use
Find & Replace:

| Find | Replace with |
|---|---|
| `+9779800000000` | your mobile, no spaces (used in `tel:` links) |
| `+977 98-0000 0000` | your mobile, as you want it displayed |
| `+97723000000` and `+977 23-000000` | your landline |
| `info@meroyantra.com.np` | your real email address |
| `Main Road, Birtamode-04` | your exact street address |
| `Sunday – Friday, 10:00 AM – 6:00 PM` | your real office hours |

Also update:

- **Social links** — in the footer, the four `<a href="#" class="social-icon">`
  links are Facebook, Instagram, LinkedIn and WhatsApp. Replace each `#` with
  your real profile URL.
- **Privacy Policy / Terms** — footer links currently point to `#`.

---

## The contact form

There is no backend, so the form currently opens the visitor's email app with
their enquiry pre-filled. That works, but many visitors will drop off.

To receive enquiries properly, pick one of these (both have free tiers):

1. **Web3Forms** (`web3forms.com`) or **Formspree** (`formspree.io`) — sign up,
   get an endpoint URL, then set `<form action="YOUR_URL" method="POST">` and
   delete the `form.addEventListener('submit', ...)` block at the bottom of
   `index.html`.
2. **Your own PHP script**, if your hosting supports it — point the form's
   `action` at it the same way.

---

## Putting it online

Any of these will work. Options 1 and 2 are free:

1. **Netlify** — go to `app.netlify.com/drop` and drag the folder in. Live in
   about ten seconds, free HTTPS included.
2. **GitHub Pages** — push the folder to a repository, then Settings → Pages.
3. **cPanel hosting in Nepal** — upload `index.html` into `public_html/`.
   Providers like Babal Host, Himalayan Host or AGM Web Hosting sell
   `.com.np` hosting locally.

For a `.com.np` domain: registration is free through Mercantile
Communications (`register.com.np`), but it requires business registration
documents. A `.com` domain is faster if you're in a hurry.

---

## Design system

Bright, colourful and light — built around the exact colours in your logo.
All values are CSS variables at the top of the `<style>` block, so changing
one line recolours the whole site.

| Token | Hex | Where |
|---|---|---|
| `--clr-navy` | `#031E55` | Headings, "Mero", nav, primary button — straight from your logo |
| `--clr-red` | `#d70417` | "Yantra", CTA button, accents — straight from your logo |
| `--clr-blue` / `--clr-blue-light` | `#2a5298` / `#4a86e8` | Gradient icons, hover states |
| `--clr-purple` / `--clr-violet` | `#8a2be2` / `#a855f7` | Gradient text and glows |
| `--clr-cyan` / `--clr-teal` | `#06b6d4` / `#14b8a6` | Service and industry icons |
| `--clr-amber` / `--clr-pink` | `#f59e0b` / `#ec4899` | Service and industry icons |
| `--bg` / `--bg-soft` / `--bg-lav` | `#ffffff` / `#f4f8ff` / `#faf7ff` | Alternating section backgrounds |
| `--ink` / `--muted` | `#0b1a3a` / `#5a6a8a` | Body and secondary text |

Fonts are Outfit (headings) and Inter (body), from Google Fonts. Both are
free for commercial use.

**Buttons are flat** — solid fill, no glow. They lift slightly and change
colour on hover, nothing more.

**Animations:** animated gradient text (`shine`), five drifting pastel colour
spheres in the hero, a rotating halo and dashed orbit rings behind the logo,
floating badges, scroll-reveal via IntersectionObserver (`.reveal`,
`.reveal-up`, `.reveal-scale` with `.reveal-delay-1…5`), a looping technology
marquee, and lift-on-hover cards with a coloured top bar. All of it is
disabled automatically for visitors who have "reduce motion" turned on.

**Services grid:** 4 across on desktop, 3 on large tablets, 2 from 900px down
(including all phones).

---

## Sections, in order

Header → Hero (logo centrepiece) → Guarantees strip → Services (8) →
Industries (8) → About → Process (5 steps) → Technologies → Call to action →
Contact → Footer

Everything is responsive down to 360px, works without JavaScript for the
core content, and includes SEO meta tags plus `LocalBusiness` structured
data for Google.
