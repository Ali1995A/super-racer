# Super Racer 🚗

A Tesla FSD-style web racing game with desktop and mobile device support.

## ✨ Features

- 🎮 **Tesla FSD-style Interface** - Simulates Tesla's autopilot interface with dark theme and clean design
- ⌨️ **Keyboard Controls** - Use arrow keys ← → to control the car
- 📱 **Touch Support** - Full support for iPad and iPhone touch controls
- 🎨 **iPhone Aesthetic Standards** - Beautiful UI design following Apple design guidelines
- 🚀 **Vercel One-Click Deployment** - Can be directly deployed to Vercel platform
- 🎯 **Multiple Difficulty Levels** - Choose between Easy-Easy, Easy, Normal, and Hard modes

## 🎮 How to Play

1. Select your difficulty level (Easy, Normal, or Hard)
2. Click "START GAME" button
3. Use arrow keys or touch buttons to control the car left and right
4. Press and hold the down arrow (↓) to brake/slow down
5. Avoid other vehicles and drive as far as possible
6. Game difficulty gradually increases as distance increases
7. Enjoy the dynamic sound effects as you play!

## 🎯 Difficulty Levels

### Easy-Easy Mode
- Extremely slow enemy cars (0.1x speed)
- Very low maximum speed (2.5 km/h)
- Minimal enemy spawns
- Very slow acceleration
- Perfect for absolute beginners and children

### Easy Mode
- Very slow enemy cars (0.5x speed)
- Much lower maximum speed (8 km/h)
- Fewer enemy spawns
- Slower acceleration
- Great for beginners and casual players

### Normal Mode
- Balanced gameplay
- Moderate enemy speed and spawn rate
- Default gaming experience

### Hard Mode
- Faster enemy cars
- Higher maximum speed
- More frequent enemy spawns
- Challenge for experienced players

## 🚀 Deploy to Vercel

### Method 1: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Navigate to project directory
cd super-racer

# Login to Vercel
vercel login

# Deploy
vercel
```

### Method 2: Deploy via Vercel Website

1. Push the project to GitHub
2. Login to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Select your GitHub repository
5. Click "Deploy"

### Method 3: Deploy via Vercel Drag & Drop

1. Visit [vercel.com/new](https://vercel.com/new)
2. Drag and drop the `super-racer` folder into the page
3. Wait for deployment to complete

## 📁 Project Structure

```
super-racer/
├── index.html      # Main game file (contains all HTML, CSS, JavaScript)
├── vercel.json     # Vercel deployment configuration
├── start.bat       # Windows startup script
└── README.md       # Project documentation
```

## 🎨 Design Features

### FSD-Style Interface
- Dark theme background
- Neon blue accent colors
- Glassmorphism effects (backdrop-filter)
- Clean lines and icons
- Real-time speed and distance display

### iPhone Aesthetic Standards
- SF Pro font system
- Rounded corner design
- Smooth animation transitions
- Elegant gradient effects
- Responsive layout

## 📱 Device Support

- ✅ Desktop browsers (Chrome, Firefox, Safari, Edge)
- ✅ iPad (touch controls)
- ✅ iPhone (touch controls)
- ✅ Android devices (touch controls)

## 🎯 Controls

### Desktop Devices
- `←` Left arrow: Move left
- `→` Right arrow: Move right
- `↓` Down arrow: Hold to brake/slow down
- Home button: Return to main menu
- Fullscreen button: Toggle fullscreen mode

### Mobile Devices (iPad/iPhone)
- **Left Button**: Located at bottom-left corner for left movement
- **Right Button**: Located at bottom-right corner for right movement
- **Brake Button**: Located at bottom-center for braking/slowing down
- **Home Button**: Located in top-right corner, allows you to return to main menu
- **Fullscreen Button**: Located in top-right corner, toggle fullscreen mode

#### iPad-Specific Controls
- **Ergonomic Layout**: Buttons positioned for comfortable thumb reach
- **Large Touch Areas**: Spacious buttons for accurate touch input
- **Visual Feedback**: Buttons highlight when pressed
- **Brake Control**: Dedicated brake button for precise speed control

## 🔧 Tech Stack

- HTML5 Canvas
- Vanilla JavaScript (no dependencies)
- CSS3 (Flexbox, Grid, Animations)
- Web Audio API (for dynamic sound effects)
- Responsive Design

## 🔊 Sound Effects

The game features dynamic sound effects created with Web Audio API:

- **Engine Sounds**: Random engine noises during gameplay
- **Turn Sounds**: Audio feedback when changing lanes
- **Brake Sounds**: Deceleration audio when pressing down arrow
- **Crash Sounds**: Impact sound when colliding with vehicles
- **Score Sounds**: Celebration sounds when passing vehicles or reaching milestones

All sounds are generated programmatically using Web Audio API oscillators and filters, requiring no external audio files.

## 🖥️ Fullscreen Mode

The game supports fullscreen mode for an immersive gaming experience:

- **Desktop**: Click the fullscreen button in the top-right corner or press F11
- **Mobile**: Tap the fullscreen button in the top-right corner
- **Exit**: Press ESC key or click the fullscreen button again

Fullscreen mode provides:
- Immersive gameplay without browser distractions
- Better visibility on larger screens
- Enhanced focus on the racing experience

## 🏠 Navigation

- **Home Button**: Located in the top-right corner, allows you to return to the main menu at any time
- **Game State**: Your current game progress will be lost when returning to the main menu
- **Quick Access**: Easily switch between difficulty levels without refreshing the page

##  License

MIT License

## 🤝 Contributing

Issues and Pull Requests are welcome!

---

**Enjoy the game!** 🏎️
