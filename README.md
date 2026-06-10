# OnionButties Tilemap Pixel Editor


A tool to create and pixel edit tilemaps, designed to work in a modern web browser (HTML5 + Javascript), because I couldn't find one out there for free.

It's considered a work in progress, and isn't perfect. It has as much as what allowed me to get on with some game stuff in Godot.
Let me know if there's a missing feature or anything broken, but you're also welcome to throw the code into AI and have it do it.

![Screenshot](images/screenshot1.png)


[github.com/onionbutties](https://github.com/onionbutties)

MIT License - do what you wish.
2026-06-10

---

## Getting Started

Open `ob-tilemap-pixel-editor.html` in any modern browser. The editor starts with a default 640×480 canvas and one layer.

## Features

### Tilemap Editor
- **Multi-layer canvas** with blend modes (12 modes) and per-layer opacity/visibility
- **Tile-based grid system** — configurable cell size, grid colour, grid opacity
- **Drawing tools**: Pen, Brush, Eraser, Fill, Line, Rectangle, Ellipse, Color Picker
- **Tool properties** — size, opacity, hardness, shape (circle/square/diamond/plus/star/ring/blob), blend mode, fill mode (outline/filled/both), corner style (miter/round/bevel), line style (solid/dashed/dotted)
- **Live shape previews** for line, rect, ellipse tools while dragging
- **Tool cursor outlines** showing brush extent on hover
- **Selection** — click to select tiles, Shift+click to toggle, drag for rectangle selection
- **Marquee selection** — rect or lasso mode with feather support
- **Move tool** — drag selected tiles to reposition, snap-to-grid or freeform, keep-as-object mode
- **Cell rotation** — rotate single tile in-place; rotate multi-tile group from common centre with interactive paste transform overlay (bounding box, handles, drag-to-reposition)
- **Cell scale** — scale tiles via paste layer (Ctrl to snap to cell steps)
- **Tile palette** — scans tiles on the active layer and shows unique tiles as swatches for quick selection

### Pixel Editor
- **Zoom in** to edit individual tiles at pixel level
- **Per-tile pixel editing** — drawing is clipped to the active tile
- **Minimap** — shows full canvas overview with tile grid, active tile and hover highlight
- **Navigate** between tiles using arrow keys (with hold acceleration)
- **Double-click** a tile in tilemap mode to jump to pixel editor
- **Per-pixel grid** overlay at high zoom levels

### Paste Transform
- Paste images from clipboard (Ctrl+V) or import as overlay
- **Interactive overlay** with move, scale, and rotate handles
- **Bounding box** with corner handles (scale) and rotation handle
- **Drag behaviour** — click inside to move, drag corners to scale, drag rotation handle to rotate
- **Mode switching** — quick-click (no drag) toggles transform mode
- **Keyboard modifiers**: Alt+drag to snap movement to cell grid, Shift for scale, Ctrl for rotate
- **On-screen indicators** — degree arc for rotation, move vector, scale percentage bar
- **Adjustable opacity** — separate for dragging and static states
- **Commit** (Enter) or **Cancel** (Esc)
- Import images as new paste layers or as flattened canvas

### Undo / Redo
- Full history with configurable depth (default 80 steps)
- **History panel** — lists all actions with timestamps
- Click any history entry to jump to that state (double-click or right-click context menu)
- Delete all history after a chosen point

### Layer Management
- Add, delete, duplicate, rename layers
- Merge down, merge selected, flatten all
- Reorder layers (move up/down)
- Paste layers with transform — edit transform or rasterise
- Right-click context menu on layers

### Canvas Operations
- **Resize canvas** with Nearest Neighbour, Bilinear, or Bicubic resampling
- **New tilemap** with custom dimensions, cell size, background colour, and presets
- **Save As** — PNG, JPEG, WebP
- **Download in browser** (single-click PNG export)
- **Open image** as a new canvas
- **Import image** as paste overlay

### Colour Picker
- **Foreground/Background** colour stack (Photoshop-style)
- **Swap colours** (X key) and reset to defaults (D key)
- **Palette modes**: Common swatches, Image colours (extracted from active layer), Custom palette
- **Advanced colour picker dialog** — wheel view or square (SV) view, RGB/HSV sliders, hex input, plus/minus buttons per channel
- **Eye dropper** with sample size options (point, 3×3, 5×5)

### View Options
- **Zoom** — Ctrl++/-, scroll wheel, presets (25%–12800%), Fit to Window
- **Grid** — toggle, colour, opacity
- **Tool windows** — toggle Layers, Undo History, Tile Palette, Colour Picker, Minimap
- **Sidebars** — collapse/expand left and right panels
- **Reset panel sizes** (View menu)
- **Tab switching** — Tilemap / Pixel Editor (Ctrl+Tab)

### Export / Import
- Export to PNG, JPEG, WebP (with quality slider)
- Import images as new paste layer
- Open image as new canvas
- Paste from system clipboard
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
| Hand / Pan | `H` | / Space+drag | |
| Select | `V` | | |
| **View** | | | |
| Marquee | `Q` | Zoom In | `Ctrl++` |
| Move / Transform | `M` | Zoom Out | `Ctrl+-` |
| | | Fit to Window | `Ctrl+0` |
| **Pixel Editor** | | | |
| Zoom 100% | `Ctrl+1` | Zoom 200% | `Ctrl+2` |
| Navigate Tiles | Arrow keys | | |
| Enter Pixel Mode | Double-click cell | Toggle Grid | `Ctrl+G` |
| Switch Tab | `Ctrl+Tab` | | |

### Paste Transform Shortcuts
| Action | Key |
|--------|-----|
| Commit paste | `Enter` |
| Cancel paste | `Esc` |
| Snap move to cell grid | `Alt` + drag |
| Force scale mode | `Shift` + drag |
| Force rotate mode | `Ctrl` + drag |

## Context Menu (Right-Click on Tile)

- **Edit in Pixel Editor**
- **Fill with Foreground / Background**
- **Clear Tile**
- **Rotate 90° CW / CCW**

## Technical Details

- Canvas size: configurable (default 640×480)
- Tile size: configurable (default 32×32)
- Max history: configurable (default 80 states)
- Zero external dependencies — single HTML file
- Works in Chrome/Edge, Firefox, Safari
- Settings persisted in `localStorage`

## License

MIT
