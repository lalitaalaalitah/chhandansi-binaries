# How to Download, Verify, and Use chhandansi Standalone Binaries

- **Software**: `lalitaalaalitah_chhandAnsi` (Standalone Binary Edition)
- **Author**: `lalitaalaalitah`
- **Website**: [https://www.lalitaalaalitah.com](https://www.lalitaalaalitah.com)
- **GitHub**: [https://github.com/lalitaalaalitah](https://github.com/lalitaalaalitah)
- **Version**: `3.0.0`
- **License**: AGPL-3.0

---

## १. प्रतिष्ठापनम् (Installation & Setup)

### विधिः १: Homebrew Tap द्वारा (Recommended for macOS)

If you use Homebrew on macOS, install `chhandansi` with a single command:

```bash
# Tap the repository
brew tap lalitaalaalitah/tap

# Install chhandansi
brew install --cask chhandansi
```

*(You can also use the full cask name: `brew install --cask lalitaalaalitah-chhandansi`)*

Homebrew places `chhandansi` directly in your PATH (`/opt/homebrew/bin/chhandansi`) and clears quarantine attributes automatically.

---

### विधिः २: Standalone Binary प्रत्यक्ष-अवरोहणम् (Direct Download)

Pre-compiled standalone executables are available for macOS and Linux. All download links below dynamically point to the latest stable release.

#### macOS (Apple Silicon M1/M2/M3/M4)

```bash
# 1. Download binary and checksum
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-darwin-arm64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt

# 2. Verify checksum
grep "chhandansi-darwin-arm64" SHA256SUMS.txt | shasum -a 256 -c -

# 3. Make executable and install to PATH
chmod +x chhandansi-darwin-arm64
sudo mv chhandansi-darwin-arm64 /usr/local/bin/chhandansi

# 4. Clear Gatekeeper quarantine (if prompted by macOS)
xattr -d com.apple.quarantine /usr/local/bin/chhandansi 2>/dev/null || true
```

#### Linux x86_64 (64-bit Intel / AMD)

```bash
# 1. Download binary and checksum
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-x86_64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt

# 2. Verify checksum
grep "chhandansi-linux-x86_64" SHA256SUMS.txt | sha256sum -c -

# 3. Make executable and install to PATH
chmod +x chhandansi-linux-x86_64
sudo mv chhandansi-linux-x86_64 /usr/local/bin/chhandansi
```

#### Linux ARM64 (aarch64 / Raspberry Pi 4/5 / Ampere)

```bash
# 1. Download binary and checksum
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/chhandansi-linux-arm64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/latest/download/SHA256SUMS.txt

# 2. Verify checksum
grep "chhandansi-linux-arm64" SHA256SUMS.txt | sha256sum -c -

# 3. Make executable and install to PATH
chmod +x chhandansi-linux-arm64
sudo mv chhandansi-linux-arm64 /usr/local/bin/chhandansi
```

---

## २. मुख्य-आदेशाः (Core Command Reference)

### 1. Direct Verse Scansion (प्रत्यक्ष-परीक्षणम्)

Pass any Sanskrit verse (Devanagari, Telugu, Kannada, Malayalam, Bengali, Grantha, IAST, or SLP1) as an argument:

```bash
chhandansi "कश्चित् कान्ताविरहगुरुणा स्वाधिकारात्प्रमत्तः
शापेनास्तङ्गमितमहिमा वर्षभोग्येण भर्तुः ।
यक्षश्चक्रे जनकतनयास्नानपुण्योदकेषु
स्निग्धच्छायातरुषु वसतिं रामगिर्याश्रमेषु ॥"
```

### 2. Random Example Discovery (यादृच्छिकोदाहरणम्)

Randomly choose and scan a verified classical verse from the SQLite database, classical treatises (*Vṛttaratnākara*, *Chhandomañjarī*, *Piṅgala*), and literary corpus:

```bash
chhandansi --example
```

You can also specify a target meter name to pull a random verified classical example for that specific meter:

```bash
chhandansi --example "मन्दाक्रान्ता"
chhandansi --example "अनुष्टुप्"
chhandansi --example "भुजङ्गप्रयातम्"
chhandansi --example "शालिनी"
```

### 3. Interactive Web GUI (जालपृष्ठ-रूपम्)

You can access the live hosted web application directly at [https://chhandaansi.lalitaalaalitah.com](https://chhandaansi.lalitaalaalitah.com) (or [https://chhandansi-863219144057.us-central1.run.app](https://chhandansi-863219144057.us-central1.run.app)).

Alternatively, launch the embedded Catppuccin web interface locally from the binary:

```bash
chhandansi -w --port 8765
```

Open [http://127.0.0.1:8765](http://127.0.0.1:8765) in your web browser. Includes:
- Multi-script live transliteration (Telugu, Kannada, Malayalam, Bengali, Devanagari, IAST).
- Syllable-by-syllable interactive weight cards with laghu/guru highlights.
- Visual alignment matrix with color-coded matches (`✓`) and divergences (`✗`).
- Classical treatise definition (लक्षणम्), caesura rule (यतिनियमः), and randomized classical verse (प्रसिद्धोदाहरणम्).

### 4. Interactive Terminal REPL (संवादात्मक-रूपम्)

Start an interactive terminal prompt:

```bash
chhandansi -i
```

Type or paste verses; press `Enter` to analyze immediately. Type `exit` or `quit` to leave.

### 5. Multi-Script Transliterated Output (बहुलिपि-निर्गमः)

Render the scansion results, meter names, gaṇas, and alignment matrices in your preferred Indic script or Roman transliteration:

```bash
# Output in Telugu script
chhandansi "कश्चित् कान्ताविरहगुरुणा..." -s Telugu

# Output in IAST
chhandansi "कश्चित् कान्ताविरहगुरुणा..." -s IAST

# Output in Kannada
chhandansi "कश्चित् कान्ताविरहगुरुणा..." -s Kannada

# Output in Grantha
chhandansi "कश्चित् कान्ताविरहगुरुणा..." -s Grantha
```

### 6. Batch Text File Scansion (सञ्चिका-परीक्षणम्)

Scan a text file containing hundreds of verses:

```bash
# Summary table of recognized meters
chhandansi -f padya_corpus.txt --summary

# Structured JSON output for downstream NLP / digital humanities pipelines
chhandansi -f padya_corpus.txt --json > results.json
```

---

## ३. नूतन-संस्करण-नवीनीकरणम् (Upgrading to New Versions)

### Upgrading via Binary

Because the download URLs use the dynamic `/releases/latest/download/` path, you can re-run the download commands at any time to upgrade to the latest stable binary.

### Upgrading via Homebrew

```bash
brew update
brew upgrade --cask chhandansi
```
