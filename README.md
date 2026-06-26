# BellEquation

BellEquation is a cross-platform desktop reminder and travel-aware task assistant.

It helps users create scheduled tasks, receive timely reminders, open linked apps or URLs, and plan travel-related tasks with traffic and public transit awareness.

## Core Idea

BellEquation is not a simple to-do list. It is a desktop assistant for tasks that are connected to time, applications, links, meetings, and travel.

Example normal task:

```text
Task: Join the meeting
Date: 27/06/2026
Time: 14:00
Reminder: 20 minutes before
Action: Open Zoom
```

Example travel task:

```text
Task: Go to work
Target arrival: 09:00
Origin: Current location or saved home address
Destination: Workplace
Transport mode: Driving or Public Transit
Reminder mode: Travel-aware
```

## Planned Features

### v0.1 MVP

- C# + .NET + Avalonia desktop application
- Windows and Linux support
- Add, complete, and delete tasks
- Date/time based reminders
- Reminder offsets: 5, 10, 20, 30 minutes before
- Link or application path attached to a task
- Open linked app or URL from reminder
- Local JSON storage
- In-app bottom notification panel
- Basic settings file

### Later Versions

- Native system notifications
- System tray / background mode
- Edit task flow
- Recurring tasks
- Windows installer
- Linux AppImage / tar.gz package
- PowerShell install script
- Linux terminal install script
- Travel-aware task type
- Route and traffic provider abstraction
- Public transit provider abstraction
- Location permission/settings model
- GitHub Actions release pipeline

## Technology Direction

- Language: C#
- Runtime: .NET
- UI: Avalonia UI
- Storage: JSON for MVP, SQLite optional later
- Architecture: MVVM + Services
- Target OS: Windows and Linux

## Documentation for AI/Codex

Before implementing, read the docs in this order:

1. `docs/AI_IMPLEMENTATION_GUIDE.md`
2. `docs/PROJECT_PLAN.md`
3. `docs/ROADMAP.md`
4. `docs/ARCHITECTURE.md`
5. `docs/INSTALLATION.md`
6. `docs/PRIVACY.md`

## Privacy Direction

BellEquation should only use location data when the user explicitly enables travel-aware reminders. Saved locations should be stored locally. API keys must never be committed to GitHub.
