# AFK Status Tracker 😴

> A smart, feature-rich AFK (Away From Keyboard) tracker with AI-powered estimations, analytics, and gamification.

**Live Demo:** [View on GitHub Pages](#) *(Update with your GitHub Pages URL)*

![AFK Tracker Banner](https://via.placeholder.com/1200x400/1a1a2e/ff6b6b?text=AFK+Status+Tracker)

## Features

### 🤖 Smart AI-Powered Estimation
- **Fuzzy Matching**: Automatically groups similar AFK reasons using Levenshtein distance algorithm
- **Pattern Learning**: Learns from your AFK history to predict return times
- **Time-Aware**: Considers time-of-day and recency when making predictions
- **Outlier Detection**: Filters anomalies using statistical IQR method
- **Confidence Scoring**: Shows high/medium/low confidence based on data quality

### ⏱️ Multiple Timer Modes
1. **Track Time**: Simple elapsed time counter
2. **Countdown**: Set a manual "back in X minutes" timer
3. **Smart Estimate**: AI predicts when you'll return based on past patterns

### 📊 Comprehensive Analytics
- **Hourly Breakdown**: Visual chart showing your AFK patterns by hour
- **Duration Distribution**: See how long your typical breaks are
- **Top Reasons**: Track your most frequent AFK activities
- **Statistics Dashboard**: Total sessions, time tracked, streaks, and more
- **History Viewer**: Browse all past sessions with filtering options

### 🏆 Achievements & Gamification
- Unlock badges for milestones (first break, coffee addict, night owl, etc.)
- Track consecutive days streak
- Progress tracking for all achievements
- 8 unique achievements to unlock

### 🎨 Customization
- **5 Beautiful Themes**:
  - Swirly Sunset (default)
  - Matrix Rain (with animated canvas effect)
  - Cyberpunk Neon
  - Space Stars
  - Chill Gradient
- **Custom Backgrounds**: Upload your own images
- **Color Picker**: Customize the primary accent color
- **Animation Speed**: Control background animation speed (0.1x to 3x)
- **Custom Emoji**: Set your own status icon
- **Dark/Light/High Contrast**: Accessibility-first design

### 👤 Multi-Profile System
- Create separate profiles for Work, Personal, Gaming, etc.
- Each profile maintains independent:
  - Session history
  - Statistics
  - Achievements
  - Settings

### 🔔 Notifications & Reminders
- **Desktop Notifications**: Get notified when you return from AFK
- **Pomodoro Timer**: Built-in 25/5 work/break timer
- **Break Reminders**: Customizable work duration and break length
- **Sound Effects**: Optional audio cues (with volume control)

### 📱 Mobile & Touch Support
- Fully responsive design
- Touch gestures:
  - Swipe right to return from AFK
  - Swipe down to close modals
- PWA support (installable on mobile)
- Widget/OBS mode for streaming overlays

### 🌐 Sharing & Social
- **URL Sharing**: Generate shareable AFK status links
- **QR Codes**: Instant mobile access
- **Twitter Integration**: Tweet your stats
- **Discord Copy**: Formatted message for Discord
- **Status Cards**: Generate beautiful PNG images of your stats
- **Auto-start**: URL parameters for instant AFK mode

### 💾 Data Management
- **Export/Import**: Backup your data as JSON
- **IndexedDB Storage**: Fast, local persistence
- **Data Validation**: Import safety checks
- **Profile Management**: Create, switch, delete profiles
- **Clear Data**: Reset everything with confirmation

### ♿ Accessibility
- **Reduce Motion**: Disable animations
- **High Contrast**: Enhanced visibility mode
- **Font Size Options**: Small, Medium, Large, Extra Large
- **Keyboard Shortcuts**:
  - `Enter` - Go AFK
  - `Esc` - Return from AFK
  - `1-9` - Quick select presets
  - `S` - Open settings
  - `H` - View history
- **Screen Reader Friendly**: Semantic HTML

### ⚙️ Advanced Features
- **Custom Presets**: Create your own quick-select buttons
- **Screen Wake Lock**: Keep display on while AFK
- **Widget Mode**: Transparent mode for OBS/streaming (`?widget=true`)
- **Motivational Quotes**: Rotating inspirational messages
- **Fullscreen Mode**: Auto-enter fullscreen when going AFK
- **Quote Rotation**: Customizable interval (10-300 seconds)

## Quick Start

### Option 1: GitHub Pages (Recommended)
1. Visit the live demo: *[Your GitHub Pages URL]*
2. Start using immediately - no installation needed!

### Option 2: Local Development
```bash
# Clone the repository
git clone https://github.com/yourusername/afk.git
cd afk

# Open in browser
open index.html
# or just double-click index.html
```

### Option 3: Install as PWA
1. Visit the site in Chrome/Edge
2. Click the install icon in the address bar
3. Use as a standalone app!

## Usage

### Basic Usage
1. **Enter a reason** for going AFK (or choose a preset)
2. **Select timer mode**:
   - Track time (simple)
   - Countdown (set minutes)
   - Smart estimate (AI prediction)
3. **Click "GO AFK"** - enters fullscreen
4. **Press "I'm back!"** or swipe right when you return

### Keyboard Shortcuts
- `Enter` - Go AFK
- `Esc` - Return
- `1-9` - Use preset #1-9
- `S` - Settings
- `H` - History

### URL Parameters
Share specific statuses:
```
?reason=Coffee&duration=15&auto=true
```
- `reason` - AFK reason
- `duration` - Countdown minutes
- `auto=true` - Auto-start AFK mode
- `widget=true` - Widget/transparent mode

## Architecture

### Technology Stack
- **Pure HTML/CSS/JavaScript** - No framework dependencies
- **IndexedDB** - Client-side database for sessions
- **Canvas API** - Matrix rain effect, status cards
- **Web Audio API** - Sound effects
- **Service Worker** - PWA offline support
- **Wake Lock API** - Keep screen active
- **Notifications API** - Desktop alerts

### Smart Estimation Algorithm
```
1. Normalize reason (remove emoji, lowercase, trim)
2. Find similar sessions using:
   - Exact match (1.0)
   - Substring match (0.9)
   - Levenshtein distance (0.0-1.0)
3. Filter outliers (IQR method)
4. Calculate weighted average:
   - Recent sessions weighted more (7 days: 1.0x, 30 days: 0.5x, older: 0.25x)
   - Similarity score multiplier
5. Determine confidence:
   - High: 10+ sessions, low variance (<0.3)
   - Medium: 5+ sessions, medium variance (<0.5)
   - Low: Fewer sessions or high variance
```

### File Structure
```
afk/
├── index.html          # Main application (single-file)
├── service-worker.js   # PWA offline support
├── README.md           # This file
└── transcript.md       # Development notes
```

## Contributing

This project is open to contributions! Areas for improvement:
- Additional themes
- More achievements
- Enhanced analytics
- Language translations
- Bug fixes

## Privacy

**100% Privacy-Focused:**
- All data stored **locally** in your browser (IndexedDB)
- **No server**, no tracking, no analytics
- **No cookies**, no external requests (except QR code API)
- Export your data anytime
- Delete everything with one click

## Browser Support

| Browser | Support | PWA | Wake Lock |
|---------|---------|-----|-----------|
| Chrome | ✅ Full | ✅ | ✅ |
| Edge | ✅ Full | ✅ | ✅ |
| Firefox | ✅ Full | ✅ | ❌ |
| Safari | ⚠️ Partial | ⚠️ | ❌ |
| Mobile | ✅ Full | ✅ | ✅ |

## License

MIT License - feel free to use, modify, and distribute!

## Acknowledgments

- Inspired by the need for better break tracking
- Built with ❤️ for productivity and wellness
- Special thanks to Claude for assistance in development

---

**Made with 😴 by [Your Name]**

🌟 Star this repo if you find it useful!
🐛 [Report bugs](https://github.com/yourusername/afk/issues)
💡 [Suggest features](https://github.com/yourusername/afk/issues)
