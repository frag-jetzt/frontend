# Feature Request: Web Push Notifications

## Overview

Implement native web push notifications to alert users about important activity even when frag.jetzt is not in the foreground. This enhancement improves engagement by delivering real-time updates through the browser's push API.

## Motivation

- Keep participants informed of new questions, answers, or moderation events without needing the app open.
- Reduce missed interactions during lectures or discussions.
- Provide a modern notification option in addition to email or in-app notices.

## Proposed Functionality

- Prompt users to enable browser push notifications on supported platforms.
- Use the existing `WebPushService` to subscribe and manage push endpoints.
- Notify when:
  - a new question or comment appears in a subscribed room,
  - a moderator responds to the user's post,
  - announcements or important events occur.
- Allow users to manage their subscriptions and opt out at any time.
- Ensure all push messages are localized (EN/FR/DE) and respect existing notification settings.

## Acceptance Criteria

1. Users can grant or deny permission for web push notifications.
2. Subscribed users receive push notifications even when the PWA is closed.
3. Notifications open the relevant room or comment when clicked.
4. Feature works in modern desktop and mobile browsers (Chrome, Firefox, Safari where supported).
5. Option to disable or re-enable notifications is available in user settings.

## Additional Notes

- This builds on the `src/app/services/http/web-push.service.ts` infrastructure.
- Backend support for sending push messages must be available.
- Thorough testing across devices is required to meet the project's Definition of Done.
