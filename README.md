# GABIC  
Generative Anatomically-Constrained Bidirectional Connectivity

**MATLAB implementation of the GABIC framework for inferring directional effective connectivity using whole-brain Hopf models constrained by structural connectomes**

This repository contains the MATLAB code used in:

> Deco, G., Vidaurre, D., & Kringelbach, M. L. (2021). *Revisiting the global workspace orchestrating the hierarchical organization of the human brain*. Nature Human Behaviour, 5, 497–511. https://doi.org/10.1038/s41562-020-01003-6

This work introduces the GABIC framework, which estimates generative bidirectional effective connectivity by optimizing a whole-brain Hopf model to reproduce the empirical normalized directed transfer entropy (NDTE) flow. The method provides a model-based inference of causally directed interactions constrained by structural connectivity and optimized using particle swarm algorithms.

---

## Purpose & Scope

- Estimate directed effective (generative) connectivity matrices from empirical NDTE using anatomically constrained models.
- Fit whole-brain Hopf oscillators with asymmetric coupling weights reflecting NDTE flow.
- Investigate the causal role of high-hierarchy brain regions (global workspace) through model-based lesioning.
- Provide a neurobiologically plausible simulation platform to reproduce empirical hierarchy of information flow.

---

## Repository Structure

- Core MATLAB scripts implementing are in the folders:
  - MODEL: Whole-brain Hopf model dynamics.
  - NDTE: NDTE flow computations.

> **Note**: Input neuroimaging data (fMRI and SC matrices) are not provided in the repository. Users should provide their own data.

---

## Requirements

- MATLAB R2020a or later
- Required Toolboxes:
  - Optimization Toolbox (for particle swarm optimization)
  - Signal Processing Toolbox
---

## Usage Instructions

1. **Prepare input data**:
   - Empirical NDTE flow matrix computed from preprocessed fMRI time series.
   - Structural connectivity (SC) matrix derived from DTI-based tractography.
   - Parcellation scheme (e.g., DK80) consistent across modalities.

2. **Organize your data**:
   - Store matrices as `.mat` files (e.g., `NDTE_empirical.mat`, `SC.mat`) within the `data/` folder.
   - Ensure dimensional consistency across inputs (same number and order of regions).

3. **Configure model parameters**:
   - Set simulation parameters (e.g., number of particles, time step, duration) in the provided scripts or via custom configuration files.

4. **Run GABIC optimization**:
   - Launch the optimization routine to fit the generative model to the empirical NDTE matrix using particle swarm methods.

5. **Analyze results**:
   - Assess fit quality between empirical and simulated NDTE.
   - Examine the inferred asymmetric GABIC matrix.
   - Conduct in silico lesion analyses on selected regions to test causal influence on whole-brain dynamics.

6. **Visualize outputs**:
   - Use plotting functions to inspect connectivity matrices, node hierarchies, and simulation behaviour.

---

## Data Sources & Ethics

- This repository does not include human subject data.

---

## Citation

If you use this repository or adapt the GABIC methodology, please cite:

Deco, G., Vidaurre, D., & Kringelbach, M. L. (2021). *Revisiting the global workspace orchestrating the hierarchical organization of the human brain*. Nature Human Behaviour, 5, 497–511. https://doi.org/10.1038/s41562-020-01003-6

---

## License

This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0).

---

## Contact

For scientific questions, please contact:

**Prof. Gustavo Deco**  
Center for Brain and Cognition  
Universitat Pompeu Fabra, Barcelona  
[gustavo.deco@upf.edu](mailto:gustavo.deco@upf.edu)
