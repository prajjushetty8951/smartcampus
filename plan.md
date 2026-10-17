# Smart Campus AI — Implementation Plan

## Approach

Ship a polished demo-first vertical slice in React/Vite/TypeScript that is useful without live credentials, while keeping clear integration seams for a Flask API, Firebase, Maps, and a configurable LLM. The frontend will use realistic sample data marked as demo content and will never imply that sample campus facts are official.

## Project structure

- `src/main.tsx` — React entry point and application shell.
- `src/styles.css` — design tokens, responsive layout, motion and accessibility styles.
- `public/manus-routes.json` — route declarations for Preview and publishing.
- `backend/README.md` — Flask/Firebase/LLM integration contract and deployment notes.
- `.env.example` — browser-safe and server-side configuration checklist.
- `README.md` — setup, demo-mode behavior, testing and production integration guidance.

## Design system

**Design movement:** Neo-campus editorial / low-light control room.

**Core principles:** information density with breathing room; campus utility before decoration; calm, precise motion; visible system status at every step.

**Color philosophy:** midnight navy creates focus and trust, while mint and ultraviolet signals create a recognizable AI layer without turning the interface into a neon toy.

**Layout paradigm:** an asymmetric dashboard frame with a persistent left rail, wide hero canvas, and stacked utility modules that feel like a living campus operations map.

**Signature elements:** a mint signal line, translucent glass panels with thin borders, and small uppercase metadata labels that make every card feel operational.

**Interaction philosophy:** controls should reveal context rather than create surprise. Hover states are quiet, focus states are strong, and every action produces visible feedback or an empty/error state.

**Animation:** use short ease-out entrances, subtle orbiting background geometry, and typing/expand transitions. Respect `prefers-reduced-motion` and never make information dependent on motion.

**Typography system:** Inter for UI copy with Space Grotesk for display moments; compact uppercase labels for metadata and relaxed sentence case for explanations.

**Brand essence:** a calm AI operating layer for the everyday student — focused, intelligent, grounded.

**Brand voice:** direct, capable, warm. Example lines: “Your campus, in one clear signal.” and “Ask a better question. Get the next move.”

**Wordmark & logo:** a split-square signal mark: two offset rounded rectangles forming an open doorway around a mint pulse.

**Signature brand color:** `#9CF7EB`, Signal Mint.

## Build workflow

1. Establish the responsive shell and design tokens.
2. Add core routes and demo data.
3. Wire chat, search, filters, theme, language, and accessible accordions.
4. Add backend and integration documentation with safe fallback behavior.
5. Run typecheck/build and inspect Preview at desktop and mobile widths.
6. Commit the validated deliverable to the managed project history.
