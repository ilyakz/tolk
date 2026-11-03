# Changes

## 1.6.0

- **Tolk for macOS (preview):** a menu-bar app for Apple Silicon, macOS 13+. It turns Teams' captions on by itself.
- Export a meeting to JSON or to CSV for Excel (in the meeting's menu, next to Markdown and HTML).

---

- **Tolk для macOS (предварительная версия):** приложение в строке меню для Apple Silicon, macOS 13+. Субтитры Teams включает само.
- Экспорт встречи в JSON и в CSV для Excel (в меню встречи, рядом с Markdown и HTML).

## 1.5.18

- Captions are saved while the meeting window is minimized or the whole screen is shared (they used to be lost).
- No more repeated lines in transcripts.
- If captions cannot be read, the tray icon shows "needs attention" right away.

---

- Субтитры сохраняются, когда окно встречи свёрнуто или идёт показ всего экрана (раньше терялись).
- Больше никаких повторяющихся строк в расшифровках.
- Если субтитры нельзя прочитать, значок в трее сразу показывает «нужно внимание».

## 1.5.16

The first public release of Tolk.

**English**

- Saves the live captions of Microsoft Teams meetings as text files on your computer — when, who and what was said — automatically when a meeting shows captions; a rejoin within 10 minutes continues the same file.
- Terms of use first: on the first start Tolk asks you to accept that you inform meeting participants yourself and that the responsibility is yours (the installer shows the same terms). Until you accept them, Tolk saves no meetings and deletes nothing.
- "Copy the notice": a ready message for the meeting chat that you are saving the captions — in the tray panel while a meeting is saved or paused, in the welcome window and in Settings, where the text can be changed.
- Tray icon with the current state (waiting, saving, paused, needs attention, off) and a panel to pause, stop saving the current meeting or skip it, with the last meeting to open or copy its path.
- Notifications by the tray icon, with the meeting's title and the number of lines saved, never what was said: a meeting starts being saved, or continues the same file; a meeting goes on with its captions off (once per meeting, with where to turn them on); every end of saving — the meeting ended, captions were lost, another meeting's captions appeared, you stopped it, automatic saving was turned off, or no lines were said; a new version (once per version); and, once, a hint to pin the icon when Windows 11 keeps it in the hidden icons. Clicking a meeting's notification opens it in the list. Settings → Captions → "Show notifications" turns them off.
- Captions turned off in the middle of a meeting: Tolk says so, keeps watching the meeting with the "needs attention" icon, and continues the same file when they are back on.
- Reliability: if Teams stops answering, Tolk no longer waits on it for good — a scan stuck for a minute is abandoned and watching for meetings starts again by itself. Once every 10 minutes the log notes that Tolk is watching (number of scans and their duration); an unexpected error is written to the log, and the error window names the version and the log file.
- Follows Teams as it changes: a new captions panel after the spoken language is changed is picked up within seconds, so is captions popped out into their own or a pinned window; the end of a call is noticed about 5 seconds after its window closes.
- Light in the background: while Tolk only sits in the tray it uses well under 1% of one CPU core and about 15 MB of memory (Task Manager); the windows' memory is given back a few seconds after they close.
- Setup checks GitHub for a newer release and offers to download and install it instead (the download is checked against its SHA-256); without a connection it simply goes on.
- Meetings window: a compact list of every saved meeting by day, each with its date and start time. Enter opens the transcript in your program for .txt files; show it in its folder, copy its path, text or the file itself (paste it into a chat or an e-mail as an attachment), export it to Markdown or HTML for Word, or move it to the Recycle Bin — also for several meetings at once. Search across titles, dates, participants and the text, with the matching line under each meeting found.
- Import of a Teams recording's transcript: download the recording's transcript as .vtt in Teams and import it with the button at the bottom of the Meetings window, or drop the file onto the window. It becomes a meeting "<title> (recording)" in the list that search, export and retention treat like any other; importing the same file twice adds nothing. Tolk never saves recordings by itself.
- Meetings are kept for 1 year by default: once a day, older meetings go to the Recycle Bin; 30, 90 or 180 days or "Never delete" can be chosen. The meeting being saved is never touched. Settings → Storage shows how many meetings the folder holds and how many are due, and can move the meetings with the folder. Nothing is deleted before the terms are accepted.
- Tolk's windows are hidden when you share your screen (can be turned off).
- Update check once a day against this repository's releases (can be turned off); an update is installed only when you choose, verified by its SHA-256 checksum.
- Installer for all users (the default on a first install) or just for you (no administrator rights), and a portable ZIP. Updates keep the installed mode; "Reinstall for all users / for me only" switches it. `Tolk.exe --shutdown` asks a running Tolk to finish its transcript and exit. Uninstalling keeps your meetings unless you tick the box. For troubleshooting, `Tolk.exe --dump-uia` writes a snapshot of how the Teams windows look to Tolk, with names hidden except labels and window titles.
- Interface in English and Russian, light and dark theme.
- Everything stays on your computer: no telemetry, no accounts; the network is used only for updates. See docs/PRIVACY.md.

**Русский**

- Сохраняет живые субтитры встреч Microsoft Teams в текстовые файлы на вашем компьютере — когда, кто и что сказал — автоматически, как только на встрече появляются субтитры; если вернуться на встречу в течение 10 минут, запись продолжится в том же файле.
- Сначала условия использования: при первом запуске Tolk просит принять, что участников встречи предупреждаете вы сами и ответственность — ваша (те же условия показывает установщик). Пока они не приняты, Tolk не сохраняет встречи и ничего не удаляет.
- «Скопировать уведомление»: готовое сообщение для чата встречи о том, что вы сохраняете субтитры, — на панели у значка, пока встреча сохраняется или стоит на паузе, в окне приветствия и в настройках, где текст можно изменить.
- Значок в трее показывает состояние (ждёт, сохраняет, пауза, нужно внимание, выключен), на панели — пауза, остановка для текущей встречи или отказ от её сохранения и последняя встреча, которую можно открыть или скопировать путь к ней.
- Уведомления у значка — с названием встречи и числом сохранённых реплик, но без того, что было сказано: встреча начала сохраняться или запись продолжается в том же файле; встреча идёт с выключенными субтитрами (один раз за встречу, с подсказкой, где их включить); любое окончание записи — встреча закончилась, субтитры пропали, появились субтитры другой встречи, вы остановили запись, выключили автосохранение или реплик не было; вышла новая версия (один раз на версию); и один раз — подсказка закрепить значок, если Windows 11 прячет его в скрытых значках. Щелчок по уведомлению о встрече открывает её в списке. Отключаются в настройках: «Субтитры» → «Показывать уведомления».
- Субтитры выключили посреди встречи: Tolk сообщает об этом, продолжает следить за встречей со значком «нужно внимание» и, когда субтитры снова включены, продолжает тот же файл.
- Надёжность: если Teams перестал отвечать, Tolk больше не ждёт его бесконечно — опрос, зависший на минуту, бросается, и наблюдение за встречами запускается заново само. Раз в 10 минут журнал отмечает, что Tolk следит за встречами (число опросов и их длительность); непредвиденная ошибка пишется в журнал, а окно ошибки называет версию и файл журнала.
- Успевает за Teams: новая панель субтитров после смены языка речи подхватывается за секунды, как и субтитры в отдельном или закреплённом окне; конец звонка замечается примерно через 5 секунд после закрытия его окна.
- Лёгкий в фоне: пока Tolk только в трее, он тратит заметно меньше 1 % одного ядра процессора и около 15 МБ памяти (Диспетчер задач); память окон возвращается системе через несколько секунд после их закрытия.
- Установщик проверяет на GitHub, нет ли более новой версии, и предлагает скачать и установить её (загрузка сверяется по SHA-256); без связи он просто продолжает.
- Окно «Встречи»: компактный список всех сохранённых встреч по дням, у каждой — дата и время начала. Enter открывает расшифровку в программе для файлов .txt; можно показать её в папке, скопировать путь, текст или сам файл (вставить в чат или письмо вложением), экспортировать в Markdown или HTML для Word или отправить в корзину — в том числе несколько встреч сразу. Поиск по названиям, датам, участникам и тексту, под каждой найденной встречей — строка с совпадением.
- Импорт стенограммы записи Teams: скачайте в Teams стенограмму записи в формате .vtt и импортируйте её кнопкой внизу окна «Встречи» или перетащите файл в окно. В списке появится встреча «<название> (запись)», с которой поиск, экспорт и срок хранения работают как с любой другой; повторный импорт того же файла ничего не добавляет. Сам Tolk записи не сохраняет никогда.
- Встречи по умолчанию хранятся 1 год: раз в день более старые уходят в корзину; можно выбрать 30, 90 или 180 дней или «Не удалять». Встречу, которая сохраняется сейчас, Tolk не трогает. В настройках, в разделе «Хранение», видно, сколько встреч в папке и сколько подходит под очистку, и можно переносить встречи вместе с папкой. До принятия условий ничего не удаляется.
- Окна Tolk скрыты, когда вы показываете экран (можно отключить).
- Проверка обновлений раз в день в выпусках этого репозитория (можно отключить); обновление ставится, только когда вы решите, и проверяется по контрольной сумме SHA-256.
- Установщик для всех пользователей (по умолчанию при первой установке) или только для вас (без прав администратора) и портативный ZIP. Обновление сохраняет режим установленной копии; «Переустановить для всех пользователей / только для меня» меняет его. `Tolk.exe --shutdown` просит запущенный Tolk дописать расшифровку и завершиться. При удалении встречи остаются, если не поставить галочку. Для разбора неполадок `Tolk.exe --dump-uia` записывает снимок того, как окна Teams видны Tolk; имена в нём скрыты, кроме подписей элементов и заголовков окон.
- Интерфейс на русском и английском, светлая и тёмная тема.
- Всё остаётся на вашем компьютере: без телеметрии и учётных записей; в сеть Tolk выходит только за обновлениями. См. docs/PRIVACY.ru.md.
