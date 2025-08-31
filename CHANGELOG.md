## 1.2.0 — 2025-08-31

- New: Added Maven Central bundle publishing via `maven-publish` with tasks:
  - `publishMavenPublicationToCentralBundleRepository`, `generateCentralBundleChecksums`, `zipCentralBundle`, `printCentralBundleLayout`.
- Build: Upgraded Android Gradle Plugin to 8.5.0 and Gradle wrapper to 8.7.
- Build: Removed Sonatype/MOTECH snapshot repositories; prefer Maven Central/JitPack only.
- Deps: Switched to Maven Central `io.github.bluecodesystems:android-p2p-sync:0.4.1`.
- Deps: Ensured `io.github.bluecodesystems:opensrp-plan-evaluator:1.7.0` and `opensrp-client-core:6.2.0` alignment.
- Fix: Resolved Jetifier crash on Jackson MRJARs by pinning Jackson to 2.16.1 and excluding Jackson from Jetifier transforms.

Breaking changes
- Minimum build tooling updated (AGP 8.5 / Gradle 8.7). Consumer APIs remain unchanged.
- Publishing group changed to `io.github.bluecodesystems`. New coordinates:
  - `io.github.bluecodesystems:opensrp-configurable-views:1.2.0`
