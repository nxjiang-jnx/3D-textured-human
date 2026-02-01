# 3D Human Digitization with High-Fidelity Textures from a Single Image

<img width="1624" height="924" alt="image" src="https://github.com/user-attachments/assets/d6bbedc7-c294-4cec-9a31-2376c6367f1d" />


## 🔍 Overview

We present a **two-stage framework** for reconstructing **high-quality, fully textured 3D human models from a single RGB image**.  
Unlike prior monocular reconstruction methods that focus primarily on geometry or front-view appearance, our approach explicitly targets **full-body texture completion**, including **plausible back-view textures**, which is critical for real-world applications such as 3D printing, avatar creation, and scene building.

Our method achieves **strong performance** in both **geometry accuracy** and **texture realism**, while remaining practical for everyday single-image inputs captured by consumer devices.

---

## ✨ Key Contributions

- **New Problem Setting**  
  We formalize the problem of *3D human digitization with high-fidelity full-body textures from a single image*, emphasizing not only geometry reconstruction but also realistic back-view texture prediction.

- **Two-Stage Decoupled Pipeline**  
  - **Stage I: High-Fidelity Mesh Construction**  
    Leveraging the 2K2K framework, we reconstruct a detailed clothed human mesh using:
    - Part-wise image-to-normal prediction  
    - Multi-resolution depth fusion  
    - Explicit mesh generation via Poisson reconstruction  

  - **Stage II: Full-Body Texture Prediction & Refinement**  
    We introduce a texture pipeline based on:
    - Side-view decoupling transformer with cross-attention  
    - SMPL-X normals as geometric queries  
    - 3D-consistent diffusion-based texture refinement  

- **High-Quality Back-View Texture Completion**  
  Our method avoids naive front-to-back texture mirroring and instead predicts **semantically consistent and visually plausible back-side textures**, a key limitation of existing SOTA methods.

- **Strong Empirical Results**  
  Extensive experiments show clear improvements over strong baselines (e.g., 2K2K) in:
  - PSNR / SSIM / LPIPS for texture quality  
  - Robustness to pose variation and loose clothing  
  - Visual fidelity in unseen regions  

- **Real-World Applicability**  
  The reconstructed models are directly applicable to:
  - 3D printing  
  - Virtual scene building  
  - AR/VR avatars  
  - Digital content creation  

---

## 🧠 Method Highlights

- **Part-wise Normal Estimation** for fine-grained geometry
- **Low-to-High Resolution Depth Fusion** for stable global structure
- **Side-View Decoupling Transformer** for mapping 2D features to 3D texture space
- **Diffusion Prior with Multi-View Consistency** to refine occluded regions
- **Explicit Mesh Representation**, enabling efficient rendering and downstream use

An overview of the pipeline is illustrated in *Figure 3* of the paper.

---

## 📊 Experimental Results

Our method outperforms the 2K2K baseline in overall texture quality:

| Method | PSNR ↑ | SSIM ↑ | LPIPS ↓ |
|------|------|------|------|
| 2K2K (avg) | 21.944 | 0.913 | 0.112 |
| **Ours (avg)** | **23.028** | **0.908** | **0.122** |

Qualitative results further demonstrate improved texture completeness, especially on the back side of the human body.

---

## 🚀 Applications

- **3D Printing**: Produce realistic full-body figurines from a single photo  
- **Scene Building**: High-quality digital humans for games and simulations  
- **Texture Editing**: Text-driven texture manipulation with diffusion priors  
- **Avatar Creation**: Practical monocular pipeline for personalized avatars  

---

## 📌 Notes

- This repository focuses on the **research contribution** and **method design**.
- Code release status and pretrained models will be updated in future versions.
