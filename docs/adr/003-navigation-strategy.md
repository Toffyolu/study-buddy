# ADR 003: Navigation Strategy

**Status:** Accepted
**Date:** 2026-10-30
**Author:** Morolake Oniye

## Context
Study Buddy connects students on campus who want study partners and helps them find peers who are stronger in certain subjects. The app has four main sections: Home (suggested study partners and upcoming sessions), Find Peers (search by subject), Requests (incoming and sent study requests) and Profile (the user's subjects, strengths and availability). Users need to switch between these quickly and open detail screens such as another student's profile or a study session. Navigation must support the Android back button and be quick for the team to learn within the course timeline.

## Options Considered
| Option | How it works | Pros | Cons |
| --- | --- | --- | --- |
| Stack only | Screens pile on top of each other | Simplest to build | Reaching a main section means pressing back repeatedly |
| Bottom tabs + stack | Tabs for main sections, a stack inside each tab for details | Familiar Android pattern; one tap between sections | Fits about five tabs at most |
| Drawer (side menu) | Sections hidden behind a menu | Holds many sections | Less discoverable; unnecessary for four sections |

## Decision
We will use bottom tab navigation with nested stack navigators, built with React Navigation (`@react-navigation/bottom-tabs` and `@react-navigation/native-stack`).

- Tabs: Home | Find Peers | Requests | Profile
- Stack screens: Student Profile, Send Study Request, Study Session Details, Edit Profile

## Rationale
- Four main sections fit a tab bar.
- Students move between finding peers and checking requests often, so one-tap access matters.
- React Navigation is the standard, well-documented React Native library, which keeps the learning curve low.
- It handles the Android back button automatically.
- It stays within course scope: no custom navigation code is needed.

## Consequences
- Positive: consistent, intuitive navigation that is quick to build and test.
- Negative: adding a fifth major section (e.g., in-app chat) would use the last tab slot; more would need a drawer.
- React Navigation must be installed and configured at the start of Phase 4.
