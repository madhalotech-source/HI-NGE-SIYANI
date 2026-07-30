# Testing Strategy

## Testing Levels

### 1. Manual Functional Testing (MVP priority)

- Full onboarding flow walkthrough in each of the 5 supported languages
- Focus-area selection with single and multiple selections
- Guidance flow: at least 10 representative questions per vertical (Education, Government Services)
- Explicit test of the confidence-fallback path (deliberately ambiguous input) in each language

### 2. API Testing

- Manual `curl`/Postman verification of every endpoint listed in [API Architecture](12-api-architecture.md) before UI integration
- Automated integration tests for Edge Functions — **Coming Soon**

### 3. Device Testing

- Test on at least one mid-range Android device (not flagship-only) to reflect realistic target users
- Verify language switching does not require app restart
- Verify performance under throttled/slow network conditions

### 4. Security Testing

- Verify RLS policies: attempt cross-user data access and confirm it is denied
- Verify deletion requests fully remove `profiles`, `focus_areas`, and `guidance_sessions` rows
- Penetration testing — **Coming Soon**, planned ahead of any public/production release

### 5. Regression Testing — **Coming Soon**

Automated regression suite planned for Phase 2, once the Edge Function guidance logic stabilises enough to be worth locking behind tests.

## Demo-Day Testing Checklist

- [ ] Full demo script rehearsed end-to-end at least 5 times
- [ ] Confidence-fallback moment tested and reproducible on demand
- [ ] Backup demo recording prepared in case of live network failure
- [ ] All test accounts reset to a clean onboarding state before judging

## Bug Tracking

Issues are logged as GitHub Issues (see [GitHub Tutorial](../github-guide/GITHUB_TUTORIAL.md)) rather than informal notes, so judges reviewing the repository can see real development history.
