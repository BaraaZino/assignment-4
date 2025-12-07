# AI Usage Report

## Tools Used
- **ChatGPT-5 Codex:** Primary collaborator for ideation, code generation, debugging, accessibility checks, and documentation review across Assignments 2–4.


## Detailed Log

### 1. Spotlight Section Copy & Interaction Plan
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Suggest an interactive way to let visitors switch between different focus areas on my portfolio front page. Provide button labels, short descriptions, and any accessibility considerations.”  
- **AI Output (excerpt):**
  > Use three pill-style buttons (About Me, Projects, Goals). Each button should toggle a short paragraph. Bind `aria-controls`/`aria-selected` for accessibility and animate the content transition for clarity.
- **Edits & Integration:** I adopted the button labels and copy as the default text in `index.html`, then coded the toggles in `js/script.js` (`Spotlight` module) with custom styling in `css/styles.css`.  
- **What I Learned:** Reinforced how to wire accessible tab patterns (matching buttons to panels with `aria` attributes) and animate content changes smoothly.

### 2. Contact Form Validation Flow
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Help me upgrade a contact form: I need inline validation errors, `aria-invalid` support, and animated feedback that highlights success versus error states.”  
- **AI Output (excerpt):**
  > Use `aria-invalid` when fields fail `checkValidity()`, surface error text near each input, and animate the status banner so users notice it without resorting to intrusive alerts.
- **Edits & Integration:** Implemented the inline error system, `aria-invalid` styling, and animated feedback as suggested. I adapted the recommended copy to match my tone and kept the logic modular for future enhancements.  
- **What I Learned:** Picked up a cleaner pattern for keeping validation logic modular and discovered how a quick animation on status messages dramatically improves perceived responsiveness.

### 3. Documentation & Comment Placeholders
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Draft an outline for the README and technical documentation that highlights new Assignment 2 features. Include reminders to add personal comments later.”  
- **AI Output (excerpt):**
  > Add sections for Assignment 2 enhancements, mention `localStorage` data handling, and call out where comment placeholders exist so graders know they’re intentional.
- **Edits & Integration:** Expanded the README and `docs/technical-documentation.md` with customized text, elaborated on testing details.  
- **What I Learned:** Better appreciation for documenting interactive features explicitly and making it clear how AI participated in the workflow.

### 4. Assignment 3 Scope & Feature Map
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Help me plan Assignment 3 so it satisfies the rubric (API integration, complex logic, state management, countdown, AI report). Suggest which files should change and why.”  
- **AI Output (excerpt):**  
  > Add a new GitHub activity section below Projects, wire a fetch module, reuse DocumentFragment for rendering, and expand docs to explain the new modules plus AI usage.  
- **Edits & Integration:** Used the plan to prioritize HTML structure changes (project controls, GitHub feed container, countdown section) before touching CSS/JS.  
- **What I Learned:** Mapping rubric bullets directly to components up front keeps the implementation and documentation aligned.

### 5. GitHub API Feed + Project Controls
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Generate vanilla JS modules to (a) fetch my latest GitHub repos with cached responses and (b) add sortable, hideable project cards with persistent state. Include friendly error handling.”  
- **AI Output (excerpt):**  
  > Create a `GitHubFeed` module with a `CACHE_WINDOW_MS` constant, reuse `DocumentFragment`, and toggle a status banner for loading/error states. For the project grid, read/write `localStorage`, reorder nodes with `appendChild`, and expose a hide/show toggle for the section.  
- **Edits & Integration:** Adapted the response to existing naming conventions, swapped in my GitHub username, added a refresh button, and pared the controls down to sorting plus a visibility toggle per the latest requirements.  
- **What I Learned:** Reinforced how to keep DOM updates cheap and how little code it takes to persist UI state once the data attributes are designed carefully.

### 6. Documentation Refresh & AI Log
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Summarize the new Assignment 3 work for README and the AI usage report. Highlight API integration, countdown, and performance tweaks.”  
- **AI Output (excerpt):**  
  > Emphasize the GitHub feed, timer, and stateful controls under ‘Highlights’, and record specific prompts/outputs in the AI log.  
