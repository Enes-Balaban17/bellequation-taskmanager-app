# BellEquation Architecture

## Recommended Stack

- C#
- .NET
- Avalonia UI
- MVVM pattern
- JSON storage for MVP

## Root Structure

```text
BellEquation/
├── README.md
├── docs/
├── scripts/
├── src/
│   └── BellEquation/
├── packaging/
├── screenshots/
└── .github/workflows/
```

## App Project Structure

```text
src/BellEquation/
├── App.axaml
├── App.axaml.cs
├── MainWindow.axaml
├── MainWindow.axaml.cs
├── Models/
│   ├── TaskItem.cs
│   ├── TravelInfo.cs
│   └── AppSettings.cs
├── ViewModels/
│   ├── MainWindowViewModel.cs
│   ├── TaskEditorViewModel.cs
│   └── SettingsViewModel.cs
├── Services/
│   ├── TaskStorageService.cs
│   ├── ReminderService.cs
│   ├── NotificationService.cs
│   ├── AppLauncherService.cs
│   ├── LocationService.cs
│   ├── RouteAdvisorService.cs
│   └── TransitAdvisorService.cs
└── Assets/
```

## Models

### TaskItem

```csharp
public class TaskItem
{
    public Guid Id { get; set; }
    public string Title { get; set; } = string.Empty;
    public DateTime DueDateTime { get; set; }
    public int ReminderMinutesBefore { get; set; } = 20;
    public TaskType Type { get; set; } = TaskType.Normal;
    public TaskActionType ActionType { get; set; } = TaskActionType.None;
    public string ActionTarget { get; set; } = string.Empty;
    public bool IsCompleted { get; set; }
    public bool ReminderShown { get; set; }
    public TravelInfo? Travel { get; set; }
}
```

### Enums

```csharp
public enum TaskType
{
    Normal,
    Travel
}

public enum TaskActionType
{
    None,
    Url,
    ApplicationPath
}

public enum TransportMode
{
    Driving,
    PublicTransit,
    Walking,
    WalkingAndTransit
}
```

### TravelInfo

```csharp
public class TravelInfo
{
    public string OriginName { get; set; } = string.Empty;
    public string OriginAddress { get; set; } = string.Empty;
    public string DestinationName { get; set; } = string.Empty;
    public string DestinationAddress { get; set; } = string.Empty;
    public TransportMode TransportMode { get; set; }
    public DateTime TargetArrivalTime { get; set; }
    public int SafetyBufferMinutes { get; set; } = 10;
    public string? PreferredRouteName { get; set; }
}
```

## Services

### TaskStorageService

Responsibilities:

- Load tasks from local JSON
- Save tasks to local JSON
- Create app data directory if missing
- Handle corrupted/missing file safely

### ReminderService

Responsibilities:

- Check task reminder times
- Ignore completed tasks
- Avoid duplicate reminders with `ReminderShown`
- Trigger notification service

### NotificationService

Responsibilities:

- v0.1: show in-app bottom notification panel
- Later: bridge to native OS notifications

### AppLauncherService

Responsibilities:

- Open URLs using system default handler
- Launch local application paths
- Validate empty or invalid action targets
- Keep cross-platform behavior where possible

### RouteAdvisorService

Future service.

Responsibilities:

- Estimate travel time
- Compare routes
- Generate traffic-aware warning text
- Provide fallback if API unavailable

### TransitAdvisorService

Future service.

Responsibilities:

- Estimate public transit arrival/departure
- Report delays or early arrivals
- Generate transit-aware warning text

### LocationService

Future service.

Responsibilities:

- Use manual location first
- Use live/current location only when user enables it
- Never track continuously without explicit travel-aware task need

## Storage Location

Use platform app data folders.

Suggested file:

```text
BellEquation/tasks.json
BellEquation/settings.json
```

The exact folder should be resolved through a cross-platform .NET app data path.
