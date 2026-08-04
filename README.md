```markdown
# xF3 Laplace DGLAP Solver (NLO & NNLO)

[![Wolfram Mathematica](https://img.shields.io/badge/Wolfram-Mathematica-red)](https://www.wolfram.com/mathematica/)
[![Fortran](https://img.shields.io/badge/Language-Fortran-blue)](https://fortran-lang.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Numerical implementations for the evolution and analysis of the **non-singlet \(xF_3\)** structure function in charged-current deep-inelastic scattering (DIS), based on a **Laplace-transform solution** of the DGLAP evolution equations.

The repository contains **Wolfram Mathematica notebooks** and **Fortran programs** for perturbative QCD calculations at:

- **Next-to-Leading Order (NLO)**
- **Next-to-Next-to-Leading Order (NNLO)**

---

## Related Publication

This repository accompanies the following research article:

> **Laplace-Space Analysis of xF3 Including Nuclear Effects and Gegenbauer-Polynomial Parton Distributions**

**Authors**

- Shahin Atashbar Tehrani
- Javad Sheibani
- Elham Astaraki

**Preprint:** [arXiv:2607.28105 [hep-ph] (2026)](https://arxiv.org/abs/2607.28105)

- [arXiv abstract page](https://arxiv.org/abs/2607.28105)
- [PDF version](https://arxiv.org/pdf/2607.28105.pdf)

The notebooks and numerical codes in this repository support the NLO and NNLO analyses described in the accompanying work.

---

## Overview

The project implements non-singlet QCD evolution for the \(xF_3\) structure function in Laplace space. It is designed for phenomenological studies of neutrino-nucleus DIS data, including the CCFR, NuTeV, and CHORUS datasets.

### Features

- Laplace-space solution of non-singlet DGLAP evolution equations;
- NLO and NNLO perturbative-QCD evolution;
- Jacobi-polynomial reconstruction in Bjorken-\(x\) space;
- Gegenbauer-polynomial parameterization of input parton distributions;
- Numerical evaluation of the \(xF_3\) structure function;
- Analysis based on a 230-point DIS dataset;
- Nuclear corrections in the initial PDF parameterization;
- Mathematica notebooks for the analytical/numerical workflow;
- Fortran implementations for numerical evolution and fitting.

---

## Repository Structure

```text
xF3-Laplace-DGLAP-Solver/
│
├── README.md
├── LICENSE
│
├── NLO/
│   ├── Mathematica/
│   │   └── xF3_Laplace_DGLAP_NLO.nb
│   │
│   ├── Fortran/
│   │   ├── dglap_evolution_nlo.f
│   │   ├── input_parameters.f
│   │   ├── jacobi_reconstruction.f
│   │   ├── nlo_fit_230_data.f
│   │   └── psi_functions.f
│   │
│   ├── Input/
│   │   └── xF3_230_data.dat
│   │
│   └── Output/
│       └── nlo_fit_results.txt
│
└── NNLO/
    ├── Mathematica/
    │   └── xF3_Laplace_DGLAP_NNLO.nb
    │
    ├── Fortran/
    │   ├── dglap_evolution_nnlo.f
    │   ├── input_parameters.f
    │   ├── jacobi_reconstruction.f
    │   ├── minuit_fit_230_data.f
    │   ├── psi_functions.f
    │   └── wilson_coefficients.f
    │
    ├── Input/
    │   └── xF3_230_data.dat
    │
    └── Output/
        └── nnlo_fit_results.txt
