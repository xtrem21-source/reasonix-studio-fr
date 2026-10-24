# Changelog

All notable changes to this project are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

The version number follows the upstream Reasonix Studio release it packages.

---

## [2.50-fr] — 2026-10-24

First published French build of **Reasonix Studio 2.50.0** for Windows x64.
This is a derivative work of the upstream project, distributed under its MIT
license; see `LICENSE`.

### Added

- **Complete French interface**, 5 047 strings translated, delivered as a ready
  to run folder: no installer, no registry entry, no administrator rights.
- **Built-in dictation microphone**: a microphone button in the chat composer,
  provider selection, and automatic fallback when a provider fails.
- `README.md` (English) and `README.fr.md` (French), both stating what was
  changed from upstream, what the known limitation is, and what the license
  requires.
- `ReasonixStudio-windows-amd64-fr.zip` (193 MB) published as a release asset. The
  upstream executable weighs 234 MB, above the 100 MB per-file limit GitHub
  enforces on repository trees — a release asset is the only compliant way to
  distribute it.

### Changed

- **Three interface files are modified** relative to upstream, all under
  `resources\frontend-next\dist\`: the i18n bundle (French dictionary, `fr`
  accepted, automatic detection forced to `fr`), the Settings bundle (`Français`
  added to the language selector), and `index.html` (loads the microphone
  module).
- **Automatic language detection now answers `fr`.** Without this, French does
  not hold on 2.50: the application resets its language setting to empty at
  startup and falls back to auto-detection.

### Known issues

- **The language selector does not persist.** Choosing English in the settings
  is overwritten at the next start. In practice the interface stays French.
- Two settings labels, `Ask` and `MCP · Skills`, remain untranslated: their
  source strings changed in 2.50 and no longer match the dictionary.
- The root cause of the language reset is not identified. It is most likely
  inside the host executable, which is why it is worked around rather than fixed.

### Upgrade notes

- Do not accept updates offered by the application: they overwrite the
  translated files and remove the microphone. Every upstream release needs a new
  release here.
- Previous releases of this repository are kept; nothing is deleted.
