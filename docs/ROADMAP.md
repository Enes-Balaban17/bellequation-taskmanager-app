# BellEquation Roadmap

## v0.1 - MVP Desktop Reminder

Goal: Build a working Windows/Linux desktop reminder app.

Features:

- Avalonia UI app scaffold
- Task model
- Task list UI
- Add task UI
- Delete task
- Complete task
- Date/time field
- Reminder offset field
- Action type: None / URL / Application Path
- Action target input
- JSON local storage
- Reminder checking service
- In-app bottom notification panel
- Open linked URL/application

## v0.2 - Better Task Management

Features:

- Edit task
- Filter tasks: All / Active / Completed
- Search tasks
- Better empty states
- Settings page
- Light/dark theme
- Better validation and error messages

## v0.3 - Native Notifications and Background Mode

Features:

- Native Windows notifications
- Native Linux notifications where practical
- Minimize to tray
- Start minimized option
- Optional start with system
- Notification click actions

## v0.4 - Installer and Release System

Features:

- Windows portable executable
- Windows installer
- Linux portable tar.gz
- Linux AppImage target if practical
- PowerShell install script
- Linux terminal install script
- GitHub Actions build workflow
- GitHub Releases artifacts

## v0.5 - Travel-Aware Task Model

Features:

- Task type: Normal / Travel
- Origin field
- Destination field
- Target arrival time
- Transport mode: Driving / Public Transit / Walking / Walking + Transit
- Safety buffer minutes
- Manual estimated travel time fallback
- Route advisor service interface
- Mock route advisor for development

## v0.6 - Real Route and Transit Providers

Features:

- Route provider integration
- Traffic-aware duration estimates
- Public transit provider integration
- Delay and service warning support
- API key settings screen
- Provider error handling
- Privacy-first location controls
