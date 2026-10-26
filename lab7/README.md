# Lab 7: Laplacian Sharpening and Noise Filtering on Color Images

## Overview
This lab demonstrates spatial-domain image enhancement and restoration techniques applied to **color (BGR/RGB) images**. We explore image sharpening via the Laplacian operator, then simulate four noise models and restore the corrupted images using arithmetic, geometric, harmonic, contra-harmonic, median, max/min and midpoint filters.

---

## Tasks Implemented

### Task 1: Laplacian Sharpening (Lab 7A)
* Loaded the test image in color using `cv2.imread` and converted BGR to RGB for display.
* Defined the 3x3 Laplacian kernel manually and applied it to each color channel with `cv2.filter2D`:
  $$\nabla^2 f = f(x+1,y) + f(x-1,y) + f(x,y+1) + f(x,y-1) - 4f(x,y)$$
* Converted the signed response back to 8-bit using `cv2.convertScaleAbs`.
* Produced the sharpened image by adding the Laplacian to the original with saturation (`cv2.add`) to avoid `uint8` overflow:
  $$g(x,y) = f(x,y) + |\nabla^2 f(x,y)|$$
* Repeated the process with a Gaussian blur (`cv2.GaussianBlur`) followed by the built-in `cv2.Laplacian` to reduce noise amplification.

### Task 2: Noise Models (Lab 7B)
* Generated four noise types on a color image, with noise added independently to every channel:
  * Gaussian noise (mean 0, variance 0.01)
  * Salt & Pepper noise (4% of pixels, set to white or black across all channels)
  * Exponential noise (scale 10)
  * Uniform noise (range -20 to 20)

### Task 3: Mean Filters
* Arithmetic mean filter using both `cv2.blur` and a manual averaging kernel with `cv2.filter2D`.
* Geometric mean filter, implemented via the log transform:
  $$\hat{f}(x,y) = \left[ \prod_{(s,t)\in S_{xy}} g(s,t) \right]^{\frac{1}{mn}}$$
* Harmonic mean filter:
  $$\hat{f}(x,y) = \frac{mn}{\sum_{(s,t)\in S_{xy}} \frac{1}{g(s,t)}}$$
* Contra-harmonic mean filter, where Q > 0 removes pepper noise and Q < 0 removes salt noise:
  $$\hat{f}(x,y) = \frac{\sum_{(s,t)\in S_{xy}} g(s,t)^{Q+1}}{\sum_{(s,t)\in S_{xy}} g(s,t)^{Q}}$$

### Task 4: Order-Statistic Filters
* Median filter using `cv2.medianBlur` (effective against Salt & Pepper noise).
* Max filter (`cv2.dilate`) to remove pepper noise and Min filter (`cv2.erode`) to remove salt noise.
* Midpoint filter, the average of the max and min in each neighborhood:
  $$\hat{f}(x,y) = \frac{1}{2}\left[ \max_{(s,t)\in S_{xy}} g(s,t) + \min_{(s,t)\in S_{xy}} g(s,t) \right]$$

---

## Files in this Directory
* `Lab_7__A__Laplacian_Filter.ipynb`: Jupyter notebook with the Laplacian sharpening code for color images.
* `Lab_7__B__Maths___Statistics_Filters.ipynb`: Jupyter notebook with the noise generation and filtering code for color images.
* `moon.jpg`, `noise.jpg`: Input color images used in the notebooks.
* `README.md`: Technical documentation of the spatial filtering workflows.
