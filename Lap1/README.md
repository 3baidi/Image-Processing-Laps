# Lab 1: Basics of Image Representation

## Overview
This lab covers the fundamentals of digital image loading, visualization, format conversion, and pixel array representations using OpenCV, Pillow (PIL), Matplotlib, and NumPy.

---

## Tasks Implemented

### Task 1: Environment Setup & Test Images
* Generated standard grayscale benchmark test images (`cameraman.tif` and `lena_gray_256.tif`) directly into the local environment.

### Task 2: Loading and Visualizing Images
* Loaded and displayed images using OpenCV (`cv2.imread`) with grayscale colormaps.
* Loaded and displayed images using Pillow (`Image.open`) alongside Matplotlib.

### Task 3: Image Storing
* Saved processed image arrays to disk in JPEG format using OpenCV (`cv2.imwrite`) and PIL (`Image.save`).

### Task 4: Array Data Inspection
* Examined image matrix structures, printing array shapes and raw pixel intensity values.

---

## Files in this Directory
* `Lab1.ipynb`: Jupyter notebook containing all executed tasks and image outputs.
* `images/`: Local storage containing benchmark test images.
* `README.md`: Lab documentation and task breakdown.