# Database Design

## Engine

PostgreSQL via Supabase, with Row-Level Security (RLS) enabled on every user-scoped table.

## Core Tables (MVP)

### `profiles`

| Column | Type | Notes |
|---|---|---|
| id | uuid (PK, FK → auth.users) | |
| full_name | text | |
| age | int | |
| province | text | |
| status | text | e.g. learner, student, entrepreneur, employed, pensioner |
| preferred_language | text | ISO-style code, e.g. `xts`, `zul`, `eng` |
| created_at | timestamptz | |

### `focus_areas`

| Column | Type | Notes |
|---|---|---|
| id | uuid (PK) | |
| user_id | uuid (FK → profiles.id) | |
| area | text | `education` \| `government_services` (Phase 2+: `finance`, `healthcare`, etc.) |
| selected_at | timestamptz | |

### `guidance_sessions`

| Column | Type | Notes |
|---|---|---|
| id | uuid (PK) | |
| user_id | uuid (FK → profiles.id) | |
| message | text | User's input |
| response | text | Siyani's response |
| confidence_score | numeric | 0.0–1.0 |
| needs_clarification | boolean | |
| created_at | timestamptz | |

### `opportunities` (reference data)

| Column | Type | Notes |
|---|---|---|
| id | uuid (PK) | |
| type | text | `bursary` \| `funding` \| `tvet` \| `university` |
| title | text | |
| province | text | nullable = national |
| eligibility_criteria | jsonb | |
| deadline | date | nullable |
| source_url | text | |

### `reminders` — **Coming Soon**

Planned columns: `id`, `user_id`, `related_opportunity_id`, `remind_at`, `channel` (push/email), `status`.

## Row-Level Security

- `profiles`: a user may only `SELECT`/`UPDATE`/`DELETE` where `id = auth.uid()`.
- `focus_areas`, `guidance_sessions`: a user may only access rows where `user_id = auth.uid()`.
- `opportunities`: publicly readable (reference data), writable only via service role (admin/content team).

## Firebase Realtime Database (supplementary)

Used only for ephemeral/live data, not source-of-truth records:

```
/chat/{sessionId}/messages/{messageId}
/notifications/{userId}/{notificationId}   // Coming Soon
```

All persistent guidance history remains in PostgreSQL; Firebase is not treated as a system of record.
