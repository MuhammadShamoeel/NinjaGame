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
- 🖥️ **Fullscreen Mode** - Click FS button for immersive gameplay on any device

## Files Included

- `index.html` - Main game file (all-in-one HTML with embedded CSS/JS)
- `manifest.json` - PWA manifest for installation and configuration
- `sw.js` - Service Worker for offline functionality and caching
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
1. Open the game in your browser at the GitHub Pages URL
2. Wait for the Service Worker to install (check DevTools → Application)
3. Look for the **"Install"** button in the address bar (or menu → "Install app")
4. Click to install - the game will appear in your applications menu
5. Launch it anytime, just like a native app

### On Mobile (Android)
1. Open the game in Chrome or Edge on your phone
2. Wait for Service Worker to register
3. Tap the **menu** (⋮) → **"Install app"** or tap the install icon in the address bar
4. The game will be added to your home screen
5. Tap the icon to launch

### On Mobile (iOS)
1. Open the game in Safari on your iPhone/iPad
2. Tap the **share icon** at the bottom
3. Scroll down and tap **"Add to Home Screen"**
4. Enter a name (or use default) and tap **Add**
5. The game will appear on your home screen

### Why Install Button Not Appearing?
**Checklist:**
- ✅ Service Worker must be registered (check DevTools → Application → Service Workers)
- ✅ Must be served over HTTPS (GitHub Pages provides this)
- ✅ Manifest.json must be valid and linked in HTML
- ✅ Wait 5-10 seconds for Service Worker to fully install
- ✅ Try opening in a new incognito/private window
- ✅ Clear browser cache if you've visited before
- ✅ Desktop browsers (Chrome 57+, Edge 79+, Brave) support installation
- ❌ Firefox: Limited PWA support, but still works as web app

## Controls

### Desktop/Keyboard
- **A / ← Arrow** - Move Left
- **D / → Arrow** - Move Right
- **W / ↑ Arrow / Space** - Jump
- **J** - Slash Attack
- **K** - Shield/Block

### Mobile/Touch
- **Left Button** - Move Left
- **Right Button** - Move Right
- **Guard Button** - Shield/Block
- **Slash Button** - Attack
- **Jump Button** - Jump

### In-Game
- **🤖 AUTO ON / 👤 MANUAL** - Toggle between AI autoplay and manual control
- **🖥️ FS** - Toggle fullscreen mode (works on desktop AND mobile!)
- **RESPAWN WARRIOR** - Restart after death (manual mode only)

## Why Fullscreen Button?

**Problem:** Fullscreen doesn't work on mobile browsers through the Fullscreen API

**Solution:** The **🖥️ FS** button provides:
- On **Desktop**: Toggle true fullscreen (F11-like experience)
- On **Mobile**: Requests fullscreen + locks orientation to landscape
- On **Installed PWA**: Runs natively in fullscreen mode

**Note:** Mobile browsers have limitations, so when installed as PWA, the game automatically launches in fullscreen.

## Gameplay Tips

- 🛡️ **Shield** incoming missiles and bombs
- ⚔️ **Slash** enemies when they're close (about 1 ninja-width away)
- 👣 **Jump on enemies' heads** to stomp them and chain double jumps
- 🔥 **Avoid fire spots** left by missile explosions
- 💪 **Health bar** at top-left shows remaining HP
- 📊 **Score increases** over time - survive as long as possible!

## Troubleshooting

### Game not loading?
- Make sure all 3 files are in the same directory
- Check browser console for errors (Press F12)
- GitHub Pages takes 1-2 minutes to deploy - wait and refresh
- Clear browser cache (Ctrl+Shift+Delete) and try again

### Install button not appearing?
- Open DevTools (F12) → Application → Service Workers
- Wait for Service Worker status to show **"activated"** (not just "installed")
- Refresh the page after Service Worker is active
- Try opening in a new incognito window
- Use Chrome, Edge, or Brave (Firefox has limited PWA support)
- Ensure you're on HTTPS (GitHub Pages provides this)

