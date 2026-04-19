# PnP in STIR (via DeepInverse)

A set of experiments demonstrating how to extend **SIRF/STIR PET reconstruction workflows** with **DeepInverse-style learned priors**.

## Goal

The goal of this contribution is to explore how learned priors can be integrated into SIRF-based PET reconstruction pipelines, replacing or augmenting classical regularization methods currently available in STIR.

In standard SIRF workflows, PET reconstruction relies on hand-crafted priors such as the Relative Difference Prior (RDP). Here, we investigate how these can be extended using learned components:

* DRUNet: denoiser-based prior used within Plug-and-Play (PnP) reconstruction
* WCRR: learned regularizer used in a variational reconstruction framework

## Methods overview

Two complementary approaches are explored:

(i) **Variational learned regularization**
* Uses Weakly Convex Ridge Regularization (WCRR) as an explicit learned regularizer
* Optimization is performed using the Primal-Dual Three-Operator (PD3O) algorithm.

(ii) **Plug-and-Play (PnP)**
* Integrates learned priors (DRUNet) into SIRF reconstruction loop as an implicit proximal mapping.
* Implemented with multiple optimization strategies:
    * Half Quadratic Splitting (HQS)
    * Stochastic Variance Reduced Gradient (SVRG)

These demonstrate how SIRF can be extended to incorporate learned priors from external libraries (DeepInverse), enabling both implicit (PnP) and explicit (variational) regularization within a unified reconstruction framework.

## Notebooks

* `PD30_WCRR_PET.ipynb` — Variational reconstruction in SIRF using PD3O with WCRR as a learned explicit regularizer  
* `HQS_DRUNet_PET.ipynb` — Plug-and-Play reconstruction in SIRF using HQS with DRUNet denoiser  
* `SVRG_DRUNet_PET.ipynb` — Plug-and-Play reconstruction in SIRF using SVRG with DRUNet denoiser  

## Setup

* Install `deepinv` from PyPI.
* SIRF and CIL are required and are recommended to be used via the official SIRF Docker environment.

## References

* https://github.com/SyneRBI/SIRF  
* https://github.com/TomographicImaging/CIL 
* https://deepinv.github.io/deepinv/
* https://github.com/TomographicImaging/CIL-User-Showcase/tree/main/016_cil_torch_fista_pnp
