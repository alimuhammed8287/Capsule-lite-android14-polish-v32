# Capsule Lite — v35 build-ready source

This is the Android source project based on the v32 project, with the appearance/theme and charging-pill icon updates carried forward from v33/v34.

## Included
- Updated appearance settings and live theme preview.
- Frosted Glass compositor blur request when supported, with a tinted fallback.
- Distinct Futuristic Cyan and iOS-inspired surface palettes.
- Charging metric glyphs and lightning glyph in the compact charging pill.
- GitHub Actions workflow to compile a debug APK and publish it as a downloadable workflow artifact.

## Build on GitHub
Push this project to a GitHub repository, then open **Actions → Build Capsule Lite APK**. The workflow installs Java 17 and Gradle 8.9, runs `assembleDebug`, and uploads `app-debug.apk` as an artifact.

## Validation caveat
This source archive has not been compiled in this local environment because no Android SDK/Gradle installation is available here. The workflow is configured to perform the actual Android build in GitHub Actions. Device-specific behavior (especially blur on MIUI/HyperOS) still needs testing on the target phone.
