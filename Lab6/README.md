# Lab 6: Filtering in the Frequency Domain

## Overview
This lab demonstrates image filtering techniques transformed into the 2D Fourier (frequency) domain using Fast Fourier Transforms (FFT). We explore high-pass filtering via the continuous Laplacian operator and spatial-to-frequency kernel embedding for Sobel gradient edge detection.

---

## Tasks Implemented

### Task 1: Frequency Domain Laplacian Operator
* Transformed the cameraman test benchmark to the frequency spectrum using 2D FFT (`np.fft.fft2`).
* Constructed a continuous second-derivative Laplacian transfer function:
  $$H(u, v) = -4\pi^2(u^2 + v^2)$$
* Applied frequency-domain point-wise multiplication and recovered the sharpened spatial boundary map via the Inverse FFT (`np.fft.ifft2`).

### Task 2: Frequency Domain Sobel Gradient Filtering
* Embedded $3 \times 3$ horizontal and vertical Sobel spatial impulse kernels into zero-padded full-dimension grids.
* Aligned spatial centers with phase origins via circular shifts (`ifftshift`) before taking the discrete Fourier transform.
* Convolved filters with image spectrum via complex multiplication:
  $$G_x = \text{Re}\{\mathcal{F}^{-1}\{F(u, v) \cdot H_{S_x}(u, v)\}\}$$
  $$G_y = \text{Re}\{\mathcal{F}^{-1}\{F(u, v) \cdot H_{S_y}(u, v)\}\}$$
* Synthesized the comprehensive edge magnitude:
  $$M = \sqrt{G_x^2 + G_y^2}$$

---

## Files in this Directory
* `Lab6.ipynb`: Jupyter notebook with complete FFT transformation code and visual output spectra.
* `Lab6.pdf`: Exported notebook execution report.
* `README.md`: Technical documentation of frequency-domain workflows.