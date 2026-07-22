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
**hold** on the ground.

**Types (12):** Raise · Lower · Smooth · Flatten · Noise · Erode · **Extrude**
(pull the footprint straight up, hard-edged) · **Cliff** (terrace into flat
steps) · **Roughen** (light scattered pitting) · **Distort** (rolling
world-anchored waves) · **Shatter** (break into sunken slabs along Voronoi
seams) · **Slope** — a ramp you can **press-and-drag** from one end to the
other (live preview, sweep left/right) or place with **two clicks** (one end,
then the other); a single graded ramp connects the points.

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
