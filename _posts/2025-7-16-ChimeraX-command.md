---
title: 'ChimeraX Command Cheatsheet'
date: 2025-07-16
permalink: /posts/blog-post-5/
tags:
  - ChimeraX
  - Figure making
  - command
---
# ChimeraX Command Cheatsheet

## Masking for Local Refinement

```chimerax
volume gaussian #1 sDev 2
volume resample #4 onGrid #1
```

## Opening Files

**Open a PDB:**
```chimerax
open 4JIX
```

**Open an EM map:**
```chimerax
open emdb:25658
```

## Map Manipulation

**Z-flip a volume:**
```chimerax
volume flip #1
```

**Invert contrast for tomogram:**
```chimerax
volume scale #1 factor -1
```

**Hide small disconnected regions (dust):**
```chimerax
surface dust #1 size 10
```

**Change window size:**
```chimerax
windowsize 500 500
```

## Region Focus and Visualization

**Focus on one region and fog background:**
```chimerax
camera ortho
lighting depthCue true
```

**Change helices to cylinders:**
```chimerax
preset cylinders
```

## Side Chain Density Display

```chimerax
surface zone #2 near #1/A:404-441
color byhetero
volume #2 subdivide true subdivisionlevels 2
```

## Coloring

**Color map by nearby model:**
```chimerax
color zone #1 near #2 dist 3
```

**Color atoms by element:**
```chimerax
color O red
color N darkblue
```

## Map Orientation

**Orient and clip:**
```chimerax
view clip false orient
turn z 90
clip
clip near 5
```

## Saving Structures

**Save PDB of selected model only:**
```chimerax
save /path/to/test.pdb selectedOnly true relModel #3
```

## Scene Settings

**Set lighting and silhouette:**
```chimerax
light soft
graphics silhouettes true width 1
```

**Make the map transparent:**
```chimerax
transparency 95 target s
```


## Assign Secondary Structure

**Assign helix or beta sheet:**
```chimerax
setattr r isHelix true :1-10.a,23-36.b
setattr r isSheet false :1-10.a,23-36.b
```

## Selection and Deletion

**Delete everything except the selected region:**
```chimerax
del ~sel
```

**Select chains A–D:**
```chimerax
sel /A-D
```

**Select multiple specific chains:**
```chimerax
sel #6/BV/BO
```

**Make cartoon thicker:**
```chimerax
cartoon style width 3 thick 3
```



**Low-pass filter a map:**
```chimerax
surface resolution 10
```

**Create a base mask using Gaussian filter:**
```chimerax
volume gaussian #1 sDev 2
```

**Mask a map using a surface:**
```chimerax
volume mask #3 surface #4 fullMap true
```

**Zone around one part of the map and save as new map:**
```chimerax
volume zone #6 nearAtoms #3 range 20 newMap True minimalBounds True
```



**Match map #5 to #3/C:**
```chimerax
mm #5 to #3/C
```

**Combine models into one:**
```chimerax
combine #2,4,5 modelId 7 name 512combine.pdb
```

## Movie Making
# Make movie going through tomogram slices 
```chimerax
movie record
volume #2 plane z,84,338
wait 264
volume #2 plane z,338,84
wait 264
movie encode ~/Desktop/tomogram.mp4 quality high
```
