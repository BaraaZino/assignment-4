# Technical Documentation

## Overview
Assignment 4 delivers the production-ready version of my single-page portfolio. It preserves the proven foundations from earlier assignments (personalization, GitHub feed, countdown, validation, documentation) and focuses on polish, accessibility, and deployment readiness.

## Architecture
- `index.html` defines semantic sections for About, Experience, Spotlight, Projects & Research, GitHub activity, Skills, the “I Can Help You With” services overview, Awards, Countdown, and Contact.
- `css/styles.css` hosts the end-to-end design system built on CSS custom properties, Flexbox, and Grid, including styles for spotlight toggles, GitHub cards, services grid, countdown timer, forms, and reveal animations.
- `js/script.js` bundles each interaction into an isolated module that initializes on `DOMContentLoaded` (theme toggle, personalization, spotlight, project controls, GitHub fetcher, countdown, contact form validation, etc.).
- `assets/images/` contains hero/project imagery, while `presentation/` stores the slide deck and demo video placeholders needed for submission packaging.

## Responsive Design Strategy
- CSS Grid powers experience cards, awards, services grid, project gallery, GitHub feed, and countdown segments so layouts adapt naturally.
- Flexbox manages header alignment, hero CTAs, contact form layout, and footer spacing.
- Media queries at 900px and 600px collapse the hero into a single column, wrap navigation links, and adjust spacing for phones.
- Typography leverages `clamp()` plus relative units to remain legible across devices.

## JavaScript Features
- **Theme toggle:** Persists light/dark preference, syncs with OS settings, and updates instantly.
- **Personalization module:** Stores a visitor's preferred name, reflects it in greetings, and injects it into the contact form when possible.
- **Spotlight tabs:** Accessible buttons (`aria-selected`, `aria-controls`) animate between focus-area cards.
- **Project cards:** Accordions expose extra project details while `localStorage` tracks grid sorting and visibility preferences.
- **GitHub feed:** Fetches `https://api.github.com/users/baraazino/repos?sort=updated&per_page=5`, caches responses for three minutes, and surfaces status updates for loading/error/cached states.
- **Graduation countdown:** Runs a one-second interval to compute remaining days/hours/minutes/seconds until April 2027 and clamps at zero afterward.
- **Contact form safeguards:** Inline validation, animated feedback, and polite error copy protect against bad submissions without blocking accessibility.
- **Reveal animations & footer autoupdate:** Sections fade in via `IntersectionObserver`, and the footer year stays current automatically.

## API Integration
- Only the GitHub feed calls external data, so no backend is required. Requests include the `application/vnd.github+json` header to receive metadata such as topics.
- Responses are cached client-side; clicking the refresh button bypasses the cache intentionally when needed.
- Failures (network, rate-limit, empty data) update a status banner so the UI never appears broken.

## Performance Considerations
- Lazy-loaded images, async decoding, and a lean asset footprint keep First Contentful Paint low.
- DOM writes batch via `DocumentFragment` in both the GitHub feed renderer and the project sorter to minimize layout thrash.
- Event listeners are scoped to specific modules, and most state (theme, personalization, project preferences) resides in `localStorage` to avoid unnecessary recompute.
- Local caching of the GitHub feed limits API calls; everything else executes locally without third-party libraries.

## Accessibility Considerations
- Semantic landmarks (`header`, `nav`, `main`, `section`, `footer`) provide a logical reading order.
- `aria-live` regions announce greeting updates, GitHub status, and form feedback in assistive tech.
- Spotlight tabs, project accordions, and theme toggles expose clear focus outlines and ARIA attributes for state.
- Inputs respect native validation plus descriptive error copy; reduced-motion users still see content thanks to IntersectionObserver fallbacks.

## Running Locally
Open `index.html` directly or serve the repository with a lightweight HTTP server (e.g., `python -m http.server`). No bundlers or package installs are required.

## Testing and Validation
- Resized the viewport to confirm responsive breakpoints across hero, grid sections, GitHub feed, and countdown.
- Exercised personalization storage, greeting updates, and contact form prefills (including clearing preferences).
- Triggered spotlight controls, project accordions, sorting, and section visibility toggles via keyboard + pointer to confirm focus handling.
- Verified GitHub feed flows: initial load, cached replay, forced refresh, and offline error messaging.
- Advanced the system clock to ensure the countdown clamps at zero, then displays celebratory copy.
- Confirmed contact form validation states (value missing, type mismatch, min length) and success messaging animations.
- Checked that presentation artifacts resolve in the `presentation/` directory for packaging.
