# Scripts Directory

This directory contains C# and UdonSharp scripts for Matt's Lair VRChat World.

## Organization

Scripts should be organized by functionality:

### `/Scripts/Portal/`
Portal management and navigation scripts.
- Portal activation/deactivation
- Portal visual effects
- Portal state management

### `/Scripts/Teleportation/`
Teleportation system scripts.
- Teleport triggers
- Spawn point management
- Conditional teleportation logic

### `/Scripts/State/`
State persistence and tracking scripts.
- Player progress tracking
- Choice history
- Cross-world state management

### `/Scripts/UI/`
User interface scripts.
- Information displays
- Navigation hints
- Quest logs

### `/Scripts/Empire/`
Empire-specific gameplay scripts.
- Empire 1-4 specific logic
- Narrative branching
- Quest systems

## UdonSharp

VRChat worlds use UdonSharp (U#) for scripting, which is a C#-like language that compiles to Udon.

Key differences from standard C#:
- Limited standard library
- Networking must use VRChat networking APIs
- Performance considerations are critical
- Must be VRChat SDK compatible

## Best Practices

1. **Keep scripts simple**: Udon has performance limitations
2. **Optimize networking**: Minimize synced variables
3. **Test frequently**: VRChat behavior can differ from Unity editor
4. **Comment thoroughly**: Help future developers understand VRChat-specific code
5. **Follow VRChat guidelines**: See https://docs.vrchat.com/docs/udon

## Getting Started

1. Install VRChat SDK via VCC
2. Enable UdonSharp in project
3. Create new U# scripts from Assets > Create > U# Script
4. Reference VRChat SDK documentation for APIs

## Resources

- UdonSharp GitHub: https://github.com/vrchat-community/UdonSharp
- VRChat Udon Documentation: https://docs.vrchat.com/docs/udon
- Example scripts: VRChat SDK includes example scenes
