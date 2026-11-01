# chhandansi-binaries (ललितालालित-छन्दांसि)

[![Latest Release](https://img.shields.io/github/v/release/lalitaalaalitah/chhandansi-binaries?color=green&label=release)](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest)
[![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0.html)
[![Author: lalitaalaalitah](https://img.shields.io/badge/author-lalitaalaalitah-orange.svg)](https://www.lalitaalaalitah.com)

Official distribution repository for pre-compiled, standalone single-file executables of **`lalitaalaalitah_chhandAnsi`** (Comprehensive Sanskrit Metrical Recognition Engine & Multi-Script Prosody Platform).

- **Author**: `lalitaalaalitah`
- **Website**: [https://www.lalitaalaalitah.com](https://www.lalitaalaalitah.com)
- **GitHub**: [https://github.com/lalitaalaalitah](https://github.com/lalitaalaalitah)
- **Version**: `3.0.0`
- **Latest Release**: [v3.0.0](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest)
- **Live Web Application**: [https://chhandaansi.lalitaalaalitah.com](https://chhandaansi.lalitaalaalitah.com) (also [https://chhandansi-863219144057.us-central1.run.app](https://chhandansi-863219144057.us-central1.run.app))
- **Companion Guide**: [HOW_TO_USE.md](HOW_TO_USE.md)

---

## 🌟 Why Standalone Binaries?

- **Zero Prerequisites**: Runs natively without requiring Python, `pip`, `uv`, compilers, or external dependencies.
- **Self-Contained**: Packed with the complete metrical rules database (1,574+ meters), multi-script transliteration engine (*Aksharamukha*), SQLite cache, and embedded web GUI.
- **Multi-Platform**: Native standalone single binaries available for macOS (Apple Silicon ARM64), Linux (x86_64), and Linux (ARM64/aarch64).
- **Instant Speed**: Starts in milliseconds with persistent SQLite WAL caching for sub-millisecond repeat scans.
- **Privacy First**: Fully offline; no telemetry, tracking, or network calls required.

---

## 📥 Available Downloads (Latest Release)

Download the standalone executable or compressed archive for your operating system and CPU architecture. All links below dynamically resolve to the latest stable release assets:

| Platform / Architecture | Standalone Executable | Compressed Archive | Checksum |
| :--- | :--- | :--- | :--- |
| **macOS Apple Silicon (M1/M2/M3/M4)** | [`chhandansi-darwin-arm64`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-darwin-arm64) | [`chhandansi-v3.0.0-darwin-arm64.tar.gz`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest) | [`SHA256SUMS.txt`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt) |
| **Linux 64-bit PC / Cloud (x86_64)** | [`chhandansi-linux-x86_64`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-x86_64) | [`chhandansi-v3.0.0-linux-x86_64.tar.gz`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest) | [`SHA256SUMS.txt`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt) |
| **Linux 64-bit ARM (aarch64 / RPi 4/5)** | [`chhandansi-linux-arm64`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-arm64) | [`chhandansi-v3.0.0-linux-arm64.tar.gz`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest) | [`SHA256SUMS.txt`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt) |

---

## 🚀 Quick Start (macOS & Linux)

### Option A: macOS (Apple Silicon M1/M2/M3/M4)

```bash
# 1. Download latest Apple Silicon binary & checksum
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-darwin-arm64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt

# 2. Verify checksum integrity
grep "chhandansi-darwin-arm64" SHA256SUMS.txt | shasum -a 256 -c -

# 3. Make executable & install to PATH
chmod +x chhandansi-darwin-arm64
sudo mv chhandansi-darwin-arm64 /usr/local/bin/chhandansi

# 4. Clear macOS Gatekeeper quarantine (if prompted)
xattr -d com.apple.quarantine /usr/local/bin/chhandansi 2>/dev/null || true
```

### Option B: Linux x86_64 (Intel / AMD 64-bit)

```bash
# 1. Download latest Linux x86_64 binary & checksum
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-x86_64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt

# 2. Verify checksum integrity
grep "chhandansi-linux-x86_64" SHA256SUMS.txt | sha256sum -c -

# 3. Make executable & install to PATH
chmod +x chhandansi-linux-x86_64
sudo mv chhandansi-linux-x86_64 /usr/local/bin/chhandansi
```

### Option C: Linux ARM64 (aarch64 / Raspberry Pi / Ampere)

```bash
# 1. Download latest Linux ARM64 binary & checksum
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-arm64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt

# 2. Verify checksum integrity
grep "chhandansi-linux-arm64" SHA256SUMS.txt | sha256sum -c -

# 3. Make executable & install to PATH
chmod +x chhandansi-linux-arm64
sudo mv chhandansi-linux-arm64 /usr/local/bin/chhandansi
```

### Verify Installation & Run

```bash
# Check version
chhandansi --version

# Run random classical verse scansion
chhandansi --example

# Start local interactive web application
chhandansi -w --port 8765
```

---

## 🍺 Homebrew Installation (macOS)

You can install and update `chhandansi` effortlessly using Homebrew via the official tap:

```bash
# Tap the repository
brew tap lalitaalaalitah/tap

# Install chhandansi
brew install --cask chhandansi
```

*(You can also use the full package identifier: `brew install --cask lalitaalaalitah-chhandansi`)*

To update when a new version is released:
```bash
brew upgrade --cask chhandansi
```

---

## 📖 Complete Documentation

For detailed usage, interactive REPL options, multi-script output, and text file batch processing, see [HOW_TO_USE.md](HOW_TO_USE.md).
