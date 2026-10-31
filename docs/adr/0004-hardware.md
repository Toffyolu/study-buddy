# ADR 004: Hardware Features

**Status:** Accepted
**Date:** 2026-10-30
**Author:** Morolake Oniye

## Context
Study Buddy helps students find study partners on campus and arrange study sessions. Android devices offer GPS, camera, speaker, vibration, notifications and a fingerprint scanner. Each feature adds permissions, testing work and complexity, so we will only use hardware that supports a core feature and can be tested on the Android emulator and team devices.

## Options Considered
| Hardware | Use? | Reason |
| --- | --- | --- |
| Notifications | Yes | Alert students to new study requests and upcoming sessions |
| Vibration | Yes | Notification alerts when the phone is on silent |
| GPS / Location | Yes (optional for users) | Show peers who are nearby on campus |
| Camera | No | Profile photos can be picked from the gallery instead |
| Speaker | No | Default notification sound is enough; no audio features |
| Fingerprint scanner | No | Standard login is enough; adds complexity outside course scope |

## Decision
We will use notifications, vibration and GPS only, through `expo-notifications`, `expo-haptics` and `expo-location`. Location is optional: users can turn it off and still search peers by subject. All other hardware is excluded.

## Rationale
- Notifications and vibration support the core flow of sending and accepting study requests.
- Location supports the "students on campus" purpose without being required.
- Expo modules provide simple APIs and handle Android permission prompts.
- All three can be tested on the emulator (location can be simulated).

## Consequences
- Positive: small scope, few permissions, faster development.
- Negative: if a user denies location, the app must fall back to subject-only search; if they deny notifications, requests must still show in the Requests tab.
- Location data must only be used to show distance, not stored precisely, to protect student privacy.
