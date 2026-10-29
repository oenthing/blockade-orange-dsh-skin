# Changelog

## 2.3.2

- Boot-in: the sidebar and dock slide in from their own edges with a single
  edge flash, then the composer, cards and HUD settle; tagged once per load,
  skipped under `prefers-reduced-motion`.
- Window blur dims the whole HUD, like a game that pauses when you look away.
- Streaming cursor sits at the tail of the text; HUD values roll to their new
  numbers instead of jumping.
- Running tool cards light up; entrance and scroll loops pause while the window
  is hidden.
- Docs: corrected the uninstall name and the note on how Borda is embedded.

## 2.3.1

- Hover language unified: every surface with a bar now brightens, lifts, turns
  white and draws its bar from the left (130ms fade, 150ms lift, 200ms draw).
- Header icon buttons, dock file rows, dock tabs and dock menu entries joined
  the same system.
- Windows: no double blur on top of DWM acrylic, no heavy panel shadows, all
  loops paused while the window is hidden.
- Fewer layout polls (450ms dock, 700ms HUD, 1500ms tagging).
- Settings: removed the nav scroll rail; active toggles carry a persistent bar.
- Fixed the bar rendering half-drawn (an animation restarted on every host
  re-render).

## 2.3.0

- Settings: master switch, background-light switch, contour switch, custom
  background (URL or local file), lite mode for weak GPUs.
- HUD cluster now renders as plain DOM inside the sidebar flow, so it can never
  cover the session list.
- Sidebar: no more blinking on layout changes; light edge and settle ring follow
  real width changes only.
- Conversation: turn separators, terminal-style code blocks, streaming light,
  send-button ripple, HUD status pulse.
- Fixed a crash that silently unregistered the settings section.

## 2.2.0

- Right dock: docked and fullscreen states share one readable plate.
- Conversation: turn separators with an amber tick, terminal-style code blocks,
  streaming light along the top edge.
- Motion: hover lift, press sink, selection bar draw, popover content scale.
- Scrollbars: gradient thumb with an amber hover glow.
- HUD: value/unit rows, first four units right-aligned, cluster lifted 40px.
