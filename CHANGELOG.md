# Lyra changelog

Lyra releases are published from the private source repository to the public [Lyra-Releases](https://github.com/OrionAISystems/Lyra-Releases) repository. The private source copy is the canonical release history; tagged builds mirror it publicly and use the current version section as their release notes.

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

[0.4.0]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.4.0
[0.3.1]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.3.1
[0.3.2]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.3.2
[0.3.0]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.3.0
[0.2.0]: https://github.com/OrionAISystems/Lyra-Releases/releases/tag/v0.2.0
