## Lab 9: Morphological Operations

**Objective:** Apply morphological operations to a binary image and investigate how structuring element shape and size affect the result.

### Task 1: Morphological Operations
Applied the following operations to `Balls.png` (an image of my own choice, not the one in the original notebook), using Otsu thresholding and a 5x5 square kernel:
- **Erosion:** shrinks white objects and removes small specks
- **Dilation:** enlarges white objects and fills small holes
- **Opening:** erosion followed by dilation, removes small noise while keeping object size
- **Closing:** dilation followed by erosion, fills small gaps and holes

The original image and the four results are displayed together.

### Task 2: Effect of Structuring Elements
Erosion and dilation were applied with three kernel shapes at three sizes (3x3, 5x5, 7x7) and the results shown in grids:

| Shape | Result |
|-------|--------|
| Square | Strongest effect, objects become boxy |
| Cross | Mildest effect, only horizontal and vertical neighbors affected |
| Ellipse | Keeps round objects round |

Larger kernels produced a stronger effect for every shape.