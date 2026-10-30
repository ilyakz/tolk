# Tolk — user guide

Everything about Tolk in detail. The short version is on the [main page](../README.md).

## What it does

- **Asks first.** On its first start Tolk shows a short welcome. Its last step asks you to accept the
  terms of use — you tell meeting participants yourself that you save the captions, and you are
  responsible for it. Until you tick that box, Tolk saves no meetings and deletes nothing.
- **Saves meetings automatically.** When a Teams meeting shows captions, Tolk starts a new text file
  and adds every caption line with its time and speaker; when the meeting ends, the file is closed.
  If you drop out and rejoin the same meeting within 10 minutes, the same file continues.
- **Shows its state in the tray**: waiting for a meeting, saving, paused, needs attention, or off.
  From the icon you can pause, stop saving the current meeting, or skip it altogether. The panel also
  shows the last meeting with **Open** and **Copy path**.
- **Copy the notice**: a ready message for the meeting chat saying that you are saving the captions
  for your notes. It is in the tray panel while a meeting is being saved or paused, in the welcome
  window and in Settings, where you can change the text.
- **Tells you when captions are off** in a running meeting, so you know that nothing is being saved.
  If captions go off in the middle of a meeting, Tolk keeps watching it and continues the same file
  when they are back on within 10 minutes.
- **Meetings window**: a compact list of all saved meetings, grouped by day, the one being saved at
  the top. **Enter** or a double click opens the transcript in your usual program for `.txt` files.
  For a selected meeting: **Show in folder**, **Copy path** (Ctrl+C), **Copy text** (Ctrl+Shift+C),
  **Copy file** — paste it into a Teams chat or an e-mail as an attachment — **Export…** to Markdown
  or to HTML for Word, and **Move to Recycle Bin** (Del). Select several meetings to copy their paths
  or files, export them into a folder or move them to the Recycle Bin at once. Right-click a meeting
  for the same actions. The meeting being saved is never deleted.
- **Search** (Ctrl+F) across titles, dates, participants and the text of every meeting; each meeting
  found shows the line with your word. Esc clears it.
- **Keeps meetings for 1 year** by default: once a day, meetings that started longer ago go to the
  Recycle Bin. The meeting being saved is never touched. Choose 30, 90 or 180 days or **Never
  delete** in the welcome window or in Settings → Storage, which also shows how many meetings the
  folder holds and how many are due.
