# Materials, Palettes & Presets

The **right panel** has three tabs: **MATERIAL** (what you place), **RECENT**
(your last materials), and **PROPS** (the context inspector).

## The material picker

Click the material row (or a gradient swatch, or press the eyedropper) to open
the picker **as an overlay** — the tools stay visible behind it. **Type to
search**, click a block to choose it, or click **✕** / outside to close.

- **Air is the first entry** (a hollow slashed square). Painting, filling, or
  building with **Air erases** — a brush-shaped delete, a fill-as-clear, a
  geometry-as-carve.
- **Middle-click** any block in the world to **eyedrop** it as the material,
  exact block states included.
- Blocks with **states** (stairs facing, log axis…) show cyclable property rows
  under the material.

## Recent materials

The **RECENT** tab lists your last **10** materials — picked, eyedropped, or
swapped — newest first, with the active one marked. Click any to use it again.

## Named palettes

Under the **MATERIAL** tab, the **PALETTES** section saves **named material
sets** — "sandstone set", "nether reds", etc.

- **+ Save current as palette…** names and stores the current **Paint** palette,
  or (if that's empty) your recent materials — whichever you've been curating.
- Each saved palette is a row; click it to **expand its swatches**. Click a
  swatch to make it the active material.
- **>P** loads the whole palette into the **Paint tool** (swap your entire noise
  mix in one click). **x** deletes it.
- Palettes persist across restarts (ordered, capped at 24).

## Per-tool presets

**Sculpt**, **Paint**, and **Biome** each have **three preset slots** on the
Tool Options title bar:

- Click an **empty** slot to save the current setup.
- Click a **filled** slot to load it.
- Click **+** first to arm an **overwrite** of a filled slot.

A preset captures that tool's knobs (radius, strength, shape, falloff, mode,
palette, etc.).

## Persistence

Everything above — every tool's knobs, the paint/biome palettes, the active
material and recents, your **named palettes**, and all presets — is written to
**`config/compbuildtools-settings.json`** when the editor closes and restored
next launch. A missing or corrupt file just means defaults; it never blocks
startup.
