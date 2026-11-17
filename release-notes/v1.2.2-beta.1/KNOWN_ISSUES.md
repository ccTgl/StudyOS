# StudyOS 1.2.2-beta.1 — Known Issues

## Release blockers / open items

- **No code signature.** SmartScreen and Defender behaviour on a clean Windows machine have not been verified for this candidate.
- **No Setup installer.** The previous Inno Setup candidate was withheld after Defender flagged its unsigned temporary uninstaller. Only the single-file executable and Portable ZIP are candidates.
- **Release evidence binding remains manual.** The candidate manifest records the tested artifacts, but published GitHub assets are not created by this repository and are not updated by this build.

## Manual verification still required

- Real Google first consent, consent cancellation, token refresh and disconnect.
- Real Windows sleep/resume and logoff/shutdown.
- Native Windows file picker in the packaged build.
- SmartScreen and Defender on a clean Windows x64 machine.
- Upgrade from an existing 1.2.1 workspace with real user data.
- Full backup/restore on another machine, including missing library paths.
- Mixed-DPI, notification-centre and external-storage hot-plug behaviour.

## Technical limitations

- Focus Timer persistence is batched; a hard crash can lose up to the last 10 seconds of observed time. A clean Stop/Exit/SessionEnding flushes the final interval.
- Sleep is excluded through the Windows power event. If Windows fails to deliver a suspend event, an unattended gap may be counted; this is recorded as a residual risk.
- Pending note journals are plaintext under the workspace and are not encrypted. They are removed after a successful save.
- A failed note save can leave an unreferenced screenshot attachment; attachment deduplication prevents duplicate bytes but does not garbage-collect orphans.
- Legacy `.studyos` restore is database-only; managed library files are not inside that format. Missing roots are rebased to the current library, and a report is written under `Recovery`.
- The build is deterministic at the configuration level, not proven bit-for-bit reproducible across machines because ZIP metadata and toolchain differences are not normalized.
