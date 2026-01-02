# EcoMorph User Guide

## Table of Contents

1. [Getting Started](#getting-started)
2. [Loading Images](#loading-images)
3. [Segmentation](#segmentation)
4. [Measurements](#measurements)
5. [Scaling](#scaling)
6. [Body Part Analysis](#body-part-analysis)
7. [Batch Processing](#batch-processing)
8. [Exporting Results](#exporting-results)
9. [Cloud Processing](#cloud-processing)
10. [Tips & Tricks](#tips--tricks)

## Getting Started

### First Launch

When you first open EcoMorph, the SAM3 model (~2GB) will be downloaded automatically. This only happens once — subsequent launches are fast.

## Loading Images

### Single Image

- Click **Load Image** button, or
- Use the **+** button in the Images panel

### Supported Formats

- JPEG (.jpg, .jpeg)
- PNG (.png)

## Segmentation

### Setting a Prompt

Type what you want to segment in the **Prompt** field:

| Prompt | What it segments |
|--------|------------------|
| `bee` | Bees, bumblebees |
| `flower` | Flower petals |
| `leaf` | Leaves |
| `insect` | Any insect |
| `ant` | Ants |
| `butterfly` | Butterflies |
| `ruler` | Rulers, scale bars |
| `brown square cardboard` | Reference cards |

### Adjusting Threshold

The **Threshold** slider (0.0 - 1.0) controls detection sensitivity:

- **Lower values (0.05-0.15)**: More detections, may include false positives
- **Higher values (0.3-0.5)**: Fewer, more confident detections

**Tip:** Start with 0.15 and adjust based on results.

### Running Analysis

1. Set your prompt and threshold
2. Select which features to extract (Area, Dimensions, Shape, Color)
3. Click **Run Analysis**

### Viewing Results

Switch between views using the tabs:

- **Original**: Your input image
- **Segmentation**: Binary mask showing detected objects
- **Overlay**: Original image with colored mask overlay

## Measurements

### Area

- **Total area**: Sum of all segmented pixels
- **Mean area**: Average per object
- **Count**: Number of objects detected

### Dimensions

- **Width**: Horizontal extent
- **Height**: Vertical extent
- **Midpoint width**: Width at vertical center (useful for body measurements)
- **Aspect ratio**: Width / Height

### Shape Metrics

- **Circularity**: How circular (1.0 = perfect circle)
- **Eccentricity**: How elongated (0 = circle, 1 = line)
- **Solidity**: Convex hull coverage
- **Compactness**: Perimeter² / Area relationship

### Color Analysis

- **RGB mean/std**: Average color in RGB space
- **HSV mean**: Hue, Saturation, Value
- **LAB mean**: Perceptually uniform color space
- **Dominant colors**: Top 5 colors and their proportions

## Scaling

### Why Scale?

Pixel measurements need conversion to real-world units (cm, mm) for scientific use.

### Reference-Based Scaling

Use when you have a known-size object in the image:

1. Set **Scaling Method** to "Reference-based"
2. Set **Reference Prompt** (e.g., "ruler", "brown square cardboard")
3. Enter **Reference Length** in cm
4. Run analysis

EcoMorph will detect the reference object and calculate pixels-per-cm.

### Distance-Based Scaling

Use when you know the camera-to-subject distance:

1. Set **Scaling Method** to "Distance-based"
2. Enter camera parameters:
   - Sensor width (mm)
   - Sensor height (mm)
   - Focal length (mm)
   - Distance to subject (cm)

**Tip:** Find sensor specs in your camera's manual or online.

## Body Part Analysis

Segment individual body parts of arthropods.

### Enabling Body Part Mode

1. Check **Enable body part analysis**
2. Select **Type**: insect, spider, ant, or bee
3. Run analysis

### What Gets Segmented
- Head, thorax, abdomen, legs, and antennae

### Body Part Results

Each body part gets individual measurements for area, dimensions, shape, and color.

## Batch Processing

Process multiple images with the same settings.

### Starting Batch Processing

1. Load multiple images into the gallery
2. Configure your settings (prompt, threshold, features, scaling)
3. Click **Batch Process**
4. Wait for all images to complete

### Batch Export

After batch processing:
- Click **Export All to CSV** for a combined spreadsheet
- All images' measurements in one file

## Exporting Results

### CSV Export

- **Single image**: Click **Copy** or save from Results panel
- **All images**: Click **Export All to CSV**

### Mask Export

- Click **Save View** to save the current view as PNG

## Cloud Processing

### Why Use Cloud?

- **Quality Results**: Better SAM3 segementation on GPU
- **Faster**: GPU acceleration (10x faster than CPU)


### Getting Started

1. Click **Cloud** status in bottom-right corner
2. Create an account or log in
3. Enable **Cloud Processing** in settings

### Free Tier

- 100 images/month free
- No credit card required

## Tips & Tricks

### Better Segmentation

1. **Use specific prompts**: "honey bee" works better than "insect"
2. **Good lighting**: Even lighting improves detection
3. **Clean backgrounds**: Solid backgrounds help
4. **Adjust threshold**: If missing objects, lower threshold

### Faster Processing

1. **Resize large images**: 1024px is usually sufficient
2. **Use cloud**: GPU is much faster than CPU
3. **Batch process**: More efficient than one-by-one

### Accurate Measurements

1. **Always use scaling**: Pixel measurements aren't comparable across images
2. **Consistent reference**: Use same reference object/size
3. **Check segmentation**: Edit masks if needed before measuring

## Troubleshooting

### "SAM3 not available"

The model is still downloading. Wait for it to complete.

### Segmentation misses objects

- Lower the threshold (try 0.05-0.10)
- Try a more specific prompt
- Check image quality

### Measurements seem wrong

- Verify scaling is configured correctly
- Check that reference object was detected
- Ensure mask covers the right area

### App crashes on startup

- Delete preferences: `~/.ecomorph/` (macOS) or `%APPDATA%\EcoMorph` (Windows)
- Reinstall the application

## Getting Help
- **Email**: eai6@psu.edu
