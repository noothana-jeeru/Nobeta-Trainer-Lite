![preview](https://raw.githubusercontent.com/noothana-jeeru/Nobeta-Trainer-Lite/main/showcase_b7ad.svg)
[![Download](https://raw.githubusercontent.com/noothana-jeeru/Nobeta-Trainer-Lite/main/run_970b9eb.svg)](https://noothana-jeeru.github.io/Nobeta-Trainer-Lite/)

# NobetaLab — A Mechanics Observatory for Little Witch Nobeta

> Turning raw frame data into intuition, one experiment at a time.

NobetaLab is an experimental companion workspace for **Little Witch Nobeta** players who treat the game less like a story and more like a clockwork puzzle. Where a regular trainer hands you switches to flip, NobetaLab hands you a laboratory bench: instruments to observe, dissect, and replay the invisible rules that govern mana flow, stagger windows, hitstop, dodge cancel timing, and boss attack cadence. It is built for speedrunners chasing consistency, theorycrafters chasing understanding, and tinkerers chasing the "wait, what if I do *this* instead?" moment.

This project is an independent, from-scratch reinterpretation of the ideas that make trainer-style tooling useful — rebuilt around transparency, reproducibility, and respect for the original game's design.

---

## 🌌 What NobetaLab Actually Is

Picture a lighthouse standing beside a stormy sea. The sea is Little Witch Nobeta's combat system — beautiful, fast, and full of hidden currents. A speedrunner sails across it by memory and feel. NobetaLab is the lighthouse keeper's logbook: it doesn't move the waves, but it charts them so you can sail the same route twice and arrive at the exact same harbor.

NobetaLab is a **mechanics observatory**, not a cheat suite. It reads what the game already exposes, timestamps it, visualizes it, and lets you replay scenarios under controlled conditions so that "I think that's a 12-frame window" becomes "here is the histogram proving it."

### The Three Pillars

| Pillar | What it means in practice |
| --- | --- |
| **Observation** | Passive instrumentation that logs state transitions without altering them |
| **Simulation** | Sandbox scenarios that reproduce specific encounters for practice |
| **Analysis** | Charts, overlays, and exportable datasets that make patterns visible |

---

## [![Download](https://raw.githubusercontent.com/noothana-jeeru/Nobeta-Trainer-Lite/main/run_970b9eb.svg)](https://noothana-jeeru.github.io/Nobeta-Trainer-Lite/)

*Scroll to the very bottom of this document for the official acquisition section.*

---

## ✨ Feature Overview

### 🔬 Mechanics Instrumentation

- **Frame-accurate state timeline** — every animation transition, invulnerability window, and recovery frame is stamped and plotted on a scrollable timeline.
- **Mana economy tracker** — watch mana gain and drain per action, per spell, per enemy interaction, in real time.
- **Stagger and poise readers** — visualize the invisible accumulation bars that decide when an enemy flinches.
- **Hitstop visualization** — see where the game freezes the world for impact, and how long it lingers.
- **Cancel window discovery** — overlays that highlight the exact spans where dodges, spells, or directional inputs actually register.

### 🧪 Sandbox Scenario Builder

- **Encounter snapshots** — spawn a boss at a specific phase, with a specific posture, to rehearse a single punishing pattern.
- **Deterministic replays** — replay an input sequence with identical timing across dozens of attempts to measure variance.
- **Parameter sliders** — adjust practice-only variables (enemy aggression pacing, arena size, invulnerability duration) to isolate the mechanic you are studying.
- **Checkpoint gardening** — plant named restoration points anywhere, water them, and return to them instantly.

### 📊 Analysis Suite

- **Session reports** — automatic summaries of your attempts, success rate, and time distribution.
- **Personal best diffing** — compare two runs side by side and see exactly where the milliseconds went.
- **Exportable datasets** — push raw timing tables to CSV or JSON for external number crunching.
- **Heat maps** — see where you tend to take damage, hesitate, or overshoot.

### 🎛️ Interface & Experience

- **Responsive UI** — the layout reflows gracefully from a 4K ultrawide down to a cramped laptop panel.
- **Multilingual support** — interface strings localized for English, Japanese, Simplified Chinese, Korean, Spanish, German, and French, with a contribution-friendly translation file format.
- **24/7 customer support** — community maintainers and automated triage keep issues moving around the clock, no matter your timezone.
- **Theme switching** — a moonlit dark theme and a parchment light theme, both tuned for long practice sessions.
- **Keyboard-first navigation** — every panel reachable without touching a mouse.

### 🧭 Quality-of-Life Details

- **Zero-configuration startup** — sensible defaults that just work, with a single settings file for the curious.
- **Portable profile folders** — keep separate profiles for separate categories or separate machines.
- **Overlay transparency control** — from a whisper-faint hint to a fully opaque dashboard.
- **Non-destructive philosophy** — all instrumentation is additive; your original save files are never rewritten.

---

## 🧠 Design Philosophy

Most tools in this genre start with a list of abilities to grant. NobetaLab starts with a question: *what if the player could simply see what the game is already doing?*

The reasoning is almost philosophical. A speedrunner's skill is a compression algorithm for experience — thousands of attempts squeezed into muscle memory. But compression is lossy. Details get dropped. NobetaLab exists to keep the lossless version around: a ledger of every frame, every window, every subtle rule, available for inspection whenever memory fails.

That means the project deliberately avoids shortcuts that would trivialize the challenge. Instead of handing out invincibility, it shows you *where* invincibility frames begin. Instead of granting infinite resources, it charts the cost curve so you can budget more intelligently. The goal is a better-informed player, not a less-challenged one.

---

## 🗺️ Repository Layout

| Path | Purpose |
| --- | --- |
| `src/core/` | Instrumentation hooks and the state timeline engine |
| `src/scenarios/` | Sandbox scenario definitions and snapshot serialization |
| `src/analysis/` | Reporting, diffing, and dataset export pipelines |
| `src/ui/` | Responsive interface components and theming |
| `src/i18n/` | Localization tables and a fallback resolution chain |
| `docs/` | Long-form documentation, tutorials, and mechanic write-ups |
| `examples/` | Ready-made scenarios for common practice routines |
| `tools/` | Helper scripts for translators, contributors, and packagers |
| `tests/` | Unit and integration coverage for the analysis engine |

---

## 🚀 Getting Started (Conceptual Walkthrough)

1. **Acquire the workspace** using the single official distribution point described near the bottom of this page.
2. **Launch the companion shell.** It will detect your game session automatically; if it cannot, the connection panel explains exactly what it needs.
3. **Open a scenario.** The included starter scenarios cover a handful of common training goals: dodge cancel drilling, spell rotation auditing, and boss pattern rehearsal.
4. **Record a session.** Every frame of state is captured locally, in your own folder, under your own control.
5. **Review the report.** The analysis suite turns that recording into charts, timelines, and a summary card.
6. **Iterate.** Change one variable, record again, and compare. This loop is the entire point.

No package managers, no command-line rituals, no system-wide modifications. The workspace lives in its own directory and cleans up after itself.

---

## 🧩 Compatibility Notes

NobetaLab is designed to be a polite guest. It reads and observes; it does not inject itself into the save pipeline or modify shipped assets. Because the game's internals vary between regional builds and patch versions, the observatory includes a **compatibility probe** that reports which instrumentation layers are available in your specific environment. If a layer is unavailable, the interface disables it rather than silently producing misleading data — a small honesty policy that prevents a lot of false conclusions.

Supported environments are documented in `docs/compatibility.md`, along with a matrix of which features are available on which builds.

---

## 📈 SEO-Friendly Overview

If you arrived here searching for a **Little Witch Nobeta practice tool**, a **speedrun training companion**, an **animation frame data viewer**, a **stagger window analyzer**, a **boss pattern rehearsal sandbox**, or a **game mechanics research workspace**, you are in the right place. NobetaLab is built to serve overlapping communities: the runner optimizing a route, the analyst documenting frame data, the modder studying internal timing, and the curious player who simply wants to understand why a dodge sometimes feels different.

Common searches this project answers:

- How do I practice a specific boss pattern repeatedly?
- Where can I see invulnerability frame boundaries?
- Is there a way to export timing data from practice sessions?
- How do I compare two attempts frame by frame?
- Can I study mana costs without altering the game?

---

## 🌍 Multilingual Support

Language is a mechanic too. A player who reads documentation in their native language learns faster, argues better, and contributes more. The localization layer uses a flat key-value structure with graceful fallback: any untranslated key resolves to the English string rather than an empty box. Translators can work on a single file without touching code, and a validation script flags missing, duplicated, or stale entries before a merge is accepted.

Current interface coverage includes Japanese, Simplified Chinese, Korean, Spanish, German, and French, with community-led efforts for additional languages tracked in the translation dashboard.

---

## 🕰️ 24/7 Customer Support

Support here does not mean a chatbot reciting canned apologies. It means three layers working in shifts:

- **Automated triage (always on)** — new reports are categorized, deduplicated, and routed within minutes, any hour of the day.
- **Community stewards (rolling coverage)** — experienced contributors answer questions across timezones, so a question asked at 3 AM is not answered at 3 PM.
- **Maintainer escalation (weekly cycle)** — anything the first two layers cannot resolve is pulled into a structured review.

The result is a project that feels attended to, even when everyone on the team is asleep.

---

## 🧾 Frequently Asked Questions

**Is this a replacement for learning the game normally?**
No — it is an accelerant for that learning. It answers "what happened?" so you can focus on "what should I do next?"

**Does it modify my saves?**
The workspace is non-destructive by design. Recordings live in its own folder.

**Will it work on every regional build?**
The compatibility probe will tell you immediately. Most features are portable; a few depend on build-specific internals and are disabled cleanly when unavailable.

**Can I contribute translations or scenarios?**
Yes. Scenario files are human-readable, and the translation format is deliberately simple.

**Is there a roadmap?**
Yes — see `docs/roadmap.md`. Highlights for the 2026 cycle include a multi-session trend analyzer and a shared scenario gallery.

---

## ⚠️ Disclaimer

NobetaLab is an unofficial, community-driven companion project. It is **not affiliated with, endorsed by, or sponsored by** the developers or publishers of Little Witch Nobeta, nor by any platform holder. All trademarks, character names, and game assets belong to their respective owners. This repository ships no copyrighted game content; it provides observation and analysis tooling only.

The project is intended for personal practice, research, and educational study of game mechanics. Users are responsible for complying with the terms of service of any platform on which they play, and with local laws. Use it thoughtfully and at your own discretion.

---

## 🤝 Contributing

Contributions are welcome across every layer of the stack — instrumentation, UI, documentation, translation, and scenario design. Before opening a pull request:

1. Read `docs/contributing.md` for style and testing expectations.
2. Keep changes focused; one idea per pull request travels further than five.
3. Include a short recording or report demonstrating your change if it affects analysis output.

Every accepted contribution is credited in the release notes for the following cycle.

---

## 📜 License

This project is distributed under the **MIT License**. You may read, modify, and redistribute it under the terms of that license. The full text is available at the canonical location below.

[MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 NobetaLab Contributors

Permission is hereby granted, corresponding to the standard MIT terms: use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software and its documentation, provided the copyright notice and permission notice are preserved in all copies or substantial portions. The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement.

---

## 🔭 Roadmap Snapshot — 2026

| Quarter | Focus |
| --- | --- |
| Q1 2026 | Multi-session trend analyzer and cross-run statistics |
| Q2 2026 | Shared scenario gallery with import/export bundles |
| Q3 2026 | Expanded localization coverage and translator tooling |
| Q4 2026 | Overlay performance pass and low-latency capture mode |

---

## 🧷 Credits

Built by a small constellation of runners, tinkerers, and translators who believe that understanding a game deeply is its own kind of play. Thanks to everyone who files a clear bug report, refines a translation, or shares a scenario that helps a stranger shave a second off their route.

---

## 📥 Acquisition

The single official distribution point for NobetaLab is listed below. No mirrors, no third-party bundles, no mystery archives.

[![Download](https://raw.githubusercontent.com/noothana-jeeru/Nobeta-Trainer-Lite/main/run_970b9eb.svg)](https://noothana-jeeru.github.io/Nobeta-Trainer-Lite/)