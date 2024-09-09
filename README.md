# Dual Diffusion Implicit Bridges for Image-to-Image Translation

**Xuan Su**, **Jiaming Song**, **Chenlin Meng**, **Stefano Ermon**  
*Stanford University*  
In ICLR 2023  

[**Paper**](#) | [**GitHub**](#) | [**Colab**](#)

---

## Introduction

DDIBs are an image-to-image translation method based on **probability flow ordinary differential equations (PF ODEs)** of generative diffusion models. The method enables independent model training, guarantees exact cycle-consistent translation, and produces impressive results on high-resolution image datasets.

---

![DDIB Diagram](path_to_diagram.png)

From the source domain, the image is transformed to a latent representation using an ODE solver, and then the target image is reconstructed from this latent space.

- **Source** → ODESolve($x^{(0)}, v^{(s)}_\theta, 0, 1$) → **Latent** → ODESolve($x^{(l)}, v^{(t)}_\theta, 1, 0$) → **Target**

---

## Abstract

Common image-to-image translation methods rely on joint training over data from both source and target domains, which often requires concurrent access to both datasets, hindering data
