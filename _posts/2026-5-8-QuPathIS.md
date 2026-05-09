---
title: 'How to Measure Cell Interface Intensity in QuPath'
date: 2026-5-8
permalink: /posts/blog-post-16/
tags:
  - Qupath
  - quantification
---

# How to Measure Cell Interface Intensity in QuPath

This guide walks you through measuring fluorescence intensity at the interface between a target cell (red) and a T cell (green) using QuPath.

---

## Prerequisites

- QuPath installed
- CZI image files ready
- An empty folder for your project

---

## Step 1: Set Up Your QuPath Project

1. Create an empty folder on your computer to serve as the project directory.
2. Open QuPath and create a new project, selecting that empty folder as the project location.
3. Drag your CZI files into the QuPath window — QuPath will automatically split each file into its individual images.

---

## Step 2: Annotate the T Cell

1. Draw a **rectangle annotation** around the target interaction area: the red (target) cell binding to the green (T cell).
   > **Important:** The rectangle should contain only the T cell (green), not the red cell.
2. Select the **magic wand tool** from the toolbar.
3. Hold **Alt** and click to remove any regions within the selection that are not part of the T cell.

---

## Step 3: Generate the T Cell Membrane Ring

1. Go to **Object → Annotations → Expand Annotations**.
2. Enter **-0.8 µm** to erode the annotation inward.

This produces a thin ring that traces the full T cell membrane.

---

## Step 4: Define the Cell Interface

1. Draw **two lines** across the T cell membrane ring to mark the boundaries of the interface region (where the T cell contacts the red cell).
2. Go to **Object → Annotations → Split Annotations by Line**.
   > **Note:** Do **not** check the second checkbox in the dialog.

This splits the ring into separate annotation segments.

---

## Step 5: Name the Annotations

Double-click each split annotation in the annotation table on the left panel and rename them:

| Annotation | Label |
|---|---|
| Interface region | `cell5-interface` |
| Outside region | `cell5-outside` |
| Full T cell | `cell5` |

Repeat this naming convention (incrementing the number) for each cell you analyze.

---

## Step 6: Measure Fluorescence Intensity

1. Go to **Analyze → Calculate Features → Add Intensity Features**.
2. Configure the settings:
   - **Pixel size:** 0.071 µm
   - **Channel:** Green channel
   - **Measurement:** Mean
   - **Apply to:** All annotations
3. Click **OK** to run the analysis.

---

## Step 7: Export the Data

1. Go to **Measure → Export Measurements**.
2. Select **Annotations** as the export target.
3. Choose **CSV** as the file format and save.

---

## Tips

- If you forget where any menu option lives, press **Ctrl + L** to open the command search bar and type keywords to find it quickly.
- Consistent annotation naming (e.g., `cell5-interface`, `cell6-interface`) makes downstream analysis much easier to automate or sort in spreadsheet software.
