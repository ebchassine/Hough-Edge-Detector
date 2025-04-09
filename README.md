# Image Filtering and Hough Transform

## Overview

This project implements a line detector using the Hough Transform, which identifies and fits lines to edges in images. The code processes images through various stages, including image filtering, edge detection, and Hough Transform to detect lines.

## Project Structure

The main script `houghScript.py` handles the overall process, from reading images to generating output. Other scripts implement the core functions of image filtering, edge detection, and Hough Transform.

- `python/`:
  - `houghScript.py`: Main script for image processing
  - `myImageFilter.py`: Implements image filtering
  - `myEdgeFilter.py`: Implements edge detection
  - `myHoughTransform.py`: Implements the Hough Transform
  - `myHoughLines.py`: Implements line detection based on the Hough Transform
  - Helper functions

## Math Behind the Pipeline

- **Edge Detection**: Based on image gradients:
  - \( G_x = \frac{\partial I}{\partial x}, \quad G_y = \frac{\partial I}{\partial y} \)
  - Gradient magnitude: \( G = \sqrt{G_x^2 + G_y^2} \)
  - Gradient direction: \( \theta = \arctan\left(\frac{G_y}{G_x}\right) \)

- **Hough Transform**:
  - A line in image space: \( \rho = x \cos \theta + y \sin \theta \)
  - Each point \((x, y)\) maps to a sinusoid in Hough space. Peaks in the accumulator correspond to line parameters \((\rho, \theta)\) that fit multiple edge points.

This mathematical mapping allows detection of lines, even if they are fragmented or noisy, by aggregating evidence across the image.

### Code Structure
- The main script, `houghScript.py`, integrates various functions and generates intermediate images.
- The `myImageFilter.py`, `myEdgeFilter.py`, and `myHoughTransform.py` scripts implement the respective stages of the process.
- The `myHoughLines.py` script extracts lines from the Hough transform output.

## Results

The results of running the image processing pipeline on various test images are included in the write-up. The write-up discusses the effect of parameters like sigma, threshold, and resolution on the quality of line detection. It also includes intermediate images from each function step.

