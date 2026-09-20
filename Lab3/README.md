# Lab 3: Image Manipulations using OpenCV

## Overview
This lab covers reading, writing, and color space representations using OpenCV, alongside fundamental geometric transformations (scaling, rotation, affine shearing) and point-wise intensity transformations (image negative, logarithmic transform, power-law gamma correction).

---

## Implemented Tasks

### Procedural Demonstrations
* Reading color images and decoding them to Grayscale.
* Saving processed images to disk (`cv2.imwrite`).
* Conversion between BGR and YUV color models, separating Y (luminance), U (blue projection), and V (red projection) channels.

### Task 1: Geometric Transformations
1. **Enlargement:** Upscaled spatial dimensions by $1.5\times$ using linear interpolation (`cv2.INTER_LINEAR`).
2. **Rotation:** Rotated image $120^\circ$ counter-clockwise around its central coordinate via `cv2.getRotationMatrix2D` and `cv2.warpAffine`.
3. **Shear:** Constructed an affine shearing matrix ($s_x = 0.3$) and warped coordinates to produce directional skew without vertical compression.

### Task 2: Intensity Transformations
1. **Negative Image:** Inverted intensity mapping via $s = 255 - r$.
2. **Log Transformation:** Dynamic range expansion using $s = c \cdot \log(1 + r)$, where constant $c = \frac{255}{\log(1 + \max(r))}$.
3. **Power-Law (Gamma) Correction:** Applied $s = 255 \cdot \left(\frac{r}{255}\right)^\gamma$ with $\gamma = 0.5$ to expand dark shadows and enhance lower-tone contrast.

---

## Files in this Directory
* `Lab3.ipynb`: Jupyter notebook containing all code, parameter explanations, and output plots.
* `images/`: Directory containing input test images and generated outputs.
* `README.md`: Lab task summary and operational explanations.