# Lyra changelog

Lyra releases are published from the private source repository to the public [Lyra-Releases](https://github.com/OrionAISystems/Lyra-Releases) repository. The private source copy is the canonical release history; tagged builds mirror it publicly and use the current version section as their release notes.

## [0.5.0] - 2026-09-26

### Added

- Added opt-in, Windows-user-encrypted Transcript History with Off-by-default retention choices, expiry, clear, copy, paste-again, delete, and promotion to Scratchpad.
- Added an intentional Scratchpad capture route with its own shortcut, no automatic paste or clipboard write, persistent entries, pinning, copy, paste, and delete.
- Added paginated History and Scratchpad screens with saved-item metadata and empty states.

### Changed

- Kept daily aggregate Insights indefinitely and changed metadata-only session retention to a rolling one-year age policy.
- Added settings schema v4 migration with Transcript History Off by default and preserved existing user preferences.

## [0.4.4] - 2026-09-24

### Security

- Keep Nemotron streaming sessions open while collecting partial results, then finalize once after the last audio chunk so configured local/cloud routing remains intact.
- Bound Windows clipboard reads and make sequence-checked recovery writes atomic so malformed clipboard data cannot trigger an unbounded scan or overwrite newer clipboard contents.
- Recheck the captured foreground window and owning process immediately before each paste injection.
- Enforce the expected size limit on runtime and model downloads and remove oversized partial artifacts.
- Restrict copied diagnostics and persisted fallback details to allowlisted metadata; omit local paths, endpoints, executable paths, and free-form error text.
- Update `rustls` to 0.23.45 to address [RUSTSEC-2026-0285](https://rustsec.org/advisories/RUSTSEC-2026-0285.html).

### Fixed

- Keep the completed transcript available in Lyra when clipboard recovery cannot safely restore the previous clipboard contents.

## [0.4.3] - 2026-09-22

### Fixed

- Made the custom Windows title bar draggable and restored working minimize, maximize/restore, and close-to-tray behavior with appropriately sized controls.
- Restored the compact legacy dictation bar and fixed its live elapsed/max-duration display for both toggle and push-to-talk sessions.
- Improved custom dropdown keyboard, focus, hover, selected, disabled, and light-theme states so options remain readable and contained across the settings screens.
- Replaced the diagnostics global-shortcut retry action with a stable text-only Verified state after registration succeeds.
- Allowed benchmarking from completed or failed idle sessions while continuing to guard active capture and processing requests.

### Release

- Published the v0.4.3 Windows x64 release with the signed in-app updater feed and the current v0.4 daily-use fixes.

## [0.4.2] - 2026-09-22

### Fixed

- Replaced macOS-style titlebar dots with working Windows minimize, maximize, and close-to-tray controls.
- Restored the compact v0.3 dictation bar with a small microphone pill and settings shortcut.
- Fixed light and system themes so cards, controls, navigation, and text switch together instead of mixing dark surfaces into a light shell.
- Improved native dropdown contrast, focus treatment, and hover styling.
- Made benchmark and global-shortcut retry actions provide visible progress, errors, and refreshed status.

### Added

- Split daily Insights bars by Parakeet and Nemotron usage with a legend and accessible engine totals.
- Added an optional Advanced Insights panel with RTF, fallback, paste, silence-only, and range totals.
- Added configurable typing speed (default 40 WPM) for the typing-time-saved estimate.
- Excluded silence-only/no-speech captures from the success-rate denominator.

## [0.4.1] - 2026-09-22

### Fixed

- Prevented the dictation shortcut from repeatedly launching visible `nvidia-smi` console probes when session events refresh multiple Lyra windows.
- Kept renderer event subscriptions stable across request changes and reused the cached runtime snapshot for routine status reads.
- Replaced truncated ISO chart labels such as `-22` with locale-aware month-and-day labels.
- Added explicit native dropdown option colors for readable dark, light, and system-theme menus.

### Release

- Published a focused updater release for the v0.4.0 daily-use regressions without changing settings or personalization schemas.

## [0.4.0] - 2026-09-22

### Added

- Added an optional English Nemotron streaming engine with contextual Words, request-scoped partials, final-only paste, and deterministic Parakeet replay fallback.
- Added separate local Words, Corrections, Snippets, and app-aware formatting profiles with atomic migration from the v0.3 correction list.
- Added adaptive audio diagnostics, multiple recovery shortcuts, target-aware paste strategies, a one-recording local engine benchmark, and privacy-safe session diagnostics.
- Added 90-day aggregate insights and the latest 200 metadata-only session records without transcript, audio, clipboard, window-title, full-path, or credential persistence.

### Changed

- Rebuilt Home, Dictation, Personalization, Audio & Engine, Insights, Appearance, and Diagnostics in a shared frameless desktop shell.
- Upgraded settings to schema v3 while preserving v0.3 microphone, duration, startup, placement, corrections, and cost preferences.
- Kept Parakeet TDT as the stable default; benchmark recommendations require an explicit user switch.

### Release

- Kept the signed in-app updater available in Diagnostics and the tray for installed v0.3.2 clients.
- Kept runtime and both model artifacts independently versioned, checksum-verified, and outside the application bundle.

## [0.3.2] - 2026-09-07

### Fixed

- Kept local transcription recoverable when the active native recognizer reports a recognition failure by retrying verified Vulkan and CPU fallbacks.
- Added captured-audio validation and actionable native status details for unsupported sample rates, invalid samples, and recognizer failures.
- Exposed runtime paths, model paths, and recognizer diagnostics in the Settings Diagnostics section.

### Release

- Prepared the Windows x64 NSIS and updater-signed release path for the local recognition reliability fix.
- Kept runtime and Parakeet model artifacts managed outside the application bundle.

## [0.3.1] - 2026-09-02

### Fixed

- Pinned the Settings sidebar to the viewport so only the main content pane scrolls through long sections such as General and Usage.
- Kept the responsive settings layout usable at narrow window sizes, with navigation visible while the content row scrolls.

### Release

- Published the Windows x64 NSIS installer and cryptographically signed updater artifacts.
- Kept runtime and Parakeet model downloads explicit and app-managed after installation.

## [0.3.0] - 2026-09-01

### Added

- Added mode-aware dictation-bar gestures, including true push-to-talk pointer capture and toggle-mode silence endpointing.
- Added deterministic spoken formatting commands and a local personal vocabulary/correction dictionary.
- Added active-window, primary-display, and fixed-monitor bar placement.
- Added recorded hotkey configuration with validation and registration-error rollback.
- Added explicit model warm policies and compact recognizer runtime status.
- Added local aggregate usage and performance statistics without transcript or raw-audio history.
- Added updater installation gates, local signed-fixture coverage, and release acceptance evidence.

### Improved

- Settings changes now converge immediately across the settings window, persistent bar, capture limits, and runtime policy.
- Dynamic maximum-duration updates apply to the active capture as well as the next session.
- Clipboard sequence guards and target-window recovery keep cross-application paste failures recoverable.

### Release

- Published the first daily-use hardening release and completed the installed v0.2.0 to public v0.3.0 updater path.
- Published the Windows x64 NSIS installer and cryptographically signed updater artifacts.
- Kept runtime and Parakeet model downloads explicit and app-managed after installation.

## [0.2.0] - 2026-08-31

### Added

- Established the Windows-first, tray-first Lyra application shell and settings surface.
- Added local-first Parakeet transcription with optional cloud fallback, secure credential storage, and in-memory audio handling.
- Added global shortcut activation, a non-activating dictation bar, foreground-target capture, and guarded clipboard paste.
- Added explicit runtime/model setup metadata and a per-user Windows x64 NSIS installer.
- Added the signed updater feed and the release-only public Lyra-Releases repository.

### Release

- Published the initial public Windows x64 installer and updater baseline.

[0.4.4]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.4.4
[0.4.3]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.4.3
[0.4.2]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.4.2
[0.4.1]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.4.1
[0.4.0]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.4.0
[0.3.1]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.3.1
[0.3.2]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.3.2
[0.3.0]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.3.0
[0.2.0]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.2.0
