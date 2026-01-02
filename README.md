


<p align="center">
A cross-platform desktop music client for Stingray Music
</p>

<p align="center">
<img src="https://img.shields.io/badge/Electron-32.2.6-47848F?logo=electron&logoColor=white" alt="Electron" />
<img src="https://img.shields.io/badge/Vue.js-2-4FC08D?logo=vue.js&logoColor=white" alt="Vue.js" />
<img src="https://img.shields.io/badge/License-AGPL--3.0-blue.svg" alt="License" />
</p>

---

## 🎵 About

**Stingray Music Desktop** is a cross-platform desktop client for streaming music from Stingray Music. Built with modern web technologies including [Electron.js](https://electronjs.org), [Vue.js 2](https://vuejs.org), and [Webpack](https://webpack.js.org), this application provides a native desktop experience for enjoying your favorite music.

## ✨ Features

- 🎶 Full Stingray Music streaming support
- 🎨 Modern and intuitive user interface
- 🔊 Advanced audio features including:
  - Spatial audio support
  - Built-in equalizer
  - Audio enhancement options
- 🎮 Discord Rich Presence integration
- 📻 Last.fm scrobbling support
- 🎛️ Cast support (Chromecast, AirPlay)
- 🌐 Remote control via web interface
- 🎨 Theme support
- 🔌 Plugin system
- 🖥️ Cross-platform (Windows, macOS, Linux)

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher)
- [pnpm](https://pnpm.io/) (v9.15.0 or higher)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/bruhdev1290/Stingray-music-desktop.git
cd Stingray-music-desktop
```

2. Install dependencies:
```bash
pnpm install
```

3. Build the application:
```bash
pnpm run build
```

4. Start the application:
```bash
pnpm start
```

## 🔨 Building

### Development
```bash
pnpm run build    # Build TypeScript and compile LESS
pnpm start        # Start the application
```

### Distribution Builds

```bash
# Build for all platforms
pnpm run dist:all

# Platform-specific builds
pnpm run dist:win      # Windows
pnpm run dist:linux    # Linux
pnpm run dist          # Current platform
```

## 🛠️ Development

### Code Formatting
```bash
pnpm run format:check   # Check code formatting
pnpm run format:write   # Auto-format code
```

### Project Structure

```
├── src/
│   ├── main/          # Main process (Electron)
│   ├── renderer/      # Renderer process (Vue.js UI)
│   ├── preload/       # Preload scripts
│   ├── web-remote/    # Web remote interface
│   └── ciderkit/      # Core utilities
├── resources/         # Application resources
└── build/            # Build output
```

## 📝 License

This project is licensed under the **AGPL-3.0 License** - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

This project is based on [Cider](https://github.com/ciderapp/Cider), a cross-platform Apple Music client. We thank the original developers and contributors for their excellent work.

## ⚠️ Disclaimer

This is an independent community project and is not affiliated with, endorsed by, or connected to Stingray Music or Apple Inc. All trademarks, service marks, trade names, product names, and logos are the property of their respective owners.

## 📫 Support

For issues, questions, or contributions, please visit the [GitHub Issues](https://github.com/bruhdev1290/Stingray-music-desktop/issues) page.
