# Empire Worlds Assets

This directory contains assets for the four independent Empire worlds.

## Structure

Each Empire world has its own subdirectory:
```
Empire Worlds/
├── Empire1/
├── Empire2/
├── Empire3/
└── Empire4/
```

## Per-Empire Organization

Each Empire folder should contain:
```
EmpireX/
├── Models/          # 3D models specific to this empire
├── Textures/        # Texture atlases for this empire
├── Materials/       # Materials using empire textures
├── Prefabs/         # Empire-specific prefabs
├── Audio/           # Sound effects and music
└── README.md        # Empire-specific documentation
```

## Empire Budget (Each)

**Target Filesize**: 40-50 MB per empire  
**Polygon Budget**: 200,000-250,000 triangles  
**Texture Budget**: 8-12 atlases at 2048x2048

## Empire Design Framework

Each empire world should:

### 1. Self-Contained Narrative
- Complete story arc within the world
- Internal branching and choices
- Narrative closure/resolution
- No dependencies on other empires

### 2. Thematic Differentiation
- Distinct visual language
- Unique environmental storytelling
- Different gameplay mechanics
- Varied atmosphere and tone

### 3. Gameplay Systems
- Portal entry/exit points
- Internal teleportation waypoints
- Quest/progression tracking
- State persistence
- Conditional access areas

### 4. Performance Optimization
- Efficient LOD systems
- Occlusion culling
- Texture compression
- Minimal dynamic objects
- Mobile VR compatibility

## Empire Themes (To Be Defined)

### Empire 1: [Theme TBD]
Description: _Define the political, environmental, or cultural context_

Visual Language: _Color palette, architectural style, key elements_

Gameplay Focus: _Primary mechanics or narrative approach_

### Empire 2: [Theme TBD]
Description: _Define the political, environmental, or cultural context_

Visual Language: _Color palette, architectural style, key elements_

Gameplay Focus: _Primary mechanics or narrative approach_

### Empire 3: [Theme TBD]
Description: _Define the political, environmental, or cultural context_

Visual Language: _Color palette, architectural style, key elements_

Gameplay Focus: _Primary mechanics or narrative approach_

### Empire 4: [Theme TBD]
Description: _Define the political, environmental, or cultural context_

Visual Language: _Color palette, architectural style, key elements_

Gameplay Focus: _Primary mechanics or narrative approach_

## Asset Sharing Strategy

### Shared Resources
Some assets can be shared across empires to save space:
- Base material libraries
- Common architectural elements (with variations)
- Standard UI elements
- Generic audio effects

Store shared resources in parent directories:
- `/Assets/Materials/` for shared materials
- `/Assets/Textures/` for shared textures
- `/Assets/Prefabs/` for shared prefabs

### Empire-Unique Resources
Each empire needs unique:
- Environment models
- Thematic textures
- Special prefabs
- Empire-specific scripts
- Unique audio/music

## Development Workflow

### Adding a New Empire

1. Create empire folder structure
2. Define theme and visual language
3. Create asset budget tracking spreadsheet
4. Build basic geometry and layout
5. Implement portal entry/exit
6. Add internal navigation system
7. Implement narrative elements
8. Optimize and test
9. Link from Matt's Lair hub

### Testing Each Empire

- [ ] Loads independently
- [ ] Portal entry works from hub
- [ ] Exit/return to hub works
- [ ] Filesize under 50 MB
- [ ] Performance acceptable
- [ ] Narrative complete
- [ ] VRChat SDK validation passes

## Optimization Guidelines

### Texture Management
- Use texture atlases (combine multiple textures)
- Compress with BC7 format
- Use mipmaps
- Minimize unique textures
- Target 2048x2048 max resolution

### Model Optimization
- Keep polygon counts reasonable
- Use LOD systems
- Bake lighting when possible
- Combine meshes where appropriate
- Remove hidden faces

### Material Optimization
- Minimize material count
- Use instanced materials
- Avoid expensive shaders
- Test on mobile VR

### Audio Optimization
- Compress audio files
- Use spatial audio efficiently
- Limit concurrent audio sources
- Stream long audio when possible

## Cross-Empire Considerations

### State Persistence
If implementing cross-empire progression:
- Use VRChat PlayerData
- Sync critical state variables
- Handle edge cases (player leaves/rejoins)
- Test state persistence

### Visual Consistency
While thematically distinct, maintain:
- Consistent UI style
- Similar control schemes
- Comparable quality levels
- Unified art direction philosophy

### Performance Parity
All empires should:
- Load in similar timeframes
- Maintain similar framerates
- Use similar optimization techniques
- Target same VR hardware specs

## References

See main Game Design Document for:
- Detailed empire specifications
- Narrative architecture
- Systems design
- Implementation roadmap

Path: `Matt's Lair GDD 01-04-26/Matt's Lair GDD 01-04-26.md`
