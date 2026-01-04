


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

## 📦 Building and Deploying

### Windows

#### Prerequisites
- **Node.js** v18 or higher ([Download](https://nodejs.org/))
- **pnpm** v9.15.0 or higher (Install via: `npm install -g pnpm`)
- **Visual Studio Build Tools** or **Visual Studio 2019+** with "Desktop development with C++" workload
- **Python 3.x** (required for node-gyp)
- **Git** for cloning the repository

#### Build Steps

1. **Clone and Setup**
   ```bash
   git clone https://github.com/bruhdev1290/Stingray-music-desktop.git
   cd Stingray-music-desktop
   pnpm install
   ```

2. **Build the Application**
   ```bash
   pnpm run build
   ```

3. **Create Windows Installer**
   ```bash
   # Standard Windows build (creates NSIS installer)
   pnpm run dist:win
   ```
   
   The installer will be created in the `dist/` directory as `Stingray Music-Setup-{version}.exe`

4. **Alternative Windows Builds**
   ```bash
   # Build for Windows Store (APPX package)
   pnpm run winget
   
   # Build for Microsoft Store testing
   pnpm run mstest
   ```

#### Deployment

**Local Installation:**
- Run the generated `.exe` installer from the `dist/` folder
- The application will be installed to `%LOCALAPPDATA%\Programs\Stingray Music`

**Distribution:**
- Share the `.exe` installer file from `dist/` directory
- For enterprise deployment, use the installer with silent install flags: `/S` (silent) or `/D=path` (custom directory)

### Linux

#### Prerequisites
- **Node.js** v18 or higher
- **pnpm** v9.15.0 or higher (Install via: `npm install -g pnpm`)
- **Build essentials**: `build-essential`, `libssl-dev`, `rpm` (for RPM builds)
- **Git** for cloning the repository

#### Distribution-Specific Setup

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install -y build-essential git nodejs npm python3
sudo npm install -g pnpm
```

**Fedora/RHEL/CentOS:**
```bash
sudo dnf install -y gcc-c++ make git nodejs npm python3 rpm-build
sudo npm install -g pnpm
```

**Arch Linux:**
```bash
sudo pacman -S base-devel git nodejs npm python
sudo npm install -g pnpm
```

#### Build Steps

1. **Clone and Setup**
   ```bash
   git clone https://github.com/bruhdev1290/Stingray-music-desktop.git
   cd Stingray-music-desktop
   pnpm install
   ```

2. **Build the Application**
   ```bash
   pnpm run build
   ```

3. **Create Linux Packages**
   ```bash
   # Standard Linux build (creates AppImage, .deb, and .rpm)
   pnpm run dist:linux
   ```
   
   The following packages will be created in the `dist/` directory:
   - `Stingray Music-{version}.AppImage` - Universal Linux package
   - `stingray-music_{version}_amd64.deb` - Debian/Ubuntu package
   - `stingray-music-{version}.x86_64.rpm` - Fedora/RHEL package

4. **Steam Deck Build**
   ```bash
   pnpm run steamdeck
   ```

#### Deployment

**AppImage (All distributions):**
```bash
chmod +x Stingray\ Music-*.AppImage
./Stingray\ Music-*.AppImage
```

**Debian/Ubuntu (.deb):**
```bash
sudo dpkg -i stingray-music_*.deb
sudo apt-get install -f  # Install dependencies if needed
```

**Fedora/RHEL (.rpm):**
```bash
sudo rpm -i stingray-music-*.rpm
# Or using dnf:
sudo dnf install ./stingray-music-*.rpm
```

**Arch Linux (from source):**
```bash
# Create and install using makepkg
makepkg -si
```

#### Flatpak Build

For Flatpak distribution:
```bash
# Install flatpak-builder
sudo apt install flatpak-builder  # Ubuntu/Debian
sudo dnf install flatpak-builder  # Fedora

# Build Flatpak
flatpak-builder --repo=repo --force-clean build-dir flatpak/flathub.json
```

### Troubleshooting

**Windows:**
- If build fails with "node-gyp" errors, ensure Visual Studio Build Tools are installed
- Run `npm config set msvs_version 2019` (or your VS version) if needed
- Clear cache: `pnpm store prune` and retry

**Linux:**
- If FUSE errors occur with AppImage: `sudo apt install libfuse2` (Ubuntu 22.04+)
- For permission issues: Ensure your user is in the required groups
- Missing dependencies: Use `ldd` to check: `ldd dist/linux-unpacked/stingray-music`

**Common Issues:**
- `EACCES` permission errors: Try with `sudo` or fix npm permissions
- Out of memory during build: Increase Node.js heap size: `export NODE_OPTIONS="--max-old-space-size=4096"`
- TypeScript errors: Ensure you're using Node.js v18 or higher

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
