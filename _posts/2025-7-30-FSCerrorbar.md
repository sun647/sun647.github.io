---
title: 'FSC Error Bar Calculator'
date: 2025-7-30
permalink: /posts/blog-post-25/
tags:
  - FSC
  - error bar
  - confidence interval 
---
### 🧊 About This FSC Confidence Estimation Web App  

Fourier Shell Correlation (FSC) is the standard method used in the cryo-electron microscopy (cryo-EM) field to estimate the resolution of reconstructed 3D maps, serving as a key indicator of overall map quality. FSC is computed as the cross-correlation coefficient between two independently reconstructed “half maps” as a function of spatial frequency. At each resolution shell, FSC quantifies how well the two maps agree, with higher values indicating better reproducibility and signal.

However, a single FSC value per shell assumes uniformity in signal quality across all voxels within that shell. In practice, this assumption oversimplifies the reality: **voxel intensities vary substantially across different spatial locations**, even within the same frequency band. This spatial heterogeneity can arise from anisotropic sampling, preferred particle orientations, or local disorder in the structure.

To better capture these local variations, this web application computes FSC **not just as an average**, but includes **statistical confidence intervals** around each FSC value. It does so by estimating the distribution of voxel-wise cross-correlations in each shell and applying a Fisher *z*-transformation to calculate confidence bounds.

#### FSC Confidence Interval Formula  

The upper and lower bounds of FSC are computed from the following equation:  
Where:
- **z** = 0.5 × log((1 + FSC) / (1 - FSC)) is the Fisher *z*-transform of the FSC    
- **n** is the number of voxels in the resolution shell    
- **σ** (sigma) is a user-defined z-score (e.g., 1.96 for 95% confidence, 3 for 99.7%)  

By allowing you to set the sigma value, this app gives you flexible control over the **statistical stringency** of the FSC envelope, helping you better interpret the reliability of FSC-based resolution estimates.  

---

[Click me to try](https://fscerrorbar-bpamnw2rerqekapp5veeddq.streamlit.app/)  

Example FSC error bar for EMPIAR 10084 Cryo-EM structure of haemoglobin at 3.2 Å determined with the Volta phase plate     
![example FSC error bar](/images/posts/example.png)


### 📚 References

- Penczek PA. *Resolution measures in molecular electron microscopy*. **Methods Enzymol. 2010; 482:73–100**  
  PMID: [20888958](https://pubmed.ncbi.nlm.nih.gov/20888958) | PMCID: [PMC3165049](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3165049)

- Cardone G, Heymann JB, Steven AC. *One number does not fit all: mapping local variations in resolution in cryo-EM reconstructions*. **J Struct Biol. 2013; 184(2):226–236**  
  PMID: [23954653](https://pubmed.ncbi.nlm.nih.gov/23954653) | PMCID: [PMC3837392](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3837392)
