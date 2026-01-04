# VRChat Creator Companion Setup Guide

This guide will help you set up this Matt's Lair project with VRChat Creator Companion (VCC) for development.

## Prerequisites

### 1. Install Unity Hub
- Download Unity Hub from: https://unity.com/download
- Install Unity version **2022.3.22f1** (LTS)
  - This is the only supported version for VRChat SDK3
  - In Unity Hub, go to Installs > Install Editor > Archive > 2022.3.22f1

### 2. Install VRChat Creator Companion
- Download from: https://vrchat.com/home/download
- Run the installer for your platform (Windows/Mac)
- Launch VCC after installation

## Setting Up This Project

### Step 1: Add Project to VCC

1. Open VRChat Creator Companion
2. Click the **"Projects"** tab
3. Click **"Add Existing Project"**
4. Navigate to the folder where you cloned this repository
5. Select the `MattsLair-01-04-26` folder
6. VCC will scan and recognize the project configuration

### Step 2: Install VRChat SDK

Once the project is added to VCC:

1. The project will appear in your Projects list
2. Click on the project card
3. VCC will show available packages to install
4. Click **"Manage Project"** or the project settings icon
5. In the Packages section, ensure these are installed:
   - **VRChat Worlds SDK** (v3.7.4 or latest)
   - **VRChat Base** (automatically installed as dependency)
   - **VPM Resolver** (automatically installed)
6. Click **"Install"** or **"Update"** as needed
7. Wait for VCC to download and install the packages

### Step 3: Open Project in Unity

1. After SDK installation completes, click **"Open Project"** in VCC
2. VCC will launch Unity 2022.3.22f1 with the project
3. Unity will import assets (this may take a few minutes on first open)
4. Wait for all imports to complete

### Step 4: Verify VRChat SDK Installation

Once Unity opens:

1. Check the menu bar - you should see **"VRChat SDK"** menu
2. Go to **VRChat SDK > Show Control Panel**
3. The VRChat SDK Control Panel should open
4. You should see:
   - Authentication section (login with VRChat account)
   - Builder section (for building worlds)
   - Content Manager section

### Step 5: Setup VRChat Account Integration

1. In the VRChat SDK Control Panel, click **"Sign in"**
2. Enter your VRChat credentials
3. After login, you'll see your VRChat username
4. You're now ready to build and upload worlds

## Project Configuration Details

### What's Already Configured

This project includes all necessary configuration for VCC:

✅ **Unity Version**: Locked to 2022.3.22f1  
✅ **Package Manifest**: Configured with VRChat package registry  
✅ **VPM Manifest**: VCC-specific project identification  
✅ **Layer Configuration**: VRChat-standard layers (8-22)  
✅ **Project Settings**: Optimized for VRChat development  
✅ **Scene Setup**: Basic MattsLair.unity scene created  

### What You Need to Add

After opening in Unity, you'll need to:

1. **Add VRC_SceneDescriptor** to MattsLair.unity scene
   - VRChat SDK > Show Control Panel > Builder
   - Click "Add VRC_SceneDescriptor" or add manually to a GameObject
   
2. **Configure Spawn Points**
   - Create GameObject with VRC_SpatialTrigger
   - Set spawn locations for players

3. **Add Portals** (when building multiple worlds)
   - Use VRC_PortalMarker components
   - Link to other world scenes

## Troubleshooting

### "Project doesn't appear in VCC"
- Ensure you selected the correct folder (should contain `Packages/vpm-manifest.json`)
- Check that `Packages/manifest.json` exists
- Try restarting VCC

### "Wrong Unity Version"
- VCC requires exactly Unity 2022.3.22f1
- Install this version through Unity Hub
- VCC will use the correct version automatically

### "VRChat SDK Menu Missing"
- Open VRChat Creator Companion
- Select the project
- Click "Manage Project"
- Ensure VRChat Worlds SDK is installed
- Restart Unity

### "Package Installation Fails"
- Check internet connection
- Verify VRChat package registry is accessible
- Try removing and re-adding the project in VCC
- Check VCC logs: Help > Show Logs

### "Scene Validation Errors"
- Normal on initial setup
- Add VRC_SceneDescriptor to fix most errors
- Follow VRChat SDK validation messages
- See: https://docs.vrchat.com/docs/creating-your-first-world

## Development Workflow

### Making Changes

1. Open project through VCC (not directly in Unity)
2. Make changes in Unity Editor
3. Save scenes and assets
4. Test locally using VRChat SDK > Build & Test

### Testing Locally

1. VRChat SDK > Show Control Panel
2. Builder tab > Build & Test
3. VRChat client will launch with your world
4. Iterate on design

### Publishing to VRChat

1. Ensure you're logged in (VRChat SDK Control Panel)
2. Build & Publish in SDK Control Panel
3. Fill in world details (name, description, tags)
4. Upload to VRChat servers
5. World will be private by default

## Additional Resources

- **VRChat Documentation**: https://docs.vrchat.com/
- **VCC Documentation**: https://vcc.docs.vrchat.com/
- **Unity Documentation**: https://docs.unity3d.com/2022.3/Documentation/Manual/
- **VRChat Creator Guidelines**: https://hello.vrchat.com/creator-guidelines
- **VRChat Discord**: https://discord.gg/vrchat

## Project-Specific Setup

### Hub-and-Spoke Architecture

This project uses a hub-and-spoke design:
- **Matt's Lair** (hub) contains portals to 4 empire worlds
- Each empire world is a separate scene/world
- Portals use VRChat's native portal system

### Development Phases

Current setup is Phase 1 - Foundation:
- [x] Project structure created
- [x] VCC compatibility configured  
- [ ] Add VRC_SceneDescriptor
- [ ] Create portal prefabs
- [ ] Build Empire World 1

See `PROJECT_STRUCTURE.md` for detailed architecture.

## Getting Help

If you encounter issues:
1. Check VRChat SDK documentation
2. Review VCC troubleshooting guide
3. Join VRChat Creator Discord
4. Open an issue on this repository

---

**Ready to Start Development?**
Once you've completed this setup, you're ready to begin building Matt's Lair!
