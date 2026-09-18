# Lab 2: Digital Image Fundamentals

## Overview
This lab covers fundamental digital image representation and pixel-level manipulation techniques, including sampling, quantization, arithmetic operations, and bitwise set operations using OpenCV, Pillow, and NumPy.

---

## Tasks Implemented

### Task 1: Image Sampling and Quantization
* **Sampling:** Implemented spatial resolution reduction using nearest-neighbor downsampling (`cv2.INTER_NEAREST`) with a sampling factor of 4.
* **Quantization:** Reduced the intensity levels (gray-level resolution) down to 8 discrete bins using integer floor division.
* **Visualization:** Plotted the original, downsampled, and quantized representations side by side.

### Task 2: Arithmetic Operations
* Resized both input images (`lena_gray_256.tif` and `cameraman.tif`) to standard matching dimensions ($400 \times 400$) using Lanczos resampling.
* **Image Subtraction:** Computed difference matrix between the two images, properly clamped to the $[0, 255]$ range.
* **Constant Addition:** Scaled image brightness by adding a constant offset ($+175$) with pixel clipping to prevent byte overflow.

### Task 3: Sets and Logical Operations
Applied bitwise logic directly on 8-bit grayscale pixel values:
* **Set Difference ($A \setminus B$):** Evaluated as $A \text{ AND } (\sim B)$.
* **Symmetric Difference ($A \oplus B$):** Computed bitwise XOR.
* **Intersection ($A \cap B$):** Computed bitwise AND.

---

## Files in this Directory
* `Lab2.ipynb`: Jupyter notebook containing complete implementations and rendered visual outputs.
* `README.md`: Lab task summary and operational explanations.