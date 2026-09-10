# Security & Privacy Strategy

## Guiding Principle

Privacy is a foundational requirement, not a feature to add later. HI NGE SIYANI is designed around **POPIA (Protection of Personal Information Act)** principles from the first schema decision.

## Data Minimisation

Only information necessary to deliver guidance is collected: name, age, province, current status, preferred language, and the content of guidance conversations. No unnecessary demographic, biometric, or financial data is requested.

## Consent

- Information is stored only after explicit user consent during onboarding.
- Consent language is presented in the user's selected language, not English-only.
- Consent status is stored per-user, not assumed.

## User Control

- Users can request full deletion of their stored information at any time (`DELETE /rest/v1/profiles/:id`, cascading to related tables).
- Users can review what Siyani knows about them — **Coming Soon**: an in-app "My Data" screen; MVP supports this via direct request/support channel.

## Access Control

- **Row-Level Security (RLS)** enforced on all user-scoped PostgreSQL tables — see [Database Design](13-database-design.md).
- Supabase Auth issues short-lived session tokens; no long-lived credentials stored on-device beyond the standard session token.
- Firebase Realtime Database rules restrict read/write access to a user's own chat session path.

## Data Transmission

- All client-server traffic uses HTTPS/TLS.
- No personal data is logged in plaintext application logs.

## Never Sold, Never Shared for Advertising

Personal information is never sold, and is never shared with third parties for advertising purposes. Any future partner data-sharing (e.g. verified opportunity feeds) will be reference data only, not personal user data.

## Coming Soon

- Formal penetration testing before any public/production release
- SOC2-style audit logging
- Data Processing Agreement templates for government/NGO partners
- Full "My Data" self-service dashboard in-app

## Incident Response — **Coming Soon**

A formal incident response plan will be documented before any production deployment beyond the hackathon demo environment.
