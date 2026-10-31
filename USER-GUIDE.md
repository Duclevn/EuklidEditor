# Euklid Editor User Guide

Euklid Editor is a lightweight text and code editor for Windows with a built-in **Preview**, an integrated **Terminal** and a folder **Explorer**. This guide ships inside the app, works offline and opens with **Help → Documentation** or `F1`.

## Getting started

- **Open something.** `Ctrl+O` opens a file, `Ctrl+K Ctrl+O` opens a folder as your workspace, and `Ctrl+R` lists recent files and folders. You can also drag files onto the window, or use **Open with** in File Explorer (the installer and the Store version add it).
- **Start typing.** With no document open the start page offers Open File and Open Folder, your recent items and the main keys. Typing on it starts a new file.
- **Find any command.** `Ctrl+Shift+P` opens the Command Palette: every command, the ones you used recently first. `Ctrl+P` goes to a file in the workspace, `Ctrl+G` to a line, `Ctrl+Shift+O` to a symbol in the current file.
- **Your work is safe.** Unsaved edits and open tabs are kept when you close the window and come back at the next start (hot exit; you can turn it off in Settings). Saves keep the file's encoding and line endings and never leave half a file. If another program changes a file you have open, Euklid Editor reloads it when you have no edits, or asks what to do when you do.

## The window

- **Title bar:** the menus, the command center, the **Read** / **Edit** button for View only mode, and the window buttons.
- **Activity rail** (left edge): the Explorer, Find in Files and the Terminal.
- **Editor:** tabs with a dot on unsaved files. `Ctrl+\` splits the editor into two groups that can show the same file or different ones; **View → Editor Layout** chooses one or two columns. `Ctrl+K Ctrl+P` lists every open file, and `Ctrl+K Ctrl+Shift+T` reopens the last closed one.
- **Preview** (right of the editor, `Ctrl+Shift+V`) and **Terminal** (below, `Ctrl+Shift+T` or `` Ctrl+` ``) open only when you ask for them. Euklid Editor stays small until you do.
- **Status bar:** the caret position, indentation, encoding, line endings and language; each one is clickable and offers to change it.
- In a narrow window the side panels step aside: the one you asked for last stays.
- `F6` and `Shift+F6` move the keyboard focus between the panes; `Ctrl+1`, `Ctrl+2` and `Ctrl+3` jump to the editor, the Preview and the Terminal.

## Explorer and Find in Files

- The **Explorer** (`Ctrl+B` to show or hide, `Ctrl+Shift+E` to focus) shows your workspace folder with file-type icons. Create, rename, move by drag and drop and delete files and folders there; deleting moves them to the Recycle Bin. A folder that is a symbolic link or junction is listed greyed out and is not opened, so a link never leads outside the workspace.
- **Go to File** (`Ctrl+P`) matches your typing fuzzily against every file of the workspace. `name:line` jumps to a line, and `@` lists the symbols of the current file.
- **Find in Files** (`Ctrl+Shift+F`) searches the workspace in the background and groups the results by file. It takes regular expressions, case and whole-word options, and **files to include** and **files to exclude** (glob patterns). Build folders such as `build`, `out`, `dist`, `bin`, `obj` and `target` are skipped unless you include them. Unsaved editors are searched as they are on screen.
- **Replace in Files** (`Ctrl+Shift+H`) asks before it changes anything, skips files that changed since the search, and each open file can be undone with `Ctrl+Z`.

## Editing

