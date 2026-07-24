# Tools

The left **rail** holds every tool (hover an icon for its name). The active
tool's settings appear in the right **Tool Options** panel, whose title bar has
a **?** button (a short description of the tool) and, for Sculpt/Paint/Biome,
three **preset slots** — see [[Materials, Palettes & Presets]].

Most numeric values are **draggable sliders** (click the track to jump, drag
the knob); some use −/＋ steppers or cycle chips. Every control **explains
itself on hover**.

---

## Select (pointer)

The neutral pointer. Aim and click to box-select (first click a corner, second
completes the box). A carried clipboard can be **planted** and placed here too.
Clicking away from the selection clears it.

## Selection

Two clicks make a box. Drag its **arrows** to move, its **edges** to resize,
and the gold **ring** to rotate 90°. The right panel shows size/volume, a
**Confirm selection** button, **New**/**Clear**, and rotate/nudge controls
under **More…**.

## Sculpt (terrain)

Raises, lowers, and reshapes terrain under the brush. Pick a **Type** from the
grid (icons + hover text), set **Radius** and **Intensity**, then click or
**hold** on the ground. Sculpting is **terrain-based**: raised ground reuses
each column's own surface block (grass stays grass, sand stays sand), so the
picked material never changes a sculpt result.

**Types (12):** Raise · Lower · Smooth · Flatten · Noise · Erode · **Extrude**
(pull the footprint straight up, hard-edged) · **Cliff** (terrace toward the
nearest step — low ground **builds up**, high ground **shaves down**, so it
shapes plateaus rather than only carving) · **Roughen** (light scattered
pitting) · **Distort** (rolling world-anchored waves) · **Shatter** (break into
sunken slabs along Voronoi seams) · **Slope** (see below).

### Slope

A two-step grade tool:

1. **Click point 1**, then **click point 2** to set the slope's **angle** (any
   angle — a **press-and-drag** from point 1 sets point 2 as you release).
2. Now **paint** with the brush: every dab fills low columns up and shaves high
   columns down onto that inclined plane, so you can extend the same grade in
   any direction — left, right, past either end.

The Tool Options panel shows the current state (`Click point 1` → the live
angle) and a **Reset slope points** button to start a new grade.

**Falloff** is a curve picker: **Flat**, **Smooth** (rounded dome), **Linear**,
**Plateau** (flat top then drop), **Spike**, **Round** (spherical cap). **Edge**
= **Natural** (organically wobbled rim, never a perfect circle) or **Exact**.
**Stroke** = **Flow** (hold-and-drag continuous) or **Tap** (one apply/click).

## Paint

Re-skins the terrain **Surface** (a few layers deep) or fills the brush
**Volume** with your material.

- **Mode:** **Single** (one material), **Noise** (a weighted **palette** shaped
  by a pattern), or **Gradient** (radial fade through the palette).
- **Patterns:** Smooth (rolling blobs) · Cells (Voronoi patches) · Cracks (thin
  boundary lines) · Blobs (lava-lamp metaballs) · Static (per-block mix) ·
  Scatter (blobs with dithered edges), with a live preview swatch and a **Size**.

## Paint Brush

Freehand block placing: paints your material wherever you click or drag, using
the current brush shape and radius.

## Scatter

Scatters objects across terrain **inside the brush** — the natural-detail tool
for trees, rocks, foliage and props.

- **Palette:** build a list of objects to scatter from three sources —
  **+ Clipboard copy** (whatever you last copied), **+ Schematic file** (opens
  the browser to add a `.schem`), and **+ Single block** (grass, flowers, …).
  Each object has a **weight** (how often it's picked) and can be toggled off
  by clicking its thumbnail.
- **Brush:** **Density** (sparse / medium / dense), **Size** (radius),
  **Spacing** (minimum gap between placements), **Random turn** (random
  quarter-turns), and **Mirror**.
- **Clump:** single blocks grow into **blobs** — set the clump size and a
  **Round** or **Square** shape — so grass and flowers land in natural patches
  that hug the surface instead of lone blocks.
- **Place on:** an optional **mask** restricting placement to chosen surface
  blocks (e.g. only grass); default is any surface.
- **Live preview:** the panel shows a **genuine simulated dab** — a pad the
  brush's exact radius with the real planner run over it — so density, spacing,
  turning and clumping read true before you paint.

**Paint to place** — each stroke lands as one **undoable** edit (**Ctrl+Z**).

## Gradient

A Photoshop-style dithered fade between **two material swatches** (A → B).
Choose **Linear** or **Radial**, run it along the selection's tallest axis or
**click two blocks** to aim the fade at any angle, then **Apply**.

## Transform (clipboard)

Shapes the **clipboard** before you place it. Copy something, then:

- **Rotate** to any angle (15° steps or ±90 chips) — block *positions* rotate
  exactly; block *states* snap to the nearest 90° (stairs can't face 37°).
- **Scale** per axis or uniformly (Lock/Free).
- **Mirror**, and **snap** placement to a grid (off/2/4/8/16).

A textured ghost shows the exact result on top of the block you point at; click
to place (and place again — settings stay until **Reset**).

## Array

Places repeated copies of the clipboard in a line: set the count with
**Ctrl+wheel**, then click a block to set the step direction/spacing. Air is
skipped so copies overlay terrain.

## Path

Click to drop points; a **live ghost** shows the exact blocks the path will
place. A bottom-right card holds Type/Width/Height/Slack/Build/Clear.

**Types:** **Line** (1-wide) · **Band** (adjustable-width road/wall) · **Drape**
(sags like rope; Invert arches) · **Smooth** (curve through every point) ·
**Curve** (pulled toward interior points) · **Stamp** (repeats the **clipboard**
at a spacing — copy something first).

Wheel = width, Shift+wheel = height, Ctrl+wheel = slack/spacing.

## Geometry

Plots exact shapes from a few clicked points — lines, circles, spheres, domes,
cylinders and more, hollow or filled. **Keep existing** places into air only.

## Biome

Paints **biomes** with the same noise patterns as Paint: build a weighted biome
palette (**+ Biome** opens the chooser), pick Pattern/Size/Radius/Shape, and
click. Applied via vanilla `/fillbiome`; each stroke snapshots what it replaced,
so **Ctrl+Z paints the old biomes back** while the Biome tool is active.

---

Every geometry edit is a single **undoable** operation backed by the same
tested engine. See **[[Controls]]** for keys and **[[Multiplayer (Paper)]]**
for how tools behave on a server.