### Fullscreen not working on mobile?
- Click the **🖥️ FS** button to request fullscreen
- Some mobile browsers restrict fullscreen to user interactions only
- **Best experience:** Install as PWA - it launches in native fullscreen!
- On iOS: The app will run fullscreen when added to home screen

### Buttons not responding on mobile?
- Ensure you've selected **👤 MANUAL** mode (not AI)
- Buttons only work in manual mode
- Try refreshing the page
- Check if browser has touch permission enabled

### Audio not playing?
- Audio requires user interaction first - click/tap to enable
- Some browsers disable audio on mute - unmute your device
- Check browser audio settings (not system mute)
- Try refreshing the page

### Game feels laggy?
- Close other browser tabs
- Close other applications
- Try a different browser (Chrome/Edge recommended)
- Reduce graphics settings in other apps
- Check Device Performance (DevTools → Performance tab)

## Advanced: Custom Deployment

### Self-hosted (Your own server)
1. Upload all 3 files to your server
2. Ensure **HTTPS is enabled** (required for PWA)
3. Serve files with correct MIME types:
   - `manifest.json` → `application/manifest+json`
   - `sw.js` → `application/javascript`
4. Set CORS headers if needed

### Local Development
1. Clone/download the files
2. Run a local server:
```bash
# Python 3
python -m http.server 8000

# Python 2  
python -m SimpleHTTPServer 8000

# Node.js (with http-server)
npx http-server

# PHP
php -S localhost:8000
```
3. Open `http://localhost:8000` in your browser

**Note:** PWA features (offline, install) won't work on `http://` - only on `https://` or `localhost:8000`

## Technical Details

- **Framework**: Vanilla JavaScript (no dependencies)
- **Rendering**: HTML5 Canvas
- **Audio**: Web Audio API (procedurally generated)
- **PWA**: Service Worker + Web App Manifest
- **Size**: ~50 KB (3 files combined)
- **Performance**: 60 FPS target, optimized for all devices
- **Compatibility**: Progressive enhancement - works on older browsers too

## Browser Support

| Browser | Support | Install | Fullscreen | Offline |
|---------|---------|---------|-----------|----------|
| Chrome/Chromium | ✅ Full | ✅ Yes | ✅ Yes | ✅ Yes |
| Edge | ✅ Full | ✅ Yes | ✅ Yes | ✅ Yes |
| Brave | ✅ Full | ✅ Yes | ✅ Yes | ✅ Yes |
| Firefox | ✅ Full | ⚠️ Limited | ✅ Yes | ✅ Yes |
| Safari (Desktop) | ✅ Full | ⚠️ Limited | ✅ Yes | ✅ Yes |
| Chrome Mobile | ✅ Full | ✅ Yes | ⚠️ Limited | ✅ Yes |
| Safari Mobile (iOS) | ✅ Full | ✅ Yes | ✅ PWA | ✅ Yes |
| Samsung Internet | ✅ Full | ✅ Yes | ✅ Yes | ✅ Yes |

## File Size Breakdown

- `index.html` - ~45 KB (includes all HTML, CSS, and game code)
- `manifest.json` - ~3 KB (PWA configuration)
- `sw.js` - ~2 KB (Service Worker)
- **Total**: ~50 KB

## Performance Optimization

- Single HTML file with embedded CSS/JS = fewer HTTP requests
- Service Worker caching = instant loads on repeat visits
- Optimized canvas rendering targeting 60 FPS
- Minimal external dependencies (only Google Fonts)
- Procedural audio generation (no audio files!)

## License

Free to use, modify, and share!

## Credits

- **Game Design**: Cyberpunk ninja platformer with AI
- **Code**: Vanilla JavaScript implementation
- **Audio**: Procedural Web Audio synthesis
- **Framework**: HTML5 Canvas

---

**Enjoy the game! 🥷**

### Quick Start
1. Visit: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`
2. Click the install icon (or wait for install button)
3. Choose AI Autoplay or Manual Mode
4. Use **🖥️ FS** button for fullscreen on any device
5. Share your high score!
