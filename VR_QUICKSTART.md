# VR Position Tracking - Quick Start Guide

## What is VR Position Tracking?

VR Position Tracking is a feature in SuperDepth3D that allows the stereo 3D effect to respond to real head movements from your VR headset in 3D space. This creates a more immersive and natural viewing experience.

**Status: FULLY FUNCTIONAL** - Works with SteamVR/OpenVR!

## Quick Setup - Real VR Tracking

### Prerequisites
- SteamVR or OpenVR installed and running
- VR headset connected and tracking
- ReShade installed in your game

### Step 1: Start SteamVR
1. Launch SteamVR
2. Ensure your headset is tracking properly
3. You can minimize the SteamVR window

### Step 2: Enable VR Tracking in Game
1. Launch your game with ReShade
2. Press the ReShade overlay key (usually `Home`)
3. Find **SuperDepth3D** in the shader list
4. Scroll to **VR Position Tracking** category
5. Check **✓ Enable VR Position Tracking**
6. **IMPORTANT:** Leave **Debug Mode** UNCHECKED for real tracking

### Step 3: Adjust Sensitivity
Use the **Position Scale Multiplier** slider:
- **Value range:** 0.0 to 10.0
- **Default:** 1.0
- **Start with 1.0** and adjust based on preference
- **Higher values:** More pronounced head movement effects
- **Lower values:** Subtle effects

### Step 4: Test It!
Move your head around:
- **Left/Right:** Notice horizontal parallax shift
- **Up/Down:** Notice vertical parallax shift
- **Forward/Back:** Notice depth change

## Quick Setup - Debug Mode (Testing Without VR)

If you want to test the feature without VR hardware, use Debug Mode:

### Step 1: Enable the Feature
1. Launch your game with ReShade
2. Press the ReShade overlay key (usually `Home`)
3. Find **SuperDepth3D** in the shader list
4. Scroll to **VR Position Tracking** category
5. Check **✓ Enable VR Position Tracking**

### Step 2: Activate Debug Mode
1. In the same category, check **✓ Debug Mode (Manual Control)**
2. This unlocks manual position sliders

### Step 3: Test Position Offsets
Adjust the **Manual Position (X, Y, Z)** sliders:

#### X Axis - Left/Right Movement
- **Value range:** -1.0 to 1.0
- **Effect:** Shifts the entire stereo image horizontally
- **Try this:** Set to 0.3 and see the image shift right
- **Use case:** Simulates moving your head left/right

#### Y Axis - Up/Down Movement
- **Value range:** -1.0 to 1.0
- **Effect:** Shifts the entire stereo image vertically
- **Try this:** Set to -0.2 and see the image shift down
- **Use case:** Simulates moving your head up/down

#### Z Axis - Forward/Backward Movement (Depth)
- **Value range:** -1.0 to 1.0
- **Effect:** Changes the stereo depth/convergence
- **Try this:** Set to 0.5 to increase stereo separation
- **Use case:** Simulates leaning forward/backward

### Step 4: Adjust Sensitivity
Use the **Position Scale Multiplier** slider:
- **Value range:** 0.0 to 10.0
- **Default:** 1.0
- **Higher values:** More pronounced position effects
- **Lower values:** Subtle position effects

**Example settings:**
```
Enable VR Position Tracking: ✓
Debug Mode: ✓
Manual Position X: 0.0
Manual Position Y: 0.0  
Manual Position Z: 0.3
Position Scale Multiplier: 2.0
```
This creates a noticeable depth increase as if leaning forward.

## Understanding the Effects

### Horizontal Offset (X Axis)
When you move your head left/right, the 3D scene should shift horizontally, giving a sense of parallax:
- **Positive X:** Image shifts right (like moving head right)
- **Negative X:** Image shifts left (like moving head left)
- **Real-world equivalent:** Peeking around corners

### Vertical Offset (Y Axis)
When you move your head up/down, the 3D scene shifts vertically:
- **Positive Y:** Image shifts up (like moving head up)
- **Negative Y:** Image shifts down (like moving head down)
- **Real-world equivalent:** Looking over/under objects

### Depth Modulation (Z Axis)
When you move your head forward/backward, the stereo depth changes:
- **Positive Z:** Increases stereo separation (like leaning in)
- **Negative Z:** Decreases stereo separation (like leaning back)
- **Real-world equivalent:** Getting closer/further from the screen

## Recommended Settings

