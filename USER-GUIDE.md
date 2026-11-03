# Euklid Editor User Guide

Euklid Editor is a lightweight text and code editor for Windows with a **Preview**, a **Terminal** and a folder **Explorer** built in. This guide works offline and opens any time with **Help → Documentation** or `F1`.

New here? Read the next two sections (about five minutes), then use the rest as a reference.

## Why Euklid Editor

### 1. Light and fast

- A native Windows program, not a web app in disguise: no Electron, no bundled browser. It opens in a moment.
- **You pay only for what you open.** The editor alone uses about 17 MiB of memory in a 1600×1000 window (measured on the 0.9.0 release; a maximized window on a 4K screen needs more). Preview and Terminal cost nothing until you open them.
- Markdown, PDF, images and CSV are drawn by Euklid Editor itself. In the same window a Markdown Preview measured about 22 MiB for the whole program, a PDF about 42 MiB (version 0.7.0). The browser component of Windows starts only for diagrams, math, API documents and the Terminal.
- The download is 22.4 MiB zipped.

### 2. Editor, Preview and Terminal in one window

- Write on the left, see the result on the right, run commands below or beside it. No window juggling.
- **Preview** shows Markdown (tables, task lists, highlighted code, Mermaid and PlantUML diagrams, math), PDF, images, CSV and TSV, HTML pages (their own styles, no scripts) and OpenAPI documents. It follows your edits and your scroll position.
- **Export as PDF** turns a Markdown document into a PDF file in one step.
- The **Terminal** has tabs, PowerShell, Command Prompt, Git Bash and WSL, and can sit below the editor, in a full-height column, or fill the window.

### 3. A good home for the AI coding agent you already use

- Run **Claude Code, Codex, opencode, Copilot CLI, Gemini CLI or Pi** in a real Terminal next to your files. Each one found on your computer is in the New Tab menu, one click away.
- Give the agent the whole window with `Ctrl+Shift+M`, or keep it in a full-height column on the right.
- **Claude Code is connected to the editor.** It opens its files in tabs, sees your selection, and shows every change it wants to make in a review window where you press **Accept** or **Reject**.
- **Insert File Reference** types `src/main.cpp:10-20` at the prompt of any agent: the file and the lines you selected.
- Euklid Editor has no AI of its own and never uploads your files. Your agent, your account, your choice.

### 4. Private, safe and familiar

- **Private:** no telemetry, no accounts, no update check and no network requests of its own. Preview pages cannot reach the network.
- **Safe:** closed by accident? Unsaved edits and open tabs come back (hot exit). Saves never leave half a file and keep the encoding and line endings. A file changed by another program is noticed.
- **Familiar:** the keys of VS Code and Sublime Text, a Command Palette (`Ctrl+Shift+P`), multiple cursors, find in files, and your own keys in `keybindings.json`.
- **Free and open source** under the GPL-3.0.

## Quick guide: 10 things in 10 minutes

Ten steps for a first session. The keys are the defaults; the buttons are on screen.

1. **Open a folder.** `Ctrl+K Ctrl+O`, or **Open Folder…** on the start page. The Explorer shows it on the left (`Ctrl+B` hides and shows it). Drag files onto the window to open them.
2. **Find anything fast.** `Ctrl+P` goes to a file by a few letters of its name. `Ctrl+Shift+P` is the Command Palette: every command, with its key.
3. **Open the Terminal.** `` Ctrl+` ``, or the **Terminal** button on the activity rail (the narrow strip at the left edge). It starts in your folder. The **+** in its header opens another tab (`` Ctrl+Shift+` ``).
4. **Give it room.** In the Terminal header, **Move Terminal to the right** puts it in a full-height column; **Maximize** (`Ctrl+Shift+M`) lets it fill the window. The same key brings the editor back.
5. **Start an AI agent.** Click the arrow beside **+** in the Terminal header and pick Claude Code (or Codex, opencode and the others on your computer). The agent is a separate program that you install and sign in to yourself; it uses your own account. In Claude Code, type `/ide`: it lists **Euklid Editor**.
6. **Ask it for a Markdown file.** For example:

   > Create notes.md with a short summary, a table comparing three options and a Mermaid diagram of the steps.

   Claude Code shows the new file in a **review window**: read it, then press **Accept** and the file is saved. Other agents write the file themselves; open it from the Explorer.
7. **Preview it.** `Ctrl+Shift+V`, or the eye button at the right end of the tab strip. The table is a table, the diagram is a diagram. Scroll the editor and the Preview follows.
8. **Export it as PDF.** **File → Export as PDF…**, or the PDF button in the Preview header. Choose a name; the file is written beside your Markdown file by default.
9. **Search and edit at scale.** `Ctrl+Shift+F` searches the whole folder, `Ctrl+Shift+H` replaces across files (it asks first). `Ctrl+D` adds the next match as another cursor, so one typing edits them all.
10. **Compare, then relax.** **Tools → Compare Files…** shows two files side by side with the differences tinted. `Ctrl+Alt+V` switches to **View only**, a quiet reader with nothing but the file.

