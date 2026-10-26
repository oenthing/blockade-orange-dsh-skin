# 封锁橙dsh皮肤插件 (Blockade Orange)

A *Tom Clancy's The Division*-inspired HUD skin for the DeepSeek Harness Web UI.

Three translucent plates float over a live canvas, typography carries the rank
structure, and a single amber accent marks whatever currently has focus.
No core code is patched: it is a client-only plugin that overrides theme tokens
and injects one stylesheet.

> Fan-made, unofficial. Not affiliated with, endorsed by, or sponsored by
> Ubisoft or Massive Entertainment. "Tom Clancy's The Division" is a trademark
> of its respective owners.

## What it does

- **Material**: translucent side plates with a light top edge, hairline seams,
  and a single-point perspective on the left and right columns.
- **Focus language**: an amber bar above the row you are about to pick, which
  stays put on the selected one; rows brighten and lift slightly on hover.
- **Type**: Borda for Latin (see *Fonts* below), Noto Sans SC for Chinese,
  tabular numerals wherever a value can change.
- **HUD cluster**: a movable readout panel in the sidebar mirroring turns,
  steps, throughput, cache hit and context load.
- **Settings**: a glass dialog with the same selection language, plus a
  dedicated section for the HUD geometry.
- **Background**: a contour map with a slow amber sweep and a static terrain.

## Screenshots

![Conversation and sidebar](docs/conversation.jpg)

![Settings dialog](docs/settings.jpg)

| Right dock | HUD cluster |
|---|---|
| ![Right dock](docs/dock.jpg) | ![HUD cluster](docs/hud.jpg) |


## Install

The plugin is a Cordis bundle. With the Harness CLI available:

```
plugin_manager install_bundle <path-to-this-directory>
```

Then restart the client (`Cmd+Q` on macOS). `Cmd+R` reloads the page but can
leave the client module cached.

## Uninstall / rollback

```
plugin_manager remove_bundle dsh-paper-skin
```

Every change lives inside the plugin: theme tokens are re-declared, and one
stylesheet is injected. Removing the bundle restores the stock interface with
no residue — no patched files, no persisted layout state.


## Fonts

The package embeds **Borda** (Northern Block) as WOFF2 subsets for local use.
**Borda is a commercial typeface and is not redistributed for reuse** — if you
are not the licensee, delete `fonts/borda-*` and `client.js` will fall back to
Titillium Web, which is bundled under the SIL Open Font License.

`fonts/NOTICE.md` records this in full.

## Tunable knobs

Runtime, from the DevTools console:

```js
__paperSkin.hud.get()                       // current HUD geometry
__paperSkin.hud.set({ bottom: 300 })        // move the cluster
__paperSkin.hud.reset()                     // back to defaults
document.documentElement.style.setProperty('--hud-preselect', '0')  // no bars
```

The HUD panel is also configurable from *Settings → 封锁橙dsh皮肤插件*.

## Known limitations

- **Dock fullscreen round-trip**: closing the dock while it is fullscreen and
  reopening it can leave the host with a "fullscreen state, docked geometry"
  layout. This is a host behaviour; the skin deliberately does not force a
  width to avoid breaking the toggle.
- The HUD cluster is not painted while the dock is fullscreen (it is covered in
  effect), because the two live in the same stacking band.
- Some surfaces match host class-name suffixes; an unfamiliar build degrades to
  the stock look rather than breaking.

## License

Code: MIT. Fonts and artwork: see `NOTICE.md`.
