---
title: 'What is the Preferred Orientation Problem?'
date: 2019-03-03
permalink: /posts/blog-post-1/
tags:
  - preferred orientation
  - cryo-EM
  - image processing
---


Preferred orientation occurs when most of the particles present the same view in the EM image. This has been a persistent issue for high-resolution structure determination with cryo-EM, especially for asymmetric samples. It is typically caused by the adherence of the sample to the air-water interface or to the substrate of the grid (e.g., carbon film or graphene oxide). 

Let’s take the 20S Proteasome as an example.

**Figure 1.** The side view and top view (A) of the 20S proteasome (EMD-8726). The simulated image with the preferred side view and top view (B). 
![Figure 1](/images/posts/post1fig1.png)

When most of the proteasome particles prefer to *lie on the grid*, we see many side views as shown in Fig. 1B (left panel). Conversely, when they *stand on the grid*, only top views are observed (Fig. 1B, right panel).

---

## How Does the Preferred Orientation Affect the Resolution?

To answer this, we first need to understand the **central slice theorem**:

> The Fourier transform of a 2D projection is equal to the central slice of the Fourier transform of the 3D object.

The EM images collected by TEM are 2D projections of the real particle. Cryo-EM image processing reconstructs the 3D Fourier transform of the particle from these 2D projections. Then, by applying an inverse Fourier transform, we obtain the 3D structure.

**Figure 2.** The central slice theorem. 
![Figure 2](/images/posts/post1fig2.png)

For cylindrical samples like the 20S proteasome:

- If the dataset has **preferred side views**, it is usually *not a big deal*.
- If the dataset has **preferred top views**, it significantly *degrades the resolution*.

Here’s why:

For **side-view preferred** datasets, particles still have the freedom to rotate along the y-axis (see Fig. 3A). This results in 2D projections at various rotation angles along the y-axis. After Fourier transforms, these different views populate the 3D Fourier space, which can be inverted to reconstruct the real-space structure.

However, for **top-view preferred** datasets, z-dimensional information is lost. Particles primarily rotate along the z-axis, so all 2D projections lie on the same XY plane. These projections, when Fourier transformed, still fall on the same plane—failing to reconstruct a full 3D Fourier object. As a result, the structure cannot be resolved.

**Figure 3.** The reconstruction process of side-view preferred dataset (A) and top-view preferred dataset (B). 
![Figure 3](/images/posts/post1fig3.png)

---

## How to Deal with the Preferred Orientation Problem?

**Figure 4.** The sample orientation on a non-tilted grid (left) vs. a tilted grid (right). 
![Figure 4](/images/posts/post1fig4.png)

The most common strategy is to **tilt the grid** during data collection. Tilting the grid is equivalent to changing the orientation of the particles (Fig. 4). This approach helps capture more z-dimensional information in the projection images, improving the resolution and overcoming the limitations of preferred orientation.

---
