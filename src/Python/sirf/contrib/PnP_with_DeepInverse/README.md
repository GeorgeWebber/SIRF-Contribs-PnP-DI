# PnP in STIR (via DeepInverse)

Minimal experiments combining **STIR reconstruction** with **DeepInverse-style learned priors**.

## Notebooks

* `HQS_DRUNet_PET.ipynb` — HQS + DRUNet (PnP denoiser)
* TODO

## Setup

Install `deepinverse` from PyPi.

## Goal

Replace classical priors in STIR with learned components:

* DRUNet (denoiser-based PnP)
* WCRR (learned regulariser)
* TODO

## References

* https://github.com/TomographicImaging/CIL-User-Showcase/tree/main/016_cil_torch_fista_pnp
* https://deepinv.github.io/deepinv/