Your work is kept when you close the window, so you can stop at any step and come back.

## Features in detail

The rest of this guide describes each part of Euklid Editor.

## Getting started

- **Open something.** `Ctrl+O` opens a file, `Ctrl+K Ctrl+O` opens a folder as your workspace, and `Ctrl+R` lists recent files and folders. You can also drag files onto the window, or use **Open with** in File Explorer (the installer and the Store version add it). The Open, Save As and Open Folder windows start in the folder of the file you are editing, else your workspace folder, else where you last chose something.
- **Start typing.** With no document open the start page offers Open File and Open Folder, your recent items and the main keys. Typing on it starts a new file.
- **Find any command.** `Ctrl+Shift+P` opens the Command Palette: every command, the ones you used recently first. `Ctrl+P` goes to a file in the workspace, `Ctrl+G` to a line, `Ctrl+Shift+O` to a symbol in the current file.
- **Your work is safe.** Unsaved edits and open tabs are kept when you close the window and come back at the next start (hot exit; you can turn it off in Settings). Saves keep the file's encoding and line endings and never leave half a file. If another program changes a file you have open, Euklid Editor reloads it when you have no edits, or asks what to do when you do.

## The window

- **Title bar:** the menus, the command center, the **Read** / **Edit** button for View only mode, and the window buttons.
- **Activity rail** (left edge): the Explorer, Find in Files, the Terminal and Settings.
- **Editor:** tabs with a dot on unsaved files. `Ctrl+\` splits the editor into two groups that can show the same file or different ones; **View → Editor Layout** chooses one or two columns. `Ctrl+K Ctrl+P` lists every open file, and `Ctrl+K Ctrl+Shift+T` reopens the last closed one.
- **Preview** (right of the editor, `Ctrl+Shift+V` or the eye button in the tab strip) and **Terminal** (below, or in a column on the right; `Ctrl+Shift+T` or `` Ctrl+` ``) open only when you ask for them. Euklid Editor stays small until you do.
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

`Ctrl+F` opens the Find bar over the editor, `Ctrl+H` adds Replace. It finds as you type, shows the number of matches, and offers regular expressions, match case and whole word. The regular expressions use the same syntax as Find in Files, with `$1` (or ``) for a captured group in the replacement.

## Preview

The Preview shows the active file next to the editor and follows your edits. It works offline, and its pages cannot reach the network, not even for images.

| File | Preview |
|---|---|
| Markdown | Tables, task lists, highlighted code, Mermaid and PlantUML diagrams and KaTeX math |
| YAML and JSON that is an OpenAPI document | The API reference |
| CSV and TSV | A table |
| HTML | The page with its own styles; scripts are never run |
| PDF | The pages, with zoom and search |
| PNG, JPEG, GIF, BMP, WebP, TIFF | The picture, with zoom |

An HTML page shows its own styles (CSS) but runs no scripts, and loads nothing from the network. Other JSON and XML files have no Preview. Markdown without diagrams or math, PDF, images and CSV are drawn by Euklid Editor itself, so they open quickly and use little memory; diagrams and math use the browser engine that Windows provides (the WebView2 Runtime), which starts only for those documents. With **Scroll sync** on (Settings, on by default), the Preview and the editor scroll together, and double-clicking in the Preview jumps to that line of the source. Links in a Preview open in your browser only after you confirm.

### Export as PDF

**File → Export as PDF…** (`file.exportPdf`, no default key; you can give it one in `keybindings.json`) and the small download button in the Preview header save the Markdown document you are editing as a PDF file.

- It is available for Markdown documents only, also in View only mode. The text is taken as it is on screen, unsaved edits included.
- The pages are A4 with 18 mm margins, black on white whatever theme the editor uses, with page numbers in the footer. Long lines of code wrap instead of being cut. Web (`https`) links in the document stay clickable; links to a heading of the same document do not.
- You choose the name and folder; the suggestion is `<name>.pdf` beside the Markdown file. The file is written under a temporary name and renamed at the end, so a cancelled or failed export never leaves half a file or damages an existing PDF, and the Markdown file itself is never replaced.
- Pictures from the document's folder are included. Plain Markdown is exported by Euklid Editor itself; a document with diagrams or math is drawn by the browser component of Windows for the export.
- A progress window with **Cancel** appears for a long document, and the status bar tells you the file and the number of pages when it is done.
- The limit is the same as Preview's (1 MiB of text); a larger document is refused with a message.

## Terminal

