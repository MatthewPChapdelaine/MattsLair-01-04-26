# Matt's Lair Hub Assets

This directory contains assets specific to the Matt's Lair central hub world.

## Purpose

Matt's Lair serves as the central navigation hub for the entire experience. This folder contains all unique assets for the hub that are NOT shared with the Empire worlds.

## Asset Budget

**Target Filesize**: 25-30 MB  
**Polygon Budget**: 50,000-75,000 triangles  
**Texture Budget**: 4-6 atlases at 2048x2048

## Asset Categories

### Architecture
Hub architectural elements:
- Central chamber geometry
- Portal alcoves/frames
- Floor, walls, ceiling
- Structural elements

Design principles:
- Minimal, functional architecture
- Clear navigation paths
- Emphasis on portal visibility
- Low polygon count

### Portals
Four portal systems for Empire worlds:
- Empire 1 portal (theme: TBD)
- Empire 2 portal (theme: TBD)
- Empire 3 portal (theme: TBD)
- Empire 4 portal (theme: TBD)

Each portal should:
- Be visually distinct
- Hint at destination theme
- Use consistent base structure
- Support activation states

### Materials
Hub-specific materials:
- Stone/metal base materials
- Portal effect materials
- Lighting materials
- UI materials

Optimization:
- Share base materials
- Use vertex colors for variation
- Minimize unique textures
- Compress all textures

### Lighting
Hub lighting setup:
- Ambient lighting
- Portal accent lights
- Navigation lighting
- Atmosphere lighting

Considerations:
- Baked lightmaps preferred
- Realtime lights minimal
- Mobile VR compatible
- Clear visibility priority

### UI Elements
Hub navigation aids:
- Portal labels/names
- Directional markers
- Information panels
- Empire descriptions

Design:
- Clear, readable text
- VR-friendly sizing
- Consistent style
- Minimal screen space

## Design Philosophy

The hub should be:
1. **Functional**: Easy navigation is priority #1
2. **Minimal**: Low complexity, fast loading
3. **Atmospheric**: Sets tone for experience
4. **Scalable**: Can add more portals if needed

Avoid:
- Excessive decoration
- Complex geometry
- Large textures
- Heavy particle effects
- Dense foliage

## Empire World Theming

Each portal should visually communicate the empire world theme:
- Color coding
- Architectural style hints
- Symbol/iconography
- Environmental effects

Examples:
- Industrial empire → Metal, gears, steam
- Natural empire → Vines, wood, organic
- Tech empire → Neon, circuits, holographic
- Ancient empire → Stone, runes, weathered

## Testing Checklist

- [ ] Loads within 30 seconds
- [ ] Under 30 MB filesize
- [ ] All portals visible from spawn
- [ ] Clear path to each portal
- [ ] No performance warnings
- [ ] VRChat SDK validation passes
- [ ] Mobile VR compatible

## Development Priority

Phase 1 (Current):
1. Basic hub geometry
2. Portal frames
3. Spawn point
4. Basic lighting

Phase 2:
1. Portal visual effects
2. Navigation markers
3. Information displays
4. Polish lighting

Phase 3:
1. Atmosphere details
2. Audio integration
3. Final optimization
4. User testing refinement
