# EN3160 Assignment 1: Intensity Transformations and Neighborhood Filtering

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=for-the-badge&logo=opencv&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)

This repository contains the implementation of **Assignment 01** for the **EN3160 (Image Processing and Machine Vision)** module. The project explores fundamental computer vision techniques, focusing on spatial domain processing, non-linear intensity mappings, and edge-preserving filtering[cite: 1, 2].

## 📌 Overview

The assignment is divided into several image processing tasks demonstrating the mathematical manipulation of pixel intensities and localized neighborhood operations.

### Key Implementations
* **Piecewise Intensity Transformations:** Custom non-linear contrast adjustments and medical image thresholding (isolating white/gray matter in brain MRI scans)[cite: 1, 2].
* **Color Space Manipulations:** Gamma correction in the LAB color space and vibrance enhancement via a Gaussian-weighted boost in the HSV saturation plane[cite: 1, 2].
* **Histogram Equalization:** Custom CDF-based equalization for full images and targeted equalization isolated strictly to foreground subjects using Otsu's thresholding[cite: 1, 2].
* **Spatial Filtering & Edge Detection:** Validation of the 2D Sobel operator's separable property using 1D row and column convolutions[cite: 1, 2].
* **Image Scaling (Zooming):** Implementation of Nearest-Neighbor and Bilinear interpolation algorithms from scratch, evaluated using Normalized Sum of Squared Differences (NSSD)[cite: 1, 2].
* **Segmentation & Depth of Field:** Foreground extraction using OpenCV's `grabCut` algorithm, followed by background blurring to simulate a shallow depth of field (bokeh effect)[cite: 1, 2].
* **Edge-Preserving Smoothing:** Custom implementation of a Bilateral Filter, mathematically compared against OpenCV's optimized `cv.bilateralFilter` using Mean Squared Error (MSE)[cite: 1, 2].

---

## 🧠 What I Learned

Through this assignment, I gained hands-on experience with the underlying mechanics of core computer vision algorithms rather than just relying on high-level library calls:

* **Algorithmic Optimization:** I learned how to mathematically decompose a 2D filter (like the Sobel operator) into separable 1D row and column vectors, significantly reducing computational complexity[cite: 1, 2].
* **Color Space Independence:** I discovered the importance of isolating image channels. By applying transformations in the LAB (Lightness) or HSV (Saturation) color spaces, I learned how to enhance contrast and vibrance without introducing unnatural color shifts or altering base luminance[cite: 1, 2].
* **Targeted Image Processing:** I successfully combined segmentation techniques (like Otsu's thresholding and GrabCut) with filtering techniques to apply localized transformations, such as equalizing only the foreground subject or applying a bokeh blur strictly to the background[cite: 1, 2].
* **Matrix Dimensionality & Data Types:** Building custom filters from scratch reinforced the critical importance of handling boundary padding (`cv.BORDER_REFLECT`), managing `float32` vs `uint8` data type conversions during matrix arithmetic, and dynamically resolving array shape mismatches when computing error metrics like NSSD[cite: 2].
* **Edge-Preserving vs. Uniform Smoothing:** Implementing the Bilateral filter mathematically demonstrated how incorporating range (intensity) variance alongside spatial variance prevents the destructive edge-blurring caused by standard Gaussian filters[cite: 1, 2].

---

## 🚀 Results Summary

* **Intensity Transformations (White/Gray Matter Accentuation):** Piecewise linear transformations applied to highlight specific anatomical structures in a brain proton density slice[cite: 1, 2].
* **HSV Vibrance Enhancement:** Applying a Gaussian-weighted boost to the mid-tones of the Saturation plane to enhance colors without clipping[cite: 1, 2].
* **Foreground Histogram Equalization:** Isolating the foreground using an Otsu-generated mask on the Saturation plane, equalizing it, and smoothly recombining it with the original background[cite: 1, 2].
* **Image Interpolation (Nearest-Neighbor vs. Bilinear):** Scaling images by a factor of 4. Bilinear interpolation consistently provides smoother edges and a lower NSSD score compared to Nearest-Neighbor[cite: 1, 2].
* **GrabCut Segmentation & Background Blur:** Separating a complex foreground subject using `cv.grabCut` and blurring the background to enhance depth[cite: 1, 2].
* **Custom Bilateral Filtering:** An edge-preserving filter that smooths low-variance regions while maintaining sharp structural transitions[cite: 1, 2].

---

## 🛠️ Usage

To run the implementations locally:

1. Clone the repository:
   ```bash
   git clone [https://github.com/NethsanduKumarasinghe/EN3160_Assignment_01.git](https://github.com/NethsanduKumarasinghe/EN3160_Assignment_01.git)
