# Lab 5: Spatial Filtering – Smoothing and Sharpening

## Overview
This lab implements fundamental spatial domain filtering algorithms for image smoothing and sharpening using OpenCV, NumPy, and Matplotlib. It covers low-pass box filtering, multi-scale Gaussian smoothing, unsharp masking, and second-order derivative sharpening using the Laplacian operator.

---

## Tasks Implemented

### Procedural Task: Unsharp Masking
* Generated a blurred mask using a Gaussian kernel ($\sigma = 2$).
* Calculated high-frequency details and applied unsharp masking with scaling factor $\text{amount} = 1.5$:
  $$\text{Sharpened} = \text{clip}(\text{Image} + \text{amount} \times (\text{Image} - \text{Blurred}), 0, 1)$$

### Assessment Task 1: Box Filtering
* Applied a normalized $7 \times 7$ box filter via `cv2.blur` to demonstrate spatial neighborhood averaging and smoothing.

### Assessment Task 2: Multi-scale Gaussian Smoothing
* Convolved the test image with two distinct Gaussian kernel dimensions ($5 \times 5$ and $21 \times 21$) using `cv2.GaussianBlur` to analyze the effect of neighborhood size on edge attenuation.

### Assessment Task 3: Laplacian Sharpening
* Converted the image to `float32` representation.
* Computed second-order spatial derivatives using `cv2.Laplacian` ($3 \times 3$ kernel, `cv2.CV_32F`).
* Restored and highlighted edge transitions via:
  $$\text{Sharpened} = \text{clip}(\text{Image} - \text{Laplacian}, 0, 1)$$

---

## Files in this Directory
* `Lab5.ipynb`: Jupyter notebook containing all implementations and inline comparison figures.
* `images/`: Directory containing benchmark images used in filtering tests.
* `README.md`: Summary and technical overview of Lab 5 tasks.