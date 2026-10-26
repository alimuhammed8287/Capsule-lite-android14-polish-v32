# Capsule Lite — Polish v29

Android 14 source project for Capsule Lite.

This is a **source ZIP**, not a compiled APK. This iteration reduces repeated play/pause icon and accessibility-description updates. See `PATCH_NOTES.md` for details and validation limits.

Compilation and real-device testing have not been performed in this environment.


## v30 update

This revision avoids redundant media progress-bar and elapsed/remaining text assignments during playback. See `PATCH_NOTES.md` for the full revision notes.

## v31 update

The collapsed player's seek control now reflects whether track duration is available, exposes clearer accessibility text, and clamps seek requests to the track's valid range. See `PATCH_NOTES.md`.
