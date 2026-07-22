# Installation

There are two jars. Most players only need the **client mod**. The **Paper
plugin** is only for editing on a multiplayer server.

| Jar | Where it goes | Who needs it |
| --- | --- | --- |
| `compbuild-studio-tools-<version>.jar` | your Minecraft **`mods/`** folder | every player |
| `compbuild-studio-tools-paper-<version>.jar` | the server's **`plugins/`** folder | the server admin (multiplayer only) |

Both jars are built together, so they always share a wire protocol — see
[[FAQ]] on version compatibility.

## Client mod (players)

1. Install **Fabric Loader** (≥ 0.19.3) for Minecraft **1.21.11**, and
   **[Fabric API](https://modrinth.com/mod/fabric-api)**.
2. Drop `compbuild-studio-tools-<version>.jar` into your instance's **`mods/`**
   folder. (In the vanilla launcher this is `<game-dir>/mods`; in
   MultiMC/Prism/CurseForge it's that instance's `mods` folder.)
3. Make sure there's only **one** Compbuild jar in there — remove older copies.
4. **Fully restart** Minecraft (not just leave/rejoin a world).
5. Press **Home** in‑game to open the editor.

**Confirm it loaded:** the log prints
`Compbuild net: multiplayer bridge registered on channel compbuild:edit1 …`
at startup, and **Home** opens the docked editor.

### Downloading a build

Grab the jars from the repository's **GitHub Actions** — open the latest green
run and download the `compbuild-studio-tools-jar` (client) and
`compbuild-studio-tools-paper-jar` (plugin) artifacts. Artifacts are **zips**;
unzip and use the `.jar` inside (putting the zip in `mods/` does nothing).

## Paper plugin (servers)

See **[[Multiplayer (Paper)]]** for the full setup, but in short:

1. Put `compbuild-studio-tools-paper-<version>.jar` in the server's `plugins/`.
2. Restart. The console prints
   `Compbuild Studio Tools server companion enabled (protocol v1, channel compbuild:edit1).`
3. Grant editors the **`compbuild.edit`** permission (default: op).
4. Join with the client mod installed — chat shows **"Server link active"**.

## Compatibility

- **Minecraft:** 1.21.11 (Java). Other versions are not supported.
- **Java:** 21+ (required by Minecraft 1.21).
- **Singleplayer** works out of the box. **Multiplayer** needs the Paper plugin
  (see [[Multiplayer (Paper)]]).
