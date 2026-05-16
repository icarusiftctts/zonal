<div align="center">

<br />
<img width="3168" height="1344" alt="Gemini_Generated_Image_zh8f0izh8f0izh8f" src="https://github.com/user-attachments/assets/631aceac-9720-4abb-855c-4d572d56d388" />

**Your focus atmosphere. Native, offline, quiet.**

<br />

[![Release](https://img.shields.io/github/v/release/YOUR_USERNAME/zonal?style=flat-square&color=7C8DFF&label=release)](https://github.com/YOUR_USERNAME/zonal/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-7C8DFF?style=flat-square)](https://github.com/YOUR_USERNAME/zonal/releases)
[![Flutter](https://img.shields.io/badge/built%20with-Flutter-54C5F8?style=flat-square&logo=flutter&logoColor=white)](https://flutter.dev)
[![License](https://img.shields.io/github/license/YOUR_USERNAME/zonal?style=flat-square&color=4CAF7D)](LICENSE)
[![Good First Issues](https://img.shields.io/github/issues/YOUR_USERNAME/zonal/good%20first%20issue?style=flat-square&color=D4A853&label=good%20first%20issues)](https://github.com/YOUR_USERNAME/zonal/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22)

<br />

<!-- Replace this block with your demo GIF: record a 20–30s clip showing the overlay fading in,
     soundscape switching, and the soft-end toast. Export at 600px wide. -->
> 📹 **Demo GIF goes here** — record with OBS (Windows) or `peek` (Linux) and drop the file in `docs/`.

<br />

[**Download for Windows**](#install) · [**Download for Linux (AppImage)**](#install) · [**Download for Linux (RPM)**](#install)

<br />

</div>

---

Zonal is a native desktop application that pairs a focus timer with a layered ambient soundscape. It sits in the corner of your screen, gets out of the way while you work, and fades its audio automatically when you take a break — without you asking it to.

It is not a timer app. It is a **controllable desktop focus atmosphere** — the ambient layer running quietly beneath everything else you do.

<br />

## Why Zonal

Most people who want to work with intention end up with three separate things open: a timer tab in the browser, a music app behind their work, and a notification they keep dismissing. None of it feels like a system. None of it disappears.

Zonal is one thing that does all three — and then gets out of your way.

| The problem | How Zonal handles it |
|---|---|
| Browser timers steal a tab and vanish when the window closes | Native app — always running, tray-resident |
| Hard alarms interrupt flow at the worst moment | Soft ending: overlay pulses, then offers "Continue 10 min?" before transitioning |
| Ambient audio and timers are separate products | Built-in soundscape engine with auto-fade on break |
| Focus apps demand your attention to work | Overlay auto-hides in fullscreen, collapses to a 20px dot when idle |

<br />

## Features

### ⏱ Flowmodoro by default
The timer counts up. You stop when you're ready. The break is proportional to how long you worked (elapsed ÷ 5). No fixed endpoints cutting into momentum. Pomodoro mode is available for those who prefer it.

### 🎧 Layered soundscape engine
Three curated ambient mixes at launch. Each is a blend of procedurally generated noise and locally bundled audio — no streaming required. Audio fades out automatically when a break starts and fades back in when work resumes.

| Soundscape | Mix |
|---|---|
| Deep Coding | Brown noise 50% · Rain 30% · Lo-fi 20% |
| Library Silence | Brown noise 40% · White noise 35% · Rain 25% |
| Rainy Night | Rain 65% · Brown noise 35% |

An "Adjust mix" panel lets you tune individual channels. The preset is the experience for most users — the mixer is there for those who want it.

> **Online streaming (opt-in):** When enabled, Zonal queries the [Radio Browser API](https://api.radio-browser.info/) — a free, open-source database of 35,000+ internet radio stations — and replaces the musical channel of your soundscape with a live lo-fi or jazz stream. Noise and rain layers remain local. Falls back to bundled audio silently if the network is unavailable.

### ◎ Overlay that disappears
Three density modes:

```
Full — 220×70px          Compact — 140×40px     Dot — 20×20px
┌──────────────────────┐  ┌─────────────┐         ●
│ ◉ 32:14   [▶] [⏭] 🔇│  │ 32:14   [🔇]│
│ Finish auth module   │  └─────────────┘
└──────────────────────┘
```

**Fullscreen behaviour** — three-way toggle in settings:
- **Auto-hide** *(default)* — fades invisible when a fullscreen app is detected
- **Always show** — persists above fullscreen apps and games
- **Dot only** — collapses to the progress circle when fullscreen is detected

**Click-through mode** — the overlay renders but all mouse events pass through to whatever is beneath it. Essential for programmers and designers.

### ✦ Focus Confidence
One question before each session: **Light · Medium · Intense**. A single tap that subtly adjusts the audio mix, break length suggestion, and strictness level — making the app feel responsive to your state without requiring AI or complex settings.

### ↺ Session continuity
Zonal remembers. Close the lid, quit, or crash mid-session — the next launch offers to resume exactly where you were, with the same soundscape and intention loaded.

```
You had a session running.
  Coding Sprint · 23 min elapsed · "Finish DSA sheet 4"

  [Resume]   [Discard]
```

### ⌘ Keyboard first
Every action is reachable without a mouse. A command palette gives fuzzy search over all actions — switching profiles, changing soundscapes, toggling modes.

| Shortcut | Action |
|---|---|
| `Ctrl+Alt+Space` | Start / Pause |
| `Ctrl+Alt+S` | Skip to break |
| `Ctrl+Alt+M` | Mute / Unmute |
| `Ctrl+Alt+T` | Toggle click-through |
| `Ctrl+Alt+D` | Toggle dot mode |
| `Ctrl+Alt+Z` | Open command palette |

<br />

## Install

### Windows

Download `zonal_0.1.0_x64-setup.exe` from [Releases](https://github.com/YOUR_USERNAME/zonal/releases/latest) and run the installer.

> Windows 10 (21H1) or later required. The installer bundles the WebView2 runtime and installs it automatically if missing.

### Linux — AppImage (recommended)

```bash
chmod +x zonal_0.1.0_amd64.AppImage
./zonal_0.1.0_amd64.AppImage
```

The AppImage bundles all dependencies including GStreamer. No installation needed — runs on any x86_64 Linux distribution.

### Linux — RPM (Fedora / RHEL)

```bash
sudo dnf install ./zonal-0.1.0-1.x86_64.rpm
```

For audio streaming, also install GStreamer plugins:
```bash
sudo dnf install gstreamer1-plugins-good
```

> **GNOME users:** The system tray icon requires the [AppIndicator extension](https://extensions.gnome.org/extension/615/appindicator-support/). KDE Plasma shows tray icons natively with no extensions needed.

> **Wayland:** The overlay is fully functional on Wayland. The "Always show" fullscreen mode is not available under Wayland due to compositor security restrictions — "Auto-hide" is used automatically in this case.

<br />

## Building from source

**Prerequisites:** [Flutter SDK](https://docs.flutter.dev/get-started/install) (stable channel), Rust 1.74+ (for C compilation via FFI), and the platform dependencies below.

```bash
# 1. Clone
git clone https://github.com/YOUR_USERNAME/zonal.git && cd zonal

# 2. Platform dependencies (Linux only)
sudo dnf install -y clang cmake ninja-build gtk3-devel   # Fedora
# sudo apt-get install -y clang cmake ninja-build libgtk-3-dev  # Ubuntu/Debian

# 3. Fetch packages
flutter pub get

# 4. Run in debug mode
flutter run -d linux     # or -d windows

# 5. Build release binary
flutter build linux --release    # produces build/linux/x64/release/bundle/
flutter build windows --release  # produces build/windows/x64/runner/Release/
```

Full packaging (AppImage, RPM, NSIS installer) is handled by the Python scripts in `scripts/`:
```bash
python scripts/build_linux_packages.py   # produces dist/*.AppImage and dist/*.rpm
python scripts/build_installer.py        # Windows only — produces dist/*-setup.exe
```

<br />


## Profiles

Three session profiles ship with v0.1. Profiles set the timer mode, default soundscape, and strictness level all at once — switchable from the tray or command palette.

| Profile | Mode | Soundscape | Strict level |
|---|---|---|---|
| **Coding Sprint** | Flowmodoro | Deep Coding | Soft — pause requires confirmation |
| **Revision Session** | Pomodoro 40/10 | Library Silence | Medium — pause button hidden |
| **Reading Mode** | Pomodoro 50/15 | Rainy Night | Nudge — button grays out for 5s |

<br />

## Audio licensing

Every audio asset in Zonal is documented before it ships. The full license table is at [`assets/audio/LICENSE.md`](assets/audio/LICENSE.md).

| Asset | Source | License |
|---|---|---|
| Brown noise | Procedurally generated — Dart | — |
| White noise | Procedurally generated — Dart | — |
| Rain | [freesound.org](https://freesound.org) | CC0 |
| Lo-fi music | [Free Music Archive](https://freemusicarchive.org) | CC BY / CC0 |
| Café ambience | [freesound.org](https://freesound.org) | CC0 |
| Jazz | [Kevin MacLeod — incompetech.com](https://incompetech.com) | CC BY 4.0 |
| Stream stations | [Radio Browser API](https://api.radio-browser.info) + [SomaFM](https://somafm.com) | Per-station (player, not distributor) |

Attribution for CC BY 4.0 content (Kevin MacLeod) appears in **Settings → About**.

No undocumented audio ships. If you are contributing a soundscape preset or alarm sound, your PR must include the source URL and license in `assets/audio/LICENSE.md` — the CI pipeline enforces this.

<br />

## Roadmap

| Version | Theme | What ships |
|---|---|---|
| **v0.1** | Core experience | Flowmodoro + Pomodoro · 3 soundscapes · Overlay · Session restore · Command palette · 3 profiles · Opt-in internet radio streaming |
| v0.2 | Analytics + Media | 7-day stats dashboard · 3 additional soundscapes · Media player overlay (SMTC/MPRIS2 now-playing) · Gentle strict mode · Notification personalities |
| v0.3 | Power users | Custom stream URLs · YAML config · WebSocket local API · OS audio ducking · macOS (if hardware available) |
| v0.4 | Community | JSON theme gallery · Flatpak on Flathub · i18n — Hindi, Spanish, Japanese |
| v1.0 | Stable | Stable public API · Community-maintained themes · Full documentation · Android companion app |

Stats are behind a 7-day data gate in v0.2 — they are meaningless with fewer than a week of sessions and are not shown until that threshold is reached.

<br />

## Contributing

Zonal is open source from day one and designed to have clear contribution entry points at every skill level.

```bash
git clone https://github.com/YOUR_USERNAME/zonal.git
cd zonal && flutter pub get
flutter run -d linux   # or -d windows
```

Before submitting a PR, run:
```bash
flutter analyze          # no issues
flutter test             # all tests pass
python scripts/verify_assets.py   # all audio assets licensed
```

### Good first issues

These are scoped for contributors without deep knowledge of the codebase:

| Issue | Skills needed | Where to look |
|---|---|---|
| 🎵 [Add a soundscape preset](https://github.com/YOUR_USERNAME/zonal/issues) | Audio sourcing, Dart | `lib/core/models/soundscapes.dart` |
| 🌐 [Add a translation](https://github.com/YOUR_USERNAME/zonal/issues) | Language, Dart | `lib/l10n/` |
| 🔔 [Add an alarm sound](https://github.com/YOUR_USERNAME/zonal/issues) | Audio sourcing | `assets/audio/` |
| 🐧 [Improve KDE Wayland idle detection](https://github.com/YOUR_USERNAME/zonal/issues) | Linux, C | `native/idle_detector.c` |

**Adding a soundscape:** Add your entry to `kSoundscapes` in `soundscapes.dart`, source all audio assets from CC0 or CC BY sources, document them in `assets/audio/LICENSE.md`, and open a PR. The maintainer will do a listening test before merge.

**Adding a translation:** Copy `lib/l10n/app_en.arb`, rename it for your locale (`app_hi.arb`, `app_es.arb`, etc.), translate the strings, and open a PR.

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for the full PR checklist and branch naming conventions.

<br />

## Platform notes

<details>
<summary><strong>Windows</strong></summary>
<br />

- Requires Windows 10 21H1 or later
- The NSIS installer handles WebView2 runtime automatically
- Global shortcuts use `hotkey_manager` and work from any foreground window
- Media session detection (SMTC) for now-playing display ships in v0.2
- The "Always show" fullscreen overlay uses `WS_EX_LAYERED + WS_EX_TOPMOST` — works correctly over DirectX/Vulkan exclusive fullscreen applications

</details>

<details>
<summary><strong>Linux (X11)</strong></summary>
<br />

- Full overlay support including always-on-top and fullscreen pierce via `_NET_WM_STATE_ABOVE`
- Global shortcuts work from any window via `hotkey_manager`
- MPRIS2 media detection for now-playing display ships in v0.2
- GNOME requires the [AppIndicator extension](https://extensions.gnome.org/extension/615/appindicator-support/) for the tray icon
- Install `gstreamer1-plugins-good` for stream audio on the RPM package (AppImage bundles it)

</details>

<details>
<summary><strong>Linux (Wayland)</strong></summary>
<br />

- The overlay renders and stays above regular windows
- The "Always show" fullscreen mode is not available — Wayland's compositor security model prevents arbitrary windows from piercing fullscreen surfaces. This is a compositor constraint, not a Zonal bug
- "Auto-hide" is enforced automatically when Zonal detects a Wayland session
- All other features (click-through, dot mode, corner snap, shortcuts) work normally
- For always-visible-in-fullscreen behaviour on Linux, use an X11 session

</details>

<details>
<summary><strong>Internet radio streaming</strong></summary>
<br />

Streaming is **off by default**. Enable it in **Settings → Audio → Audio source → Stream**.

When enabled, Zonal:
1. Queries the [Radio Browser API](https://api.radio-browser.info) for lo-fi, jazz, and ambient stations — a free, open-source, no-API-key community database
2. Caches results locally (refreshed every 24 hours)
3. Plays the highest-voted station matching your active soundscape's genre through the musical channel
4. Falls back through: primary stream URL → fallback URL → next available station → bundled local loop

SomaFM stations (Drone Zone, Groove Salad, Deep Space One) are hardcoded as seed stations for immediate availability before the cache populates.

When streaming is disabled, no network requests are made. Zonal is fully air-gap capable.

</details>

<br />

## License

MIT — see [`LICENSE`](LICENSE).

Zonal is free software. You may use it, fork it, and modify it for any purpose. Attribution is appreciated but not required.

---

<div align="center">

Built with [Flutter](https://flutter.dev) · [Radio Browser API](https://api.radio-browser.info) · [SomaFM](https://somafm.com)

<sub>Zonal v0.1 · May 2026</sub>

</div>
