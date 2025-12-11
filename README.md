# Q5 – Spatial Filtering (Box & Gaussian)

## Original Image
<img src="Q5/Torgya - Arunachal Festival.jpg" width="450">

---

## 5×5 Box Filter

| Normalized | Non-Normalized |
|-----------|----------------|
| <img src="Q5/5.5_normlised.jpg" width="350"> | <img src="Q5/5.5_non_normlised.jpg" width="350"> |

---

## 20×20 Box Filter

| Normalized | Non-Normalized |
|-----------|----------------|
| <img src="Q5/20.20_normalised.jpg" width="350"> | <img src="Q5/20.20_non_normalised.jpg" width="350"> |

---

## Gaussian Filter (σ = 3)

| Non-Normalized | Sum Normalized | Area Normalized |
|----------------|----------------|-----------------|
| <img src="Q5/sigma_3_non_normalised1.jpg" width="300"> | <img src="Q5/sigma_3_normalised_sum.jpg" width="300"> | <img src="Q5/sigma_3_normalised_area.jpg" width="300"> |

---

## **Question**
**Spatial Filtering:**  
Implement 5×5 and 20×20 box filters with and without normalization for  
*Torgya – Arunachal Festival.jpg*.  
This is a color image (RGB), so filtering must be done on all channels.  
Compute σ, determine the corresponding Gaussian filter size, and apply:  
- A separable Gaussian filter  
- A separable normalized Gaussian filter  

Display all outputs.

---

## **Explanation**
A box filter replaces each pixel with the average or sum of its neighbors. Normalized box filters divide by the window area to preserve brightness, while non-normalized filters cause images to brighten due to raw summation. Larger kernels like 20×20 blur more than 5×5 due to a wider neighborhood.

Gaussian filters use weighted averaging, giving more influence to nearby pixels. Without normalization, the Gaussian kernel sum is greater than 1, causing brightness increase. Normalizing by the kernel sum prevents this. Gaussian filters produce smoother, edge-preserving blur, and the separable approach speeds up computation by applying horizontal and vertical passes instead of full 2-D convolution.

---

# Q6 – Bit-Plane Slicing

## Low-Light Image Results

| Original | Reconstructed (Bits 0–2) | Difference |
|----------|---------------------------|------------|
| <img src="Q6/low_original.png" width="300"> | <img src="Q6/low_reconstructed.png" width="300"> | <img src="Q6/low_difference.png" width="300"> |

---

## Bright-Light Image Results

| Original | Reconstructed (Bits 0–2) | Difference |
|----------|---------------------------|------------|
| <img src="Q6/bright_original.png" width="300"> | <img src="Q6/bright_reconstructed.png" width="300"> | <img src="Q6/bright_difference.png" width="300"> |

---

## **Question**
Capture one photo in low light and one in bright light.  
Extract all bit-planes for each image, reconstruct the image using the lowest three bit-planes (bits 0, 1, 2), and compute the difference between this reconstruction and the original.

---

## **Explanation**
A grayscale pixel is represented by 8 bits (bit 0 = least significant).  
Bit-plane slicing visualizes how each bit contributes to the overall image.  
Reconstruction using only bits 0–2 keeps only coarse details, while finer textures are stored in higher bits (3–7).  
The difference image highlights what information is lost.  
Bright-light images contain stronger high-bit details, producing larger differences, while low-light images generally have weaker high-bit structure.

---


