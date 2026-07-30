# Sprint Plan (Hackathon Window)

Given a days-long hackathon timeline, work is organised into short, focused sprints rather than multi-week cycles.

## Sprint 0 — Foundation (Day 1)

- [x] Repository structure, README, and documentation set
- [x] Supabase project setup: schema, RLS policies, Auth configuration
- [x] Firebase project setup: Realtime Database rules
- [ ] Delphi FMX project scaffold: navigation shell (`TTabControl`, `ISiyaniNavigator`), singleton session unit

## Sprint 1 — Core Onboarding Flow (Day 1–2)

- [ ] Language selection screen (5 languages)
- [ ] Onboarding form (name, age, province, status) wired to `profiles` table
- [ ] Focus-area multi-select (Education, Government Services) wired to `focus_areas` table
- [ ] Consent screen with per-language copy

## Sprint 2 — Guidance Engine (Day 2–3)

- [ ] `/functions/v1/guidance` Edge Function: message → response + confidence score
- [ ] Confidence-fallback clarification logic
- [ ] Education vertical guidance content & logic
- [ ] Government Services vertical guidance content & logic
- [ ] Chat UI in Delphi wired to the guidance endpoint

## Sprint 3 — Polish & Rehearsal (Final day)

- [ ] End-to-end testing per [Testing Strategy](15-testing-strategy.md)
- [ ] Demo script rehearsal (5+ full run-throughs)
- [ ] Backup demo recording captured
- [ ] Pitch deck and documentation final pass
- [ ] GitHub repository cleaned up: clear commit history, tagged release (see [GitHub Tutorial](../github-guide/GITHUB_TUTORIAL.md))

## Sprint Tracking

Each checklist item above should correspond to a GitHub Issue and be closed via a commit or pull request referencing it (e.g. `Closes #4`), so judges can see real, timestamped progress in the repository's commit history — not just a finished result.
