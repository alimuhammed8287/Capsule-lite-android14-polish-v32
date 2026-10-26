# Capsule Lite Polish v33 — visual redesign and glass implementation

## Appearance and settings
- Redesigned settings screens with a deep blue-black background, more consistent typography, spacing, rounded gradient cards, subtle borders, and higher-contrast controls.
- Added a live-style theme preview to the Look screen and made theme selection refresh the preview and settings screen immediately.
- Expanded Frosted Glass controls to describe actual compositor blur and the platform fallback behavior.
- Made Futuristic Cyan and iOS Inspired surfaces use stronger, more coherent background tones as well as their respective outlines.

## Blur behavior
- When the user enables glass blur, Android 12+ devices are checked for cross-window blur support.
- On supported devices, the overlay requests the platform compositor blur using `FLAG_BLUR_BEHIND` and `setBlurBehindRadius`, with radius tied to the blur-strength slider.
- If blur is unsupported or unavailable, the service removes the blur flag and retains the translucent themed surface. The expanded panel uses the same policy.
- The Android platform blur-behind API blurs content behind the overlay window, not only within the pill's rounded bounds. This limitation is documented in settings; blur remains opt-in because some OEMs disable it dynamically or render it differently.

## Preserved behavior
- Existing gesture mappings, media handling, notifications, charging, navigation, quick controls, permissions, diagnostics, and settings keys are retained.

## Validation status
- Source edits and ZIP packaging checks completed.
- Android manifest XML and resource XML parse checks completed.
- This environment has no configured Android SDK or Gradle executable/wrapper, so Kotlin compilation, APK generation, and real-device testing could not be performed here. Install/build on Android Studio or with a configured Android SDK before relying on the release.


## v34 charging-pill icon pass
- Added compact inline metric glyphs for ETA, voltage, current, battery percentage, temperature, and charging power.
- Added a lightning glyph beside the collapsed charging percentage.
- Kept the existing layout dimensions and charging data logic unchanged.
- Build/device testing remains required; no Android SDK/Gradle executable is available in this environment.

## v35 build pipeline and handoff
- Kept the v33 appearance/theme/blur implementation and v34 charging glyphs.
- Improved GitHub Actions workflow to run on pushes, pull requests, and manual dispatch.
- Uses Java 17 and Gradle 8.9, validates manifest XML, compiles `assembleDebug`, and uploads the APK as an artifact.
- Local Kotlin compilation and device testing are still unverified because this runtime has no Android SDK or Gradle executable.
