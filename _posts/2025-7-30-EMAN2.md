---
title: 'Useful EMAN2 Commands'
date: 2025-7-30
permalink: /posts/blog-post-23/
tags:
  - EMAN2
  - commands
  - processing
---


## 1. Check Movie or Micrograph Information

```bash
e2iminfo.py -H micrograph.mrc
```

## 2. Convert MRC to TIF

```bash
e2proc2d.py input.mrc output.tif
```

## 3. Convert Multiple MRC Files into TIFs

```bash
e2proc2d.py *mrc @tif
```

## 4. Scale a Map

```bash
e2proc3d.py input.hdf output.hdf --clip=140,140,140 --scale=2.8
```

## 5. Generate Random Projections of a Map

```bash
e2project3d.py map.mrc --outfile=proj.mrcs --orientgen rand:n=10:phitoo=1:trans=4
```

## 6. Low-Pass Filter a Map

```bash
e2proc3d.py input.mrc output.mrc --process filter.fourier:curres=3.5:targetres=7:dampamp=1:randomizephase=0
```

## 7. Sharpen a Map

```bash
e2proc3d.py input.mrc output.mrc --process filter.autosharpening:cref=1:mapres=2.5:lpfile=fsc.txt.fit
```

## 8. Calculate Structure Factor Curve of a Map

```bash
e2proc3d.py input.mrc output.mrc --calcsf output_sf.txt
```

## 9. Match Structure Factor Curve to Another Curve

```bash
e2proc3d.py input.mrc output.mrc --apix 1.08 --setsf sf.txt
```

## 10. Match Filtering Level of Another Map

```bash
e2proc3d.py input.mrc output.mrc --apix 1.08 --matchto other.mrc
```

## 11. Generate Random 2D Projections from a 3D Map

```bash
e2project3d.py map.mrc --outfile=projections.mrcs --orientgen random:n=1000:phitoo=1:inc_mirror=1:trans=10
```

## 12. Rotate a Map

```bash
e2proc3d.py input.mrc output.mrc --rot az,alt,phi
e2proc3d.py input.mrc output.mrc --rotspin n1,n2,n3,angle
```

## 13. Rotate Octahedral Map from 4-Fold View to 3-Fold View

```bash
e2proc3d.py input.mrc output.mrc --oct4fto3f
e2proc3d.py input.mrc output.mrc --rot 45,54.7356,0
```

## 14. Flip Handedness of a 3D Map

```bash
e2proc3d.py input.mrc output.mrc --process xform.flip:axis=o
```

## 15. Y-Flip a 3D Reference

```bash
e2proc3d.py input.mrc output.mrc --process xform.flip:axis=y
```

## 16. Apply Mask to a Map

```bash
e2proc3d.py input.mrc output.mrc --process mask.file:file=mask.mrc
```

## 17. Apply Cylindric Mask to a Map

```bash
e2proc3d.py input.mrc output.mrc --process mask.cylinder3d:innerradius=10A:outerradius=20A:length=60A:masksoft=10A
```

## 18. Simulate a Cylinder

```bash
e2proc3d.py :96:96:96:1 output.mrc --apix 1 --process mask.cylinder3d:innerradius=10A:outerradius=20A:length=60A:masksoft=10A
```

## 19. Simulate a Spherical Mask with RELION

```bash
relion_mask_create --denovo --box_size 256 --inner_radius 0 --outer_radius 50 --angpix 1.6 --o mask.mrc
```

## 20. Make a Mask Based on Threshold

```bash
e2proc3d.py input.mrc output.mrc --process mask.auto3d:nshells=5:nshellsgauss=5:thresh=3
```

## 21. Refine and Apply Helical Symmetry

```bash
e2proc3d.py input.mrc ouput.mrc --process xform.helical:apix=1.1:az0=22:z0=37.2:cdsym=c6:verbose=1:rstep=1
```

## 22. Apply Helical Symmetry Without Refinement

```bash
e2proc3d.py input.mrc ouput.mrc --process xform.helical:apix=1.1:az0=22:z0=37.2:cdsym=c6:verbose=1
```
