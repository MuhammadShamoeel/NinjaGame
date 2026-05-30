# Midnight Shadow Ninja - PWA Game

A cyberpunk ninja platformer game with autonomous AI gameplay and manual warrior mode. Fully installable as a Progressive Web App (PWA).

## Features

- 🤖 **Autonomous AI Autoplay Mode** - Watch the AI ninja automatically play and score points
- 👤 **Manual Warrior Mode** - Control the ninja with keyboard or mobile buttons
- 📱 **Fully Responsive** - Works perfectly on PC, tablet, and mobile devices
- 💾 **Offline Support** - Works offline when installed as PWA
- 🎮 **Touch Controls** - Mobile-friendly D-pad and action buttons
- 🌙 **Dynamic Day/Night Cycle** - Beautiful parallax backgrounds
- 🔊 **Procedural Chiptune Soundtrack** - Generated using Web Audio API

## Files Included

- `ka.html` - Main game file (all-in-one HTML with embedded CSS/JS)
- `index.html` - Redirect file for GitHub Pages
- `manifest.json` - PWA manifest for installation and configuration
- `sw.js` - Service Worker for offline functionality
- `README.md` - This file

## How to Deploy to GitHub Pages

### 1. Create a GitHub Repository
```bash
git init
git add .
git commit -m "Initial commit: Shadow Ninja PWA Game"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```

### 2. Enable GitHub Pages
1. Go to your repository settings
2. Navigate to **Pages** section (left sidebar)
3. Under "Build and deployment", select:
   - Source: `Deploy from a branch`
   - Branch: `main` (or your branch name)
   - Folder: `/ (root)`
4. Click **Save**

### 3. Access Your Game
After a few moments, your game will be available at:
```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

## How to Install as PWA

### On Desktop (Chrome/Edge/Brave)
1. Open the game in your browser
2. Click the **"Install"** button in the address bar (or menu → "Install app")
3. The game will appear in your applications menu

### On Mobile (Android/iOS)
1. Open the game in Chrome or Edge
2. Tap the **menu** (⋮) → **"Install app"** or **"Add to Home Screen"**
3. The game will be added to your home screen
4. Launch it anytime, just like a native app

## Controls

### Desktop/Keyboard
- **A / ← Arrow** - Move Left
- **D / → Arrow** - Move Right
- **W / ↑ Arrow / Space** - Jump
- **J** - Slash Attack
- **K** - Shield/Block
- **Right Click + Hold** - Shield (alternative)

### Mobile/Touch
- **Left Button** - Move Left
- **Right Button** - Move Right
- **Guard Button** - Shield/Block
- **Slash Button** - Attack
- **Jump Button** - Jump

### In-Game
- **🤖 AUTO ON / 👤 MANUAL** - Toggle between AI autoplay and manual control
- **RESPAWN WARRIOR** - Restart after death (manual mode only)

## Gameplay Tips

- 🛡️ **Shield** incoming missiles and bombs
- ⚔️ **Slash** enemies when they're close (about 1 ninja-width away)
- 👣 **Jump on enemies' heads** to stomp them and chain double jumps
- 🔥 **Avoid fire spots** left by missile explosions
- 💪 **Health bar** at top-left shows remaining HP
- 📊 **Score increases** over time - survive as long as possible!

## Troubleshooting

### Game not loading?
- Make sure all 4 files are in the same directory
- Check browser console for errors (F12)
- GitHub Pages takes a minute to deploy - wait and refresh

### Buttons not responding on mobile?
- Ensure browser has permission to use touch events
- Try refreshing the page
- Mobile buttons only work in manual mode (👤 MANUAL)

### Audio not playing?
- Audio requires user interaction - click to enable first
- Some browsers disable audio on mute - unmute your device
- Service worker might block audio on first load - refresh

### Can't install as PWA?
- Use a modern browser (Chrome 57+, Edge 79+, Safari 15.1+)
- Must be served over HTTPS (GitHub Pages provides this automatically)
- Visit the page first, then look for install prompt

### Game feels laggy?
- Close other browser tabs
- Reduce screen brightness slightly
- Try a different browser
- On mobile, close other apps

## Advanced: Custom Deployment

### Self-hosted (Your own server)
1. Upload all 4 files to your server
2. Ensure HTTPS is enabled
3. Configure CORS if needed
4. Access via `https://yourdomain.com/path/to/ka.html`

### Local Development
1. Open `ka.html` directly in a browser (works offline)
2. Or use a simple HTTP server:
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (with http-server)
npx http-server
```

## Technical Details

- **Framework**: Vanilla JavaScript (no dependencies)
- **Rendering**: HTML5 Canvas
- **Audio**: Web Audio API (procedurally generated)
- **PWA**: Service Worker + Web App Manifest
- **Size**: ~120KB single HTML file
- **Performance**: 60 FPS target, optimized for low-end devices

## Browser Support

| Browser | Support | Install |
|---------|---------|---------|
| Chrome/Edge | ✅ Yes | ✅ Yes |
| Firefox | ✅ Yes | ⚠️ Limited |
| Safari | ✅ Yes | ✅ iOS 15.1+ |
| Mobile Chrome | ✅ Yes | ✅ Yes |
| Mobile Safari | ✅ Yes | ✅ Yes |

## License

Free to use, modify, and share!

## Credits

- Game Design: Cyberpunk ninja platformer
- Code: Original JavaScript implementation
- Audio: Procedural Web Audio synthesis

---

**Enjoy the game! 🥷**
