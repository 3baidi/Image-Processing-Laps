# Lab 4: Intensity Transformations and Spatial Domain Filtering

## Overview
This lab implements basic image intensity transformations, contrast adjustments, thresholding, and histogram processing techniques (contrast stretching, histogram equalization, and histogram specification/matching) using OpenCV, Scikit-Image, and Matplotlib.

---

## Tasks Implemented

### Task 1: Binary Thresholding
* Applied fixed global thresholding across arbitrary thresholds ($[0, 50, 100, 150, 200]$) using `cv2.threshold` to examine foreground and background binary segmentation.

### Task 2: Contrast Stretching
* Computed cumulative percentile bounds (2nd-98th and 3rd-80th percentiles via `np.percentile`).
* Rescaled intensity distributions across bounds using `skimage.exposure.rescale_intensity` and evaluated resulting histograms.

### Task 3: Histogram Equalization
* Linearized cumulative distribution function (CDF) to flatten the tonal histogram of low-contrast imagery using `skimage.exposure.equalize_hist`.

### Task 4: Histogram Matching
* Transferred multi-channel color histogram characteristics from a reference image (`rocket`) onto a target image (`chelsea`) using `skimage.exposure.match_histograms`.

---

## Files in this Directory
* `Lab4.ipynb`: Jupyter notebook containing executed code and all graphical comparison plots.
* `images/`: Local storage containing sample test benchmark images.
* `README.md`: Lab task summary and operational explanations.