# Controls

All keys are rebindable in **Options → Controls → Studio Tools** (the mod has
its own dedicated category, separate from the vanilla binds). Defaults:

| Key | Action |
| --- | ------ |
| **Home** | Open/close the docked editor (**Esc** also closes) |
| **B** | Set a selection corner from the block you're looking at |
| **G** | Delete the selection (clear to air) |
| **C** | Copy the selection to the clipboard |
| **V** | Paste at the block you're looking at |
| **R** | Rotate the clipboard 90° clockwise |
| **F** | Flip (mirror) the clipboard |
| **Ctrl + Z** | Undo |
| **Ctrl + Y** | Redo |

**Fill** and **Replace** are **unbound by default** (R/F now rotate/flip the
clipboard) — they're on the **Edit** menu and **ACTIONS** panel, and you can
bind them to any key in Options → Controls.

## Navigation (editor open)

| Input | Action |
| ----- | ------ |
| **Move mouse** | Look around (free camera) |
| **Esc** | Flying → cursor; **Esc again** closes the editor |
| **Tap Left-Alt** | Toggle look ↔ cursor |
| **W / A / S / D** | Move / strafe |
| **Space / Left-Shift** | Up / down |
| **Left-Ctrl** | Move faster |
| **Mouse wheel** | Fly speed (or brush/path size in those tools) |
| **Middle-click** | **Eyedropper** — adopt the block under the cursor (exact states) |

There's no crosshair — the **block you're aiming at is outlined**; that's your
pointer. To click a tool or panel, release the cursor with **Esc** or **Left-Alt**.

**Chat from the editor:** press **T** (or **/** for a command) to open the
normal chat screen; reopen the editor afterward with **Home**. Edit feedback
shows as a short **toast in the status bar** rather than in chat, so the log
stays clean.

## Cursor-mode clicks

| Input | Action |
| ----- | ------ |
| **Click** | Use the active tool at the outlined block |
| **Two clicks** | Make a selection box |
| **Click a carried ghost** | **Plant** it — arrows move, ring rotates, check places |
| **Right-click a ghost** | Pick a planted ghost back up; again drops the clipboard |
| **Ctrl + wheel** (carrying a clipboard) | Lift/sink the ghost (place below surface) |

## Screen shortcuts (editor focused)

| Shortcut | Action |
| -------- | ------ |
| **Ctrl + C** | Copy the selection |
| **Ctrl + X** | Cut (copy, then clear) |
| **Ctrl + V** | Paste at the hovered block |
| **Ctrl + Z / Ctrl + Y** | Undo / redo |

## Wheel modifiers by tool

| Tool | Wheel | Shift + wheel | Ctrl + wheel |
| ---- | ----- | ------------- | ------------ |
| Sculpt | Radius | Strength | — |
| Paint | Radius | — | Depth |
| Scatter | Size (radius) | — | — |
| Path | Width | Height | Slack / Stamp spacing |
| Array | — | — | Copy count |

> **Tip:** the **Help → Controls** overlay in-game shows this same cheat-sheet
> on one card (Esc or click closes it).