```

---

## File Organization

| Original file | Recommended repository location |
|:--|:--|
| `xf3laplaceNLOfor test230 data ggen result nuclear input.nb` | `NLO/Mathematica/xF3_Laplace_DGLAP_NLO.nb` |
| `xf3laplaceNNLO2ggen230datanuclear.nb` | `NNLO/Mathematica/xF3_Laplace_DGLAP_NNLO.nb` |
| `NLO/evoloutionNLO2.f` | `NLO/Fortran/dglap_evolution_nlo.f` |
| `NLO/input2.f` | `NLO/Fortran/input_parameters.f` |
| `NLO/jacobi.f` | `NLO/Fortran/jacobi_reconstruction.f` |
| `NLO/NLO-2016-230.f` | `NLO/Fortran/nlo_fit_230_data.f` |
| `NLO/psifcts.f` | `NLO/Fortran/psi_functions.f` |
| `NNLO/evoloutionNNLO2.f` | `NNLO/Fortran/dglap_evolution_nnlo.f` |
| `NNLO/input2.f` | `NNLO/Fortran/input_parameters.f` |
| `NNLO/jacobi.f` | `NNLO/Fortran/jacobi_reconstruction.f` |
| `NNLO/MINUITNLO6fix230data.f` | `NNLO/Fortran/minuit_fit_230_data.f` |
| `NNLO/psifcts.f` | `NNLO/Fortran/psi_functions.f` |
| `NNLO/wilson.f` | `NNLO/Fortran/wilson_coefficients.f` |
| `NLO/230.dat` | `NLO/Input/xF3_230_data.dat` |
| `NNLO/230.dat` | `NNLO/Input/xF3_230_data.dat` |
| `NLO/NLO-Final-2-gegen-230-nuclear.txt` | `NLO/Output/nlo_fit_results.txt` |
| `NNLO/f90-windows-230datafixgegennuclear.txt` | `NNLO/Output/nnlo_fit_results.txt` |

---

## Requirements

### Mathematica workflow

- **Wolfram Mathematica 13.0** or newer.

Earlier versions may work, but have not been systematically tested.

### Fortran workflow

- A Fortran compiler, such as [`gfortran`](https://gcc.gnu.org/fortran/);
- A compatible implementation of **CERN MINUIT**, if the NNLO fitting program is compiled and used;
- A standard Unix-like environment is recommended, although the code may also be adapted for Windows compilers.

---

## Running the Mathematica Notebooks

### NLO analysis

1. Open the notebook:

   ```text
   NLO/Mathematica/xF3_Laplace_DGLAP_NLO.nb
   ```

2. Check the input-data path and numerical parameters.

3. Evaluate the notebook sequentially from the first cell.

4. The notebook produces evolved \(xF_3\) distributions, numerical predictions, fitted quantities, tables, and figures.

### NNLO analysis

1. Open the notebook:

   ```text
   NNLO/Mathematica/xF3_Laplace_DGLAP_NNLO.nb
   ```

2. Check the input-data path and model parameters.

3. Evaluate all cells sequentially.

4. The notebook produces NNLO predictions, fitted quantities, numerical tables, and figures.

---

## Running the Fortran Codes

The Fortran sources are provided as numerical implementations of the evolution, Jacobi reconstruction, Wilson-coefficient evaluation, and fitting procedures.

A typical compilation command using `gfortran` may have the form:

```bash
gfortran -O2 \
  dglap_evolution_nlo.f \
  input_parameters.f \
  jacobi_reconstruction.f \
  psi_functions.f \
  nlo_fit_230_data.f \
  -o xF3_nlo_fit