- **Multiple cursors:** `Ctrl+D` adds the next occurrence of the selected word, `Ctrl+Shift+L` selects every occurrence, `Ctrl+Alt+Up` and `Ctrl+Alt+Down` add a cursor on the line above or below, `Shift+Alt+I` puts a cursor at the end of each selected line, and `Ctrl+U` removes the last one. Ordinary typing, paste, delete and the line commands work on all cursors at once.
- **Lines:** move (`Alt+Up`, `Alt+Down`), copy (`Shift+Alt+Up`, `Shift+Alt+Down`), delete (`Ctrl+Shift+K`), insert above or below, join (`Ctrl+J`), indent and outdent (`Ctrl+]`, `Ctrl+[`), comment (`Ctrl+/`), expand the selection by line (`Ctrl+L`). **Edit → Line** also sorts (ascending, descending, ignoring case, by number, by length), reverses, removes duplicate, empty and blank lines and trims whitespace.
- **Selection and case:** **Edit → Selection** has the case transforms (upper, lower, title, sentence, invert) and more selection helpers.
- **Code folding:** the chevrons in the gutter, `Ctrl+Shift+[` and `Ctrl+Shift+]`, and `Ctrl+K Ctrl+0` / `Ctrl+K Ctrl+J` for all.
- **Bookmarks:** `Ctrl+F2` toggles one, `F2` and `Shift+F2` go to the next and previous.
- **Format Document** (`Shift+Alt+F`) re-indents JSON, XML and SVG. It only changes whitespace, and a document with an error is left as it is, with the error in the status bar.
- **Markdown:** `Enter` continues lists, quotes and tasks; **Edit → Markdown** has Toggle Task Item, Format Table and heading promote and demote.
- **Encodings and line endings:** the status bar reopens or saves a file as another encoding (UTF-8, UTF-16, UTF-32 and Windows code pages) and converts line endings. A file that is not valid text opens as raw bytes and is saved back unchanged.
- **Run:** `F5` runs the active file and `F9` the selection in the Terminal, and `Ctrl+Alt+T` opens a Terminal in the file's folder.

## Find and Replace

`Ctrl+F` opens the Find bar over the editor, `Ctrl+H` adds Replace. It finds as you type, shows the number of matches, and offers regular expressions, match case and whole word. The regular expressions use the same syntax as Find in Files, with `$1` (or ``) for a captured group in the replacement.

## Preview

The Preview shows the active file next to the editor and follows your edits. It works offline, and its pages cannot reach the network, not even for images.

| File | Preview |
|---|---|
| Markdown | Tables, task lists, highlighted code, Mermaid and PlantUML diagrams and KaTeX math |
| YAML and JSON that is an OpenAPI document | The API reference |
| CSV and TSV | A table |
| PDF | The pages, with zoom and search |
| PNG, JPEG, GIF, BMP, WebP, TIFF | The picture, with zoom |

Other JSON and XML files have no Preview. Markdown without diagrams or math, PDF, images and CSV are drawn by Euklid Editor itself, so they open quickly and use little memory; diagrams and math use the browser engine that Windows provides (the WebView2 Runtime), which starts only for those documents. With **Scroll sync** on (Settings), the Preview and the editor scroll together, and double-clicking in the Preview jumps to that line of the source. Links in a Preview open in your browser only after you confirm.

## Terminal

