# StudyOS 1.2.2-beta.1 — Release Notes

Status: **Release Candidate**, not published. Build date and source commit are recorded in `RELEASE_MANIFEST.json`.

## Highlights

- **Data safety:** test-mode workspaces are isolated from the real workspace; migration snapshots can no longer silently fail; restore can fall back to a raw database safety copy; legacy `.studyos` restore runs after the app closes and rebases missing library paths.
- **Notes reliability:** autosave retries with backoff and retains a pending-edit journal; shutdown flushes notes; button exceptions no longer terminate the app; pending edits are recovered on startup.
- **Focus Timer:** SQLite writes are batched every 10 seconds instead of every second; a delayed UI tick no longer discards observed study time; explicit Windows suspend/resume excludes sleep; Stop/Interrupt persist the final partial interval.
- **Gmail:** first Connect Account now requests interactive consent. An older Verification token without the Gmail read scope triggers incremental consent instead of being used silently.
- **Release engineering:** a single candidate build entry validates SDK 10.0.403, a clean committed source tree, version metadata, single-file publish and flat Portable ZIP, then writes hashes and a manifest.

## Downloads in this candidate

- `StudyOS-SingleFile-1.2.2-x64.exe` — self-contained Windows x64 single-file executable.
- `StudyOS-Portable-1.2.2-x64.zip` — flat ZIP containing the executable, product licence, third-party notices and release documents.
- `LICENSE` — proprietary, free public beta terms, also available separately for single-file users.
- `SHA256SUMS.txt` — SHA-256 for the binaries and companion documents.
- `RELEASE_MANIFEST.json` — version, source commit, SDK, artifacts, hashes and test evidence.

## Upgrade

Existing workspaces remain at `%LOCALAPPDATA%\StudyOS`. Back up before upgrading. Schema 11 is unchanged from 1.2.1; a pre-migration snapshot is still required if a future schema upgrade is applied. See `INSTALL.md`.

## Not included

- Inno Setup installer (withheld because of the earlier Defender finding on an unsigned uninstaller).
- A code-signing certificate or Microsoft Store package.

StudyOS is licensed for personal education, individual study and non-commercial academic work. Read the release's `LICENSE` before use. Third-party components remain subject to their own licences. [Privacy Notice](https://github.com/ccTgl/StudyOS/blob/main/PRIVACY.md)

## Verification limits

Automated tests use isolated workspaces and mock OAuth/API fixtures. Real Google consent, Windows sleep/logoff, SmartScreen, clean Windows installation and native file-picker behaviour require manual acceptance. See `KNOWN_ISSUES.md` and `RELEASE_ACCEPTANCE_CHECKLIST.md`.