```

The exact compilation command may require adjustment depending on the compiler, operating system, and external MINUIT configuration.

> **Note:** The NNLO fitting source includes a MINUIT-related program file. Please ensure that the appropriate MINUIT library is installed and linked if required by your local setup.

---

## Input Data

The repository includes the 230-point DIS dataset used in the numerical analysis.

The input files are located at:

```text
NLO/Input/xF3_230_data.dat
```

and

```text
NNLO/Input/xF3_230_data.dat
```

If an original notebook or Fortran source contains an absolute local path, replace it with the appropriate relative path before execution.

---

## Theoretical Framework

The calculation is based on perturbative Quantum Chromodynamics (QCD) and the non-singlet DGLAP evolution equation. A Laplace transform converts the convolution structure of the evolution equation into products in transform space, enabling an analytical or semi-analytical treatment of the scale evolution.

The resulting structure function is reconstructed in Bjorken-\(x\) space using a Jacobi-polynomial expansion.

Schematically, the perturbative expansion is

\[
xF_3(x,Q^2)
=
xF_3^{\mathrm{LO}}(x,Q^2)
+
\alpha_s(Q^2)\,xF_3^{\mathrm{NLO}}(x,Q^2)
+
\alpha_s^2(Q^2)\,xF_3^{\mathrm{NNLO}}(x,Q^2)
+\cdots.
\]

The analysis incorporates non-singlet splitting kernels, Wilson coefficient functions, nuclear modifications of the input distributions, and Gegenbauer-polynomial PDF parameterizations.

---

## References and Attribution

If you use, adapt, or extend this repository, please cite the accompanying paper and the relevant theoretical literature.

### DGLAP evolution

- V. N. Gribov and L. N. Lipatov,  
  *Deep inelastic e p scattering in perturbation theory*,  
  Sov. J. Nucl. Phys. **15**, 438 (1972).

- L. N. Lipatov,  
  *The parton model and perturbation theory*,  
  Sov. J. Nucl. Phys. **20**, 94 (1975).

- G. Altarelli and G. Parisi,  
  *Asymptotic Freedom in Parton Language*,  
  Nucl. Phys. B **126**, 298–318 (1977).

- Y. L. Dokshitzer,  
  *Calculation of the Structure Functions for Deep Inelastic Scattering and e+e− Annihilation by Perturbation Theory in Quantum Chromodynamics*,  
  Sov. Phys. JETP **46**, 641 (1977).

### NNLO non-singlet splitting functions

- S. Moch, J. A. M. Vermaseren, and A. Vogt,  
  *The Three-Loop Splitting Functions in QCD: The Non-Singlet Case*,  
  Nucl. Phys. B **688**, 101–134 (2004).  
  https://doi.org/10.1016/j.nuclphysb.2004.03.030

### DIS Wilson coefficients

- E. B. Zijlstra and W. L. van Neerven,  
  *Order-\(\alpha_s^2\) corrections to the deep inelastic Wilson coefficient*,  
  Phys. Lett. B **273**, 476–482 (1991).

- E. B. Zijlstra and W. L. van Neerven,  
  *Order-\(\alpha_s^2\) QCD corrections to the deep inelastic proton structure functions \(F_2\) and \(F_L\)*,  
  Nucl. Phys. B **383**, 525–574 (1992).

### Heavy-flavor contributions

The following references are relevant where massive heavy-flavor corrections or operator matrix elements are included:

- I. Bierenbaum, J. Blümlein, and S. Klein,  
  *Mellin Moments of the \(O(\alpha_s^3)\) Heavy Flavor Contributions to Unpolarized Deep-Inelastic Scattering at \(Q^2 \gg m^2\)*,  
  Phys. Lett. B **672**, 401–406 (2009).

- I. Bierenbaum, J. Blümlein, and S. Klein,  
  *Heavy Flavor Wilson Coefficients in Deep-Inelastic Scattering*,  
  PoS DIS2010, 148 (2010).

### Target-mass corrections

- J. Blümlein and H. Kawamura,  
  *Universal Higher Order QED Corrections to Polarized Lepton-Nucleon Scattering*,  
  Phys. Lett. B **553**, 242–250 (2003).

- J. Blümlein and A. Tkabladze,  
  *Target Mass Corrections for Polarized Structure Functions and New Sum Rules*,  
  Nucl. Phys. B **553**, 427–464 (1999).

---

## Citation

If you use this repository in academic research, please cite both the accompanying paper and this software.

### Accompanying paper

```bibtex
@article{AtashbarTehrani2026,
  author        = {Atashbar Tehrani, Shahin and Sheibani, Javad and Astaraki, Elham},
  title         = {Laplace-Space Analysis of xF3 Including Nuclear Effects and Gegenbauer-Polynomial Parton Distributions},
  journal       = {arXiv preprint},
  volume        = {arXiv:2607.28105},
  year          = {2026},
  archivePrefix = {arXiv},
  eprint        = {2607.28105},
  primaryClass  = {hep-ph},
  url           = {https://arxiv.org/abs/2607.28105}
}
```

---

## Author

**Atashbar Tehrani, Shahin (1,2) and Sheibani, Javad(1) and Astaraki, Elham(3)**  ,,
(1)School of Particles and Accelerators, Institute for Research in Fundamental Sciences (IPM), P.O.Box 19395-5531, Tehran, Iran.
(2)Department of Physics, Faculty of Nano and Bio Science and Technology, Persian Gulf University, 75169 Bushehr, Iran.
(3) Department of Physics, Razi University, Kermanshah 67149, Iran.

---

## License

This project is released under the [MIT License](LICENSE).

You are welcome to use, modify, and extend the code for academic and research purposes, provided that appropriate attribution is given through citation of the associated paper and relevant theoretical references.
```
