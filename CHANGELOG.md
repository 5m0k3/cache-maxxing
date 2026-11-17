# Changelog

All notable changes to this project are documented here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the project uses [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [0.4.0] - first public release

### Added
- **The bar** above the chat box in the Claude desktop app, VS Code and the terminal: a live cache countdown, the next message's cost (dollars or "× more"), how full the chat is, and one tip (🟢 keep going, 🟡 reply soon, 🟠 small chat fine, 🔴 expired with what a handoff saves).
- A single pop-up when a big chat's cache expires, and a heads-up when you send into it. Messages are never blocked.
- Instant updates on model switch (`/model`) and compaction (`/compact`). Older chats are filled in on resume; restarts and sleep are handled.
- **`/cmaxx-handoff`:** Haiku writes a briefing from the local transcript, saved under `.claude/handoffs/` (git-ignored); a fresh chat starts from it.
- **`/cmaxx-stats`:** savings, cache hit rate, rebuilds paid and replies, for this chat and all chats.
- **`/cmaxx-update`:** updates the plugin where possible, and refreshes the model and price list.
- **`/cmaxx`:** shows or hides the bar.
- Settings: rebuild limit, warning time, long-chat size, cost style, cache time.

[Unreleased]: https://github.com/5m0k3/cache-maxxing/compare/v0.4.0...HEAD
[0.4.0]: https://github.com/5m0k3/cache-maxxing/releases/tag/v0.4.0
