# Review: keep embedded apps inside iOS safe areas

**Owner review only. No pull request or upstream issue has been submitted.**

Upstream: https://github.com/SignalK/app-dock
Base: `3fef5495f20c0e2a81bcba86c128c281eda5786b`

## Problem and proposed behavior

iOS home-screen installations can place embedded app controls behind the status area and leave the viewport incorrectly sized. Give the iframe the usable dynamic viewport, accounting for top, bottom and landscape side safe areas once.

## Scope and decisions

CSS only. No fixed dock-height spacer, app-specific offsets, generated assets or release-version changes.

## Validation status

The branch was prepared from current upstream source. Patch applicability and
diff whitespace checks are verified during preparation. These are review drafts,
not a claim of passing CI, deployment readiness or completed hardware validation.

## Before upstream submission

- [ ] Confirm a physical iPhone and iPad home-screen installation in portrait and landscape.
- [ ] Adapt the existing local browser geometry regression into upstream tests; run build, lint and the upstream test suite.

Keep boat identity, credentials, live data, custom release suffixes and deployment
scripts out of an upstream submission. Publish nothing to the parent until approved.
