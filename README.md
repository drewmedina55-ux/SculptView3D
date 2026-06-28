<img width="827" height="619" alt="Screenshot 2026-06-27 232505" src="https://github.com/user-attachments/assets/d409c45a-b637-4b68-a01a-aae639789db1" />

SculptView3D v1.1

A browser-based 3D model viewer with stereo3D support for the "Samsung Odyssey3D 4K monitor" or any SBS supported devices.

Created by https://drewmedina.com/
· Freeware MIT

---

What It Does:

SculptView3D is a stereoscopic SBS model viewer that lets you drag and drop a 3D model file directly into your browser and inspect it with full rotation, panning, scaling, and lighting controls — no installation, no account, no data sent anywhere. It supports standard and side-by-side stereo 3D viewing modes.

Designed for the Samsung Odyssey 3D 4K monitor or other SBS devices.
---

## Supported File Formats

| Format | Extension | Notes |
|--------|-----------|-------|
| GL Transmission Format | `.glb`, `.gltf` | Preferred format — supports textures, materials, animations |
| Wavefront OBJ | `.obj` | Drop alongside `.mtl` and texture files for full material support |
| Stereolithography | `.stl` | Common in 3D printing workflows |
| Polygon File Format | `.ply` | Supports color per-vertex |
| Autodesk FBX | `.fbx` | Widely used in game and film pipelines |
| Textures | `.png`, `.jpg`, `.webp`, `.bmp`, `.tga` | Drop with your model file together |

> **Tip:** Use textured glb or for OBJ models, select and drop the `.obj`, `.mtl`, and all texture image files at the same time. The viewer should resolve them automatically.

---

## Getting Started

1. Open `SculptView3D_DrewMedina.html` in a modern web browser (Chrome, Firefox, Edge, or Safari).  *tested in Chrome PC
2. Drag your 3D model file (or files) onto the drop zone, or click **Browse files**.
3. The model loads instantly in your browser. No server. No upload.
4. Switch to 3D SBS mode, select the dual image popup message on the Samsung 3D monitor.

---

## Controls

### Mouse

| Action | Result |
|--------|--------|
| Left drag | Rotate model |
| Right drag | Pan camera |
| Middle mouse hold + drag | Pan camera |
| Scroll wheel | Scale model up / down |

### Keyboard Shortcuts

#### View
| Key | Action |
|-----|--------|
| `Escape` | Exit SBS mode |

#### Model
| Key | Action |
|-----|--------|
| `T` | Toggle texture / flat shading |
| `S` | Toggle shadows on / off |
| `0` | Scale model up (×1.1) |
| `9` | Scale model down (÷1.1) |

#### Playback
| Key | Action |
|-----|--------|
| `Space` | Toggle auto-rotate |
| `1` / `2` / `3` / `4` | Rotation speed: slow / medium / fast / superfast |

#### Lighting
| Key | Action |
|-----|--------|
| `Q` / `W` | Key light intensity down / up |
| `E` / `R` | Ambient light intensity down / up |

#### Stereo (SBS mode)
| Key | Action |
|-----|--------|
| `+` / `=` | Increase eye separation |
| `-` | Decrease eye separation |
| `]` | Increase convergence distance |
| `[` | Decrease convergence distance |

#### Help
| Key | Action |
|-----|--------|
| `K` | Toggle in-scene key legend (3D overlay) |
| `?` or `/` | Open keyboard shortcut reference |

---

## Viewing Modes

### Standard
Default view. Single-camera rendering with full UI and sidebar controls.

### SBS Stereo 3D
Side-by-side split rendering for Samsung Odyssey3D monitor, VR headsets or 3D televisions. The in-scene HUD provides stereo controls (eye separation, convergence) without leaving the immersive view.

---

## Settings Sidebar

Open with the **⚙ Settings** button.

- **Stereo Settings** — eye separation and convergence distance sliders
- **Lighting** — ambient intensity, key light intensity, background brightness; color pickers for ambient, key, fill, and rim lights
- **Display** — wireframe toggle, grid toggle, shading mode (Textured / Flat), model scale slider
- **Rotation Axis Lock** — X, Y, Z toggle buttons to prevent rotation on individual axes; **⬆ Set View as Rotation Origin** resets the rotation reference to the current view so Y-drag spins correctly. *hopefully this helps!
- **Quick Orient** — six one-click presets (Front, Back, Left, Right, Top, Bottom) to snap a wrong-facing model into alignment
- **Model Info** — format, mesh count, vertex count, triangle count

### Fixing a Wrong-Facing Model

Some models load sideways or upside-down. To correct the rotation behaviour:

1. Click a **Quick Orient** preset until the model looks right.
2. Click **⬆ Set View as Rotation Origin**.
3. Drag normally — Y-rotation now spins around the correct visible axis.
4. Try locking axis rotations

---

## Web Security & Privacy

SculptView3D is a **fully client-side, single-file HTML application**. Understanding what that means for your security:

### No Data Leaves Your Device
Your 3D model files are never uploaded to any server. All file loading, parsing, and rendering happens entirely inside your browser using the 'File API' and 'WebGL'. Close the tab and the files are gone from memory.

### No Tracking or Analytics
The application contains no analytics scripts, cookies, local storage writes, or telemetry of any kind. There is no login, no account, and nothing is retained between sessions.

### External Resources
The viewer loads JavaScript libraries from a public CDN at startup:

| Library | Source | Purpose |
|---------|--------|---------|
| Three.js r158 | `unpkg.com` | 3D rendering engine (WebGL abstraction) |
| Three.js Addons | `unpkg.com` | Loaders for GLB, OBJ, STL, PLY, FBX |
These are well-maintained, widely audited open-source libraries. 

### Content Security
The viewer does not execute any code embedded in model files. 3D formats like GLB/GLTF can technically reference external URLs — Three.js's loaders will attempt to resolve these if present. In practice, most model files from standard 3D software (Blender, Maya, etc.) do not include remote references. If you are working with untrusted model files from unknown sources, review the file contents before loading. 

---

## Credits

### Created By
Drew Medina
https://drewmedina.com/
Coded in Claude Ai, hope it works well for you!  I couldn't find a model viewr for this monitor so just tried making one. -Drew

### Powered By Open Source

| Project | License | Link |
|---------|---------|------|
| **Three.js** r158 | MIT | [threejs.org](https://threejs.org/) |
| Three.js GLTFLoader | MIT | Included with Three.js |
| Three.js OBJLoader | MIT | Included with Three.js |
| Three.js STLLoader | MIT | Included with Three.js |
| Three.js PLYLoader | MIT | Included with Three.js |
| Three.js FBXLoader | MIT | Included with Three.js |

Three.js is copyright © 2010–2024 three.js authors, released under the [MIT License](https://github.com/mrdoob/three.js/blob/dev/LICENSE).

### Rendering Technology
WebGL via Three.js with ACES Filmic tone mapping, PCF soft shadow maps, and SRGBColorSpace output encoding.

### Stereo Rendering
Side-by-side stereo uses a toe-in camera rig with configurable eye separation and convergence distance.

---

## License

SculptView3D is released as **freeware**. You may use it freely for personal and commercial projects. You may not sell it as a standalone product or remove the author credit. Use at your own risk. 

---

*SculptView3D v1.0 · c. 2026 Drew Medina · freeware*  MIT license  free to use, modify... 
