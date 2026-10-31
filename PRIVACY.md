# Euklid Editor privacy statement

Euklid Editor does not collect, store or send any personal data. It has no telemetry, no analytics, no accounts and no automatic update check, and it makes no network requests of its own.

- **Your files and settings stay on your computer.** Settings, the list of open tabs and unsaved-change backups ("hot exit") are kept in your user profile (`%LOCALAPPDATA%`) and are never uploaded.
- **Preview** renders documents offline from files packaged with Euklid Editor. Its page policy blocks network access, including remote images.
- **Terminal** runs the shell you choose (PowerShell, Command Prompt, Git Bash, WSL or a profile of your own). Commands you type there run with your own permissions and can reach the network like any other shell you use. A program in the shell may copy text to your clipboard (the standard terminal escape sequence for it); Euklid Editor lets it write the clipboard and never lets it read the clipboard. The optional "Mark commands in PowerShell" setting (off by default) starts PowerShell with a small script that marks each prompt; it is passed on the command line and writes no file.
- **Links** you choose to open in Preview, or with `Ctrl+click` in the Terminal's output, are handed to your default browser only after you confirm.
- Preview and Terminal are displayed with the **Microsoft Edge WebView2 Runtime**, a Windows component maintained by Microsoft and covered by the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement). If you install Euklid Editor from the Microsoft Store, the Store's own terms and privacy statement apply to the download and updates.

Questions: open an issue at https://github.com/Duclevn/EuklidEditor/issues.
