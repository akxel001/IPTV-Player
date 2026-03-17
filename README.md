# StreamVault - Professional IPTV Player

A full-featured, browser-based IPTV Player supporting live streams, M3U playlists, and local video files.  
**No installation required** — just open `index.html` in your browser.

---

## ✨ Features

### Streaming & Playback
- **HLS** (.m3u8) live streams via **HLS.js**
- **DASH** (.mpd) streams via **Dash.js**
- **Local video files**: MP4, WebM, MKV, AVI, TS
- Adaptive bitrate streaming (automatic quality)
- Picture-in-Picture (PiP) mode
- Fullscreen support

### Playlist Management
- Import **M3U / M3U8** playlists via:
  - File upload (click or drag & drop)
  - Remote URL (with CORS proxy fallback)
  - Paste text
- Auto-parse channel metadata: name, logo, group, language
- Persistent playlists (saved to localStorage)
- Supports 500+ channels without lag

### Organization
- **Favorites** — star your most-watched channels
- **Recent** — automatic watch history (last 30)
- **Local Files** — browse locally-played files
- **Category filter** — filter by group/category
- **Search** — real-time fuzzy search by name/group

### Player Controls
| Action | Control |
|---|---|
| Play / Pause | `Space` or click |
| Seek -10s / +10s | `← →` |
| Volume | `↑ ↓` |
| Mute | `M` |
| Fullscreen | `F` |
| Next / Prev Channel | `N` / `P` |
| PiP | PiP button |

---

## 🚀 Getting Started

### Option 1: Open Directly (Recommended)
Just double-click `index.html` — it opens in your default browser.

> ⚠️ Some browsers block local file CORS. Use Option 2 if streams don't load.

### Option 2: Run via HTTP Server (Best)
If you have Python installed:
```bash
# Python 3
python -m http.server 8080
# Then open: http://localhost:8080
```

Or with Node.js:
```bash
npx serve .
```

---

## 📁 Project Structure

```
IPTV Player/
├── index.html          # Main app entry point
├── css/
│   └── style.css       # Dark theme design system
├── js/
│   ├── storage.js      # LocalStorage persistence
│   ├── parser.js       # M3U/M3U8 parser & stream detector
│   ├── player.js       # HLS/DASH/native video engine
│   ├── ui.js           # UI components (sidebar, modals, toasts)
│   └── app.js          # Main app controller
└── README.md
```

---

## 📺 Supported Formats

| Format | Extension | Notes |
|---|---|---|
| HLS | `.m3u8` | Via HLS.js (most IPTV streams) |
| DASH | `.mpd` | Via Dash.js |
| M3U Playlist | `.m3u`, `.m3u8` | Full #EXTINF parsing |
| MP4 | `.mp4` | Native browser |
| WebM | `.webm` | Native browser |
| MKV | `.mkv` | Chrome/Edge (codec-dependent) |
| AVI | `.avi` | Limited browser support |
| MPEG-TS | `.ts` | Native browser |

---

---

## 🚀 Deployment

### ⚡ Quick Frontend (GitHub Pages)
You can host the UI for free on GitHub Pages:
1. Push this repo to GitHub.
2. Go to **Settings > Pages**.
3. Select **main** branch and `/root` folder.
> [!WARNING]
> The CORS proxy (`/proxy`) requires the Python backend. Some remote playlists may fail on GitHub Pages unless you host the backend separately.

### 🌐 Full Stack (Recommended)
To keep the CORS proxy working, host on **Render**, **Railway**, or **Heroku**:
1. Connect your GitHub repo to the service.
2. Set build command: `pip install -r requirements.txt` (if applicable) or just leave empty.
3. Set start command: `python server.py $PORT`.
4. The app will be live with a public URL!

---

## 🔧 Troubleshooting

### Stream won't load
- Check stream URL is accessible in your region
- Some streams require VPN
- Try importing via file download instead of URL (CORS)

### MKV not playing
- Use Chrome or Edge (best codec support)
- Some MKV files use codecs not supported natively in browsers

### CORS errors on playlist URL
- The app automatically tries CORS proxies
- If it still fails, download the `.m3u` file and import it directly

### No channels showing
- Make sure the M3U file starts with `#EXTM3U`
- Try the "Paste Text" tab and paste M3U content manually

---

## 🌐 Browser Compatibility

| Browser | Status |
|---|---|
| Chrome 90+ | ✅ Full support |
| Edge 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support |
| Safari 14+ | ✅ (HLS native) |
| Mobile Chrome | ✅ |
| Mobile Safari | ✅ |

---

## ⚖️ Legal Notice

This player is a **technical tool only**. Ensure all content you stream is legally accessible in your country. The app does not include or promote any illegal streaming sources.

---

## 📦 Dependencies (CDN)

- [HLS.js](https://github.com/video-dev/hls.js/) — HLS streaming
- [Dash.js](https://github.com/Dash-IF/dash.js/) — DASH streaming
- [Lucide Icons](https://lucide.dev/) — UI icons
- [Inter Font](https://fonts.google.com/specimen/Inter) — Typography
