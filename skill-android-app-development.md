---
name: android-app-development
description: Plan and implement Android application features with lifecycle, permissions, storage, and device compatibility in mind.
---

# Android App Development

## Purpose
Plan and implement Android app features with attention to platform behavior, compatibility, and user privacy.

## Workflow
1. Confirm minimum and target Android SDK levels and supported device range.
2. Identify screens, navigation paths, lifecycle events, and background work.
3. Request only permissions essential to the feature and explain their purpose to users.
4. Use platform-supported storage and protect sensitive local data.
5. Handle configuration changes, process recreation, and lifecycle transitions.
6. Keep long-running work off the main thread and provide visible progress when needed.
7. Test on representative screen sizes and Android versions.
8. Build a release variant and review manifest permissions and packaged resources.

## Validation
- [ ] App launches and navigates without crashes.
- [ ] Permission denial is handled gracefully.
- [ ] UI remains responsive during work.
- [ ] Data survives expected lifecycle changes.
- [ ] Manifest contains no unnecessary permissions.
- [ ] Release build does not contain debug secrets or test endpoints.

## Safety and privacy
Collect the minimum data needed. Do not hide app behavior, bypass platform security, or access another person's data without clear authorization.
