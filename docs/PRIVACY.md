# Tolk and your data

[Русская версия](PRIVACY.ru.md)

**In short:** Tolk keeps everything on your computer. It has no telemetry, no accounts and no servers
of its own, and it sends nothing to its authors. It goes online only to check GitHub for updates.
Meeting text goes only where you copy, paste or export it yourself. Tolk saves no meetings until you
accept its terms of use on the first start.

This page describes Tolk 1.5.16.

## What Tolk reads

Tolk reads the Microsoft Teams meeting window through Windows UI Automation, the accessibility
interface that screen readers use: the meeting title and the live captions that Teams shows on your
screen — the speaker's name and the text. It does not record audio or video, take screenshots, read
Teams' chat, read Teams' files on disk, or call Teams or Microsoft 365 services.

Besides that, Tolk reads only:

- a recording's transcript (`.vtt`) that you import yourself (see below);
- from the Windows registry: whether Windows keeps Tolk's tray icon in the hidden icons
  (`HKCU\Control Panel\NotifyIconSettings`).

## What Tolk stores, and where

| What | Where | Contents |
|---|---|---|
| Transcripts | `%USERPROFILE%\TeamsTranscripts\transcripts` by default, or the folder chosen in Settings → Storage; one `<meeting name>_<date>_<time>.txt` per meeting | The meeting title and start time, then each caption line with its time, the speaker's name as Teams shows it, and the text; pause and resume marks. |
| Settings | `%APPDATA%\Tolk\settings.json` | Your choices: interface language and theme, transcripts folder and whether meetings move with it, whether you accepted the terms of use, your notice for the meeting chat if you changed it, how long meetings are kept, hiding from screen sharing, update checks on/off and the time of the last check, notifications on/off and which one-time notices were already shown (the last version announced, the hint to pin the icon), the size and position of the Meetings window, and similar. No meeting text. |
| Logs | `%APPDATA%\Tolk\logs\` (`*.log`, rotated at about 1 MB, two older copies kept) | What Tolk did and when: start and stop, meeting window titles, file names, number of lines saved, each notification (its kind, the meeting's title and whether it was shown), every 10 minutes how many scans of the Teams windows ran and how long they took, errors with the program's error details. **Never what was said or who said it.** |
| Registry | `HKCU\Software\Tolk` (`TranscriptsDir`, `Language`; `HKLM\Software\Tolk` for an all-users install), and the value `Tolk` under `...\CurrentVersion\Run` if Tolk starts with Windows | The transcripts folder (so that the uninstaller can find your meetings), the installer language, the autostart command. |
| Update download | `%TEMP%\tolk-update-…` | The downloaded installer, while it is checked and run. |

The portable version stores its settings and logs in the same `%APPDATA%\Tolk` folder.

**The clipboard.** The Meetings window puts on the Windows clipboard only what you ask for: a
transcript's path (**Copy path**), its text (**Copy text**) or the file itself, for pasting as an
attachment (**Copy file**). The tray panel's **Copy path** and **Copy the notice** put only the path
or the notice text there. If Windows clipboard history (Win+V) is on, a copy of copied text stays in
that history; if "Sync across your devices" is also on, Windows may sync it through your Microsoft
account. Clear it with Win+V → **Clear all**.

**Notifications.** When a meeting starts or stops being saved, or goes on with its captions off, Tolk
shows a Windows notification with the meeting's title and the number of lines saved — never what was
said. Other notifications (a new version, pinning the tray icon) contain no meeting data. Windows itself displays them: depending on your Windows settings
the meeting's title can be seen on the screen by anyone near it, and Windows may keep it in its
notification centre until you clear it. Settings → Captions → **Show notifications** turns them off;
Windows' own notification settings apply too.

**Imported recordings.** When you import a Teams recording's transcript (`.vtt`), Tolk reads that
file and writes a new transcript `<title> (recording)_<date>_<time>.txt` into the transcripts folder,
with the speakers' names and the text from the file. Everything happens on your computer; the `.vtt`
itself is not changed, and the new transcript is kept, searched and deleted like any meeting.

**Troubleshooting snapshot.** Only when you run `Tolk.exe --dump-uia`, Tolk writes a text file
(where `--out` says, or `%TEMP%\tolk-uia-<time>.txt`) describing how the Teams windows are built.
Names in it are replaced by their length and a hash, except labels such as buttons, menu items and
tabs, short names about captions, transcripts or recordings, and window titles, which can contain a
meeting's title. Its header names the versions of Tolk and Windows, the monitors and the Teams
process numbers. The file stays on your computer; read it before you share it with anyone.

**Exports** (Markdown or HTML) are written only where you save them.

## What leaves your computer, and when

| When | Where to | What is sent |
|---|---|---|
| Update check: automatically once a day (can be turned off in Settings → Updates) or when you check by hand | `api.github.com` (GitHub) | An ordinary HTTPS request for the latest release of `Ilyakz/tolk`, with Tolk's version in the User-Agent header. GitHub sees your IP address, as with any web request. **No meeting data.** |
| Setup: when you run the installer (not for Tolk's own silent updates) | `api.github.com` (GitHub) | The same request for the latest release, to offer a newer version than the installer you started. No meeting data. |
| Update download: only when you choose to update | `github.com` and GitHub's download servers (`objects.githubusercontent.com`, `release-assets.githubusercontent.com`) | A request for the installer and its checksum. No meeting data. |

Nothing else. Tolk has no analytics, crash reporting, advertising or "phone home" of any kind. When
an update can only be installed by hand, Tolk opens its GitHub download page in your browser; it
sends nothing itself.

What you copy, paste, attach or export from Tolk yourself — into a chat, an e-mail or another
program — is up to you and the rules of that service and your organisation.

## How long it is kept

- **Meetings** are kept for **1 year** by default: once a day (and shortly after Tolk starts)
  meetings that started longer ago go to the Recycle Bin, each with the files kept next to it. The
  meeting being saved is never touched. Choose 30, 90 or 180 days, or **Never delete**, in the
  welcome window or in Settings → Storage. Nothing is deleted before you accept the terms of use.
  Deleting a meeting in Tolk also moves it to the Recycle Bin, so it is gone for good only once the
  Recycle Bin is emptied.
- **Logs** never grow beyond about 3 MB: the oldest part is overwritten.
- **Settings** stay until you uninstall Tolk with the "settings and logs" box ticked, or delete them.

## How to delete everything

1. Uninstall Tolk (**Settings → Apps → Installed apps → Tolk → Uninstall**) and tick **both** boxes:
   meeting records, and settings and logs. The uninstaller deletes only the files Tolk created
   (recognised by their names); anything else you put into the transcripts folder stays.
2. Empty the Recycle Bin if Tolk moved meetings there earlier.
3. Delete what is left, if anything:
   - the transcripts folder (by default `%USERPROFILE%\TeamsTranscripts\transcripts`) with any exports
     or other files you put there;
   - `%APPDATA%\Tolk` (for the portable version: also the folder you unpacked it into; turn off
     "Start Tolk when I sign in to Windows" first, or delete the `Tolk` value under
     `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`);
   - `%TEMP%\tolk-update-*` folders, and `%TEMP%\tolk-uia-*.txt` snapshots if you made any;
   - exported files wherever you saved them, and copies you pasted or attached elsewhere;
   - clipboard history (Win+V → **Clear all**).

## Questions

If something here is unclear or seems wrong, open an issue at
https://github.com/Ilyakz/tolk/issues. Please never attach real transcripts or logs with real names.
