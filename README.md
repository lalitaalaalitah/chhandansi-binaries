# chhandansi-binaries (ललितालालित-छन्दांसि)

[![Latest Release](https://img.shields.io/github/v/release/lalitaalaalitah/chhandansi-binaries?color=green&label=release)](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest)
[![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0.html)
[![Author: lalitaalaalitah](https://img.shields.io/badge/author-lalitaalaalitah-orange.svg)](https://www.lalitaalaalitah.com)

Official distribution repository for pre-compiled, standalone single-file executables of **`lalitaalaalitah_chhandAnsi`** (Comprehensive Sanskrit Metrical Recognition Engine & Multi-Script Prosody Platform).

- **Author**: `lalitaalaalitah`
- **Website**: [https://www.lalitaalaalitah.com](https://www.lalitaalaalitah.com)
- **GitHub**: [https://github.com/lalitaalaalitah](https://github.com/lalitaalaalitah)
- **Version**: `4.0.0`
- **Latest Release**: [v4.0.0](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest)
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
| **macOS Apple Silicon (M1/M2/M3/M4)** | [`chhandansi-darwin-arm64`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-darwin-arm64) | [`chhandansi-v4.0.0-darwin-arm64.tar.gz`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest) | [`SHA256SUMS.txt`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt) |
| **Linux 64-bit PC / Cloud (x86_64)** | [`chhandansi-linux-x86_64`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-x86_64) | [`chhandansi-v4.0.0-linux-x86_64.tar.gz`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest) | [`SHA256SUMS.txt`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt) |
| **Linux 64-bit ARM (aarch64 / RPi 4/5)** | [`chhandansi-linux-arm64`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-arm64) | [`chhandansi-v4.0.0-linux-arm64.tar.gz`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest) | [`SHA256SUMS.txt`](https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt) |

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

---

## 🤝 Credits & Upstream Acknowledgements (कृतज्ञता-निर्देशः)

**`lalitaalaalitah_chhandAnsi`** builds upon and synthesizes decades of scholarship, open-source computational linguistics, and foundational prosody datasets. We gratefully acknowledge and credit the following upstream repositories, scholars, and open-source projects:

### 1. Foundational Sanskrit Metrical Engines & Datasets
1. **`sanskrit` (Sanskrit Metres)** by **Shreevatsa R**
   - **Repository**: [https://github.com/shreevatsa/sanskrit](https://github.com/shreevatsa/sanskrit)
   - **Web Application**: [http://sanskritmetres.appspot.com/](http://sanskritmetres.appspot.com/)
   - **Contribution**: Pioneered modern open-source algorithmic Sanskrit metrical scansion and syllabification in Python. Provided the foundational core meter catalogs, including Dr. R. Ganesh's curated core meters, the *Vṛttaratnākara* collection, and miscellaneous classical meters.

2. **`chanda` (*Chandojñānam*)** by **Hrishikesh Terdalkar & Prof. Arnab Bhattacharya** (Department of Computer Science & Engineering, IIT Kanpur)
   - **Repositories**: [https://github.com/hrishikeshrt/chanda](https://github.com/hrishikeshrt/chanda) & [https://github.com/hrishikeshrt/chandojnanam](https://github.com/hrishikeshrt/chandojnanam)
   - **Web Portal**: [https://sanskrit.iitk.ac.in/jnanasangraha/chanda/](https://sanskrit.iitk.ac.in/jnanasangraha/chanda/)
   - **Academic Publication**: *Chandojñānam: A System for Identification and Analysis of Sanskrit Meters*, 18th World Sanskrit Conference, Canberra, Australia (2023).
   - **Contribution**: Extensive structured classification datasets across *sama-vṛtta*, *ardhasama-vṛtta*, *viṣama-vṛtta*, *upajāti*, and *mātrā-vṛtta*, providing foundational data for our 1,574+ meter merged corpus.

3. **`chandas`** by **Arun Prasad**
   - **Repository**: [https://github.com/akprasad/chandas](https://github.com/akprasad/chandas) (developed collaboratively with the `sanskrit-programmers` & `sanskrit-lexicon` initiatives)
   - **Contribution**: Early Pythonic abstractions for pattern matching, Jāti/Āryā metrical scansion, and syllable grouping heuristics.

### 2. Multi-Script Transliteration & Indic Phonetics
- **`aksharamukha`** by **Vinodh Rajan**
  - **Repository**: [https://github.com/virtualvinodh/aksharamukha-python](https://github.com/virtualvinodh/aksharamukha-python)
  - **Website**: [https://aksharamukha.appspot.com/](https://aksharamukha.appspot.com/)
  - **Contribution**: The authoritative multi-script conversion engine powering lossless transliteration across Devanagari, Grantha, Telugu, Kannada, Malayalam, Bengali, Sharada, IAST, and 28+ Indic scripts and romanization systems.

### 3. User Interface & Typography
- **Catppuccin Palette**
  - **Repository**: [https://github.com/catppuccin/catppuccin](https://github.com/catppuccin/catppuccin)
  - **Contribution**: Soothing pastel color palette powering the Web UI's Mocha (dark) and Latte (light) themes.
- **Adishila Font Family**
  - **Website**: [https://adishila.com/fonts/](https://adishila.com/fonts/)
  - **Contribution**: Authentic traditional Devanagari typography with rendering support for complex classical ligatures, conjuncts (*saṃyoga*), and Vedic/classical diacritics.

### 4. Classical Sanskrit Prosodic Treatises (आकरग्रन्थाः)
Our metrical definitions, lakṣaṇas, and phonetic rules strictly adhere to the classical tradition:
- **Piṅgalācārya** (पिङ्गलाचार्यः) — *Chandaḥ-śāstram / Piṅgala-sūtrāṇi* (छन्दःशास्त्रम् / पिङ्गलसूत्राणि), especially canonical sūtras *गन्ते* (१.१०), *ध्रादिपरः* (१.११), and *हे* (१.१२).
- **Kedārabhaṭṭa** (केदारभट्टः) — *Vṛttaratnākaraḥ* (वृत्तरत्नाकरः).
- **Kālidāsa** (कालिदासः) (attributed) — *Śrutabodhaḥ* (श्रुतबोधः).
- **Gaṅgādāsa** (गङ्गादासः) — *Chandomañjarī* (छन्दोमञ्जरी).

---

## 📜 License & Attribution

This project is distributed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.
- **Author**: `lalitaalaalitah`
- **Website**: [https://www.lalitaalaalitah.com](https://www.lalitaalaalitah.com)
- **GitHub Profile**: [https://github.com/lalitaalaalitah](https://github.com/lalitaalaalitah)
