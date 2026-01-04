# Matt's Lair Development Roadmap

Detailed implementation plan based on the Game Design Document.

## Current Status: Phase 1 - Foundation

✅ **Completed**:
- Project structure created
- Unity 2022.3.22f1 configuration
- VRChat Creator Companion compatibility
- Basic asset organization
- Documentation framework
- .gitignore configuration
- Base scene (MattsLair.unity)

## Phase 1: Foundation (Weeks 1-2)

### Week 1: VCC Setup & Hub Structure
- [x] Create Unity project structure
- [x] Configure VCC compatibility
- [x] Set up version control
- [ ] Install VRChat SDK via VCC (user action)
- [ ] Add VRC_SceneDescriptor to MattsLair.unity
- [ ] Configure spawn points
- [ ] Set up reference camera

### Week 2: Asset Library & Portal Framework
- [ ] Create shared material library
- [ ] Design portal frame base model (low poly)
- [ ] Create 4 portal frame variants (one per empire)
- [ ] Build basic hub geometry
- [ ] Implement lighting rig
- [ ] Set up filesize tracking system

**Deliverable**: Functional Matt's Lair hub with 4 portal frames, ready for scripting

## Phase 2: Empire Architecture (Weeks 3-6)

### Week 3: Empire 1 Foundation
- [ ] Define Empire 1 theme
- [ ] Create Empire 1 scene
- [ ] Add VRC_SceneDescriptor to Empire 1
- [ ] Build basic environment layout
- [ ] Set up spawn point in Empire 1
- [ ] Configure exit portal back to hub

### Week 4: Portal System Implementation
- [ ] Publish Matt's Lair hub to VRChat (test upload)
- [ ] Publish Empire 1 to VRChat (test upload)
- [ ] Configure portal in hub to link to Empire 1
- [ ] Configure return portal in Empire 1 to hub
- [ ] Test portal navigation both directions
- [ ] Document World IDs for linking

### Week 5: Teleportation Primitives
- [ ] Create teleportation trigger prefab
- [ ] Create spawn point prefab
- [ ] Implement basic teleport script (UdonSharp)
- [ ] Test intra-world teleportation
- [ ] Add teleportation to Empire 1
- [ ] Optimize teleportation performance

### Week 6: State Persistence
- [ ] Design state persistence system
- [ ] Implement player data tracking (UdonSharp)
- [ ] Test state persistence across portals
- [ ] Implement basic choice tracking
- [ ] Test multiplayer state sync
- [ ] Document state system for other empires

**Deliverable**: Working hub with portal to Empire 1, full bidirectional navigation, basic teleportation and state tracking

## Phase 3: Empire Worlds (Weeks 7-12)

### Weeks 7-8: Empire 2 Development
- [ ] Define Empire 2 theme (distinct from Empire 1)
- [ ] Create Empire 2 scene
- [ ] Build environment and layout
- [ ] Implement portal system
- [ ] Add internal teleportation
- [ ] Create empire-specific narrative elements
- [ ] Test and optimize
- [ ] Publish and link to hub

### Weeks 9-10: Empire 3 Development
- [ ] Define Empire 3 theme
- [ ] Create Empire 3 scene
- [ ] Build environment and layout
- [ ] Implement portal system
- [ ] Add internal teleportation
- [ ] Create empire-specific narrative elements
- [ ] Test and optimize
- [ ] Publish and link to hub

### Weeks 11-12: Empire 4 Development
- [ ] Define Empire 4 theme
- [ ] Create Empire 4 scene
- [ ] Build environment and layout
- [ ] Implement portal system
- [ ] Add internal teleportation
- [ ] Create empire-specific narrative elements
- [ ] Test and optimize
- [ ] Publish and link to hub

**Deliverable**: All four Empire worlds accessible from Matt's Lair hub, each with unique theme and functional portal system

## Phase 4: Integration & Polish (Weeks 13-16)

### Week 13: Conditional Access & Waypoints
- [ ] Implement conditional portal access system
- [ ] Add locked portal states
- [ ] Create waypoint/checkpoint system
- [ ] Implement multi-step narrative sequences
- [ ] Test progression logic
- [ ] Add visual feedback for locked/unlocked portals

### Week 14: Environmental Narrative
- [ ] Add environmental storytelling to all empires
- [ ] Create information panels/displays
- [ ] Implement quest tracking UI
- [ ] Add atmospheric elements
- [ ] Polish visual narrative
- [ ] Test narrative clarity

