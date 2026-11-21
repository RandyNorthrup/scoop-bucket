# Randy Northrup's Scoop bucket

[![Tests](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/excavator.yml)

A [Scoop](https://scoop.sh) bucket for two free Windows apps by Randy Northrup:

| App | Manifest | What it is |
|---|---|---|
| [S.A.K. Utility](https://sakutility.com/) | `sak-utility` | A free, open-source, portable Windows toolkit for PC technicians, IT pros, and sysadmins. It combines profile backup and restore, partition management, diagnostics, app deployment and removal, file and network tools, USB image flashing, email archive tools, and optional AI repair workflows. |
| [WinAppMigrator](https://winappmigrator.com/) | `winappmigrator` | Turns an installed Windows desktop app into one self-extracting installer you can run on another PC, even when the app is on an old Windows 7 PC across your network, on a drive pulled out of a dying machine, or on an image of one, and the original installer is long gone. |

## Install

```pwsh
scoop bucket add sak https://github.com/RandyNorthrup/scoop-bucket
scoop install sak/sak-utility
scoop install sak/winappmigrator
```

Scoop adds a Start menu entry for each app (under Scoop Apps). Update with `scoop update sak-utility` or `scoop update winappmigrator`.

## What the manifests do

Both download the official release from GitHub Releases, check it against the SHA-256 in the release's `SHA256SUMS.txt`, and pick up new releases on their own: a scheduled workflow checks for a new GitHub release every 4 hours and updates the version, URL and hash.

**sak-utility**

- Downloads the release ZIP from [GitHub Releases](https://github.com/RandyNorthrup/S.A.K.-Utility/releases). The programs inside are signed by Randy Northrup.
- Persists the app's `data` folder (settings, logs and reports) in `~\scoop\persist\sak-utility\data`, so it survives updates.

**winappmigrator**

- Downloads the release `.exe` from [GitHub Releases](https://github.com/RandyNorthrup/WinAppMigrator/releases), one portable program signed by Randy Northrup.
- Nothing needs persisting: the app keeps its settings in `%LOCALAPPDATA%\WinAppMigrator`, and its logs and the records that let the apps it installed be uninstalled in `%ProgramData%\WinAppMigrator`. Uninstalling it leaves both.

## Requirements

- **S.A.K. Utility:** 64-bit Windows 11. Windows 10 version 1809 or later meets the minimum requirements but is not part of release testing. The app runs as a standard user and asks for administrator rights when a task needs them.
- **WinAppMigrator:** Windows 10 or 11. It is an x64 program, and Windows on Arm runs it through emulation. It asks for administrator rights when it starts, because reading another drive and installing services both need them.

## Help

- How to use the apps: the [S.A.K. Utility wiki](https://sakutility.com/wiki) and the [WinAppMigrator wiki](https://github.com/RandyNorthrup/WinAppMigrator/wiki).
- Problems with an app: open an issue in [S.A.K. Utility's](https://github.com/RandyNorthrup/S.A.K.-Utility/issues) or [WinAppMigrator's](https://github.com/RandyNorthrup/WinAppMigrator/issues) repository.
- Problems with this bucket: open an issue here.

S.A.K. Utility is licensed under the GNU Affero General Public License v3.0, and WinAppMigrator under the MIT License. The files in this bucket are released into the public domain ([LICENSE](LICENSE)).
