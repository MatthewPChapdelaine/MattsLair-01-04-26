# VRChat World Development Quick Reference

Essential information for developing Matt's Lair VRChat World.

## Unity Version Requirement

**CRITICAL**: Must use Unity **2022.3.22f1** (LTS)
- This is the ONLY supported version for VRChat SDK3
- Other versions will NOT work with VRChat
- Install via Unity Hub Archives section

## VRChat SDK Requirements

### Required Components Per Scene

Every VRChat world scene MUST have:

1. **VRC_SceneDescriptor** component
   - Add to empty GameObject in scene root
   - Required for VRChat to recognize the scene as a world
   - Configure spawn points, respawn height, reference camera

2. **At least one Spawn Point**
   - VRCWorldStart component or VRC_SceneDescriptor spawn
   - Where players appear when entering world
   - Should be clearly visible, safe location

3. **Reference Camera** (optional but recommended)
   - Used for thumbnails
   - Position for best representative view
   - Assign in VRC_SceneDescriptor

### VRChat Layers (Required)

Unity layers 8-22 are reserved for VRChat:
- **Layer 8**: Interactive
- **Layer 9**: Player
- **Layer 10**: PlayerLocal
- **Layer 11**: Environment
- **Layer 12**: UiMenu
- **Layer 13**: Pickup
- **Layer 14**: PickupNoEnvironment
- **Layer 15**: StereoLeft
- **Layer 16**: StereoRight
- **Layer 17**: Walkthrough
- **Layer 18**: MirrorReflection
- **Layers 19-22**: Reserved (future use)

DO NOT use these layers for other purposes!

## VRChat Optimization Guidelines

### Performance Ranks

VRChat assigns performance ranks to worlds:
- **Excellent**: Green (best)
- **Good**: Green
- **Medium**: Yellow (acceptable)
- **Poor**: Orange (degraded experience)
- **Very Poor**: Red (major issues)

Target: **Medium** or better (ideally Good/Excellent)

### Critical Metrics

**Draw Calls**: < 100 (ideally < 50)
**Material Count**: < 50
**Mesh Renderer Count**: < 200
**Particle System Count**: < 10
**Polygon Count**: Varies by world size
- Matt's Lair Hub: 50k-75k triangles
- Empire Worlds: 200k-250k triangles each

**Texture Memory**: < 100 MB
**Mesh Memory**: < 50 MB
**Overall Download Size**: Target < 200 MB total

### Mobile Quest Considerations

If targeting Quest (optional for this project):
- Even stricter polygon limits
- No post-processing effects
- Simpler shaders required
- More aggressive texture compression
- Quest-compatible materials only

For PC-only worlds, Quest support is optional.

## Scripting with Udon/UdonSharp

### Udon Basics

VRChat uses **Udon** for scripting:
- NOT standard C# (significant differences)
- Limited standard library
- Sandboxed execution
- Network-aware by design

### UdonSharp (Recommended)

**UdonSharp (U#)** is C#-like syntax that compiles to Udon:
- More familiar to Unity developers
- Easier to write and maintain
- Still has Udon limitations
- Must be SDK-compatible

Install via VCC after adding project.

### Key Limitations

1. **No reflection**: Can't use reflection APIs
2. **Limited types**: Not all C# types available
3. **No threading**: Single-threaded execution
4. **Network sync required**: For multiplayer state
5. **Performance sensitive**: Runs on all clients

### Networking in Udon

For synced behavior:
```csharp
[UdonSynced] public float syncedValue;
```

For ownership:
```csharp
Networking.SetOwner(Networking.LocalPlayer, gameObject);
```

For events:
```csharp
public override void OnPlayerJoined(VRCPlayerApi player) { }
```

## Portals in VRChat

### Portal Types

1. **World Portals**: Link to other VRChat worlds
   - Use VRC_PortalMarker component
   - Set target world ID (after publishing)
   - Can be permanent or triggered

2. **Scene Portals**: Within same Unity project
   - NOT standard for VRChat
   - Each "world" is separate Unity scene uploaded separately
   - Use world portals to link between scenes

### Matt's Lair Portal Architecture

For this project:
1. Matt's Lair hub = One VRChat world
2. Empire 1 = Separate VRChat world
3. Empire 2 = Separate VRChat world
4. Empire 3 = Separate VRChat world
5. Empire 4 = Separate VRChat world

Link them using VRC_PortalMarker after each is published.

## Building & Testing

### Local Testing

1. VRChat SDK > Show Control Panel
2. Builder tab
3. **Build & Test** button
4. VRChat launches with your world
5. Iterate quickly

### Publishing

1. **Build & Publish** in SDK Control Panel
2. Login with VRChat account
3. Configure world details:
   - World name
   - Description
   - Tags
   - Thumbnail
   - Capacity
4. Upload to VRChat
5. World is private by default
6. Share via world ID for testing
7. Set public when ready

### World IDs

After publishing, note the World ID:
- Format: `wrld_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`
- Use these IDs in portal markers
- Save these IDs for linking worlds

## Common Issues & Solutions

### "SDK Not Found"
- Install via VRChat Creator Companion
- Ensure project added to VCC first
- Restart Unity after installation

### "Validation Errors"
- Check VRChat SDK Control Panel
- Address each validation issue
- Most common: Missing VRC_SceneDescriptor
- Layer misconfigurations

### "Build Failed"
- Check Console for errors
- Ensure no compile errors
- Verify all assets are valid
- Check for missing dependencies

### "Performance Issues"
- Use VRChat SDK stats window
- Enable Stats in Control Panel
- Reduce draw calls first
- Optimize textures next
- Use occlusion culling

### "Portals Not Working"
- Ensure target world is published
- Verify World ID is correct
- Check portal placement
- Test collision/trigger setup

## Resources

### Essential Documentation
- **VRChat Docs**: https://docs.vrchat.com/
- **Udon Documentation**: https://docs.vrchat.com/docs/udon
- **UdonSharp GitHub**: https://github.com/vrchat-community/UdonSharp
- **Creator Companion**: https://vcc.docs.vrchat.com/

### Community Resources
- **VRChat Discord**: https://discord.gg/vrchat (Creator channels)
- **VRChat Forum**: https://ask.vrchat.com/
- **SDK Examples**: Included with VRChat SDK

### Optimization Tools
- **Occlusion Culling**: Unity built-in
- **Texture Compression**: BC7 format recommended
- **Profiler**: Unity Profiler for performance analysis
- **SDK Stats**: VRChat SDK Control Panel stats view

## Quick Checklist for Each World

Before publishing any world:
- [ ] VRC_SceneDescriptor present
- [ ] Spawn points configured
- [ ] Reference camera positioned
- [ ] Layers correctly assigned
- [ ] No SDK validation errors
- [ ] Performance rank acceptable
- [ ] Tested locally in VRChat client
- [ ] World name/description ready
- [ ] Thumbnail captured
- [ ] Filesize under target

## Development Tips

1. **Test early, test often**: Use Build & Test frequently
2. **Profile regularly**: Check performance as you build
3. **Save World IDs**: Track published world IDs in project notes
4. **Version control**: Commit working versions regularly
5. **Backup scenes**: Before major changes
6. **Read SDK logs**: Check for warnings/errors
7. **Join community**: VRChat Discord has helpful creators
8. **Study examples**: VRChat SDK includes example worlds

---

**Remember**: VRChat development differs from standard Unity. When in doubt, consult VRChat documentation and test in the actual VRChat client!
