# Review: do not interpret scrolling or pinching as a double tap

**Owner review only. No pull request or upstream issue has been submitted.**

Upstream: https://github.com/SignalK/app-dock
Base: `3fef5495f20c0e2a81bcba86c128c281eda5786b`

## Problem and proposed behavior

The dock counts contact-down events as taps, so two scroll starts can open it. Count a completed single-contact tap instead, rejecting movement, cancellation, long holds and multiple contacts while retaining passive event delivery.

## Scope and decisions

Preserve the 600 ms / 60 px double-tap window introduced for slow kiosk screens in upstream PR #72. Layout is a separate branch.

## Validation status

The branch was prepared from current upstream source. Patch applicability and
diff whitespace checks are verified during preparation. These are review drafts,
not a claim of passing CI, deployment readiness or completed hardware validation.

## Before upstream submission

- [ ] Add browser regressions for taps versus scroll, drag, pinch, cancelled contacts and holds.
- [ ] Verify pointer/touch deduplication, mouse input, Windows touch fallback and iframe navigation.
- [ ] Confirm the unchanged cross-origin forwarding path and document that the candidate fixes same-origin contact recognition.

## Related upstream work

- https://github.com/SignalK/app-dock/pull/72

Keep boat identity, credentials, live data, custom release suffixes and deployment
scripts out of an upstream submission. Publish nothing to the parent until approved.

## Preparation results — 6 November 2026

Fresh local validation on Node 26.12.1: full upstream build succeeded; 46/46 existing tests passed. These plugin tests do not prove gesture behavior; targeted browser/device checks remain pending.
