# How to Download, Verify, and Use chhandansi Standalone Binaries

- **Software**: `lalitaalaalitah_chhandAnsi` (Standalone Binary Edition)
- **Author**: `lalitaalaalitah`
- **Website**: [https://www.lalitaalaalitah.com](https://www.lalitaalaalitah.com)
- **GitHub**: [https://github.com/lalitaalaalitah](https://github.com/lalitaalaalitah)
- **Version**: `2.1.0`
- **License**: AGPL-3.0

---

## १. प्रतिष्ठापनम् (Installation & Setup)

### Step 1: Download Binary and Checksum

```bash
# Download binary asset for macOS arm64
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/download/v2.1.0/chhandansi-darwin-arm64

# Download SHA256 checksums file
curl -LO https://github.com/lalitaalaalitah/chhandansi-binaries/releases/download/v2.1.0/SHA256SUMS.txt
```

### Step 2: Verify Checksum

Ensure that the cryptographic hash matches the official release:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

Expected output:
```
chhandansi-darwin-arm64: OK
```

### Step 3: Install into System PATH

```bash
chmod +x chhandansi-darwin-arm64
sudo mv chhandansi-darwin-arm64 /usr/local/bin/chhandansi
```

*(Alternatively, place in `~/.local/bin/chhandansi` if you do not have root privileges).*

### Step 4: macOS Gatekeeper Quarantine Clearance

If macOS flags the standalone binary with a security popup because it was downloaded from the web:

```bash
xattr -d com.apple.quarantine /usr/local/bin/chhandansi
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

Launch the embedded Catppuccin web interface:

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

Simply download the latest binary from [Releases](https://github.com/lalitaalaalitah/chhandansi-binaries/releases), verify checksums, and overwrite `/usr/local/bin/chhandansi`.

### Upgrading via Homebrew

```bash
brew update
brew upgrade --cask lalitaalaalitah-chhandansi
```

