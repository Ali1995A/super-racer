# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Super Racer is a single-file HTML5 racing game with Tesla FSD-style interface design. The entire game (HTML, CSS, JavaScript) is contained in `index.html` with no external dependencies or build steps.

## Development Commands

```bash
# Run locally (Windows)
start.bat

# Or open directly in browser
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux

# Deploy to Vercel
vercel
```

## Architecture

### Single-File Structure
- `index.html` - Contains all HTML structure, CSS styles, and JavaScript game logic
- `vercel.json` - Vercel deployment configuration (static build, SPA rewrites)
- `start.bat` - Windows convenience script to launch game in browser

### Key Components (all in index.html)

**CSS (lines 9-711):**
- FSD/Tesla-inspired dark theme with glassmorphism effects
- Responsive layout with portrait/landscape media queries
- Touch control overlays positioned with absolute positioning
- Gamepad-style D-pad buttons for mobile controls

**JavaScript Structure:**
- `CONFIG` (lines 888-928) - Game constants and difficulty settings
- `SoundSystem` class (lines 931-1073) - Web Audio API for procedural sound generation
- `gameState` object (lines 1076-1087) - Tracks score, speed, level, difficulty
- `player` object (lines 1093-1099) - Player car position and dimensions
- Game loop: `update()` (1346-1435) → `draw()` (1438-1468) via `requestAnimationFrame`

### Difficulty System
Four difficulty levels defined in `CONFIG.difficulties`:
- `easy-easy` - Extremely slow (0.1x enemy speed, 2.5 km/h max, 70% fewer spawns)
- `easy` - Very slow (0.5x enemy speed, 8 km/h max)
- `normal` - Balanced (default)
- `hard` - Challenging (faster enemies, higher max speed)

Each difficulty affects: `enemyCarSpeed`, `maxSpeed`, `acceleration`, `spawnRate`, `levelMultiplier`.

### Canvas Rendering
- Fixed internal resolution: 400x700px (`CONFIG.canvasWidth/Height`)
- Responsive scaling via `resizeCanvas()` - maintains aspect ratio
- Road width: 300px with 4 lanes
- Car size: 40x70px

### Touch Controls Layout
Dual D-pad gamepad layout:
- **Left D-pad** (`.touch-left-dpad`): Up (accelerate), Left (move left), Down (brake)
- **Right D-pad** (`.touch-right-dpad`): Up (accelerate), Right (move right), Down (brake)
- **Top function buttons** (`.touch-top-controls`): Pause, Home

Portrait vs landscape adjustments via CSS media queries.

### Sound System
All sounds generated procedurally using Web Audio API oscillators:
- `engine` - Random engine noises during gameplay
- `turn` - Lane change feedback
- `brake` - Deceleration audio
- `crash` - Collision impact
- `score` - Milestone celebration

## Important Implementation Details

1. **No build step** - Direct HTML file editing, no npm/node_modules
2. **Mobile-first touch handling** - Prevents default touch behaviors (`touchmove` with `passive: false`)
3. **Smooth movement** - Player position uses linear interpolation: `player.x += (player.targetX - player.x) * 0.15`
4. **Collision detection** - Simple AABB rectangle overlap check
5. **Level progression** - `level = Math.floor(distance / 500) + 1`

## Making Changes

Since everything is in one file:
1. Edit `index.html` directly
2. Test by refreshing browser (hard refresh: Ctrl+Shift+R / Cmd+Shift+R)
3. No compilation needed
4. For CSS changes, look at `<style>` block (lines 9-711)
5. For JavaScript logic, look at `<script>` block (lines 886-1828)

## Deployment

The `vercel.json` configuration uses:
- Static build (`@vercel/static`)
- SPA rewrite - all routes redirect to `/index.html`
- Security headers included

One-click deploy via Vercel CLI or drag-and-drop to vercel.com/new.
