# Dynamic MRI Reconstruction using PS-Sparse 🧲

**Course:** CSCE 5013: Machine Learning in Medical Imaging
**Topic:** Low Rank and Sparse Constrained Reconstruction

## 📌 Objective
To reconstruct high-quality Dynamic Magnetic Resonance Images (dMRI) from highly undersampled k-space data. This project implements the **PS-Sparse (Partial Separability + Sparsity)** method to solve the inverse problem.

## 🧠 Mathematical Model
The reconstruction solves the following optimization problem:

$$\min_{U,V} ||Y - \phi(UV)||_2 + \lambda |\Psi(UV)|_1$$

Where:
* **Y**: Undersampled k-space data.
* **U, V**: Temporal and Spatial basis functions (Low Rank constraint).
* **$\phi$**: Fourier encoding operator with undersampling mask.
* **$\Psi$**: Sparsifying transform (e.g., temporal FFT or Wavelet).

## 🛠 Methodology
1.  **Data Ingestion:** Processing `image_xyt` (200, 256, 256) dynamic sequences.
2.  **K-Space Simulation:** Computing 2D FFT and applying undersampling masks.
3.  **Optimization:** Iterative reconstruction using Conjugate Gradient (CG) for the low-rank components.



## 📊 Results
The implementation successfully recovers anatomical structures from aliased inputs.
* **Aliased Input:** Shows significant artifacts due to undersampling.
* **Reconstruction:** Restores spatial details using the low-rank (UV) decomposition.



## 📄 Reference
Based on the PS-Sparse method for dynamic imaging (IEEE 2012).