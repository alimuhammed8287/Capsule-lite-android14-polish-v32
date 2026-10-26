# Capsule Lite Polish v32

## Changes
- Make playback-position extrapolation resilient to non-finite, non-positive, or extremely large playback-speed values from a media session.
- Saturate position addition instead of allowing `Long` overflow to wrap the displayed playhead.
- Calculate seek-bar progress using a floating-point ratio to avoid overflowing `position * 1000` for unusually large durations.
- Retains the prior media refresh, accessibility, and safe-seeking improvements.

## Validation
- ZIP integrity checked after packaging.
- Android XML files parsed successfully.
- Targeted source assertions passed.
- Kotlin compilation and real-device testing were not performed.
