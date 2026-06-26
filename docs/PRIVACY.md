# BellEquation Privacy Plan

BellEquation may eventually handle sensitive data such as saved addresses, current location, app paths, and reminder schedules.

## Privacy Rules

- No account system is required for the MVP.
- Tasks are stored locally on the user's device.
- Location data must be optional.
- Travel-aware reminders must be disabled unless the user enables them.
- Saved home/work addresses must be stored locally.
- API keys must be stored locally and never committed to GitHub.
- Do not log precise location data unless the user explicitly enables debug mode.

## Location Behavior

BellEquation should support two origin modes:

1. Manual origin address
2. Current location, only when enabled by the user

Current location must not be collected continuously by default.

## Travel Data Language

Traffic and transit data are estimates.

Use language like:

```text
This route currently looks slower than usual.
```

Avoid language like:

```text
This route will definitely be blocked.
```

## API Key Rules

- Never commit API keys.
- Use local settings or environment variables.
- Provide `settings.example.json` if needed.
- Add real settings files to `.gitignore`.
