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

Common image-to-image translation methods rely on joint training over data from both source and target domains, which often requires concurrent access to both datasets, hindering data separation and privacy protection. Existing models struggle with translation of new domain pairs.

We present **Dual Diffusion Implicit Bridges (DDIBs)**, a novel method circumventing the need for domain pair training by leveraging two diffusion models trained independently. The translation process first encodes source images into latent space using the source diffusion model and then decodes these encodings with the target model.

The process is cycle-consistent, leveraging ODE solvers, and is only affected by discretization errors. We interpret DDIBs using a combination of source-to-latent and latent-to-target Schrödinger Bridges, a form of entropy-regularized optimal transport. 

Experimentally, we show the efficacy of DDIBs on both synthetic and high-resolution image datasets, demonstrating their utility in a variety of tasks.

---

### Key Contributions:
- **Independent Training**: The method eliminates the need for joint training on source-target domain pairs.
- **Cycle Consistency**: Guaranteed by leveraging ODE solvers for both source-to-latent and latent-to-target transformations.
- **Schrödinger Bridges**: Theoretical foundation using entropy-regularized optimal transport.

---

### Experiment Results:
<div align="center">
  <img src="path_to_experiment_results.png" alt="Experiment Results">
</div>

---

## Citation

If you use this work, please cite the following:

```bibtex
@inproceedings{su2023ddib,
  title={Dual Diffusion Implicit Bridges for Image-to-Image Translation},
  author={Su, Xuan and Song, Jiaming and Meng, Chenlin and Ermon, Stefano},
  booktitle={ICLR},
  year={2023}
}
