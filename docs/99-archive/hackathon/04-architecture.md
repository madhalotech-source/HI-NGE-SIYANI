# Software Architecture

## Overview

HI NGE SIYANI follows a **thin native client, service-based backend** architecture. The Delphi FMX client never talks directly to a database — every request goes through REST APIs (Supabase) or the Firebase REST/SDK layer, keeping business logic on the server and the client focused on presentation and interaction.

```
┌─────────────────────────────┐
│   Delphi 12 FMX Client       │
│   (Android)                  │
└──────────────┬───────────────┘
               │ REST (TNetHTTPClient)
               ▼
┌───────────────────────────────────────────┐
│           Supabase                         │
│  ┌───────────────┐   ┌──────────────────┐  │
│  │ Auth           │   │ PostgreSQL        │  │
│  └───────────────┘   │ (RLS enabled)     │  │
│  ┌───────────────┐   └──────────────────┘  │
│  │ Edge Functions │◄── LLM Reasoning Layer  │
│  └───────────────┘    (multilingual,        │
└───────────────────────┘  confidence-scored) │
               │                               │
               ▼                               │
┌───────────────────────────────────────────┐ │
│        Firebase Realtime Database          │◄┘
│  (live chat state, push notifications)      │
└───────────────────────────────────────────┘
```

## Client Layer — Delphi 12 FMX

The Android client follows patterns proven across MAD HALO Technologies' prior Delphi FMX builds (MoveRides, BeburaSuperApp):

- **`TNetHTTPClient` for all REST calls** — no Indy components, avoiding historic threading and SSL friction.
- **Singleton session management** — a shared `database_u` unit holds the authenticated session, current user profile, and selected language, accessible across forms/frames without prop-drilling.
- **`TTabControl` with `TabPosition = None`** for primary navigation — swipeable, state-preserving, and avoids the overhead of multiple `TForm` instances.
- **Frame-based screens, not `Application.CreateForm`** — screens are `TFrame` descendants loaded into a host container, keeping memory use predictable on lower-end Android devices.
- **A custom navigation interface** (`ISiyaniNavigator`, following the `IAppNavigator` pattern from BeburaSuperApp) decouples frames from each other to avoid circular unit references.

## Backend Layer — Supabase

- **PostgreSQL** stores structured, relational data: user profiles, life-area selections, guidance history, opportunity records (bursaries, funding programmes).
- **Row-Level Security (RLS)** enforced on every table — a user can only read/write their own records.
- **Supabase Auth** handles sign-up, login, and session tokens consumed by the Delphi client.
- **Edge Functions** host the guidance logic: they receive a user message, call the LLM reasoning layer, and return a structured response plus a confidence score.

## Real-Time Layer — Firebase

- **Firebase Realtime Database** carries live conversation state and push notifications for the optional Reminder Centre (**Coming Soon** for full reminder delivery).
- Chosen because it is proven in MAD HALO's existing Android delivery pipeline, minimising new integration risk during the hackathon window.

## AI / Language Layer

- A confidence-scored reasoning layer interprets user intent per language.
- Below a confidence threshold, the system returns a clarifying-question response instead of a guessed answer — implemented as explicit branching logic in the Edge Function, not left to the model alone.

## Why This Stack

Every technology choice reflects what the founding team can execute correctly within the hackathon timeline, not a hypothetical ideal stack. Flutter, a full web platform, and iOS are intentionally deferred — see [Future Expansion Plan](11-future-expansion.md).
