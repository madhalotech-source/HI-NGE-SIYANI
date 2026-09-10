# API Architecture

## Design Principles

- All client-server communication is REST over HTTPS, called from Delphi using `TNetHTTPClient`.
- Supabase auto-generated REST endpoints (PostgREST) are used for straightforward CRUD; **Edge Functions** are used wherever guidance logic, confidence scoring, or cross-table orchestration is required.
- Firebase is accessed via its REST API for Realtime Database reads/writes tied to live chat state and notifications.
- Every endpoint enforces auth via the Supabase session token attached as a bearer header.

## Core Endpoints (MVP)

| Method | Endpoint | Purpose | Status |
|---|---|---|---|
| POST | `/auth/v1/token` | User login (Supabase Auth) | Working |
| POST | `/auth/v1/signup` | User registration | Working |
| GET/PATCH | `/rest/v1/profiles` | Read/update user profile (name, age, province, status, language) | Working |
| POST | `/rest/v1/focus_areas` | Save selected life-area focus | Working |
| POST | `/functions/v1/guidance` | Submit a message, receive personalised guidance + confidence score | In Progress |
| GET | `/rest/v1/guidance_history` | Retrieve a user's prior guidance sessions | Working |
| DELETE | `/rest/v1/profiles/:id` | User-initiated full data deletion | Working |
| POST/GET | Firebase RTDB `/chat/:sessionId` | Live chat state sync | In Progress |
| POST | `/functions/v1/reminders` | Create/manage reminders | Coming Soon |

## `/functions/v1/guidance` — Request/Response Shape

```json
// Request
{
  "user_id": "uuid",
  "message": "I want to apply for a bursary",
  "language": "xts",
  "focus_areas": ["education", "government_services"]
}
```

```json
// Response
{
  "response_text": "...",
  "confidence": 0.82,
  "needs_clarification": false,
  "suggested_actions": [
    { "type": "bursary_match", "title": "..." }
  ]
}
```

When `confidence` falls below the configured threshold, `needs_clarification` is `true` and `response_text` contains a clarifying question instead of a guidance answer.

## Versioning & Stability

The API is pre-v1 during the hackathon phase — breaking changes are expected and tracked via commit messages and the [Sprint Plan](17-sprint-plan.md), not a formal versioning scheme yet. Formal API versioning is **Coming Soon** ahead of any external partner integration.
