# Fieldwork Studio — Interactive Navigation Demo

A single-file HTML/CSS/JS demo page built around a fixed navigation bar that
changes style on scroll and on hover. The nav is wrapped in a full sample
site (hero, work grid, studio, journal, contact) so you can see it behave
against real content.

## Files

| File | Description |
|---|---|
| `sticky-nav.html` | The complete demo — open it directly in a browser, no build step required |

## Features

- **Fixed nav bar** — stays pinned to the top of the viewport at all times
- **Scroll-triggered style change** — transparent over the hero, then fades
  in a solid, blurred background with a bottom border once you scroll past it
- **Hover interactions** — nav links get an animated underline and shift to
  gold on hover; the active section is highlighted automatically as you scroll
- **Dark/light theme toggle** — the circular button in the nav flips a
  `data-theme` attribute that recolors the entire page
- **Mobile menu** — the nav collapses into a hamburger under 760px width,
  opening a full-screen link panel
- **Filterable project grid** — category buttons (Brand / Culture /
  Landscape) show and hide project cards by tag
- **Scroll-reveal animations** — cards and sections fade and slide into view
  as they enter the viewport, using `IntersectionObserver`
- **Sample photography** — placeholder images throughout (hero, project
  cards, team strip, journal thumbnails) via [Lorem Picsum](https://picsum.photos)

## How to use it

1. Open `sticky-nav.html` in any modern browser to preview it as-is.
2. To use the nav on your own site, copy out three pieces:
   - The `<nav>` and `.mobile-panel` markup
   - The related CSS (`.nav`, `.nav-links`, `.mobile-panel`, `.theme-toggle`,
     `.burger`, and the `[data-theme="dark"]` overrides)
   - The related JavaScript (`onScroll`, `sectionObserver`, `themeToggle`,
     and `burger` listeners near the bottom of the `<script>` block)
3. Update the `href` values in `.nav-links` and `.mobile-panel` to point at
   your real pages or section IDs.
4. Swap the `data-section` attributes on each link so they match the `id`
   of the sections you want highlighted while scrolling.

## Customizing

- **Colors** — all colors are CSS custom properties defined at the top of
  the stylesheet (`--ink`, `--paper`, `--gold`, `--rust`, `--teal`, etc.).
  Change the values once and everything updates, including the dark mode
  variant under `[data-theme="dark"]`.
- **Fonts** — loaded from Google Fonts (`Fraunces` for display type,
  `Inter` for body/UI text). Swap the `<link>` tag and the `font-family`
  declarations to change typefaces.
- **Photos** — every `<img>` currently points at a Lorem Picsum placeholder
  URL (e.g. `https://picsum.photos/seed/fw-1/600/800`). Replace the `src`
  with your own image paths or URLs before shipping to production.
- **Scroll threshold** — the nav switches to its "scrolled" state after
  80px of scroll. Adjust the number in the `onScroll()` function to change
  when that happens.

## Browser support

Built with standard CSS (custom properties, `backdrop-filter`, `grid`,
`clamp()`) and vanilla JavaScript (`IntersectionObserver`). Works in all
current versions of Chrome, Firefox, Safari, and Edge. No build tools,
frameworks, or dependencies beyond the Google Fonts stylesheet.

## Credits

- Photos: [Lorem Picsum](https://picsum.photos) (placeholder images, free to use)
- Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) and
  [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts
