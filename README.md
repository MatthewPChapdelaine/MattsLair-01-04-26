# Matt's Lair - VRChat World Project

A hub-and-spoke narrative world design for VRChat featuring Matt's Lair central hub and four independent Empire worlds.

## Project Overview

This project implements a proven 30-year-old design pattern from 1995 QBasic-based "Choose Your Own Adventure" interactive fiction into immersive 3D VRChat space. The experience centers on a central navigation hub (Matt's Lair) that provides access to four independent Empire worlds.

## Unity Version

This project uses **Unity 2022.3.22f1** - the officially supported version for VRChat SDK3 Worlds.

## VRChat Creator Companion Compatibility

This project is configured to work seamlessly with VRChat Creator Companion (VCC). The repository includes all necessary configuration files to be recognized as a VRChat World project.

### Setting Up with VRChat Creator Companion

1. **Install VRChat Creator Companion**
   - Download from: https://vrchat.com/home/download
   - Follow the installation instructions for your platform

2. **Add This Project to VCC**
   - Open VRChat Creator Companion
   - Click "Add Existing Project"
   - Navigate to this repository folder
   - VCC will automatically detect the project configuration

3. **Install VRChat SDK**
   - VCC will prompt you to install the VRChat Worlds SDK
   - Click "Install" to add the latest compatible SDK version
   - VCC will handle all dependencies automatically

4. **Open in Unity**
   - Once the SDK is installed, click "Open Project" in VCC
   - Unity 2022.3.22f1 will launch with the project

## Project Structure

```
MattsLair-01-04-26/
├── Assets/
│   ├── Scenes/
│   │   └── MattsLair.unity          # Main hub scene
│   ├── Scripts/                     # C#/UdonSharp scripts
│   ├── Prefabs/                     # Reusable game objects
│   ├── Materials/                   # Shared materials
│   ├── Textures/                    # Texture atlases
│   ├── Matt's Lair/                 # Central hub assets
│   └── Empire Worlds/               # Empire-specific assets
├── Packages/
│   ├── manifest.json                # Package dependencies
│   ├── packages-lock.json           # Resolved package versions
│   └── vpm-manifest.json            # VCC-specific configuration
├── ProjectSettings/                 # Unity project settings
└── Matt's Lair GDD 01-04-26/        # Design documentation
    └── Matt's Lair GDD 01-04-26.md  # Complete game design doc
```

## VRChat Configuration

### Package Dependencies

The project is configured with the following VRChat packages:
- `com.vrchat.worlds` - VRChat Worlds SDK (v3.7.4)
- `com.vrchat.base` - VRChat Base SDK (v3.7.4)
- `com.vrchat.core.vpm-resolver` - VPM Resolver (v0.1.28)

These are managed by VCC and will be automatically installed when you add the project.

### Layer Configuration

The project includes VRChat-standard layer configuration:
- Layer 8: Interactive
- Layer 9: Player
- Layer 10: PlayerLocal
- Layer 11: Environment
- Layer 12: UiMenu
- Layer 13: Pickup
- Layer 14: PickupNoEnvironment
- Layer 15: StereoLeft
- Layer 16: StereoRight
- Layer 17: Walkthrough
- Layer 18: MirrorReflection

## Architecture

### Hub-and-Spoke Design

- **Matt's Lair (Central Hub)**: 20-30 MB
  - Primary navigation node
  - Four portal entrances to Empire worlds
  - Minimal geometry for fast loading
  
- **Four Empire Worlds**: 40-50 MB each
  - Independent, self-contained narratives
  - Separate world files for parallel development
  - Thematically distinct environments

### Navigation System

- **Primary**: VRChat portal system for world transitions
- **Secondary**: Teleportation for intra-world movement
- **Approach**: Portals as primitive bytecode, higher-level gameplay layered on top

## Optimization Targets

- **Total Project Size**: Under 200 MB
- **Per-World Allocation**:
  - Matt's Lair: 25-30 MB
  - Each Empire World: 40-50 MB
- **Polygon Budget**:
  - Matt's Lair: 50,000-75,000 triangles
  - Each Empire World: 200,000-250,000 triangles

## Development Workflow

### Phase 1: Foundation (Current)
✓ Project structure created
✓ VCC compatibility configured
✓ Unity version specified
✓ Basic scene created
- [ ] Portal placement in Matt's Lair
- [ ] Establish asset libraries

### Phase 2: Empire Architecture
- [ ] Build Empire World 1 foundation
- [ ] Implement portal system
- [ ] Test state persistence

### Phase 3: Empire Worlds
- [ ] Complete Empires 2-4
- [ ] Environmental narrative elements
- [ ] Quest/progression systems

### Phase 4: Integration & Polish
- [ ] End-to-end testing
- [ ] Optimization pass
- [ ] Player testing

## Building for VRChat

1. Open the project in Unity via VCC
2. Navigate to VRChat SDK > Show Control Panel
3. Select the scene you want to build (MattsLair.unity for hub)
4. Click "Build & Test" to test locally
5. Click "Build & Publish" when ready to upload

## Design Philosophy

This project follows a layered architecture:

**Primitive Layer (Bytecode)**:
- Portal mechanics (world transitions)
- Teleportation (spatial navigation)
- Spawn point management

**Mid-Level Layer (Game Logic)**:
- Conditional access systems
- Narrative branching
- State persistence

**High-Level Layer (Player Experience)**:
- Emergent storytelling
- Environmental narrative
- Consequence-driven gameplay

## Contributing

When contributing to this project:
1. Maintain the 200 MB total filesize constraint
2. Follow VRChat optimization best practices
3. Test all changes with VCC before committing
4. Update documentation for significant architectural changes

## Resources

- **Design Document**: `Matt's Lair GDD 01-04-26/Matt's Lair GDD 01-04-26.md`
- **VRChat Documentation**: https://docs.vrchat.com/
- **VRChat Creator Companion**: https://vcc.docs.vrchat.com/
- **Unity Documentation**: https://docs.unity3d.com/2022.3/Documentation/Manual/

## License

See LICENSE file for details.

## Contact

For questions or issues regarding this project, please open an issue on GitHub.
