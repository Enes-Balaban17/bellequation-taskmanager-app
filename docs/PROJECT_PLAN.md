# BellEquation Project Plan

## Product Definition

BellEquation is a cross-platform desktop reminder and travel-aware task assistant built with C# and Avalonia.

It helps users create scheduled tasks, receive timely reminders, open linked apps or URLs, and later receive travel-aware alerts for tasks that require commuting or public transit.

## Target Users

- Students
- Developers
- People with meetings and scheduled daily tasks
- Users who need reminders connected to apps or links
- Users who want future travel-aware reminders for work, school, airport, or appointments

## Main Task Types

### 1. Normal Task

A normal task has a title, date/time, reminder offset, and optional action.

Example:

```text
Task: Join the meeting
Due: 27/06/2026 14:00
Reminder: 20 minutes before
Action: Open Zoom
```

### 2. Travel Task

A travel task has a target arrival time, origin, destination, transport mode, and route/transit awareness.

Example:

```text
Task: Go to work
Target arrival: 09:00
Origin: Current location or saved home address
Destination: Workplace
Transport: Public Transit
```

Travel tasks are planned for later versions. v0.1 should focus on normal reminders.

## MVP Scope: v0.1

The first version must be simple and working.

Required:

- Add task
- Complete task
- Delete task
- Store tasks locally in JSON
- Select due date/time
- Select reminder offset
- Attach URL or application path
- Show in-app reminder notification at the correct time
- Open URL/application from notification
- Basic Windows/Linux compatibility

Not required in v0.1:

- Real traffic API
- Public transit API
- Native system notifications
- System tray
- Account/login system
- Cloud sync
- SQLite
- Map UI

## User-Facing Language

Use clear and safe language. Avoid claiming certainty for traffic or route predictions.

Preferred wording:

```text
This route currently looks slower than usual.
Alternative route may save about 12 minutes.
```

Avoid wording like:

```text
You must take this route.
```

## Example Notification Texts

### Normal Reminder

```text
Meeting reminder
Join the meeting starts in 20 minutes.
```

### Future Traffic Reminder

```text
Commute update
Your usual route currently looks slower than normal.
Alternative route may be faster.
Recommended departure time: 08:10
```

### Future Transit Reminder

```text
Transit update
Bus 972 is currently estimated to arrive 10 minutes late.
You may need to leave earlier to reach the metro station on time.
```
