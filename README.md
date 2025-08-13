# Image Compression Using K-means

## Overview
This project demonstrates **image compression** using the **K-means clustering algorithm**.  
Instead of storing the full RGB value for each pixel, we reduce the total number of unique colors in the image to a fixed number **K**.  
Each pixel is then represented by the closest centroid color, significantly reducing storage size while maintaining visual similarity.

---

## How It Works
1. **Image Loading & Preprocessing**
   - The image is loaded as a NumPy array of shape `(height, width, 3)` where `3` corresponds to the RGB channels.
   - The 3D array is reshaped into a 2D array of pixels: `(num_pixels, 3)`.

2. **Applying K-means**
   - K-means clusters the pixel colors into **K centroids**.
   - Each centroid represents one of the dominant colors in the compressed image.
   - The algorithm minimizes the **cost/distortion function** (average squared distance between pixels and their assigned centroid).

3. **Image Reconstruction**
   - Each pixel is replaced with the color of its assigned centroid.
   - The reshaped image is displayed alongside the original for comparison.

4. **Compression Effect**
   - **Original size:** `Height × Width × 3` bytes (RGB channels, 8-bit each).
   - **Compressed size:** `(K × 3)` bytes for centroids + `(Height × Width × log₂(K)/8)` bytes for pixel indices.

---

## Example Output

| Original Image | Compressed Image (K = 16) |
|----------------|---------------------------|
| ![Original](original.png) | ![Compressed](comp_16.png) |

---

## Repository Contents
- **CODE.ipynb** — Jupyter notebook with the full workflow.
- **sunflower_image.jpg** — Input image (RGB).
- **comp_2.png**, **comp_4.png**, **comp_8.png**, **comp_16.png** — Outputs for different K.
- **comp_{K}.png** — Side-by-side figures generated when you run the notebook.

---

## Usage
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/Image-Compression-Using-K-means.git
