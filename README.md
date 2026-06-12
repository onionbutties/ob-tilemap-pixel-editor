# OnionButties Tilemap Pixel Editor


A tool to create and pixel edit tilemaps, designed to work in a modern web browser (HTML5 + Javascript), because I couldn't find one out there for free.

It's considered a work in progress, and isn't perfect. It has as much as what allowed me to get on with some game stuff in Godot.
Let me know if there's a missing feature or anything broken, but you're also welcome to throw the code into AI and have it do it.

![Screenshot](images/screenshot1.png)


[github.com/onionbutties](https://github.com/onionbutties)

MIT License - do what you wish.
2026-06-12

---

## Getting Started

Open `ob-tilemap-pixel-editor.html` in any modern browser. The editor starts with a default 640×480 canvas and one layer.

## Features

### Tilemap Editor
- **Multi-layer canvas** with blend modes (12 modes) and per-layer opacity/visibility
- **Drawing tools**: Pen, Brush, Eraser, Fill, Line, Rectangle, Ellipse, Color Picker, Stamp
- **Selection** — click to select tiles, Shift+click to toggle, drag for rectangle selection
- **Marquee selection** — rect or lasso mode with feather support; Shift snaps to grid
- **Move tool** — drag selected tiles to reposition, snap-to-grid or freeform, keep-as-object mode
- **Cell rotation** — rotate single tile in-place; rotate multi-tile group from common centre
- **Cell flip** — flip tiles horizontally / vertically (toolbar buttons + keyboard F / Shift+F)
- **Cell scale** — scale tiles via paste layer (Ctrl to snap to cell steps)
- **Symmetry / Mirror drawing** — horizontal, vertical, or quad mirror across a draggable axis; works with pen, brush, eraser, line, rect, and ellipse tools

### Pixel Editor
- **Per-tile pixel editing** — drawing is clipped to the active tile
- **Faint white dashed border** indicates the active tile — never interferes with pixel drawing
- **Minimap** — shows full canvas overview with tile grid, active tile and hover highlight
- **Navigate** between tiles using arrow keys (with hold acceleration), or click tiles in the palette
- **Double-click** a tile in tilemap mode to jump to pixel editor

### Symmetry / Mirror Drawing
- **Mirror modes**: Horizontal (vertical axis), Vertical (horizontal axis), Quad (both axes)
- **Draggable axis**: Click and drag the axis guide line anywhere along the workspace to reposition the mirror centre — works in Select and Hand tools only
- **Shift-snaps** the axis to tile grid lines during drag; "Shift = Lock to Tile" hint on screen
- **Restricted to Select/Hand tools** to avoid interference with drawing
- **Mirrored previews** appear automatically for pen, brush, eraser, line, rect, and ellipse tools
- **Y key** cycles through modes; toolbar buttons for direct toggle

### Stamp Tool
- **T key** activates the stamp tool
- **Capture**: Click a tile (or the bounding box of selected tiles) to load it as the stamp source
- **Paint**: Click or drag to stamp the source onto the canvas — auto-skips duplicate tiles
- **Right-click** to clear the stamp source
- **Cursor feedback**: Blue dashed border when empty, yellow dashed + ghost preview when loaded
- Each stamp stroke is a single undo step

### Palette Management
- **Palette lock** — when active, every paint/fill stroke snaps colours to the nearest swatch in the palette
- **Dynamic palette** — swatches auto-expand via flex-wrap; up to 64 colours
- **Palette undo** — dedicated undo stack for swatch changes; ↶ button to revert
- **Import palette from image** — quantises to 4‑bit per channel (12‑bit colour), sorts by frequency
- **Save / Load palettes** to/from file (hex, GIMP .gpl format, plus native File System Access API dialogs)
- **Colour ramp generator** — generates a linear RGB gradient between two colours; choose step count and target palette

### Colour Picker
- **Palette modes**: Common swatches, Image colours (extracted from active layer), Custom palette
- **Eye dropper** with sample size options (point, 3×3, 5×5)
- **Alt+click temporary eyedropper** — sample without switching tools (works with pen, brush, eraser, fill, line, rect, ellipse)
- **Right‑click colour pick** — right‑click on the canvas to sample the pixel under the cursor (pen/brush tools only)
- **Palette lock indicator** — orange padlock badge on the FG swatch when lock is active

### Export / Import
- Export to PNG, JPEG, WebP (with quality slider)
- **Scale export** — 1×, 2×, 4×, 8×, or custom (1–16) integer scaling; pixel‑perfect with nearest‑neighbour
- **Auto‑crop** — trim transparent edges before export
- **Export single tile as PNG** (File menu, Ctrl+Shift+E) — exports selected tiles as individual images
- **Export spritesheet** — arrange tiles in row, column, or grid layout; choose all tiles or selected only
- **Copy canvas to system clipboard** (Ctrl+Shift+C) — full canvas or selected‑tile bounding box as PNG
- Import images as new paste layer
- Open image as new canvas
- Paste from system clipboard (Ctrl+V)
- Drag and drop images onto canvas


## Keyboard Shortcuts

| Tool | Key | Edit | Key |
|------|-----|------|-----|
| Pen | `P` | Undo | `Ctrl+Z` |
| Brush | `B` | Redo | `Ctrl+Y` |
| Eraser | `E` | Copy Tiles | `Ctrl+C` |
| Fill | `G` | Cut Tiles | `Ctrl+X` |
| Line | `L` | Paste Tiles | `Ctrl+V` |
| Rectangle | `R` | Delete Selection | `Del` / `Backspace` |
| Ellipse | `O` | Swap FG/BG | `X` |
| Colour Picker | `I` | Reset FG/BG | `D` |
| Hand / Pan | `H` / Space+drag | Temp Eyedropper | `Alt`+click |
| Select | `V` | Stamp | `T` |
| Marquee | `Q` | Flip Horizontal | `F` |
| Move / Transform | `M` | Flip Vertical | `Shift+F` |
| **View** | | Cycle Symmetry | `Y` |
| Zoom In | `Ctrl++` | Brush Size − | `[` |
| Zoom Out | `Ctrl+-` | Brush Size + | `]` |
| Fit to Window | `Ctrl+0` | | |
| Zoom 100% | `Ctrl+1` | | |
| Zoom 200% | `Ctrl+2` | | |
| **Pixel Editor** | | **Export** | |
| Navigate Tiles | Arrow keys | Export tile PNG | `Ctrl+Shift+E` |
| Enter Pixel Mode | Double-click cell | Copy to clipboard | `Ctrl+Shift+C` |
| Toggle Grid | `Ctrl+G` | | |
| Switch Tab | `Ctrl+Tab` | | |

### Paste Transform Shortcuts
| Action | Key |
|--------|-----|
| Commit paste | `Enter` |
| Cancel paste | `Esc` |
| Snap move to cell grid | `Alt` + drag |
| Force scale mode | `Shift` + drag |
| Force rotate mode | `Ctrl` + drag |

### Symmetry Shortcuts
| Action | Key / Gesture |
|--------|---------------|
| Cycle mirror mode | `Y` |
| Drag axis line | Click + drag (Select or Hand tool) |
| Snap axis to grid | `Shift` + drag axis |
| Reset axis position | Click reset button in toolbar |

## License

MIT
