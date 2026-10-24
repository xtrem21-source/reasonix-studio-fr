# Reasonix Studio FR

**A ready-to-run French build of Reasonix Studio, with a built-in dictation microphone.**

This repository publishes the recompiled French version of **Reasonix Studio** — the
desktop application of the [**DeepSeek-Reasonix**](https://github.com/esengine/DeepSeek-Reasonix)
project — so that nobody has to patch anything after installing it.

> **Unofficial.** This project is not affiliated with, endorsed by, or sponsored by
> the DeepSeek-Reasonix (Reasonix Studio) project or its maintainers.

The translation work itself — dictionary, scripts, tooling — lives in its own
repository: [**Reasonix-Traduction-Fr**](https://github.com/xtrem21-source/Reasonix-Traduction-Fr).
This repository only ships the result.

Documentation exists in English (`README.md`, `CHANGELOG.md`) and in French
(`README.fr.md`, `CHANGELOG.fr.md`).

---

## What is inside

| Item | Detail |
|---|---|
| Reasonix Studio | **2.50.0**, Windows x64, as published upstream |
| Interface | **5 047 strings translated**, automatic language forced to French |
| Microphone | dictation wired into the chat composer, provider selection, automatic fallback |
| Packaging | a plain folder — no installer, no registry entry, no administrator rights |

## Install

1. download `reasonix-studio-2.50-fr.zip` from the **Releases** page;
2. extract it wherever you want (for example `J:\Reasonix Studio`);
3. run `Reasonix Studio.exe`.

To remove it, delete the folder. Nothing else was written.

> The archive is published as a release asset, not as a commit: `Reasonix Studio.exe`
> weighs 234 MB and GitHub rejects any file above 100 MB in a repository tree.

## What was changed from upstream

Three files of the web interface, under `resources\frontend-next\dist\`:

| File | Change |
|---|---|
| `assets\i18n-<hash>.js` | French dictionary, `fr` accepted as a language, automatic detection forced to `fr` |
| `assets\Settings-<hash>.js` | `Français` added to the language selector, three labels translated |
| `index.html` | loads the microphone module |

The microphone module (`voice-input.js`) is an addition: it does not exist upstream.

File names carry a build hash and change with every release. The scripts do not
hard-code them — they read `index.html` to find the bundle actually loaded.

## Known limitation

The language selector in the settings **does not persist**. Reasonix Studio 2.50
resets its language setting to empty at startup and falls back to automatic
detection. French holds because automatic detection was forced, not because the
choice is respected. In practice the interface is always French.

## Updates

**Do not accept the updates offered by the application.** They overwrite the
translated files and remove the microphone. Every upstream release needs a new
release here.

| Version | Status |
|---|---|
| 2.50.0 | released |

## License and attribution

Reasonix Studio is published under the **MIT license** by **esengine**. This
distribution is a derivative work: the upstream MIT license and copyright notice
apply and are reproduced in `LICENSE`.

No warranty is provided, neither by upstream nor here.