The Terminal (`` Ctrl+` `` or `Ctrl+Shift+T`, or the Terminal button on the activity rail) runs PowerShell, Command Prompt, Git Bash or a WSL distribution in the folder you choose, in up to ten tabs. `` Ctrl+Shift+` `` (or the **+** in the header) opens a new tab and `Ctrl+Shift+W` closes one; closing a tab with a running command asks first. The arrow beside **+** opens a tab with a profile you choose.

- Copy and paste work as in Windows Terminal, and a paste of several lines into a shell that cannot tell it from typing asks first.
- `Ctrl+click` opens a file path or a link in the output (links ask first).
- `Ctrl+F` finds in the output. A background tab that rings the bell shows a dot, and the taskbar button flashes; progress reported by a program shows on its tab.
- Files dropped onto the Terminal are typed as paths.
- `Shift+Enter` starts a new line in the prompt of Claude Code, Codex and similar agents; at a PowerShell prompt it keeps its own meaning.
- The Terminal sits below the editor or, with the button in its header (or **Run → Move Terminal to the Right**), in a full-height column on the right, which suits an agent such as Claude Code or a long log. Each placement remembers its own size. `Ctrl+Shift+M` (**Run → Maximize Terminal**, or the header button) makes the Terminal fill everything right of the activity rail, also from inside the Terminal; opening a file, `Ctrl+1` or the Explorer and Preview toggles bring the editor back, and a window closed while the Terminal was maximized opens maximized again.
- **Run active file or selection:** `F5` and `F9` type the command into the Terminal; **Run → Open Active File's Folder in Terminal** (`Ctrl+Alt+T`) opens a tab in the file's folder.
- **Agents:** if Claude Code, Codex, opencode, Copilot CLI, Gemini CLI or Pi is installed (found on the `PATH`), the New Tab menu lists it, and a click starts it in the workspace folder; the tab stays open as a shell when the agent exits. Euklid Editor installs no agent and runs nothing you did not install; hide one in `profiles.json` with `"hidden"` like any detected profile.
- **Run → Open Terminal Profiles (JSON)** opens `profiles.json`, where you add your own profiles (command line, arguments, start folder, environment) or hide detected ones. **Settings → Terminal** has the default profile and start folder, the font, the cursor, the scrollback and a few behaviors.

### Claude Code in the Terminal

Run `claude` in a Terminal tab and Claude Code finds this window by itself (`/ide` in Claude Code shows "Euklid Editor"). From then on:

- A file Claude Code opens appears in an editor tab, and the text you select in the editor is what Claude Code sees as your selection.
- **A change Claude Code proposes opens in a review window** (Compare Files with **Accept** and **Reject**) instead of in the terminal. **Accept** applies it to the document as one undo step and saves the file; **Reject**, `Esc` or closing the window refuses it, and Claude Code is told so. A document with unsaved changes is never overwritten: the change is refused and the status bar says why, so save or revert the document and ask again.
- Claude Code has permission modes (cycle them with `Shift+Tab`). In its **auto mode** it writes files without asking, so no review window opens; in the default mode every change is shown here first.
- **Terminal: Send Selection to Claude Code** (Command Palette, or **Run**) sends the file and the selected lines as an @-mention.
- **Terminal: Insert File Reference** (Command Palette, or **Run**) types `src/main.cpp:10-20` (the file, relative to the folder, and the selected lines) at the Terminal's prompt without pressing Enter. It works with any agent or program that reads a path from its prompt, with or without the link.
- **Tools → Compare with Version Before Reload** shows what any agent changed when the editor reloaded a file (see the Tools menu).

The link works only on this computer: Euklid Editor listens on `127.0.0.1` while a Terminal shell runs, with a secret token in a file in `.claude\ide` in your user profile that only you can read, and it stops with the last shell. It adds no network traffic. To turn it off, clear **Settings → Terminal → Claude Code**; it applies to Terminal tabs started afterwards. Claude Code's connection to the editor is not documented by Anthropic and may change between versions.

## View only mode

View only (`Ctrl+Alt+V`, or the **Read** button in the title bar) turns the window into a quiet reader: it shows just the file, as its Preview or as read-only text, with no Explorer, tabs, Terminal or menus. A file you double-click opens straight into the mode you used last. `Ctrl+=`, `Ctrl+-` and `Ctrl+0` zoom. Everything you were editing stays as it was, and **Edit** brings the full window back. The editing commands, including the Tools menu, are off while you read.

## Tools menu

The **Tools** menu has six commands. None has a default key, but you can give each one in `keybindings.json`.

- **Compare Files…** (`tools.compare`) compares the text of two files line by line. The left side is the file you are editing; choose the right side from your other open files or browse for a file. The two files appear side by side in their own window with line numbers, removed, added and changed lines tinted and one shared scroll. **Next** and **Previous** (`F7` and `Shift+F7` in that window) jump between differences, **Ignore trailing whitespace** ignores spaces at the end of lines, and `Esc` or `Ctrl+W` closes the window. A file you have changed but not saved is compared as it is on screen and marked *unsaved*. If two files differ only in line endings or encoding (for example UTF-8 and UTF-8 with BOM), the window says so instead of marking every line. Files over 5 MiB, binary files and pairs that are too different to compare line by line are refused with a reason.
- **Compare with Version Before Reload** (`tools.compareBeforeReload`) shows what an outside change did: when a file changes on disk and Euklid Editor reloads it (an agent, a formatter, `git checkout`), or you use Revert File, the text from just before is kept, and this opens it beside the document as it is now. It keeps the latest reload of the three documents most recently reloaded, up to 8 MiB each, and forgets them when the document closes.
- **Base64 Encode** and **Base64 Decode** convert every selection, or the whole document when nothing is selected, as one undo step. Text is encoded as UTF-8. Decoding accepts input without `=` padding, ignores spaces and line breaks inside the data, and accepts the URL-safe alphabet (`-` and `_`).
- **URL Encode** and **URL Decode** do the same with percent-encoding (RFC 3986): letters, digits and `-` `.` `_` `~` stay, every other byte of the UTF-8 text becomes `%XX` (space is `%20`). Decoding reads `%XX` sequences only; a `+` stays a `+`, it is not turned into a space.

If any selection cannot be converted (invalid Base64, a broken `%` sequence, or a result that is not text), nothing changes at all, and the status bar says why and how many selections failed.

## Settings and keyboard shortcuts

- **Settings** (`Ctrl+,`, or the gear on the activity rail) has Appearance (the Default, Dark and Light themes), Editor (font, tab width, spaces or tabs, wrap, rulers, auto-closing brackets, hot exit), Preview (scroll sync) and Terminal. **Reset Settings** in the Command Palette puts everything back, with an option to reset your keyboard shortcuts too.
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
| Maximize Terminal | `terminal.toggleMaximized` | `Ctrl+Shift+M` |
| New Terminal tab | `terminal.newTab` | `` Ctrl+Shift+` `` |
| Close Terminal tab | `terminal.closeTab` | `Ctrl+Shift+W` |
| Select color theme | `theme.select` | `Ctrl+K, Ctrl+T` |
| Keyboard Shortcuts | `help.keyboardShortcuts` | `Ctrl+K, Ctrl+S` |
| Documentation | `help.documentation` | `F1` |

## Privacy

Euklid Editor collects nothing: no telemetry, no analytics, no accounts, no update check, and no network requests of its own (the optional Claude Code link only listens on this computer, `127.0.0.1`). Your settings, open tabs and unsaved-change backups stay in your Windows user profile. The Preview renders offline and blocks the network. The Terminal runs the shell you choose with your own permissions, so what you run there, an AI agent included, can reach the network like any program you start. A link opens in your browser only after you confirm. The full statement is in the privacy file of the project.

## Troubleshooting

- **The Preview or the Terminal does not appear.** They need the Microsoft Edge WebView2 Runtime, which Windows 11 includes; on Windows 10 install it from Microsoft. Markdown without diagrams, PDF, images and CSV do not need it.
- **My AI agent is not in the New Tab menu.** The menu lists the agents whose command is found on the `PATH`. Install the agent, close Euklid Editor completely and start it again, so the new `PATH` is read.
- **Claude Code does not show "Euklid Editor" in `/ide`.** Start Claude Code from a Terminal tab of Euklid Editor, not from another window, and check that **Settings → Terminal → Claude Code** is on. The setting applies to tabs started afterwards.
- **Export as PDF is greyed out.** It works on Markdown documents only; open the `.md` file and try again.
- **A shortcut does nothing.** Another command may have taken the key in `keybindings.json`; the status bar reports problems in that file when it loads. **Keyboard Shortcuts** (`Ctrl+K Ctrl+S`) shows what each key does now.
- **A file opens as strange characters or as raw bytes.** It is not valid UTF-8, UTF-16 or UTF-32 text. Use the encoding in the status bar to reopen it as a Windows code page.
- **A save says the file changed on disk.** Another program wrote it after you opened it. Choose to overwrite it, reload it, or save under another name.
- **Compare says a file is too different or too large.** Compare Files handles text files up to 5 MiB that share some lines; for anything else open both files and look at them side by side with **Split Editor**.
- **Windows warns about the download.** The GitHub downloads are not code-signed, so Defender SmartScreen asks you to confirm; the Microsoft Store version has no warning.
- **Start fresh.** **Reset Settings** in the Command Palette restores the defaults and keeps your files and folder.
- **Report a problem:** the link in Help → About Euklid Editor, or <https://github.com/Duclevn/EuklidEditor/issues>.