- **Edits & Integration:** Rewrote the README/technical doc manually using the AI outline, then expanded this log with detailed prompts/outcomes.  
- **What I Learned:** Writing the report right after coding kept context fresh and made it easier to articulate how AI shaped each feature.

### 7. Services Section Copy & Structure (Assignment 4)
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Provide copy ideas for an ‘I can help you with’ section: three cards that describe how I collaborate with clients (AI/data, UI polish, team enablement). Keep it concise and action-oriented.”  
- **AI Output (excerpt):**  
  > Card 1: AI & Data Experiments… Card 2: Product UI Polish… Card 3: Team Enablement… Include short bullets such as “Fine-tuning LLMs,” “Component-driven HTML/CSS,” etc.  
- **Edits & Integration:** Used the AI bullets as a baseline but rewrote phrases to match my tone, added context about dashboards and documentation, and implemented the markup (`index.html`) plus styling (`css/styles.css`).  
- **What I Learned:** Having draft copy from AI speeds up ideation, but manual edits are still needed to keep the language authentic and aligned with my actual services.

### 8. Theme Toggle UX Refinement
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “How can I update my existing theme-toggle button so it swaps to ‘Light mode’ with a sun icon when dark theme is active, without breaking accessibility?”  
- **AI Output (excerpt):**  
  > Track the button, its label, and icon; update `aria-pressed`; swap text/icon inside `applyTheme`; ensure widths stay consistent.  
- **Edits & Integration:** Implemented a `updateToggleUI` helper, wired it into `applyTheme`, and tweaked CSS to give the label a fixed min-width. Also added extra header spacing per my own design eye.  
- **What I Learned:** Modularizing theme code keeps the UI synced with state, and small CSS tweaks (min-width, gap) prevent layout shifts when labels change.

### 9. GitHub Fallback Strategy
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “How should I handle GitHub API rate limits on a static site so the section still shows data? I was thinking about loading a local snapshot when the API fails.”  
- **AI Output (excerpt):**  
  > Bundle a static JSON file as a snapshot, attempt the live fetch first, and if it fails (especially with 403 rate-limit errors) render the local data instead with a friendly status message.  
- **Edits & Integration:** Added `assets/data/github-cache.json`, wired the GitHub module to load it when the live call fails, and updated the README/technical docs to explain the behavior.  
- **What I Learned:** Offering a fallback keeps the UX professional and avoids exposing transient API errors to visitors.

### 9. Presentation Outline & Storytelling
- **Tool:** ChatGPT-5 Codex  
- **Prompt:** “Help me craft a 6–7 minute presentation for this portfolio: include intro, demo beats, architecture overview, AI highlights, deep dive, conclusion, and future work.”  
- **AI Output (excerpt):**  
  > Suggested a slide-by-slide structure covering overview, objectives, live demo checklist, technical architecture, AI integration, deep dive, outcomes, future improvements, and Q&A.  
- **Edits & Integration:** Adapted the outline into my slide deck, swapped in actual screenshots, and customized bullet points with my personal motivations and results.  
- **What I Learned:** Using AI to scaffold the narrative freed up time to focus on visual polish while still keeping the story organized and within the time box.

## Benefits
- Accelerated ideation for UI/UX flows without sacrificing accessibility.
- Saved time drafting copy (spotlight blurbs, services cards, documentation scaffolding).
- Reduced back-and-forth debugging by validating approaches before coding.
- Quickly scaffolded the GitHub feed, stateful controls, countdown timer, and assignment polish without reinventing patterns.

## Challenges
- Needed to adapt AI suggestions to fit existing styling conventions and naming schemes.
- Balancing automated guidance with personal understanding took deliberate review to avoid treating outputs as black boxes.
- API-centric prompts occasionally returned fetch examples using frameworks, so I reworked them into vanilla modules.

## Learning Outcomes
- Strengthened knowledge of accessible tab patterns, accordions, inline validation strategies, cached API usage, and stateful UI management.
- Practiced turning AI-assisted drafts into production-ready copy and code while keeping accountability in the repo history.
- Documented AI usage in a reproducible format that links prompts, outputs, and final edits for transparency.
- Built confidence in mixing cached API calls, DOM fragments, timers, and new features (services section, theme toggle refinements) without external libraries.
