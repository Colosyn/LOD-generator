Batch LOD generation and FBX export for Unreal Engine and Unity pipelines, built for game artists.
 
---
 
## What's New in v1.4.0
 
- Renamed add-on to **LOD Architect Lite**
- Replaced Unreal/Unity toggle with a **Target Engine dropdown** (Unreal / Unity)
- Fixed: Hidden child objects are now automatically unhidden before export
See [CHANGELOG.md](CHANGELOG.md) for full version history.
 
---
 
## Lite vs Pro
 
| Feature | Lite | Pro |
|---|---|---|
| Target Engines | Unreal, Unity | Unreal, Unity, Godot |
| Export Formats | FBX | FBX, OBJ, GLTF/GLB |
| Non-Destructive Workflow | ✅ | ✅ |
| LOD Inspector | ❌ | ✅ Live stats per LOD |
| Decimate LOD0 | ❌ | ✅ |
| Optimization Modes | Decimate only | Collapse + Planar |
| Pivot Tools | ❌ | ✅ Move to Center / Bottom |
| UV Preservation | Basic | ✅ Strict preservation |
| Normal Processing | Basic | ✅ Weighted Normals or Data Transfer |
| Workflow Presets | ❌ | ✅ Built-in presets |
 
---
upgrade to [LOD Architect](https://colosyn.gumroad.com/l/lod-architect)

 
## Features
 
- Generate LOD0 through LOD6 in one click for any number of selected meshes
- Non-destructive — Decimate modifier stays live for per-LOD tweaking after generation
- **Target Engine dropdown** — select Unreal or Unity for automated FBX settings per engine
- Unreal Engine mode — correct FBX axis, LodGroup empty, SM_ prefix, custom properties
- Unity mode — correct FBX axis and smoothing for Unity imports
- Per-LOD geometry percentage sliders
- Batch export — export selected LOD groups or all groups at once
- Optional per-asset folder creation on export
- Source mesh preserved and organized automatically
- High poly detection — confirmation popup before generating on meshes above a configurable polygon threshold
- Merge vertices (configurable distance), apply transforms, and transfer normals options for pre-generation cleanup
---
 
## Requirements
 
- Blender 3.6 LTS or newer (3.6 LTS, 4.2 LTS, 4.4, 4.5, 5.1 tested)
- FBX export addon enabled (bundled with Blender by default)
---
 
## Installation
 
1. Download `LOD_Architect_lite.py`
2. In Blender go to `Edit > Preferences > Add-ons > Install`
3. Select the downloaded file
4. Enable the addon — search for **LOD Architect**
The panel appears in `View3D > Sidebar > LOD Arch`
 
---
 
## Usage
 
### Generate LODs
 
1. Select one or more mesh objects
2. Set number of LODs and geometry percentage per level
3. Choose your **Target Engine** from the dropdown (Unreal / Unity)
4. Click **Generate LODs**
Each mesh gets:
- An empty parent named after the original mesh (used as FBX filename)
- LOD0 (full resolution copy)
- LOD1 through LODn with live Decimate modifiers
- Original mesh moved to a hidden **source** collection for reference
> **Tip:** Set your object's origin to the desired pivot point before generating. The tool respects artist-placed origins and does not reset them.
 
> **Note:** Objects with zero geometry are skipped with a warning. Objects named `_LOD`, `_Source`, or `_HIGH` are automatically skipped.
 
### Export LODs
 
1. Set the export folder path in the Export panel
2. Select LOD groups to export, or deselect all to export everything in the LOD collection
3. Click **Export LODs**
> **Note:** Empties with no LOD children will be skipped with a warning during export.
 
---
 
## Known Limitations
 
- LOD groups must remain in the **LOD** collection — moving empties or meshes outside this collection will exclude them from export
- Objects named `_HIGH` are skipped during generation — rename to generate LODs on high poly meshes intentionally
- Existing modifiers on source meshes carry over to all LOD levels and will be applied on export alongside the Decimate modifier
- `SM_` prefix handling only applies in Unreal mode
- On Blender 3.6 LTS, confirmation popups display a single button instead of OK/Cancel — click outside the popup to cancel
---
 
## License
 
MIT — free to use, modify, and distribute.
 
---
 
Made by [Colosyn](https://colosyn.com)
