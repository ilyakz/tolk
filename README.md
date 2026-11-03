<p align="center">
  <img src="docs/img/logo.png" width="96" height="96" alt="Tolk">
</p>
<h1 align="center">Tolk</h1>
<p align="center">Your Teams meetings as plain text files — saved from the live captions, locally.</p>
<p align="center">
  <a href="https://github.com/Ilyakz/tolk/releases/latest"><img src="https://img.shields.io/github/v/release/Ilyakz/tolk?label=release&color=1f6feb" alt="release"></a>
  <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4" alt="Windows 10 | 11">
  <img src="https://img.shields.io/badge/macOS-13%2B-555555" alt="macOS 13+">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-Apache--2.0-green" alt="Apache-2.0"></a>
</p>
<p align="center">
  <a href="https://github.com/Ilyakz/tolk/releases/latest"><b>Download for Windows or macOS</b></a>
  &nbsp;·&nbsp; <a href="README.ru.md">Русская версия</a>
</p>

**Tolk** saves the live captions of your Microsoft Teams meetings as plain text files on your
computer: when, who and what was said. Teams does the speech recognition; Tolk records no audio or
video, has no servers and sends nothing anywhere.

> **Your responsibility:** Teams does not tell participants that you save the captions. Tell them
> yourself (**Copy the notice** gives you a ready chat message) and don't use Tolk where copying or
> transcription is not allowed. Tolk saves nothing until you accept these terms on its first start.

## Screenshots

<table>
  <tr>
    <td width="50%"><img src="docs/img/en/list.png" alt="Meetings window: the list of saved meetings grouped by day, the meeting being saved right now at the top"></td>
    <td width="50%"><img src="docs/img/en/list-selected.png" alt="Meetings window: a selected meeting with Open, Show in folder, Copy path and the menu with more actions"></td>
  </tr>
  <tr>
    <td align="center">All your meetings, the one being saved at the top</td>
    <td align="center">Open, show in folder, copy the path, text or file</td>
  </tr>
  <tr>
    <td width="50%"><img src="docs/img/en/list-search.png" alt="Meetings window, light theme: search results with a line of the transcript under each meeting found"></td>
    <td width="50%"><img src="docs/img/en/flyout-saving.png" alt="The panel above the tray icon: saving captions, pause, stop for this meeting, the last meeting, copy the notice"></td>
  </tr>
  <tr>
    <td align="center">Search titles, dates, people and what was said</td>
    <td align="center">The tray panel: what is being saved right now</td>
  </tr>
  <tr>
    <td width="50%"><img src="docs/img/en/welcome-3.png" alt="First start: the terms of use, how long to keep meetings, copy the notice"></td>
    <td width="50%"><img src="docs/img/en/settings-storage.png" alt="Settings, Storage: the meetings folder, moving meetings with it, how long to keep them"></td>
  </tr>
  <tr>
    <td align="center">First start: accept the terms, choose how long to keep meetings</td>
    <td align="center">Settings: where meetings are kept and for how long</td>
  </tr>
</table>

**On macOS** — the same list, and the menu-bar menu:

<table>
  <tr>
    <td width="50%"><img src="docs/img/mac/en/list-selected.png" alt="macOS, the Meetings window: a selected meeting with Open, Show in Finder, Copy path and more actions"></td>
    <td width="50%"><img src="docs/img/mac/en/menu-saving.png" alt="macOS, the menu-bar menu: saving captions, pause, stop for this meeting, turn Teams captions on automatically"></td>
  </tr>
</table>

The screenshots show a demo build with made-up meetings and names.

## Features

- **Automatic.** A meeting shows captions — Tolk saves it. Rejoin within 10 minutes and the same file continues.
- **Tray icon** shows the state: waiting, saving, paused, needs attention. Pause or skip a meeting in one click.
- **Notifications** when saving starts and stops, and when a meeting runs with captions off.
- **Meetings list** by day with search across titles, people and text. Open, show in folder, copy path, text or file, export to Markdown, HTML, JSON or CSV.
- **Kept for 1 year** by default, then to the Recycle Bin. Change it or turn it off.
- **Hidden from screen sharing.** Import of Teams recording transcripts (`.vtt`). English and Russian, light and dark.

## Get started

### Windows

1. Download `Tolk-<version>-setup.exe` from **[Releases](https://github.com/Ilyakz/tolk/releases/latest)** and run it.
   The installer is not code-signed yet: on "Windows protected your PC" click **More info → Run anyway**.
2. In Teams: **Settings → Accessibility → Always show captions in my calls and meetings** — then every meeting is saved without you doing anything.
3. Accept the terms in Tolk's welcome window. Done: meetings appear in the list.

Needs Windows 10 (2004+) or 11, x64, and the new Teams desktop app (not Teams in a browser).

### macOS (preview)

1. Download `Tolk-<version>-mac-arm64.dmg` from **[Releases](https://github.com/Ilyakz/tolk/releases/latest)**, open it and drag Tolk to Applications.
2. The app is not notarized by Apple yet: the first time, macOS refuses to open it. Go to **System Settings → Privacy & Security** and click **Open Anyway**.
3. Allow Tolk in **System Settings → Privacy & Security → Accessibility** (Tolk opens the page). Once: updates keep it.
4. Accept the terms in Tolk's welcome window. Tolk turns Teams' captions on by itself when a call starts (can be turned off in its menu).

Needs macOS 13 or later on Apple Silicon, and the new Teams. Not on the Mac yet: notifications and hiding Tolk's
windows from screen sharing. A meeting window in full screen on another desktop cannot be read — Tolk shows it
and suggests popping the captions out.

## Privacy

Everything stays on your computer: no telemetry, no accounts. The network is used only to check
GitHub for updates (can be turned off). Notifications show the meeting's title, never what was said.
Details: [docs/PRIVACY.md](docs/PRIVACY.md).

## Limitations

- Tolk reads the Teams window through the system accessibility interface (UI Automation on Windows, Accessibility on macOS). A Teams update can break it until Tolk is updated.
- A transcript is as good as Teams' captions: words can be misheard and speakers mixed up.

**More:** install options, updates, uninstall, where files are, FAQ — **[docs/GUIDE.md](docs/GUIDE.md)**.

---

Microsoft, Teams and Windows are trademarks of the Microsoft group of companies; Apple, Mac and macOS
are trademarks of Apple Inc. Tolk is an independent project, not affiliated with or endorsed by Microsoft or Apple.
Licensed under [Apache 2.0](LICENSE) · [NOTICE](NOTICE) · [Third-party notices](THIRD-PARTY-NOTICES.txt)
