# Changelog
## [1.4.0]
- Renamed add-on to LOD Architect Lite 
- Replaced Unreal toggle with a Target Engine dropdown (Unreal / Unity) 
- Fixed: Hidden child objects are now automatically unhidden before export
- 
## [1.3.0]
- Renamed `recalculate_normals` → `transfer_normals` (accurately reflects Data Transfer behavior)
- Merge distance is now a configurable property in the panel (range 0.00001–0.1, was hardcoded at 0.0001)
- Added `use_object_transform` to Data Transfer modifier for correct world-space normal projection

## [1.2.0]
- Added merge vertices option — removes duplicate verts on LOD0 before decimation
- Added apply scale & rotation option — applies transforms on LOD0 before generation
- Added recalculate normals option — transfers custom normals from LOD0 to all LOD levels via Data Transfer modifier (version-gated for Blender 3.6 compatibility)
- Fixed export collecting non-LOD empties and meshes with foreign parents into export set

## [1.1.0]
- Fixed FBX export failing with Blender-relative paths (//)
- Fixed export crash when destination folder doesn't exist
- Added validation for empty export path field

## [1.0.0]
- Initial release
