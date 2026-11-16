# Known Issues

## GAME-001 — Game freezes with more than 3 concurrent players
- **Priority:** P0 / highest
- **Status:** Reported, not reproduced or diagnosed by this development fork yet
- **Reported:** 2026-11-16
- **User report:** “if more than 3 people log in and play this game at the same time, it freezes”
- **Expected:** Four or more simultaneous players can join and play normally.
- **Observed (reported):** Game freezes when the concurrent player count exceeds three.
- **Unknowns:** precise freeze point, whether clients or server are affected, whether it is per-room or global, browser details, console errors, network/backend state, and exact maximum player count.
- **Reproduction draft:** Start separate authenticated sessions; have 1, 2, 3, then 4+ players enter the game and perform normal actions. Record timestamps and client/server errors.
- **Diagnostics:** browser console, performance/memory timeline, websocket/network events, data-store request volume, join/leave subscriptions, shared state changes, timeout/error messages.
- **Suspected causes:** none confirmed; avoid implementing guesses.
- **Acceptance test:** 4, 5, and 6 simultaneous players can finish repeated game rounds; joins/leaves/reconnections and simultaneous actions continue correctly; no new regression.
- **Tracking:** use this file until GitHub Issues are enabled; when possible move to a GitHub issue and link it here.

## Issue template
For future issues record: ID, title, priority, reported date, symptoms, exact reproduction, expected behavior, actual behavior, diagnostics, root cause (verified or unconfirmed), branch/PR, PASS/FAIL/NOT TESTED, and resolution.
