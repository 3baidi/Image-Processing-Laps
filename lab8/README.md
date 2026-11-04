## Lab 8: Edge Detection

**Objective:** Apply and compare edge detection methods and investigate how parameter changes affect the detected edges.

### Task 1: Edge Detection Methods
Applied the following detectors to `Butterfly.jpg` (an image of my own choice, not the one in the original notebook):
- **Sobel:** gradient-based, 3x3 kernels with built-in smoothing
- **Prewitt:** gradient-based, 3x3 kernels defined manually
- **Canny:** multi-stage detector with non-maximum suppression and hysteresis thresholding

The original image and the three edge maps are displayed together.

### Task 2: Effect of Canny Thresholds
Canny was applied with three threshold pairs and the results shown side by side:

| Low | High | Result |
|-----|------|--------|
| 30  | 90   | Most edges, lots of fine detail and noise |
| 50  | 150  | Balanced: main boundaries with moderate detail |
| 100 | 200  | Fewest edges, only strong boundaries, fine detail lost |

