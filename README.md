# Smart Campus AI

A premium, demo-first campus operating layer for students: ask a question, find a place, keep a deadline, or discover what is happening next.

## Run locally

```bash
pnpm install
pnpm dev
```

The Preview runs on port `3000`. The production build is:

```bash
pnpm build
```

## What works without credentials

The landing page, dashboard, responsive navigation, Campus AI chat demo, source citations, campus directory, map-style fallback, event and announcement filters, assignment completion state, lost-and-found report form, faculty directory search, theme persistence, language selector, settings toggles, accessible accordion, reduced-motion CSS, empty states, and route manifest are implemented with clearly labeled sample data.

Sample records are not official campus information. The assistant says when it is in demo mode and shows sample sources. It intentionally does not claim to provide precise indoor navigation or live registration links without those integrations.

## Production integration path

The frontend is designed to call a Flask REST service through `VITE_API_BASE_URL`. See [`backend/README.md`](backend/README.md) for the endpoint contract, Firebase Authentication/Firestore/Storage setup, approved-document retrieval rules, role-based admin controls, rate limiting, and safe upload guidance. Keep all LLM, Firebase Admin, Maps server, and storage secrets on the backend.

Copy [`.env.example`](.env.example) as a checklist. `VITE_*` values are browser-visible; never put private provider keys in them.

## Accessibility and responsive behavior

The app uses semantic controls, visible focusable buttons, readable contrast, keyboard-operable accordions and menus, live chat updates, touch-friendly controls, and a `prefers-reduced-motion` fallback. The layout is tested by design for narrow mobile widths, tablet widths, and wide desktop canvases.

## Deployment notes

For a static frontend deployment, build the project and publish `dist/`. For a full deployment, run the Flask service separately and configure the frontend API base URL. Use HTTPS in production, restrict CORS to the frontend origin, and keep demo and production datasets separate. Configure Firebase, Maps, notification, speech, and LLM quotas deliberately before enabling live features.
