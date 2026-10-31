# chhandansi-binaries (ललितालालित-छन्दांसि)

[![Version: 2.1.0](https://img.shields.io/badge/version-2.1.0-green.svg)](https://github.com/lalitaalaalitah/chhandansi-binaries/releases)
[![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0.html)
[![Author: lalitaalaalitah](https://img.shields.io/badge/author-lalitaalaalitah-orange.svg)](https://www.lalitaalaalitah.com)

Official distribution repository for pre-compiled, standalone single-file executables of **`lalitaalaalitah_chhandAnsi`** (Comprehensive Sanskrit Metrical Recognition Engine & Multi-Script Prosody Platform).

- **Author**: `lalitaalaalitah`
- **Website**: [https://www.lalitaalaalitah.com](https://www.lalitaalaalitah.com)
- **GitHub**: [https://github.com/lalitaalaalitah](https://github.com/lalitaalaalitah)
- **Version**: `2.1.0`
- **Release Tag**: `v2.1.0`
- **Companion Guide**: [HOW_TO_USE.md](HOW_TO_USE.md)

---

## 🌟 Why Standalone Binaries?

- **Zero Prerequisites**: Runs natively without requiring Python, `pip`, `uv`, compilers, or external dependencies.
- **Self-Contained**: Packed with the complete metrical rules database (1,574+ meters), multi-script transliteration engine (*Aksharamukha*), SQLite cache, and embedded web GUI.
- **Instant Speed**: Starts in milliseconds with persistent SQLite WAL caching for sub-millisecond repeat scans.
- **Privacy First**: Fully offline; no telemetry, tracking, or network calls required.

---

## 📥 Available Downloads (v2.1.0)

Download the executable matching your platform from the [GitHub Releases](https://github.com/lalitaalaalitah/chhandansi-binaries/releases) page:

| Platform / Architecture | File Name | Format | Checksum |
| :--- | :--- | :--- | :--- |
| **macOS Apple Silicon (M1/M2/M3/M4)** | `chhandansi-darwin-arm64` | Standalone Executable | `SHA256SUMS.txt` |
| **macOS Apple Silicon (Tarball)** | `chhandansi-v2.1.0-darwin-arm64.tar.gz` | Compressed Archive | `SHA256SUMS.txt` |

---

## 🚀 Quick Start (macOS & Linux)

### 1. Download via Terminal

```bash
# Download latest Apple Silicon binary
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/download/v2.1.0/chhandansi-darwin-arm64

# Download SHA256 checksums
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/download/v2.1.0/SHA256SUMS.txt

# Verify checksum integrity
shasum -a 256 -c SHA256SUMS.txt
```

### 2. Make Executable & Place in PATH

```bash
chmod +x chhandansi-darwin-arm64
sudo mv chhandansi-darwin-arm64 /usr/local/bin/chhandansi
```

> **macOS Note**: If macOS displays an *unidentified developer* security prompt, clear the quarantine attribute:
> ```bash
> xattr -d com.apple.quarantine /usr/local/bin/chhandansi
> ```

### 3. Verify & Run

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

You can also install and update `chhandansi` using Homebrew via the official tap:

```bash
brew tap lalitaalaalitah/tap
brew install --cask lalitaalaalitah-chhandansi
```

To update when a new version is released:
```bash
brew upgrade --cask lalitaalaalitah-chhandansi
```

---

## 📖 Complete Documentation

For detailed usage, interactive REPL options, multi-script output, and text file batch processing, see [HOW_TO_USE.md](HOW_TO_USE.md).
