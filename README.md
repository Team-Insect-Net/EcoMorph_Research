# EcoMorph

**Automated morphological trait quantification for ecological research**

EcoMorph uses SAM3 (Segment Anything Model 3) to measure biological structures from images — insects, flowers, leaves, and more — without manual annotation.

[![Download for macOS](https://img.shields.io/badge/Download-macOS-blue?style=for-the-badge&logo=apple)](https://drive.google.com/file/d/1o5B8aSEodlEnwgWBaIY69DfBb7hq9yQJ/view?usp=sharing)
[![Download for Windows](https://img.shields.io/badge/Download-Windows-blue?style=for-the-badge&logo=windows)](https://drive.google.com/file/d/1O5ZPwN4vbLsIWhDpF483rfmS46E1bFmA/view?usp=sharing)
[![Download for Linux](https://img.shields.io/badge/Download-Linux-blue?style=for-the-badge&logo=linux)](https://drive.google.com/file/d/12D3Ps-DmVq04qM1EwV0s1kQZ9VhD34Xv/view?usp=sharing)

![EcoMorph Screenshot](docs/screenshot.png)

## Features

- **Prompt-based segmentation** — Type "flower", "insect", "leaf" to segment any structure
- **Zero training required** — Works out of the box on any organism
- **Comprehensive measurements** — Area, dimensions, shape metrics, color analysis
- **Body part analysis** — Segment individual body parts (head, thorax, wings, etc.)
- **Reference scaling** — Convert pixels to real-world units (cm, mm)
- **Batch processing** — Analyze hundreds of images automatically
- **Publication-ready exports** — CSV data + PNG masks

## Installation

### macOS

1. Download `EcoMorph-macOS.dmg` 
2. Open the DMG and drag EcoMorph to Applications
3. First launch: Right-click → Open (to bypass Gatekeeper)

### Windows

1. Download `EcoMorph-Windows.zip`
2. Extract the ZIP file
3. Run `EcoMorph.exe`

### Linux

1. Download `EcoMorph-Linux.tar.gz`
2. Extract: `tar -xzf EcoMorph-Linux.tar.gz`
3. Run: `./EcoMorph/EcoMorph`

> If you get "Permission denied", run: `chmod +x EcoMorph/EcoMorph`

**Note:** First run downloads the SAM3 model (~2GB). This takes a few minutes.

## Quick Start

1. **Load an image** — Click "Load Image" 
2. **Set your prompt** — e.g., "bee", "flower", "leaf"
3. **Run Analysis** — Click the green button
4. **Export results** — CSV for data, PNG for masks 

## What You Get

| Measurement | Description |
|-------------|-------------|
| **Area** | Total segmented area (px² or cm²) |
| **Dimensions** | Width, height, aspect ratio |
| **Shape** | Circularity, eccentricity, solidity |
| **Color** | RGB, HSV, LAB means + dominant colors |
| **Count** | Number of detected objects |

## Use Cases

- **Pollinator research** — Measure bee body size, intertegular distance
- **Plant phenotyping** — Floral display area, leaf area index
- **Entomology** — Insect morphometrics from specimen photos
- **Forest ecology** — Tree diameter from photos
- **Citizen science** — Process community-contributed images

## Documentation

- [User Guide](docs/user-guide.md)
- [Changelog](CHANGELOG.md)

## Citation

If you use EcoMorph in your research, please cite:

```bibtex
@software{ecomorph2026,
  title = {EcoMorph: Automated morphological trait quantification for ecological research},
  author = {Amoah, Edward I. and Patch, Harland M. and Grozinger, Christina M.},
  year = {2026},
  url = {https://github.com/Team-Insect-Net/EcoMorph_Research.git}
}
```

## Support

- **Email:** eai6@psu.edu