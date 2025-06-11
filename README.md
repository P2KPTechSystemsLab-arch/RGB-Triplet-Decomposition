

# 📊 Optode RGB Channel Response Visualization Toolkit

A high-resolution color channel visualization and histogram analysis tool for optode-derived images, designed to support soil pH sensing and environmental monitoring workflows. Built with Python and compatible with standard scientific image formats (e.g., `.png`, `.tiff`), this script processes RGB and grayscale representations and visualizes pixel intensity distributions across spatial and statistical domains.

---

## 🔧 Features

* ✅ RGB + grayscale decomposition of optode images
* ✅ Histogram visualization for red, green, blue, and grayscale channels
* ✅ Customizable axis ticks, grid styling, and publication-quality formatting
* ✅ Compatible with scientific image stacks (e.g., 8-bit/16-bit `.png`, `.tif`)
* ✅ Elegant, high-resolution plots using `matplotlib` and `skimage`

---

## 📂 Folder Structure & Example Input

Ensure your image path points to an RGB or RGBA image (alpha channel will be dropped if present).

```
project/
├── your_script.py
├── data/
│   └── SN_ST_R0PH_00014.png
```

---

## 🖼️ Preview Output

Top row: intensity maps (R, G, B, grayscale)
Bottom row: corresponding histograms with axis formatting

---

## 🧪 Requirements

| Package         | Version |
| --------------- | ------- |
| `opencv-python` | ≥4.5    |
| `numpy`         | ≥1.21   |
| `matplotlib`    | ≥3.4    |
| `scikit-image`  | ≥0.19   |

Install via pip:

```bash
pip install opencv-python numpy matplotlib scikit-image
```

---

## 🚀 Quick Start

```python
import cv2 as cv
import numpy as np
from matplotlib import pyplot as plt
from skimage import io

# Load image
image_path = r'path_to_your_image.png'
image = io.imread(image_path)
image = cv.resize(image[:, :, :3], (512, 512))  # Drop alpha channel if present

# Split channels
R, G, B = image[:, :, 0], image[:, :, 1], image[:, :, 2]
gray = cv.cvtColor(image, cv.COLOR_RGB2GRAY)

# Plot spatial maps + histograms...
```

See full code in [`Main_model_Optode_pH.ipynb`](https://github.com/P2KPTechSystemsLab-arch/pHChromoCODE/blob/main/Main%20model_Optode_pH%20%28Fast%20run_Group%29.ipynb)

---


