# Schematics

The **File** menu (top bar) imports and exports builds through the
`<game>/schematics` folder.

## Import

**File → Import schematic…** opens a **thumbnail browser**:

- Every `.schem` / `.schematic` shows as a small isometric preview (loaded
  lazily, cached).
- Organise files into **named folders** inside `schematics/` (up to 5 levels
  deep) — click a folder to enter, `..` to go up.
- Click a file for a big preview with size, block count, and any blocks this
  game version can't map (imported as air, counted honestly).
- **Import** loads it onto the clipboard, named after the file, ready to place
  like any copy.

## Export

**File → Save clipboard as .schem…** asks for a **name** and writes a **Sponge
v2 `.schem`** (the format WorldEdit/Axiom read). The clipboard card shows the
name, and its thumbnail matches what you'd paste — including the Transform
tool's pending rotation/scale.

## Formats & fidelity

- **`.schem`** — Sponge v1–3 read, v2 write. The primary format.
- **`.schematic`** — legacy MCEdit import, best-effort: common building blocks
  map to their modern names; anything unmappable is **skipped and reported**.
- **Block entities** (chest contents, sign text) are **not** preserved on
  multiplayer paste — see [[Multiplayer (Paper)]] limitations.

## Open the folder

**File → Open schematics folder** opens `<game>/schematics` in your OS file
browser (or prints the path to chat if it can't), handy for adding files or
folders from outside the game.
