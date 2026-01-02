# Changelog

All notable changes to EcoMorph will be documented in this file.

## [0.1.0] - 2026-01-02

### 🎉 Initial Public Release

First public release of EcoMorph for macOS and Windows.

### Features

- **SAM3 Integration** — Segment Anything Model 3 for prompt-based segmentation
- **Text prompts** — Segment any structure by typing its name (e.g., "bee", "flower", "leaf")
- **Area measurement** — Total area in pixels or real-world units
- **Dimensional analysis** — Width, height, aspect ratio
- **Shape metrics** — Circularity, eccentricity, solidity, compactness
- **Color analysis** — RGB, HSV, LAB color spaces + dominant color extraction
- **Body part segmentation** — Segment individual body parts for insects, spiders, ants, bees
- **Reference-based scaling** — Convert pixels to cm using a reference object in the image
- **Distance-based scaling** — Convert pixels using camera parameters
- **Batch processing** — Process multiple images with consistent settings
- **Mask editing** — Manually refine segmentation masks
- **CSV export** — Export all measurements to spreadsheet
- **PNG mask export** — Save segmentation masks as images
- **Cloud processing** — Optional GPU-accelerated processing (requires account)
- **Local processing** — Works fully offline on CPU

### Supported Platforms

- macOS (Apple Silicon & Intel)
- Windows 10/11


---

## Future Releases

Stay tuned for:
- Linux support
- Additional arthropod types
- Improved batch processing UI
- Plugin system for custom measurements
