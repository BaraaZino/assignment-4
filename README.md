# Baraa Zino Portfolio (Assignment 4)

A polished, production-ready personal site that demonstrates the full SWE 363 toolset: responsive design, delightful UX flourishes, a persistent personalization system, live data from GitHub, and modern state management patterns.

## Highlights
- **Spotlight focus explorer:** Visitors switch between “About,” “Projects,” and “Goals” blurbs using accessible tabs that animate content swaps.
- **“I can help you with” services row:** Articulates consulting offerings with cards that complement the CTA and guide visitors toward the contact form.
- **GitHub activity feed:** Fetches the five most recently updated repositories, caches responses to stay under rate limits, and surfaces languages, topics, stars, and forks with helpful status messaging.
- **Projects dashboard:** Sort or hide the project grid via persistent preferences for a customized browsing experience.
- **Contact + personalization:** Inline validation, prefills powered by saved visitor names, and animated feedback keep the form friendly while still accessible.
- **Graduation countdown & greeting:** Time-based UI components (countdown, locale-aware greeting) showcase timers, accordions, and aria-driven state changes.
- **Theme + performance polish:** Dark/light modes sync with system preferences, while lazy-loading, DocumentFragment batching, and cached API data keep the site snappy without extra tooling.

## Live Demo
- **Production deployment:** https://baraazino.github.io/assignment-4/ (GitHub Pages)

## Project Structure
```
assignment-4/
├── README.md
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── assets/
│   └── images/
├── docs/
│   ├── ai-usage-report.md
│   └── technical-documentation.md
├── presentation/
│   ├── slides.pdf
│   └── demo-video.mp4
└── .gitignore
```

## Running Locally
No build step is required—the app is pure HTML/CSS/JavaScript.

1. Clone the repository.
2. Open `index.html` directly in a modern browser **or** run a lightweight server:
   ```bash
   cd assignment-4
   python3 -m http.server 4173
   ```
3. Visit `http://localhost:4173` and explore the interactions.

## Documentation
- `docs/technical-documentation.md` covers the architecture, responsive strategy, testing notes, and the full feature set.
- `docs/ai-usage-report.md` logs every AI-assisted task with prompts, outputs, edits, and lessons learned.

## AI Collaboration Summary
ChatGPT-5 Codex paired programming accelerated ideation and implementation for Assignment 4—especially the documentation refresh, GitHub feed enhancements, and portfolio polish. See `docs/ai-usage-report.md` for the full log per course requirements.
