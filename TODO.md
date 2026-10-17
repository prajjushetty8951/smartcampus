# Smart Campus AI — Delivery Checklist

## Application shell and visual system
- [ ] Responsive React/Vite application loads through the configured Preview port.
- [ ] Landing page contains brand identity, responsive navigation, animated hero copy, Ask Campus AI CTA, chat preview, campus visual panel, feature overview, campus information preview, events preview, and footer links.
- [ ] Dark/light mode is persistent, accessible, system-aware on first visit, and consistent across pages.
- [ ] Mobile-first layouts work without unintended horizontal scrolling and include touch-friendly controls.
- [ ] Motion has reduced-motion fallbacks and does not block access to information.

## Student workflows
- [ ] Student dashboard shows a personalized greeting, today's timetable, assignments/exams, announcements, events, quick links, AI entry point, and notifications.
- [ ] Chat interface supports text questions, suggested prompts, follow-up context, typing state, clear/retry/copy actions, source references, and a demo fallback when no LLM is configured.
- [ ] Campus directory supports searchable facilities, location details, verified building markers/labels, directions links where available, and a directory fallback when maps are unavailable.
- [ ] Events and announcements support search, category/status filters, sort controls, detail views, priority labels, and official-link affordances.
- [ ] Assignments/exams support upcoming/overdue filters, status tracking, dates, and reminder preferences.
- [ ] Lost-and-found supports lost/found reports, categories, descriptions, general locations, filtering, status, and safe contact/claim affordances without sensitive public details.
- [ ] Faculty directory supports search, department filters, office location/hours, and verified contact details.
- [ ] Settings supports profile, language, theme, notifications, accessibility, chat privacy/history controls, and sign-out.

## Trust, integration, and documentation
- [ ] Demo records are clearly labeled and are separate from production data concepts.
- [ ] Frontend uses a backend boundary for AI and documents a Flask/Firebase/LLM integration contract.
- [ ] Missing Firebase, Maps, speech, or LLM configuration produces graceful guidance instead of fabricated success.
- [ ] Route manifest covers all application pages.
- [ ] README and `.env.example` document local setup, demo behavior, testing, and production integration.
- [ ] Build and critical interaction checks pass before checkpoint.
