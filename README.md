# Housy Media — Order Page CSS Makeover

A custom-CSS makeover for the HDPhotoHub (hd.pics) order page at
**https://housymedia.hd.pics/order**.

HDPhotoHub lets site owners inject custom CSS into the shopping cart /
order form, so this repo ships a single stylesheet you paste into your
dashboard — no code changes on the platform side.

| Before (stock) | After (makeover) |
|---|---|
| ![Before](docs/before.png) | ![After](docs/after.png) |

*Screenshots are from `preview/index.html`, a mock of a typical hd.pics
order form built on stock Bootstrap.*

## What the makeover does

- **Typography** — loads the Inter webfont; tighter, bolder headings.
- **Color system** — one `:root` block of CSS variables controls the whole
  palette (brand blue, ink, muted text, page background, borders).
- **Cards & panels** — soft rounded corners, hairline borders, layered
  shadows with a gentle hover lift; selected services get a brand-tinted
  highlight.
- **Buttons** — solid brand primary with hover glow, quiet white secondary,
  press feedback, visible focus rings.
- **Forms** — thicker friendly borders, rounded inputs, brand-colored focus
  ring, branded checkboxes/radios via `accent-color`.
- **Order summary** — uppercase table headers, tabular-numeral prices,
  hover-tinted rows.
- **Chrome** — crisp white navbar, softened modals/dropdowns, subtle
  scrollbar, brand-colored text selection.

## Install

1. Open your HDPhotoHub dashboard → **Settings → Shopping Cart** (design /
   custom CSS section).
2. Paste the full contents of [`css/order-makeover.css`](css/order-makeover.css)
   into the custom CSS field. If your dashboard only offers a custom
   `<head>` HTML field, wrap the CSS in `<style> … </style>`.
3. Save and reload `https://housymedia.hd.pics/order`.

## Re-branding

All design decisions live at the top of the stylesheet:

```css
:root {
  --hm-brand:      #1d4ed8;  /* primary buttons & links */
  --hm-brand-dark: #1e40af;  /* hover state */
  --hm-brand-soft: #eff4ff;  /* tinted highlights */
  --hm-page-bg:    #f5f7fb;  /* page background */
  --hm-radius:     14px;     /* card rounding */
  ...
}
```

Change those values to match the Housy Media brand and everything —
buttons, focus rings, highlights, badges — follows.

## Local preview

Open `preview/index.html` in a browser. It is a stand-alone mock of the
order form (stock Bootstrap 5 + the makeover). Comment out the
`order-makeover.css` `<link>` in that file to compare against the stock
look.

## Notes / limitations

This stylesheet targets standard Bootstrap classes (`.card`, `.btn`,
`.form-control`, `.list-group-item`, `.table`, …), which is what the
hd.pics cart is built on. If a specific element on the live page doesn't
pick up a style, grab its exact class/ID from the browser dev tools and
add a matching rule — the variables make one-off overrides trivial.
