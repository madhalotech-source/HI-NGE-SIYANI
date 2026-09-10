# System Requirements

## Functional Requirements (MVP)

| ID | Requirement | Status |
|---|---|---|
| FR-1 | User can select a language before onboarding | Working |
| FR-2 | User can complete onboarding (name, age, province, status) | Working |
| FR-3 | User can select one or more focus areas (Education, Government Services) | Working |
| FR-4 | System returns personalised guidance based on user context | Working |
| FR-5 | System asks a clarifying question when confidence is below threshold | In Progress |
| FR-6 | User can opt into reminders | Coming Soon |
| FR-7 | User can delete their stored information on request | Working |
| FR-8 | System supports Finance & Healthcare guidance | Coming Soon |

## Non-Functional Requirements

- **Performance:** Guidance responses should return within 3–5 seconds under normal network conditions on the hackathon demo network.
- **Availability:** Demo build targets stability for the judging window; formal SLA targets are **Coming Soon** for a production release.
- **Localisation:** All UI strings and AI responses must support runtime language switching without app restart.
- **Data protection:** All personal data handling must align with POPIA principles (see [Security Strategy](16-security-strategy.md)).
- **Device support:** Android 10+ (API level 29+), tested on mid-range devices representative of the target user base — not flagship-only.

## Development Environment

- Delphi 12 Athens (or later) with FMX Android platform support installed
- Supabase project (free tier sufficient for MVP)
- Firebase project (free/Spark tier sufficient for MVP)
- Git 2.30+, GitHub account
- Python 3.10+ (for future AI microservice work — **Coming Soon**)

## Out of Scope for MVP

Voice interaction, full 11-language support, Web/iOS clients, and formal government API integrations are explicitly out of scope for the hackathon MVP and documented separately in [Future Expansion Plan](11-future-expansion.md).
