# Schematics

The **File** menu (top bar) imports and exports builds through the
`<game>/schematics` folder.

## Import

**File → Import schematic…** opens a **thumbnail browser**:

- Every `.schem` / `.schematic` shows as a small **3-D preview** — real block
  models, rendered once into a cached texture and anti-aliased so they read
  cleanly at thumbnail size (big builds stay solid, never a sparse mesh).
- Click a file for a big preview with size, block count, and any blocks this
  game version can't map (imported as air, counted honestly).
- **Import** loads it onto the clipboard, named after the file, ready to place
  like any copy.

### Organising in-editor

- **Create folders without leaving the game:** the **+ Folder** toolbar button
  makes and names a folder in the current directory (up to 5 levels deep);
  click a folder to enter, `..` to go up.
- **Folder icons:** each folder shows a small **pencil badge** in its corner —
  click it to pick an icon from a set of drawn pictographs (Vehicles, Trees,
  Vegetation, Houses, Buildings, Roads, Traffic, Construction, Water, Terrain,
  Furniture, Lighting, Rail, Marina, Favorites).
- **Favorites:** the **star** in a cell's corner favorites a schematic *or* a
  folder; the **Favorites** toolbar toggle shows only your favorites across the
  whole tree.

Icons and favorites are saved in `schematics/.compbuild-index.json`, so they
persist between sessions and travel with the folder.

## Export

**File → Save clipboard as .schem…** asks for a **name** and writes a **Sponge
v2 `.schem`** (the widely-supported schematic format). The clipboard card shows the
name, and its thumbnail matches what you'd paste — including the Transform
tool's pending rotation/scale.

## Formats & fidelity

- **`.schem`** — Sponge v1–3 read, v2 write. The primary format.
- **`.schematic`** — legacy format import, best-effort: common building blocks
  map to their modern names; anything unmappable is **skipped and reported**.
- **Block entities** (chest contents, sign text) are **not** preserved on
  multiplayer paste — see [[Multiplayer (Paper)]] limitations.

## Open the folder

**File → Open schematics folder** opens `<game>/schematics` in your OS file
browser (or prints the path to chat if it can't), handy for adding files or
folders from outside the game.
