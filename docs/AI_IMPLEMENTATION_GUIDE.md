# AI Implementation Guide

This repository is intended to be implemented by Codex or another AI coding model.

## Source of Truth Order

Read files in this order before coding:

1. `README.md` - product summary
2. `docs/PROJECT_PLAN.md` - feature scope and product rules
3. `docs/ROADMAP.md` - version order
4. `docs/ARCHITECTURE.md` - code structure and services
5. `docs/INSTALLATION.md` - packaging and install targets
6. `docs/PRIVACY.md` - privacy and location rules

## First Implementation Target

Implement only BellEquation v0.1 first.

Do not implement full traffic, public transit, map, or real-time location tracking in the first commit.

The first working app must include:

- Avalonia desktop app scaffold
- Main window
- Task list
- Add task form
- Date/time selection
- Reminder minutes selection
- Action target field for URL or application path
- Local JSON persistence
- Reminder checker service
- In-app bottom notification panel
- Open linked URL or application from reminder
- Windows/Linux compatible code path where possible

## Important Product Rules

- Keep the app cross-platform.
- Do not add Windows-only dependencies to core services.
- Do not hard-code private user paths.
- Do not commit API keys.
- Do not require a database server.
- Use JSON storage for v0.1.
- Prefer small, readable classes.
- Keep future travel features behind service interfaces.

## Naming Rules

Project name: BellEquation
Root namespace: BellEquation
Main app project: `src/BellEquation/BellEquation.csproj`

## Future-Ready Interfaces

Even if travel features are not implemented in v0.1, create clean placeholders/interfaces only if they do not overcomplicate the MVP.

Recommended future interfaces:

- `IRouteAdvisorService`
- `ITransitAdvisorService`
- `ILocationService`
- `INotificationService`
- `IAppLauncherService`
- `ITaskStorageService`

## MVP Reminder Behavior

Every 30 seconds:

1. Load active tasks from memory.
2. Ignore completed tasks.
3. Calculate reminder time: `DueDateTime - ReminderMinutesBefore`.
4. If current time is at or after reminder time and reminder was not shown, show in-app notification.
5. Mark reminder as shown and save tasks.

## MVP Notification Behavior

Use an in-app bottom notification panel first.

The panel should show:

- Task title
- Due time
- Reminder text
- Primary action button: `Open`
- Secondary action button: `Dismiss`

## App Launching Rules

If action type is `Url`, open it with the system default browser/application.
If action type is `ApplicationPath`, launch the selected executable/path.
If action target is empty, hide or disable the `Open` action.
