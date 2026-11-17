# StudyOS 1.2.2-beta.1 — Install

## Requirements

- Windows 10 x64 version 2004 (build 19041) or newer, or Windows 11 x64.
- A writable local folder for the application.
- No separate .NET installation is required: the single-file build is self-contained.

## Portable ZIP

1. Download `StudyOS-Portable-1.2.2-x64.zip` and `SHA256SUMS.txt`.
2. Verify the ZIP hash:
   `Get-FileHash .\StudyOS-Portable-1.2.2-x64.zip -Algorithm SHA256`
3. Extract the **entire** ZIP to a local folder. Do not run it from inside the ZIP or from a OneDrive placeholder.
4. Run `StudyOS.exe`.

The workspace is created at `%LOCALAPPDATA%\StudyOS` unless `--data-dir` is supplied. Application files and workspace data are separate; replacing the application does not delete notes or backups.

Read the bundled `LICENSE` before use. The optional `Install.ps1` copies it and the third-party notices beside the application.

## Single-file executable

`StudyOS-SingleFile-1.2.2-x64.exe` can be run directly. It extracts native dependencies to a temporary folder under `%TEMP%\.net` at launch.

Read the separate `LICENSE` asset on the official Release page before use. It is the same licence as the Portable ZIP copy. [StudyOS releases](https://github.com/ccTgl/StudyOS/releases) · [Privacy Notice](https://github.com/ccTgl/StudyOS/blob/main/PRIVACY.md)

## Unsigned beta

The binaries are not Authenticode-signed. Windows SmartScreen may show an unknown-publisher warning. Verify the SHA-256 and obtain the file from the expected source. Do not disable security controls to run it.

## Upgrade and rollback

Close StudyOS before replacing program files. Keep the previous executable and a full workspace backup. StudyOS creates a recovery snapshot before a restore; it does not silently overwrite a backup.

## Uninstall

There is no MSI/MSIX or Setup package in this candidate. Remove the extracted application folder to uninstall the program. Workspace data, backups, logs and Windows Credential Manager entries are intentionally not removed by deleting the folder; remove those separately only after reviewing them.