- **Imports a Teams recording's transcript** (`.vtt`): it becomes a meeting in the list like any
  other. See [Recordings](#recordings). Tolk never saves recordings by itself.
- **Notifications** when a meeting starts being saved or continues the same file, when saving stops
  (with the number of lines saved), when a meeting goes on with its captions off, and when a new
  version is out. See [Notifications and the tray icon](#notifications-and-the-tray-icon).
- **Hides its windows when you share your screen**, so participants do not see them (can be turned
  off).
- **Updates** from this page's Releases: Tolk checks once a day (can be turned off) and installs only
  when you choose.
- Interface in **English and Russian**; light or dark theme, following Windows or as you choose.

## Notifications and the tray icon

Tolk shows a Windows notification by its tray icon when:

- a meeting starts being saved — **Saving captions: "…"** — or continues the same file after you
  rejoin within 10 minutes;
- a meeting goes on with its captions off (once per meeting), with where to turn them on;
- saving stops, with the number of lines saved: the meeting ended, its captions were lost, captions
  of another meeting appeared, you stopped it, or you turned automatic saving off; or that nothing was
  said (no notification when you exit Tolk);
- a new version is out (once per version).

Click a meeting's notification to open that meeting in the list; the captions notification opens
the welcome step on turning captions on, the update notification opens Settings → Updates.
Notifications show the meeting's title and the number of lines, never what was said. Turn them off
in Settings → Captions → **Show notifications**. They also follow Windows: if you see none, check
**Settings → System → Notifications** (Tolk and Do not disturb).

**Pin the icon.** Windows 11 puts new tray icons in the hidden icons (behind the **^** arrow), where
you cannot see whether a meeting is being saved. Drag the Tolk icon from there onto the taskbar, or
turn Tolk on in **Settings → Personalization → Taskbar → Other system tray icons**. While the icon
is hidden, Tolk suggests this once in a notification; clicking it opens the taskbar settings.

## Requirements

- Windows 10 version 2004 or later, or Windows 11; 64-bit (x64). Nothing else to install — .NET is
  included.
- The **new Microsoft Teams** desktop app for Windows. Teams in a web browser is not supported.
- **Live captions turned on in the meeting.** Tolk saves what Teams shows in its captions: no
  captions, nothing to save. Your organisation's Teams administrator can disable live captions; then
  Tolk cannot work in that organisation's meetings.

### "Always show captions"

You can turn captions on in each meeting by hand (in the meeting: **More (…) → Language and speech →
Show live captions**), but it is easy to forget. Instead, turn them on once for every meeting:

1. In Teams, open **Settings** (**…** next to your profile picture) → **Accessibility**.
2. Turn on **Always show captions in my calls and meetings**.

From then on captions appear in every call and meeting, and Tolk saves them without you doing
anything. Captions are only shown to you; turning them on does not notify other participants. If the
captions come out in the wrong language, set the spoken language in the meeting: **More (…) →
Language and speech → Spoken language**.

## Recordings

Tolk saves live captions only. If a meeting was recorded in Teams with a transcript, you can add that
transcript to Tolk yourself:

1. In Teams, open the recording → **Transcript** → **Download** → `.vtt` (often only the organiser can
   download it).
2. In the Meetings window, click the import button at the bottom (the arrow, **Import a recording
   transcript…**) and choose the file — or drop the `.vtt` onto the window.

The transcript becomes a meeting named `<title> (recording)` in your meetings folder, with times
counted from the start of the recording. If the file name has no meeting title, Tolk asks for one.
Search, export and the retention period work on it as on any meeting; importing the same file again
adds nothing. The downloaded `.vtt` is not changed. Tolk never imports or saves recordings by itself.

## Install

Download from **[Releases](https://github.com/Ilyakz/tolk/releases/latest)**:

| File | What it is |
|---|---|
| `Tolk-<version>-setup.exe` | Installer. On a first install it asks how to install: **for all users** (the default; `Program Files`, needs administrator rights) or **for me only** (no administrator rights). |
| `Tolk-<version>-portable.zip` | Portable version: unpack anywhere and run `Tolk.exe`. |
| `SHA256SUMS.txt` | SHA-256 checksums of the two files above. |
| `Tolk-<version>-setup.exe.sha256` | The installer's checksum on its own, for Tolk's in-app update. |

**"Windows protected your PC"?** The installer is not code-signed yet, so Microsoft Defender
SmartScreen does not know it. Click **More info → Run anyway**. To make sure the file is the one
published here, compare its checksum with `SHA256SUMS.txt`:

```powershell
Get-FileHash .\Tolk-1.5.18-setup.exe -Algorithm SHA256
```

The installer shows Tolk's terms of use as its license page; Tolk asks you to accept them once more
on its first start. It can also start Tolk when you sign in to Windows (a checkbox). On a work
computer, check that your organisation allows installing software like this before you install it.

An update keeps the mode of the installed copy (for all users or for you only), whether you run the
new installer yourself or Tolk updates itself. To change the mode, run the installer again and choose
**Reinstall for all users** (or **Reinstall for me only**): Tolk is reinstalled in the other mode, and
your settings and meetings stay.

**For administrators.** `setup.exe /ALLUSERS` or `/CURRENTUSER` chooses the mode without asking;
`/SILENT` or `/VERYSILENT` installs without the wizard (an installed copy keeps its mode).
`Tolk.exe --shutdown` asks a running Tolk to finish the current transcript and exit; the installer
uses it before it replaces files, and asks first if a meeting is being saved. `Tolk.exe --background`
starts Tolk in the tray without opening a window (this is how it starts with Windows).

## Update

When a new version is out, Tolk shows it in the tray panel and menu (**Update to …**). In Settings →
Updates, **Download and install** downloads the installer from this page's Releases, checks its
SHA-256 checksum and installs it; Tolk restarts and continues the meeting it was saving. During a
meeting Tolk asks whether to install now or after the meeting. A release that can only be installed
by hand offers its download page instead. You can also download the new `setup.exe` yourself and run
it: it offers **Update**. Settings and meetings are kept either way. Tolk checks for updates once a
day; this can be turned off in Settings → Updates.

## Uninstall

**Settings → Apps → Installed apps → Tolk → Uninstall.** The uninstaller asks what to delete along
with the program, with two boxes that are **not ticked**:

- **Delete meeting records** (transcripts and the files next to them) — only the files Tolk itself
  created, recognised by their names;
- **Delete Tolk's settings and logs**.

Leave them unticked and your meeting files stay on disk. A silent uninstall never deletes them.

Portable version: turn off "Start Tolk when I sign in to Windows" in Tolk's settings if you turned it
on, exit Tolk, and delete its folder. Settings and logs are in `%APPDATA%\Tolk`; delete that folder
too if you want them gone.

## Where your data is

| What | Where |
|---|---|
| Meetings (transcripts) | `%USERPROFILE%\TeamsTranscripts\transcripts` by default, or the folder chosen in Settings → Storage. One file per meeting: `<meeting name>_<date>_<time>.txt`, for example `Demo planning_2026-10-28_10-00-00.txt` |
| Settings | `%APPDATA%\Tolk\settings.json` |
| Log | `%APPDATA%\Tolk\logs\tolk.log` (states, times, meeting titles and notifications shown — never what was said) |
| Program | `Program Files\Tolk` (all users) or `%LOCALAPPDATA%\Programs\Tolk` (just me) |

A transcript is plain UTF-8 text, one caption per line:

```text
# Teams transcript — Demo planning
# Started: 2026-10-28 10:00:00

[10:00:05] Alex Demo: Let's start with the release date.
[10:00:12] Sam Example: Friday works for us.
```

Details: [PRIVACY.md](PRIVACY.md).

## Privacy

- **Everything stays on your computer.** Transcripts, settings and logs are local files. Meeting text
  goes only where you copy, paste or export it yourself.
- **No telemetry**, no accounts, no servers of Tolk's own. Tolk sends nothing to its authors.
- **The network is used only for updates**: once a day (unless turned off) and when you check, Tolk
  asks GitHub for the latest Tolk release; it downloads the installer from there only when you choose
  to update. No meeting data is sent.
- **Notifications** show the meeting's title and the number of lines saved, never what was said.

The full description — what is stored, what leaves the computer and when, how to delete everything —
is in **[PRIVACY.md](PRIVACY.md)**.

## Your responsibilities

Tolk is a tool; how you use it is your responsibility. By accepting the terms of use — in the
installer and on Tolk's first start — you confirm that you inform the participants yourself and that
the responsibility is yours.

- **Teams does not notify participants** that you are saving the captions. Captions are only shown on
  your screen, and other participants see no recording or transcription notice because of Tolk.
- **Tell the participants** that you are saving a text record of the meeting — **Copy the notice**
  gives you a ready message for the meeting chat — and **get their consent** wherever the law, your
  organisation's policy or the meeting's rules require it. Laws on recording conversations and on
  personal data differ between countries and regions.
- **Do not use Tolk in meetings where copying captions or transcription is prohibited** — for example
  meetings with **Prevent copying** turned on, meetings with a **sensitivity label** that restricts
  copying, or meetings whose organiser or participants object. Use **Don't save this meeting** in the
  tray for such meetings, or turn automatic saving off.
- **Follow your organisation's policies** on recording, confidentiality, data retention and
  installing software.
- **Look after the files you create**: who can see them, where you copy or send them, and when you
  delete them.

Tolk is not meant for, and must not be used for, recording people secretly.

## Limitations

- Tolk reads the captions through **Windows UI Automation** — the accessibility interface that screen
  readers use — from the Teams window. How Teams builds its window is not a documented interface:
  **an update of Teams can stop Tolk from working** until Tolk is updated too.
- A transcript is only as good as Teams' live captions: words can be missed or misheard, speakers
  can be mixed up, and short pieces may repeat. Do not treat it as an exact record.
- Only what Teams shows as captions is saved: no audio, video, chat, shared screens or files.
- Only the new Teams desktop app for Windows is supported.

## FAQ

**Tolk is running, but nothing is saved. Why?**
Either the terms of use are not accepted yet — the tray panel then says so and **Accept the terms**
opens them — or the meeting has no captions (see below).

**I don't see Tolk's notifications.**
Check that **Show notifications** is on in Settings → Captions, that Windows allows notifications
from Tolk and Do not disturb is off (**Settings → System → Notifications**). Each notification is
also written to the log as a `[notify]` line, with whether it was shown.

**Where is the log?**
`%APPDATA%\Tolk\logs\tolk.log` (two older parts next to it, `tolk.log.1` and `tolk.log.2`). When
saving stops with an error, **Open log** in the tray panel opens it. The log holds states, times and
meeting titles, never what was said; check it before you send it to anyone.

**Why do captions have to be on?**
Tolk does not listen to the audio. It saves the text that Teams' live captions show on your screen.
If captions are off, there is nothing to save — Tolk warns you when a meeting is running without
them. Turn on **Always show captions** (see [above](#always-show-captions)) and you don't have to
think about it.

**Does Tolk delete my meetings?**
Only if they are older than the period you keep them for: 1 year unless you chose otherwise. They go
to the Recycle Bin, not straight off the disk. Choose **Never delete** in Settings → Storage to keep
everything. A meeting you delete in the Meetings window also goes to the Recycle Bin.

**Where are my files?**
By default in `%USERPROFILE%\TeamsTranscripts\transcripts`; the Meetings window lists them all, and
**Meetings folder** at its bottom opens the folder. See [Where your data is](#where-your-data-is).

**How do I send a transcript to someone?**
Select the meeting and choose **Copy file** (in the **⋯** menu or on right click), then paste it into
a Teams chat or an e-mail with Ctrl+V: it arrives as an attachment. **Copy text** copies what was
said instead, and **Export…** saves it as Markdown or as HTML that Word opens.

**How do I move the folder?**
Choose another folder in Settings → Storage. With **Move existing meetings when the folder changes**
on (the default), Tolk moves the saved meetings there; a file that already exists in the new folder
is never overwritten.

**What happens when Teams updates?**
Usually nothing. But if Teams changes how its meeting window is built, Tolk may stop finding the
captions: the tray icon then shows that saving isn't working. Check this page for a new version of
Tolk. Files already saved are not affected.

**Troubleshooting: what does Tolk see in the Teams window?**
To report a problem with how Tolk finds captions, open the Teams window in question (not minimised)
and run in PowerShell, with the path of your `Tolk.exe` (`%LOCALAPPDATA%\Programs\Tolk` or
`C:\Program Files\Tolk`):

```powershell
& "$env:LOCALAPPDATA\Programs\Tolk\Tolk.exe" --dump-uia --out "$env:USERPROFILE\Desktop\tolk-uia.txt" | Out-Host
```

It writes a text snapshot of how the Teams windows are built, as UI Automation shows them, and
prints where the file is; `--title "<part of the title>"` keeps only some windows. It saves no
meeting and sends nothing. Names in the snapshot are replaced by their length and a hash, except
labels such as buttons, menu items and tabs, short names of elements about captions, transcripts or
recordings, and window titles, which can contain a meeting's title. Read the file through and
replace anything private before you share it.

**Does Tolk work in meetings in other languages?**
Yes — it saves whatever text the captions show. Set the spoken language in the meeting so that Teams
recognises speech correctly.
