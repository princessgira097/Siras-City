# Siras-City Development Plan

**Created:** 2026-11-16  
**Status:** Initial plan — subject to findings from source review and multiplayer testing.

## Guiding principles
1. Preserve the original working game; avoid direct changes to `main`.
2. Fix the verified multiplayer defect before broad refactoring or adding features.
3. Keep changes small, reviewable, reversible, and documented.
4. Separate facts, user-reported behavior, hypotheses, and tested fixes.
5. Coordinate upstream contributions with the original repository owner.

## Phase 0 — Baseline and reproducibility
- [ ] Inventory the full HTML, embedded JavaScript/CSS, remote libraries, authentication, persistence, hosting and game lifecycle.
- [ ] Record browser/devtools errors and network failures with 1, 2, 3, 4, 5, and 6 simultaneous players.
- [ ] Define whether the freeze affects one client, every client, login, lobby, or an active game.
- [ ] Record devices, browsers, game rooms, login times, network conditions, and exact steps.
- [ ] Confirm whether more than 3 users **logged in** is enough or whether they must enter the **same game**.
- [ ] Establish a repeatable baseline and capture error logs safely (no tokens or private user data).

**Exit criteria:** clear reproduction steps and observed evidence, or an explicit log of attempts that failed to reproduce.

## Phase 1 — Investigate multiplayer freeze (P0)
Potential *hypotheses only*: expensive full-state updates, unbounded listeners/timers, race conditions, synchronization feedback loops, database/connection quotas, malformed shared state, or client-side render bottlenecks. Do not assume any is the cause.
- [ ] Trace player join/leave, presence, game-state subscriptions, write/update paths, event handlers and cleanup.
- [ ] Measure update frequency, payload sizes, concurrent writes, event-loop blocking, and memory use.
- [ ] Compare the 3-player and 4-player paths.
- [ ] Locate a specific failure mechanism and write a minimal, testable correction.

**Exit criteria:** cause supported by code and logs, plus focused fix ready for validation.

## Phase 2 — Fix and verification
- [ ] Implement in `fix/multiplayer-freeze` branched from `develop`.
- [ ] Test at 1, 2, 3, 4, 5 and 6 players in separate browser sessions/devices.
- [ ] Cover join/leave/reconnect, simultaneous actions, refresh, and slow/unstable connections.
- [ ] Run multiple game rounds and a sustained session with 4+ active players.
- [ ] Check that no timers/listeners accumulate after leaving and rejoining.
- [ ] Record PASS / FAIL / NOT TESTED plus supporting logs and regression findings.
- [ ] Merge via PR into `develop`; promote tested changes to `main` using another PR.

**Exit criteria:** 4+ simultaneous players work repeatedly, no known regressions, evidence linked in PR.

## Phase 3 — Maintenance and quality
- [ ] Add documented local setup and reproducible test harness after architecture discovery.
- [ ] Add safe linting/static checks and lightweight CI suitable for the actual stack.
- [ ] Consider splitting the 1.9 MB HTML into maintainable modules only after behavior is stable.
- [ ] Define release/version policy, rollback steps, and upstream synchronization procedure.

## Suggested priority
**P0:** freeze at >3 players.  
**P1:** observability, reproducible tests, safe cleanup of multiplayer resources.  
**P2:** modularization, quality tools, documentation enhancements.  

## Change control
Maintain `CHANGELOG.md` for accepted changes and `docs/WORK_LOG.md` for investigation sessions. Each PR must include summary, risk, test results, and rollback plan. Keep the game untouched until the first targeted code change is ready.
