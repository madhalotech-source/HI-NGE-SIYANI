# HI NGE SIYANI

**Building Together. Rising Together.**
*No one gets left behind.*

Developed by **MAD HALO Technologies**

---

## What is HI NGE SIYANI?

HI NGE SIYANI is South Africa's first multilingual AI-powered digital ecosystem, built around a conversational assistant named **Siyani**. Instead of citizens navigating dozens of separate websites and offices, Siyani becomes one trusted place to get personalised guidance on:

- Education
- Government Services
- Employment
- Finance
- Healthcare Information
- Entrepreneurship Support
- Community Opportunities

This repository contains the MVP prototype, backend services, and full project documentation prepared for hackathon submission.

> **Status:** Active hackathon build. Features not yet implemented are explicitly labelled **Coming Soon** throughout this documentation — nothing described here is claimed as complete unless it is.

## Hackathon Demo Scope

The live MVP demo focuses on two verticals, built deep rather than wide:

- **Education** — bursary matching, TVET & university guidance, career direction
- **Government Services** — funding/grant guidance, business registration walkthroughs

All other verticals are part of the long-term vision and are marked **Coming Soon** in the [Product Roadmap](docs/05-product-roadmap.md).

## Tech Stack (MVP)

| Layer | Technology |
|---|---|
| Client (Android) | Delphi 12 FMX |
| Structured data & Auth | Supabase (PostgreSQL + Supabase Auth) |
| Real-time & notifications | Firebase Realtime Database |
| Networking | REST APIs via `TNetHTTPClient` |
| Version control | Git + GitHub |
| Future AI services | Python |

Future platforms (Flutter, Web, iOS) are documented in [Future Expansion Plan](docs/11-future-expansion.md) as **Coming Soon**.

## Repository Structure

```
HI-NGE-SIYANI/
├── README.md
├── docs/                      # All project & hackathon documentation
├── github-guide/              # Step-by-step GitHub tutorial
├── src/
│   ├── android/                # Delphi 12 FMX client project
│   └── backend/
│       ├── supabase/           # SQL schema, RLS policies, Edge Functions
│       └── firebase/           # Realtime DB rules & config
├── assets/
│   └── brand/                  # Logo, color palette, brand assets
└── .github/                     # Issue templates, workflows (Coming Soon)
```

## Documentation Index

| # | Document |
|---|---|
| 1 | [Project Vision](docs/01-vision.md) |
| 2 | [Project Mission](docs/02-mission.md) |
| 3 | [Executive Summary](docs/03-executive-summary.md) |
| 4 | [Software Architecture](docs/04-architecture.md) |
| 5 | [Product Roadmap](docs/05-product-roadmap.md) |
| 6 | [Technical Roadmap](docs/06-technical-roadmap.md) |
| 7 | [User Personas](docs/07-user-personas.md) |
| 8 | [Demo Script](docs/08-demo-script.md) |
| 9 | [Investor Pitch Deck (outline)](docs/09-investor-pitch.md) |
| 10 | [System Requirements](docs/10-system-requirements.md) |
| 11 | [Future Expansion Plan](docs/11-future-expansion.md) |
| 12 | [API Architecture](docs/12-api-architecture.md) |
| 13 | [Database Design](docs/13-database-design.md) |
| 14 | [Risk Assessment](docs/14-risk-assessment.md) |
| 15 | [Testing Strategy](docs/15-testing-strategy.md) |
| 16 | [Security Strategy](docs/16-security-strategy.md) |
| 17 | [Sprint Plan](docs/17-sprint-plan.md) |
| 18 | [Project Timeline](docs/18-project-timeline.md) |

## Getting Started (Development)

1. Clone the repository: `git clone https://github.com/<your-username>/HI-NGE-SIYANI.git`
2. Open `src/android` in **Delphi 12 Athens (or later)**.
3. Copy `.env.example` (Coming Soon) into your Supabase and Firebase project keys.
4. Build and run on an Android target device or emulator.

New to GitHub? Start with [`github-guide/GITHUB_TUTORIAL.md`](github-guide/GITHUB_TUTORIAL.md) — it walks through repo creation, commits, branches, and releases from zero.

## License

Coming Soon — license to be finalised before public release.

## Company

**MAD HALO Technologies** — a South African software and digital transformation studio.
