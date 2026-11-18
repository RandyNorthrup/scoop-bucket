# S.A.K. Utility Scoop bucket

[![Tests](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/RandyNorthrup/scoop-bucket/actions/workflows/excavator.yml)

A [Scoop](https://scoop.sh) bucket for [S.A.K. Utility](https://sakutility.com/), a free, open-source, portable Windows toolkit for PC technicians, IT pros, and sysadmins. It combines profile backup and restore, partition management, diagnostics, app deployment and removal, file and network tools, USB image flashing, email archive tools, and optional AI repair workflows.

## Install

```pwsh
scoop bucket add sak https://github.com/RandyNorthrup/scoop-bucket
scoop install sak/sak-utility
```

Scoop adds an **S.A.K. Utility** entry to the Start menu (under Scoop Apps). Update with `scoop update sak-utility`.

## What the manifest does

- Downloads the official release ZIP from [GitHub Releases](https://github.com/RandyNorthrup/S.A.K.-Utility/releases) and checks it against the SHA-256 in the release's `SHA256SUMS.txt`. The programs inside are signed by Randy Northrup.
- Persists the app's `data` folder (settings, logs and reports) in `~\scoop\persist\sak-utility\data`, so it survives updates.
- Picks up new releases on its own: a scheduled workflow checks for a new GitHub release every 4 hours and updates the version, URL and hash.

## Requirements

64-bit Windows 11. Windows 10 version 1809 or later meets the minimum requirements but is not part of release testing. The app runs as a standard user and asks for administrator rights when a task needs them.

## Help

- How to use the app: the [wiki](https://sakutility.com/wiki).
- Problems with the app: [open an issue](https://github.com/RandyNorthrup/S.A.K.-Utility/issues) in its repository.
- Problems with this bucket: open an issue here.

S.A.K. Utility is licensed under the GNU Affero General Public License v3.0. The files in this bucket are released into the public domain ([LICENSE](LICENSE)).
