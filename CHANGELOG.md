## 2.0.1 — 2025-09-03

Build & CI
- JitPack now publishes the AAR and POM to Maven Local via `publishMavenPublicationToMavenLocal`, allowing JitPack to discover and serve artifacts reliably.
- Signing is conditional: publications are only signed when GPG/in‑memory signing keys are configured. This avoids CI/JitPack failures due to missing keys while preserving signing for real releases.

Notes
- No runtime or API changes; safe patch release.

## 2.0.0 — 2025-09-03

Breaking changes
- Raise `minSdkVersion` to 28 across the project. This removes support for API < 28 and allows dropping legacy multidex/desugaring setups.
- Remove core library desugaring and legacy multidex configurations. Consumers targeting API 28+ and AGP 8+ do not require these.
- Target SDK updated to 34.

Dependencies
- Switch `opensrp-client-core` resolution to JitPack coordinates: `com.github.BlueCodeSystems:opensrp-client-core:v6.2.2`.
- Keep `io.github.bluecodesystems:opensrp-plan-evaluator:1.7.0` and `io.github.bluecodesystems:android-p2p-sync:0.4.1` alignment.

Build & Tooling
- Make the `:sample` module optional via `-PincludeSample=true` or `INCLUDE_SAMPLE=true`.
- Require Java 17 toolchain and AGP 8.5+/Gradle 8.7.

Migration notes
- Bump your app `minSdk` to 28 or consume this library only in variants that target API 28+.
- Remove manual multidex and core library desugaring setup in your app when consuming this version.

## 1.2.0 — 2025-08-31

- New: Added Maven Central bundle publishing via `maven-publish` with tasks:
  - `publishMavenPublicationToCentralBundleRepository`, `generateCentralBundleChecksums`, `zipCentralBundle`, `printCentralBundleLayout`.
- Build: Upgraded Android Gradle Plugin to 8.5.0 and Gradle wrapper to 8.7.
- Build: Removed Sonatype/MOTECH snapshot repositories; prefer Maven Central/JitPack only.
- Deps: Switched to Maven Central `io.github.bluecodesystems:android-p2p-sync:0.4.1`.
- Deps: Ensured `io.github.bluecodesystems:opensrp-plan-evaluator:1.7.0` and `com.github.OpenSRP:opensrp-client-core:v6.2.2` alignment (via JitPack).
- Fix: Resolved Jetifier crash on Jackson MRJARs by pinning Jackson to 2.16.1 and excluding Jackson from Jetifier transforms.
 - Publishing: Android `namespace` changed to `io.github.bluecodesystems.configurableviews` to align with group.

Breaking changes
- Minimum build tooling updated (AGP 8.5 / Gradle 8.7). Consumer APIs remain unchanged.
- Publishing group changed to `io.github.bluecodesystems`. New coordinates:
  - `io.github.bluecodesystems:opensrp-configurable-views:1.2.0`
 - Android resource package (`R`) moved under `io.github.bluecodesystems.configurableviews`.