The Terminal (`` Ctrl+` `` or `Ctrl+Shift+T`) runs PowerShell, Command Prompt, Git Bash or a WSL distribution in the folder you choose, in up to ten tabs. `` Ctrl+Shift+` `` opens a new tab and `Ctrl+Shift+W` closes one; closing a tab with a running command asks first.

- Copy and paste work as in Windows Terminal, and a paste of several lines into a shell that cannot tell it from typing asks first.
- `Ctrl+click` opens a file path or a link in the output (links ask first).
- `Ctrl+F` finds in the output. A background tab that rings the bell shows a dot, and the taskbar button flashes; progress reported by a program shows on its tab.
- Files dropped onto the Terminal are typed as paths.
- **Terminal → Open Terminal Profiles (JSON)** opens `profiles.json`, where you add your own profiles (command line, arguments, start folder, environment) or hide detected ones. **Settings → Terminal** has the default profile and start folder, the font, the cursor, the scrollback and a few behaviors.

## View only mode

View only (`Ctrl+Alt+V`, or the **Read** button in the title bar) turns the window into a quiet reader: it shows just the file, as its Preview or as read-only text, with no Explorer, tabs, Terminal or menus. A file you double-click opens straight into the mode you used last. `Ctrl+=`, `Ctrl+-` and `Ctrl+0` zoom. Everything you were editing stays as it was, and **Edit** brings the full window back. The editing commands, including the Tools menu, are off while you read.

## Tools menu

The **Tools** menu has five commands. None has a default key, but you can give each one in `keybindings.json`.

- **Compare Files…** (`tools.compare`) compares the text of two files line by line. The left side is the file you are editing; choose the right side from your other open files or browse for a file. The two files appear side by side in their own window with line numbers, removed, added and changed lines tinted and one shared scroll. **Next** and **Previous** (`F7` and `Shift+F7` in that window) jump between differences, **Ignore trailing whitespace** ignores spaces at the end of lines, and `Esc` or `Ctrl+W` closes the window. A file you have changed but not saved is compared as it is on screen and marked *unsaved*. If two files differ only in line endings or encoding (for example UTF-8 and UTF-8 with BOM), the window says so instead of marking every line. Files over 5 MiB, binary files and pairs that are too different to compare line by line are refused with a reason.
- **Base64 Encode** and **Base64 Decode** convert every selection, or the whole document when nothing is selected, as one undo step. Text is encoded as UTF-8. Decoding accepts input without `=` padding, ignores spaces and line breaks inside the data, and accepts the URL-safe alphabet (`-` and `_`).
- **URL Encode** and **URL Decode** do the same with percent-encoding (RFC 3986): letters, digits and `-` `.` `_` `~` stay, every other byte of the UTF-8 text becomes `%XX` (space is `%20`). Decoding reads `%XX` sequences only; a `+` stays a `+`, it is not turned into a space.

If any selection cannot be converted (invalid Base64, a broken `%` sequence, or a result that is not text), nothing changes at all, and the status bar says why and how many selections failed.

## Settings and keyboard shortcuts

- **Settings** (`Ctrl+,`) has Appearance (the Default, Dark and Light themes), Editor (font, tab width, spaces or tabs, wrap, rulers, auto-closing brackets, hot exit), Preview (scroll sync) and Terminal. **Reset Settings** in the Command Palette puts everything back, with an option to reset your keyboard shortcuts too.
- **Keyboard Shortcuts** (`Ctrl+K Ctrl+S`) lists every key. To change one, choose **File → Keyboard Shortcuts (JSON)**: it opens `keybindings.json`, created with every command and its key as comments. Add entries in the format of VS Code:

  ```json
  { "key": "ctrl+alt+c", "command": "tools.compare" }
  ```

  A `-` before the command name removes a key (`"command": "-tools.compare"`). Comments and trailing commas are allowed, and the file is applied when you save it.
- Everything is kept for your Windows user only; nothing is uploaded.

## Keyboard shortcuts

The default keys. The command ID is what you use in `keybindings.json`.

| Action | Command ID | Default key |
|---|---|---|
| New file | `file.new` | `Ctrl+N` |
| Open file | `file.open` | `Ctrl+O` |
| Open folder | `workspace.openFolder` | `Ctrl+K, Ctrl+O` |
| Open recent | `file.openRecent` | `Ctrl+R` |
| Save | `file.save` | `Ctrl+S` |
| Save as | `file.saveAs` | `Ctrl+Shift+S` |
| Save all | `file.saveAll` | `Ctrl+Alt+S` |
| Reopen closed editor | `file.reopenClosed` | `Ctrl+K, Ctrl+Shift+T` |
| Settings | `settings.open` | `Ctrl+,` |
| Command Palette | `commandPalette.open` | `Ctrl+Shift+P` |
| Go to file | `workspace.quickOpen` | `Ctrl+P` |
| Go to line | `edit.goToLine` | `Ctrl+G` |
| Go to symbol | `edit.goToSymbol` | `Ctrl+Shift+O` |
| Go back | `go.back` | `Alt+Left` |
| Go forward | `go.forward` | `Alt+Right` |
| Find | `edit.find` | `Ctrl+F` |
| Replace | `edit.replace` | `Ctrl+H` |
| Find in files | `search.findInFiles` | `Ctrl+Shift+F` |
| Replace in files | `search.replaceInFiles` | `Ctrl+Shift+H` |
| Toggle comment | `edit.toggleLineComment` | `Ctrl+/` |
| Indent line | `edit.indentLines` | `Ctrl+]` |
| Outdent line | `edit.outdentLines` | `Ctrl+[` |
| Move line up | `edit.moveLinesUp` | `Alt+Up` |
| Move line down | `edit.moveLinesDown` | `Alt+Down` |
| Delete line | `edit.deleteLines` | `Ctrl+Shift+K` |
| Join lines | `edit.joinLines` | `Ctrl+J` |
| Add next occurrence | `edit.addSelectionToNextFindMatch` | `Ctrl+D` |
| Select all occurrences | `edit.selectAllOccurrences` | `Ctrl+Shift+L`, `Alt+F3` |
| Add cursor above | `edit.insertCursorAbove` | `Ctrl+Alt+Up` |
| Add cursor below | `edit.insertCursorBelow` | `Ctrl+Alt+Down` |
| Format document | `edit.formatDocument` | `Shift+Alt+F` |
| Toggle bookmark | `edit.toggleBookmark` | `Ctrl+F2` |
| Next bookmark | `edit.nextBookmark` | `F2` |
| Previous bookmark | `edit.previousBookmark` | `Shift+F2` |
| Toggle Explorer | `view.toggleExplorer` | `Ctrl+B` |
| Toggle Preview | `view.togglePreview` | `Ctrl+Shift+V` |
| Toggle Terminal | `view.toggleTerminal` | `Ctrl+Shift+T`, `` Ctrl+` `` |
| View only mode | `view.toggleViewOnly` | `Ctrl+Alt+V` |
| Focus editor | `view.focusEditor` | `Ctrl+1` |
| Focus Preview | `view.focusPreview` | `Ctrl+2` |
| Focus Terminal | `view.focusTerminal` | `Ctrl+3` |
| Next pane | `view.focusNextPane` | `F6` |
| Previous pane | `view.focusPreviousPane` | `Shift+F6` |
| Split editor | `view.splitEditor` | `Ctrl+\` |
| Show all editors | `view.showAllEditors` | `Ctrl+K, Ctrl+P` |
| Toggle word wrap | `view.toggleWordWrap` | `Alt+Z` |
| Zoom in | `view.zoomIn` | `Ctrl++`, `Ctrl+=` |
| Zoom out | `view.zoomOut` | `Ctrl+-` |
| Reset zoom | `view.zoomReset` | `Ctrl+0` |
| Run active file | `terminal.runActiveFile` | `F5` |
| Run selection | `terminal.runSelection` | `F9` |
| Open in Terminal | `terminal.openActiveFileFolder` | `Ctrl+Alt+T` |
| New Terminal tab | `terminal.newTab` | `` Ctrl+Shift+` `` |
| Close Terminal tab | `terminal.closeTab` | `Ctrl+Shift+W` |
| Select color theme | `theme.select` | `Ctrl+K, Ctrl+T` |
| Keyboard Shortcuts | `help.keyboardShortcuts` | `Ctrl+K, Ctrl+S` |
| Documentation | `help.documentation` | `F1` |

## Privacy

Euklid Editor collects nothing: no telemetry, no analytics, no accounts, no update check, and no network requests of its own. Your settings, open tabs and unsaved-change backups stay in your Windows user profile. The Preview renders offline and blocks the network. The Terminal runs the shell you choose with your own permissions, so what you run there can reach the network like any shell. A link opens in your browser only after you confirm. The full statement is in the privacy file of the project.

## Troubleshooting

- **The Preview or the Terminal does not appear.** They need the Microsoft Edge WebView2 Runtime, which Windows 11 includes; on Windows 10 install it from Microsoft. Markdown without diagrams, PDF, images and CSV do not need it.
- **A shortcut does nothing.** Another command may have taken the key in `keybindings.json`; the status bar reports problems in that file when it loads. **Keyboard Shortcuts** (`Ctrl+K Ctrl+S`) shows what each key does now.
- **A file opens as strange characters or as raw bytes.** It is not valid UTF-8, UTF-16 or UTF-32 text. Use the encoding in the status bar to reopen it as a Windows code page.
- **A save says the file changed on disk.** Another program wrote it after you opened it. Choose to overwrite it, reload it, or save under another name.
- **Compare says a file is too different or too large.** Compare Files handles text files up to 5 MiB that share some lines; for anything else open both files and look at them side by side with **Split Editor**.
- **Windows warns about the download.** The GitHub downloads are not code-signed, so Defender SmartScreen asks you to confirm; the Microsoft Store version has no warning.
- **Start fresh.** **Reset Settings** in the Command Palette restores the defaults and keeps your files and folder.
- **Report a problem:** the link in Help → About Euklid Editor, or <https://github.com/Duclevn/EuklidEditor/issues>.
