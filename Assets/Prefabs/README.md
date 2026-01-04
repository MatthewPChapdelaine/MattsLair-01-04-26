# Prefabs Directory

This directory contains reusable Unity prefabs for Matt's Lair VRChat World.

## Prefab Categories

### Portal Prefabs
- **PortalFrame_Standard.prefab** - Standard portal frame for empire world entrances
- **PortalFrame_Active.prefab** - Activated portal with visual effects
- **PortalFrame_Locked.prefab** - Locked/inaccessible portal variant

### Teleportation Prefabs
- **TeleportPoint.prefab** - Basic teleportation destination marker
- **TeleportTrigger.prefab** - Trigger zone for teleportation
- **SpawnPoint.prefab** - Player spawn point prefab

### UI Prefabs
- **InfoPanel.prefab** - Information display panel
- **NavigationMarker.prefab** - Directional navigation markers
- **QuestTracker.prefab** - Quest/progress tracking UI

### Environment Prefabs
- **LightingRig.prefab** - Standardized lighting setup
- **AudioZone.prefab** - Spatial audio trigger zones
- **SafetyBarrier.prefab** - Invisible collision boundaries

## Creating Prefabs

1. Build GameObject in scene
2. Configure all components
3. Test functionality
4. Drag to Prefabs folder to create prefab
5. Test prefab instance in clean scene

## Prefab Best Practices

### Optimization
- Keep polygon count minimal
- Use efficient materials
- Limit dynamic components
- Consider mobile VR performance

### VRChat Compatibility
- Test with VRChat SDK validation
- Ensure networked components are configured
- Use VRChat-compatible shaders
- Respect layer assignments

### Reusability
- Make prefabs as generic as possible
- Use prefab variants for customization
- Document required setup steps
- Include example usage in scene

## Filesize Considerations

Each prefab should be optimized for filesize:
- Compress textures appropriately
- Minimize material count
- Use LOD when appropriate
- Share materials across prefabs

Target contribution to world filesize:
- Simple prefabs: < 0.5 MB
- Complex prefabs: < 2 MB
- Portal systems: < 3 MB

See PROJECT_STRUCTURE.md for overall budget details.
