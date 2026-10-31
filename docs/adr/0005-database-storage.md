# ADR 005: Database Storage

**Status:** Proposed
**Date:** 31 October 2026
**Author:** Ghazal Azarnia

## Context

Study Buddy needs to save students' tasks, due dates, reminders, and completion status so they can return to them later. It also needs to store student profiles and study preferences for the study-partner matching feature. Since students would use the app on different devices, matching requires a way to share selected profile information. The storage approach should be manageable within the project timeline.

## Options Considered

| Option | Pros | Cons |
| --- | --- | --- |
| Local, unencrypted | Easy to set up and allows students to access saved data offline. | The database is not encrypted, and data is not shared between devices. |
| Local, encrypted | Allows offline access and adds protection for data stored on the device. | Takes more time to configure and does not support sharing between devices on its own. |
| Remote | Allows students to access shared profiles and find study partners on other devices. | Requires internet access for remote operations, along with login and access controls. |
| None | No storage setup is needed. | Tasks and profiles would not be saved between sessions. |

## Decision

We propose using a remote database to store student profiles, tasks, due dates, reminder settings, and completion status. Only information intended for study-partner matching, such as subjects and availability, will be shared with other students. Personal tasks and assessments will remain private. The team will confirm the database service before implementation.

## Rationale

A remote database fits Study Buddy because the app combines personal planning with finding study partners. Local storage could support the planner, but it would not let students find other users without an additional shared service. Using one main database should also keep the initial design easier for the team to manage.

## Consequences

The team will need to set up the database and make sure students can only access their own planner data and the profile details shared for matching. The app will also need clear messages when a connection fails or information cannot be saved. Full offline editing and synchronization are outside the initial scope. Reminder settings will be saved in the database, while notifications will be scheduled separately on the device.
