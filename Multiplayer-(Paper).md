# Multiplayer (Paper)

Compbuild Studio Tools edits multiplayer worlds through a **server companion
plugin** for Paper/Spigot. The client mod computes each edit from what you can
see; the plugin **validates** it (permission + size), **applies** it with full
server authority in per-tick batches, and keeps your **undo/redo history on the
server**. Everyone nearby sees the result immediately — other players don't need
anything installed.

## Setup

1. Get both jars (built together; see [[Installation]]):
   - `compbuild-studio-tools-<version>.jar` — the **client mod** (players).
   - `compbuild-studio-tools-paper-<version>.jar` — the **plugin** (server).
2. Put the **plugin** jar in the server's `plugins/` folder and restart.
3. Grant editors the **`compbuild.edit`** permission (default: **op**). Any
   permissions plugin works:
   `/lp user <name> permission set compbuild.edit true`
4. Join with the **client mod** installed. Chat shows
   **"Server link active (plugin vX): edits apply through the server…"** — the
   handshake succeeded, and every tool now works.

Without the plugin (or the permission), world-editing tools decline with a
message saying why. **Copy and schematic export still work anywhere** — they
only read your view of the world.

## How it works

- On join the client greets the plugin on the `compbuild:edit1` channel; the
  plugin replies with your permission and the server's edit-size limit.
- Every tool computes its change list exactly as in singleplayer, then ships
  compact palette-compressed chunks instead of applying locally. The server
  re-reads each block's previous state as it applies, so its undo history is
  exact.
- Large edits apply spread across ticks (`blocks-per-tick`) so the server never
  stalls; you get a progress overlay and an honest changed-block count.
- **Ctrl+Z / Ctrl+Y** send undo/redo requests; the server replays *your*
  per-player history.

## Region protection (WorldGuard)

With **WorldGuard** installed and `respect-regions` on (default), edits honour
region build permissions: a player who can't build in a region (and lacks
WorldGuard bypass — ops and `worldguard.region.bypass.*` do) has the protected
blocks **skipped and counted** (`"…128 blocks skipped (protected regions)."`).
This makes the plugin safe to grant on servers that use regions.

- No WorldGuard → nothing to enforce; the permission node is the gate.
- WorldGuard + `respect-regions: false` → protection ignored (trusted editors
  only).
- Undo/redo of your own edits is **not** re-gated, so a later region change
  can't strand your undo.

## Configuration (`plugins/CompbuildStudioTools/config.yml`)

| Key | Default | Meaning |
| --- | ------- | ------- |
| `max-blocks-per-edit` | 1000000 | Hard per-edit ceiling; larger edits are rejected before any change. |
| `blocks-per-tick` | 6000 | Apply rate; lower = smoother TPS/client FPS during edits (slower to finish), higher = faster but burstier. |
| `history-max-entries` | 24 | Per-player undo depth. |
| `history-max-mb` | 256 | Per-player history memory cap. |
| `edit-timeout-ticks` | 600 | Discard half-uploaded edits after this long. |
| `respect-regions` | true | Honour WorldGuard region build permissions. |

## Troubleshooting the handshake

If tools say the plugin isn't detected even though it's installed, walk the
chain — each side leaves a breadcrumb:

1. **Editor → Settings → "Server:" row.** `linked — plugin vX` = success.
   `no reply after N hellos` = greetings went out, nothing came back (continue).
   `disabled …` = the client's networking failed to start (see the client log
   for `Compbuild net`).
2. **Server console at startup** must show
   `Compbuild Studio Tools server companion enabled (protocol v1…)`. If not, the
   plugin didn't load — check for errors above it, and that the **plugin** jar
   (not the client jar) is in `plugins/`.
3. **Server console on join** should show
   `Compbuild handshake from <name>… : permitted`. If it does but the client
   still reports no reply, look for a warning that the player hasn't announced
   the channel.
4. If the handshake line never appears, a **proxy** (Velocity/BungeeCord) may be
   filtering the `compbuild:edit1` channel — allow it, or connect directly.
5. Make sure you're on the **current client jar** — a stale jar is the most
   common cause. The decline message and the Settings "Server:" row both change
   wording between versions.

## Honest limitations

- **Block entities carry no NBT** — a pasted chest/sign arrives empty.
- **The Biome tool** uses vanilla `/fillbiome`, so it needs vanilla command
  permission (op) independent of the plugin.
- **History is per-session** — leaving the server clears your server-side undo.
- Edits target loaded chunks (what you can see).
- **Fabric multiplayer servers** aren't covered by a companion yet — the
  protocol is platform-neutral, so a Fabric server module could follow.

See also **[[FAQ]]** for mod/plugin version compatibility.
