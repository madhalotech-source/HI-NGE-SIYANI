# Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Low-resource language (Sepedi, Tshivenda, Xitsonga) responses are inaccurate | High | High | Confidence-scoring + clarification fallback; never present low-confidence output as certain |
| Judges perceive scope as unrealistic for a solo/small team | Medium | High | MVP explicitly scoped to 2 verticals; all other features labelled Coming Soon |
| Delphi FMX on Android has device-specific rendering/performance issues | Medium | Medium | Test on mid-range devices early; reuse proven patterns from MoveRides/BeburaSuperApp |
| Personal data mishandling (POPIA non-compliance) | Low | Very High | Minimal collection, consent-first storage, user-controlled deletion — see [Security Strategy](16-security-strategy.md) |
| Supabase/Firebase free-tier rate limits hit during live demo | Medium | Medium | Pre-warm connections before demo; have a recorded backup demo video as contingency |
| Single point of failure (solo developer dependency) | High | High | Documented architecture & GitHub history so any contributor can onboard quickly |
| Government/NGO data sources become unavailable or inaccurate | Medium | Medium | Reference data (`opportunities` table) reviewed and updated manually until automated sourcing is built (Coming Soon) |
| Overpromising AI capability to judges or investors | Medium | High | Every claim in documentation is labelled Working, In Progress, or Coming Soon — no exceptions |
| Network dependency during live demo (venue Wi-Fi failure) | Medium | High | Local hotspot backup; offline-capable fallback screens showing static walkthrough |

## Escalation Principle

Any risk that materialises during the hackathon (e.g. a live bug) is disclosed to judges honestly rather than hidden — credibility is treated as more valuable than a flawless-looking demo.
