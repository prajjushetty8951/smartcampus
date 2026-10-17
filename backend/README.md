# Flask backend contract

The current Preview intentionally runs in demo mode so the interface is useful without paid credentials. A production deployment should place a Python Flask service behind the frontend and keep Firebase Admin credentials, LLM credentials, Maps server keys, and storage credentials on the server only.

## Suggested layout

```text
backend/
  app.py
  config.py
  extensions.py
  routes/
    auth.py
    chat.py
    campus.py
    events.py
    assignments.py
    faculty.py
    lost_found.py
  services/
    chatbot.py
    retrieval.py
    notifications.py
  tests/
```

## API surface

- `GET /api/health` — unauthenticated readiness check.
- `POST /api/chat` — authenticated student question; validates `message`, retrieves only approved source records, calls the configured provider, and returns `{ answer, sources, grounded, mode }`.
- `GET /api/campus/locations` — searchable verified locations.
- `GET /api/events` and `GET /api/announcements` — filtered public records.
- `GET /api/assignments` and `GET /api/exams` — authenticated student schedule data.
- `GET /api/faculty` — verified faculty directory.
- `POST /api/lost-found` — authenticated report submission with upload validation.
- `PATCH /api/admin/*` — administrator-only mutations, protected by Firebase token verification and server-side role checks.

The chat service should reject prompt-injection instructions found inside retrieved documents, pass only the minimum relevant context to the LLM, rate-limit expensive requests, and return a clear verification message whenever an answer cannot be grounded. Conversation storage should be opt-in and privacy-aware. CORS should be restricted to configured origins, uploads should be type/size restricted, and logs must not contain private student data.

## Local integration steps

1. Create a Python virtual environment and install Flask, Flask-CORS, Firebase Admin, Pydantic or Marshmallow, and the selected LLM SDK.
2. Copy the backend values from `.env.example` into a server-only environment file.
3. Create Firebase Authentication users and Firestore collections for `campus_locations`, `events`, `announcements`, `assignments`, `exams`, `faculty`, `lost_found`, and approved `source_documents`.
4. Add Firebase security rules so students can read only permitted records and administrators can mutate approved collections.
5. Update `VITE_API_BASE_URL` to the Flask URL and replace the frontend demo service calls with authenticated fetches.
6. Add the Google Maps JavaScript API only after billing/quotas and an approved campus coordinate set are configured.

The demo UI is not an official institutional source. Keep demo records in a separate namespace or database from production records.
