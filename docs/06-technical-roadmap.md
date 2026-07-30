# Technical Roadmap

## Phase 1 — MVP (Current)

| Component | Status |
|---|---|
| Delphi 12 FMX Android client (onboarding, language selection, chat UI) | In Progress |
| Supabase schema (users, profiles, focus areas, guidance history) | Working |
| Supabase Auth integration | Working |
| Supabase Edge Function: guidance reasoning endpoint | In Progress |
| Firebase Realtime DB: live chat state | In Progress |
| Confidence-scoring & clarification fallback logic | In Progress |
| GitHub repository, CI hygiene, commit discipline | Working |

## Phase 2 — Expansion — **Coming Soon**

- Migrate reminder logic from basic local notifications to full Firebase Cloud Messaging push
- Introduce a Python microservice for AI-assisted opportunity-matching (bursary/funding recommendation scoring)
- Begin Flutter proof-of-concept alongside the Delphi app (not a replacement until parity is proven)
- Expand Edge Functions to cover Finance and Healthcare Information guidance logic
- Add automated integration tests around Edge Function responses (see [Testing Strategy](15-testing-strategy.md))

## Phase 3 — Platform — **Coming Soon**

- Full web client (React or equivalent) sharing the same Supabase/Firebase backend
- iOS client via Flutter, once Android parity and stability are proven
- Formal API contracts for government/NGO partner integrations
- Multi-region Supabase/Firebase configuration for national scale
- Dedicated DevOps pipeline: staging environment, automated deployment, monitoring/alerting

## Guiding Principle

Each phase only begins once the previous phase's "Working" items are genuinely stable in production use — not simply demoed once. Technical debt introduced under hackathon time pressure is tracked, not hidden.
