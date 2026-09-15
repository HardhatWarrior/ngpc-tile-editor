# NGPC Tile Editor

A self-contained, single-file browser tool for creating Neo Geo Pocket Color tile/tileset art: pixel painting, layers, a shared palette bank with per-tile palette overrides, PNG import (including a full-color reference mode with per-tile auto-palette generation), and C-array export matching this project's toolchain's tile/palette format (2bpp, MSB-first, RGB444).

No build step, no server, no dependencies — just open `index.html`, or use the hosted version below.

**Live version:** https://hardhatwarrior.github.io/ngpc-tile-editor/

Works well as an installed home-screen app (PWA-style "Add to Home Screen") on Android devices, including e-ink tablets.

## Tilemap Editor

A companion tool for arranging tiles drawn here into larger maps: https://hardhatwarrior.github.io/ngpc-tile-editor/tilemap/

Import a project `.json` saved from this Tile Editor and it becomes a placeable tileset (each source layer pairs 1:1 with a map layer, e.g. SCR_1/SCR_2). Stamp, erase, flood-fill, and per-placement palette/flip overrides, with a hardware-budget readout (512 shared tile slots, 16 palettes per plane) and C export (`*_tiles[]`, `*_map_tiles[]`, `*_map_pals[]`, `*_map_flip[]`) consumable via `ngpc_gfx_put_tile_ex()`.
