# Places to Visit in Patan — Design

Date: 2026-08-05

## Summary

Rebuild `places.html` into a simple, responsive "Places to Visit in Patan" page
(HTML + CSS only — no JavaScript or frameworks), and replace `stylesheet.css`
with the page's stylesheet. Patan refers to **Patan (Lalitpur), Nepal**.

## Files

- `places.html` — rebuilt as the full page.
- `stylesheet.css` — replaced with the page's CSS (the only file that links it).

## Content

- **Hero**: `<h1>` "Places to Visit in Patan" + short intro paragraph + one CTA
  button ("Plan Your Visit").
- **Attractions grid**: 6 `<article>` cards, each with:
  - `<figure>` image placeholder — empty `<img>` (styled placeholder that can be
    swapped with a real photo later) + `<figcaption>`.
  - `<h3>` place name, `<p>` brief description, small location line.
  - "Learn More" link.
  - Featured: Patan Durbar Square, Krishna Mandir, Golden Temple (Hiranya Varna
    Mahavihar), Patan Museum, Mahabouddha Temple, Kumbeshwar Temple.
- **Visitor tips**: bulleted `<ul>` (entry fees, best time to visit, respectful
  dress at temples, walking/rickshaw tips).
- **Footer**: simple credits line.

## Visual Design

- **Font**: Yatra loaded from Google Fonts, applied throughout, serif fallback.
- **Palette**: beige background `#f6efe1`; deep red accent `#9a1b2e` for
  buttons, headings, small accents; warm brown text `#3d2f23`; cream card
  surface `#fffdf6`.
- **Cards**: `border-radius: 16px`, subtle layered shadow, rounded image
  placeholder (soft beige gradient + centered placeholder text).
- **Buttons**: deep red background, cream text, rounded; hover darkens + lifts.
- **Hover effects**: minimal — cards lift with a deeper shadow; buttons darken.

## Responsive Layout

- Grid: `repeat(auto-fill, minmax(280px, 1fr))` → 1 column mobile, 3 desktop.
- Flexbox for hero and tips; tips becomes two columns on wide screens.
- Fluid type via `clamp()`.
- `viewport` meta already present in `places.html`.

## Constraints

- No JavaScript, no frameworks, no external assets beyond the Google Font.
- Semantic HTML; image placeholders must be easily replaceable by changing
  `<img src>`.
