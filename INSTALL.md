# Install StudyOS Portable Beta

StudyOS v1.2.1 targets Windows x64 build 19041 or newer. It includes the .NET runtime. A writable folder is sufficient, and administrator rights are unnecessary.

1. Download `StudyOS-Portable-1.2.1-x64.zip` and `SHA256SUMS.txt` from the same official Release.
2. From the download folder, use PowerShell to check the archive:

   ```powershell
   Get-FileHash -LiteralPath .\StudyOS-Portable-1.2.1-x64.zip -Algorithm SHA256
   ```

   Match the hash against the line for the ZIP in `SHA256SUMS.txt`.
3. Extract the whole ZIP to a folder you can write to. Launch `StudyOS.exe` from the extracted folder.
4. To update an existing installation, exit StudyOS, save a full backup from **Settings → Storage**, then extract the beta to a separate program folder. The default workspace remains under `%LOCALAPPDATA%\StudyOS`.

The beta executable is unsigned. If Windows reports a block or malware detection, stop and report the alert through GitHub Issues. Download-time SmartScreen behavior is pending verification. Follow [known issues](KNOWN_ISSUES.md) for installer status.

Use **Settings → Storage → Restore Backup** and select the full backup folder containing `manifest.json` to recover a workspace. Keep that folder and its files together. OAuth sign-in may need to be set up again in a new workspace.
