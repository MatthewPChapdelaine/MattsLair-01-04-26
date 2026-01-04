# Matt's Lair - Project Structure

This document outlines the organization of the Matt's Lair VRChat World project.

## Directory Structure

### `/Assets/`
Main Unity assets directory containing all project resources.

#### `/Assets/Scenes/`
Contains Unity scene files for the world.
- `MattsLair.unity` - Central hub scene (main starting point)
- Future: `Empire1.unity`, `Empire2.unity`, `Empire3.unity`, `Empire4.unity`

#### `/Assets/Scripts/`
C# and UdonSharp scripts for world functionality.
- Portal management scripts
- Teleportation systems
- State persistence logic
- Conditional access systems

#### `/Assets/Prefabs/`
Reusable game objects and prefabs.
- Portal prefabs
- Teleportation point prefabs
- UI elements
- Environmental objects

#### `/Assets/Materials/`
Shared materials library.
- Optimized materials for performance
- Thematically appropriate variations
- Shared across all worlds for consistency

#### `/Assets/Textures/`
Texture assets.
- Texture atlases (2048x2048)
- Compressed formats (DXT5/BC7)
- Organized by world/theme

#### `/Assets/Matt's Lair/`
Assets specific to the central hub world.
- Hub architecture models
- Portal frames
- Navigation markers
- Hub-specific materials

#### `/Assets/Empire Worlds/`
Assets for the four empire worlds.
- Organized by empire (Empire1/, Empire2/, etc.)
- Each empire folder contains:
  - Models/
  - Textures/
  - Materials/
  - Prefabs/

### `/Packages/`
Unity Package Manager configuration.
- `manifest.json` - Package dependencies including VRChat SDK
- `packages-lock.json` - Resolved package versions
- `vpm-manifest.json` - VRChat Creator Companion specific configuration

### `/ProjectSettings/`
Unity project configuration files.
- `ProjectSettings.asset` - Main project settings
- `TagManager.asset` - VRChat-compatible layer configuration
- `ProjectVersion.txt` - Unity version (2022.3.22f1)
- Other Unity configuration files

### `/UserSettings/`
User-specific Unity editor settings (not tracked in git).

## Asset Organization Principles

### Filesize Budget
- **Matt's Lair Hub**: 25-30 MB
- **Each Empire World**: 40-50 MB
- **Total Target**: Under 200 MB

### Polygon Budget
- **Matt's Lair Hub**: 50,000-75,000 triangles
- **Each Empire World**: 200,000-250,000 triangles

### Texture Budget
- **Matt's Lair Hub**: 4-6 atlases at 2048x2048
- **Each Empire World**: 8-12 atlases at 2048x2048

## VRChat Integration

### Required Components
Every VRChat world must include:
1. VRC_SceneDescriptor component
2. At least one VRC_SpatialAudioSource or AudioSource
3. Spawn points (VRCWorldStart)
4. Post-processing volume (recommended)

### Layers
VRChat uses specific layer assignments (configured in TagManager.asset):
- Layer 8: Interactive
- Layer 9: Player
- Layer 10: PlayerLocal
- Layer 11: Environment
- Layer 12: UiMenu
- Layer 13: Pickup
- Layer 14: PickupNoEnvironment
- Layer 15-18: Reserved for VRChat systems

## Development Workflow

### Adding New Empire Worlds
1. Create new scene in `/Assets/Scenes/`
2. Create corresponding asset folder in `/Assets/Empire Worlds/`
3. Add VRC_SceneDescriptor to scene
4. Configure spawn points
5. Add to Build Settings
6. Link portal in Matt's Lair hub

### Asset Import Guidelines
1. **Models**: Import as FBX, optimize for VRChat
2. **Textures**: Compress with BC7 for best quality/size ratio
3. **Materials**: Use VRChat-compatible shaders
4. **Audio**: Use compressed formats, monitor filesize

### Testing Checklist
- [ ] Scene loads in VRChat SDK Control Panel
- [ ] Spawn points functional
- [ ] Portals link correctly
- [ ] Filesize within budget
- [ ] No VRChat SDK validation errors
- [ ] Performance metrics acceptable

## VRChat Creator Companion Integration

This project is designed to work with VCC:
1. Project includes `vpm-manifest.json` for VCC recognition
2. VRChat SDK dependencies managed through `manifest.json`
3. Scoped registry configured for VRChat packages
4. Unity version locked to 2022.3.22f1

## Next Steps

1. Install VRChat SDK3 Worlds via VCC
2. Set up VRC_SceneDescriptor in MattsLair.unity
3. Create portal prefabs
4. Implement teleportation system
5. Begin Empire World 1 development