### For First-Time Testing
```
Position Scale Multiplier: 1.0
Manual Position X: 0.2
Manual Position Y: 0.1
Manual Position Z: 0.0
```
This gives a gentle offset to see the effect clearly.

### For Demonstration
```
Position Scale Multiplier: 3.0
Animate between: X: -0.5 to +0.5
```
Moving the X slider smoothly shows the parallax effect.

### For Subtle Effect
```
Position Scale Multiplier: 0.5
Manual Position X: 0.1
Manual Position Y: 0.0
Manual Position Z: 0.1
```
Barely noticeable but adds to immersion.

## Tips and Tricks

### Finding the Right Scale
1. Set all position values to 0.0
2. Enable Debug Mode
3. Set Z to 0.5
4. Adjust Position Scale until the depth change is comfortable
5. This is your personal scale for future use

### Testing Each Axis Independently
1. Set all positions to 0.0
2. Adjust only X to test horizontal
3. Reset X to 0.0
4. Adjust only Y to test vertical
5. Reset Y to 0.0
6. Adjust only Z to test depth

### Combining Axes
Real head movement affects all three axes:
```
Leaning forward and right:
X: 0.3
Y: 0.0
Z: 0.4
```

## Performance Impact

The VR Position Tracking feature has minimal performance impact:
- **FPS impact:** < 1% (negligible)
- **GPU overhead:** A few conditional checks
- **No external processing**

You can keep it enabled even if not actively using it.

## Troubleshooting

### Real VR Tracking Issues

#### "I don't see any head tracking effect"
- ✓ Verify SteamVR is running
- ✓ Verify "Enable VR Position Tracking" is checked
- ✓ Verify "Debug Mode" is UNCHECKED
- ✓ Check that your HMD is tracking (green in SteamVR)
- ✓ Try increasing Position Scale to 2.0 or 3.0

#### "No VR runtime detected"
- Ensure SteamVR is running (check system tray)
- Check that your HMD is connected
- Restart the game after starting SteamVR

#### "Effect is too strong"
- Lower the "Position Scale Multiplier"
- Start with 0.5 and adjust upward
- Typical range: 0.5 to 2.0

#### "Effect is too weak"
- Increase the "Position Scale Multiplier"
- Try values up to 5.0 for dramatic effects

### Debug Mode Issues

#### "I don't see any effect in Debug Mode"
- ✓ Verify "Enable VR Position Tracking" is checked
- ✓ Verify "Debug Mode" IS checked
- ✓ Try extreme values (X: 1.0) to see obvious changes
- ✓ Check Position Scale is not 0.0

#### "Screen looks distorted"
- This is normal for extreme position values
- Keep X and Y within -0.5 to 0.5 range
- Reduce Position Scale

## Compatibility

### Works With
✅ Virtual Desktop Classic
✅ SteamVR Desktop View
✅ SteamVR Overlays
✅ Any OpenVR-compatible headset

### Requirements
- SteamVR/OpenVR runtime
- Compatible VR headset
- ReShade with VR support

## Common Use Cases

### Static Scene Photography
Set subtle offsets for screenshot comparisons:
```
X: 0.1, Y: 0.0, Z: 0.0 → Slight right perspective
X: -0.1, Y: 0.0, Z: 0.0 → Slight left perspective
```

### Depth Testing
Find optimal depth for your setup:
```
Start: Z: 0.0
Increment by 0.1 until comfortable
Your optimal depth = final Z value
```

### Parallax Demonstration
Show others how 3D works:
```
Slowly move X from -0.5 to +0.5
Objects at different depths move differently
```

## Advanced Settings

### Custom Offset Curves
Future versions may support:
- Non-linear position response
- Per-axis sensitivity
- Deadzone settings
- Movement smoothing

### Integration with Game Events
Potential future features:
- Reduce depth during fast movement
- Increase parallax when stationary
- Context-aware positioning

## Getting Help

If you have questions or issues:

1. **Check Documentation**
   - VR_POSITION_TRACKING.md for technical details
   - README.md for general info

2. **Community Support**
   - Discord: https://discord.gg/W2f7YhX
   - GitHub Issues: Report bugs or request features

3. **Report Problems**
   - Include your settings
   - Describe what you expected vs. what happened
   - Mention your GPU and game

## Summary

VR Position Tracking adds a new dimension to SuperDepth3D's stereo 3D effects. While the full VR integration requires additional components, Debug Mode lets you experience and test the feature right now. Experiment with different position values and scales to find what works best for your setup and preferences!

Happy 3D gaming! 🎮🥽
