# BellEquation Installation Plan

BellEquation should support two installation styles:

1. Command-line installation
2. Downloadable executable/package files

## Windows Command Install

Target command:

```powershell
iwr -useb https://raw.githubusercontent.com/Enes-Balaban17/bellequation-taskmanager-app/main/scripts/install.ps1 | iex
```

Expected behavior:

- Download the latest Windows release artifact from GitHub Releases
- Install to a local user directory such as `%LOCALAPPDATA%/BellEquation`
- Create a Start Menu shortcut if practical
- Add a simple launcher command if practical

## Linux Command Install

Target command:

```bash
curl -fsSL https://raw.githubusercontent.com/Enes-Balaban17/bellequation-taskmanager-app/main/scripts/install.sh | bash
```

Expected behavior:

- Download the latest Linux release artifact from GitHub Releases
- Install to `~/.local/share/BellEquation`
- Create a `.desktop` file if practical
- Add a launcher script at `~/.local/bin/bellequation`

## Downloadable Files

Windows targets:

```text
BellEquation-win-x64.zip
BellEquation-Setup.exe
BellEquation.exe
```

Linux targets:

```text
BellEquation-linux-x64.tar.gz
BellEquation.AppImage
```

## Build Targets

The implementation should later support publishing for:

```text
win-x64
linux-x64
```

Portable builds are enough for early releases.

## Release Notes

Every GitHub Release should include:

- Version number
- Changes
- Known issues
- Windows download
- Linux download
- Install commands
