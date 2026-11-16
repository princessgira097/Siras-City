# Siras-City — collaborative development fork

This repository is a **fork** of [princessgira097/Siras-City](https://github.com/princessgira097/Siras-City), maintained here for collaborative improvements and testing.

## Current state (2026-11-16)
- The inherited game is a browser-based application stored primarily in a single large `index.html` (~1.9 MB).
- Original game behavior is **not yet independently verified** in this fork.
- Reported known problem: the game freezes when more than three people are logged in and playing at once. Root cause **unconfirmed**.
- Initial goal: reproduce and resolve the multiplayer freeze without disrupting gameplay.

## Repository workflow
- `main` — stable inherited code / approved releases; do not commit experiments here.
- `develop` — integration branch for reviewed work.
- `fix/<short-description>` and `feature/<short-description>` — small focused branches created from `develop`.
- Submit pull requests into **this fork's `develop`**, test/review, then merge into `main` when stable.
- To contribute back: create a **separate upstream pull request** from `gunkrist:main` to `princessgira097:main`, ideally after discussion with the original maintainer. For smaller fixes, upstream may prefer a focused branch-specific PR.

See [development plan](docs/DEVELOPMENT_PLAN.md), [known issues](docs/KNOWN_ISSUES.md), [contribution guide](CONTRIBUTING.md), and [change log](CHANGELOG.md).

## Running the application
The inherited repository contains `index.html` and a Google site-verification HTML file. Browser runtime, hosting, authentication, networking dependencies, and local run requirements still need verification before precise setup instructions can be published. Do not commit credentials, personal data, or production authentication secrets.

## Progress and testing
Every code-change PR should state what changed, why, how to test it, and PASS / FAIL / NOT TESTED results. Never claim a multiplayer bug is fixed without a repeatable multi-client test.
