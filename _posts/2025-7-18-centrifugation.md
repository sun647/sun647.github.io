---
title: 'Centrifugation Types and Tips'
date: 2025-7-18
permalink: /posts/blog-post-18/
tags:
  - centrifugation
  - purification
  - sample
---

There are two main types of centrifugation: **differential centrifugation** and **density gradient centrifugation**. Differential pelleting is commonly used to pellet cells, bacteria, and other large particles based on differences in **mass, density and shape**.  

Density gradient centrifugation can be further divided into **isopycnic centrifugation** and **rate-zonal centrifugation**.  

Isopycnic centrifugation separates particles only based on their **buoyant density**. It uses a continuous density gradient, which can be either preformed or self-forming (e.g., using CsCl or OptiPrep). In self-forming gradients, the sample is mixed with the gradient material, and the gradient forms during centrifugation. This process typically requires long run times—often overnight—to allow the gradient and particle separation to equilibrate.  

Rate-zonal centrifugation separates particles based on their **size and sedimentation rate**. It often uses a stepwise gradient—a series of discrete layers with increasing density (e.g., 10%, 20%, 30%, 40%). The sample is layered on top of the lightest density layer. This method is widely used for virus purification and typically requires shorter centrifugation times (e.g., one to two hours). However, if spun too long, all particles may eventually pellet, reducing separation resolution.

Sometimes one has to run isopycnic and rate-zonal centrifugation in tandem to enhance purity.   

## Differential centrifugation or pelleting

- Denser particles are pelleted faster than less dense particles  
- Larger particles pellet faster than smaller ones  
- Symmetrical particles pellet faster than asymmetrical ones  
- Separation is not clean:  
  - The g-force used to pellet large particles from the top will also pellet small particles from the bottom  

---

## Desnsity gradient centrifugation

### Isopycnic Centrifugation (Density Gradient Centrifugation, DCC)

- Separates by **density**  
- Can be carried out in **all types of rotors**  
- Requires **longer run times**

#### Preformed Gradient
  
- Sample volume should be **smaller** than the gradient volume  
    
#### Self-Forming Gradient    

- Sample is homogeneously mixed with a self-forming gradient (e.g., **CsCl** or **OptiPrep**)    
- Uses solid gradient material or high-concentration gradient solution    
- Centrifuge time is **longer** than with preformed gradients  
- **Vertical or near-vertical rotors** are preferred  
            - **Swinging-bucket rotors**, which have longer sedimentation paths, are rarely used for self-forming gradients    

#### Criteria for Successful Isopycnic Separation

- Density of the sample particles must **fall within the gradient range**  
- **Any gradient length** is acceptable  
- Run time must be **sufficient for particles to band at their isopycnic point**  
- Excessive run time has **no adverse effect**

---

### Rate-Zonal Centrifugation

- Separates by **sedimentation rates**  
- Often used for **viral purification** or **characterization**  
- Initial sample volume should be **small**  
- If run **too long**, all particles will pellet at the bottom

---

## Rotor Type

- **Swinging bucket rotors**
- ![rotor types](/images/rotors.png)

> ⚠️ Care must be taken to avoid “point loads” caused by spinning **CsCl** or other dense gradient materials that can precipitate.
---

### Centrifugation Time Calculation

The centrifugation time is given by: 

$$
t = \frac{k}{s'}
$$

The k factor is a measure of the pelleting efficiency of the rotor.

![kfactor](kfactor.png)

As the k factor decreases, rotor efficiency increases.

![sedimentation coefficient formula](/images/posts/sedimentation.png)
Biochem. J. (1976) 159, 259-265 


Where:

- **t** = Centrifugation time  
- **k** = Rotor k-factor (a measure of the pelleting efficiency of the rotor)  
  - As the **k-factor decreases**, rotor efficiency **increases**  
- **s’** = Sedimentation coefficient of the particle in a particular gradient at 20°C (in Svedberg units, s)  
- **ρp** = Density of the particle (g/cm³)  
- **ρ** = Density of the gradient (g/cm³)  
- **ρ₂₀,w** = Density of water at 20°C (g/cm³)  
- **S₂₀,w** = Sedimentation coefficient of the particle in **water at 20°C** (Svedberg units, s)  
  - *1 Svedberg (S) = 10⁻¹³ seconds*

---

### Example

At **4°C in 20% sucrose**, the sedimentation coefficient of **Tulane virus**:

- **s’** = 41.87 S  
- Rotor: **SW55 Ti**, 45,000 rpm  
- **k-factor** = 72.4

Calculation:
$$
t = \frac{k}{s'} = \frac{72.4}{41.87} \approx 1.73\ \text{h} \approx 2\ \text{hours}
$$
---

> **Note**: The sedimentation coefficient is influenced by the **viscosity** and **density** of the sucrose solution. Viscosity is dependent on both **concentration** and **temperature**.

> Check out the [Practical Techniques for Centrifugal Separations](/files/Practical-Techniques-for-Centrifugal-Separations.pdf) for more details.