### Week 15: Optimization Pass
- [ ] Audit filesize for all worlds
- [ ] Optimize textures and materials
- [ ] Implement LOD systems
- [ ] Set up occlusion culling
- [ ] Reduce draw calls
- [ ] Test performance on target hardware
- [ ] Achieve Medium or better performance rank

### Week 16: End-to-End Testing
- [ ] Test all portal transitions
- [ ] Test all teleportation points
- [ ] Verify state persistence
- [ ] Test multiplayer scenarios
- [ ] Check narrative completeness
- [ ] Fix critical bugs
- [ ] Gather internal feedback

**Deliverable**: Fully integrated, optimized experience with complete narrative paths

## Phase 5: Deployment & Support (Weeks 17+)

### Week 17: Player Testing
- [ ] Recruit player testers
- [ ] Run guided test sessions
- [ ] Collect feedback
- [ ] Document issues
- [ ] Prioritize fixes
- [ ] Implement critical fixes

### Week 18: Final Polish
- [ ] Address player feedback
- [ ] Final optimization pass
- [ ] Update world descriptions
- [ ] Create promotional materials
- [ ] Prepare thumbnails for all worlds
- [ ] Write player-facing documentation

### Week 19: Public Launch
- [ ] Set all worlds to public
- [ ] Announce launch
- [ ] Monitor for issues
- [ ] Respond to player feedback
- [ ] Track performance metrics
- [ ] Plan updates based on feedback

### Ongoing: Post-Launch Support
- [ ] Monitor player behavior and feedback
- [ ] Patch critical bugs
- [ ] Iterate on narrative elements
- [ ] Optimize based on performance data
- [ ] Plan expansions (Empire 5+)
- [ ] Update documentation

## Budget Tracking

### Filesize Targets
- **Matt's Lair**: 25-30 MB (Current: TBD)
- **Empire 1**: 40-50 MB (Current: N/A)
- **Empire 2**: 40-50 MB (Current: N/A)
- **Empire 3**: 40-50 MB (Current: N/A)
- **Empire 4**: 40-50 MB (Current: N/A)
- **Total Target**: < 200 MB

Track actual filesizes in this section as development progresses.

### Performance Targets
- **VRChat Performance Rank**: Medium or better
- **Draw Calls**: < 100 (< 50 ideal)
- **Load Time**: < 30 seconds per world

## Success Metrics

### Technical Success
- [ ] All worlds under filesize budget
- [ ] Load times under 30 seconds
- [ ] No critical performance issues
- [ ] Stable networked state persistence
- [ ] VRChat SDK validation passes (all worlds)

### Design Success
- [ ] Clear navigation paths
- [ ] Intuitive portal system
- [ ] Player engagement with 3+ empires per session
- [ ] Positive feedback on narrative clarity

### Content Success
- [ ] Each empire delivers 30-45 min content
- [ ] Multiple playthroughs reveal different perspectives
- [ ] Environmental storytelling effective
- [ ] Narrative closure achieved

## Risk Management

### Identified Risks
1. **Filesize overrun**: Aggressive optimization required
2. **Performance issues**: Mobile VR constraints
3. **VRChat SDK changes**: Platform updates may break features
4. **State persistence complexity**: Networked state challenging
5. **Scope creep**: Four empires is substantial

### Mitigation Strategies
1. Regular filesize audits, texture compression
2. Early performance testing, LOD implementation
3. Follow VRChat SDK update notes, test after updates
4. Start simple with state, add complexity gradually
5. Strict scope control, focus on core experience

## Dependencies

### External Dependencies
- VRChat platform stability
- VRChat Creator Companion updates
- Unity 2022.3 LTS support
- UdonSharp community maintenance

### Internal Dependencies
- Portal system must work before Empire development
- State persistence before advanced narrative
- Hub complete before Empire linking
- Testing infrastructure before player testing

## Next Immediate Actions

1. **Install VRChat SDK** via VRChat Creator Companion
2. **Add VRC_SceneDescriptor** to MattsLair.unity scene
3. **Configure spawn points** in Matt's Lair hub
4. **Begin hub geometry** modeling or asset sourcing
5. **Create portal frame concept** (low poly base)

---

**Note**: This roadmap is a living document. Update as development progresses and priorities shift. Track actual progress in the GitHub project board or issues.
