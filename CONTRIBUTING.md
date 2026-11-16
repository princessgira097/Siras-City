# Contributing to Siras-City

1. Sync the fork with upstream before starting major work, but **inspect merge differences** before accepting upstream changes.
2. Start from `develop`: create `fix/<topic>`, `feature/<topic>`, or `docs/<topic>`.
3. Make one logical change at a time; avoid unrelated formatting of the inherited large HTML file.
4. Commit descriptive changes, e.g. `fix(multiplayer): clean up stale game listeners`.
5. Open a pull request **into `gunkrist/Siras-City:develop`**. Do not merge untested work into `main`.
6. Document summary, rationale, affected files, risks, testing steps, and PASS / FAIL / NOT TESTED results.
7. Review, test, and merge into `develop`; promote tested releases into `main` via PR.
8. Submit a separate PR to the original owner, `princessgira097/Siras-City`, after the fix is accepted in this fork. Do not assume upstream wants every experiment.

## PR description template
**Problem / goal:**

**Changes:**

**Risk / compatibility:**

**Tests:** PASS / FAIL / NOT TESTED, number of simultaneous players, browser/environment, reproduction steps

**Rollback:** revert PR / restore last known good revision

**Related issues / logs:**

## Safety and collaboration
Never put tokens, passwords, personal player information, or private debug logs in public issues/commits. Respect the upstream author's decisions and avoid pushing directly to their repository.
