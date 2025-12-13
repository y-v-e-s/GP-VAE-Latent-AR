# 2512.09535v1.pdf
## Latent-Autoregressive GP-VAE Language Model

**Yves Ruffenach**  
Conservatoire National des Arts et Métiers (CNAM), France  

- Email (institutional): yves.ruffenach.auditeur [at] lecnam [dot] net  
- Email (personal): yves [at] ruffenach [dot] net 
- ORCID: https://orcid.org/0009-0009-4737-0555  

---

### Abstract

We investigate a fully **latent autoregressive** scheme based on a **Gaussian Process (GP)**
integrated into a **Variational Autoencoder (VAE)**. In this setting, sequential dynamics are
transferred from the observation space to a continuous latent space, while linguistic generation
remains parallel through a non-autoregressive decoder.

We present a complete methodological formulation, including a **causal GP prior**, a
**structured amortized posterior**, and a training protocol based on a **regularized ELBO**.
Empirical evaluation, conducted within a deliberately constrained **proof-of-concept (POC)**
framework, shows that the model can be trained stably and that the sequential and parallel
sampling variants exhibit consistent behavior.

Overall, the results suggest that part of the temporal structure in a language model can be
supported by the **probabilistic geometry of the latent space**, rather than by explicit
token-level autoregressive neural operations.

---

### Keywords

Gaussian Process VAE; Sequential models; Latent autoregression; Language modeling;  
Reasoning; Bayesian generative models; Deep learning; Variational autoencoders;  
Gaussian processes.

---

### Repository contents

This directory contains material related to the **Latent-Autoregressive GP-VAE** model,
including methodological descriptions, experimental analyses, and associated publications.

- Supplementary material and experimental notes

The focus of this work is **methodological and conceptual**, emphasizing the role of
latent probabilistic dynamics in language modeling rather than state-of-the-art benchmarks.

---

## Citation

@article{ruffenach2025latentgpvae,
  title   = {Latent-Autoregressive GP-VAE Language Model},
  author  = {Ruffenach, Yves},
  year    = {2025},
  institution = {Conservatoire National des Arts et Métiers},
  note    = {Methodological proof-of-concept study},
  url     = {https://zenodo.org/records/17696132}
}

