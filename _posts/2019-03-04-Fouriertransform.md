---
title: 'What Does Fourier Transform Do to Cryo-EM Images?'
date: 2019-03-04
permalink: /posts/2019/blog-post-2/
tags:
  - Fourier Transform
  - Cryo-EM
  - image processing
---

Cryo-EM images are formed by pixels with different intensity in grayscale. Each pixel is represented as a number in the image file. Below is a table simulating the pixel intensity of an image.

![Figure 1](/images/posts/post2fig1.png)

If we plot the numbers in the last row with column indexes, we may get a curve look like this:

![Figure 2](/images/posts/post2fig2.png)

Here we need to introduce a theorem that every curve can be approximated by the sum of simple sine waves (y = A sin(wx +b)) as presented in the figure below. Therefore, if we apply Fourier transform to the curve, we will get a set of sine waves with different amplitude (A), phase (b) and frequency (1/w). In this way, we convert the information in the real image into three parameters in the Fourier space. And the process of converting a curve into several sine waves is called Fourier transform.

 
![Figure 3](/images/posts/post2fig3.png)

The red curve on the left is able to be approximated by the sum of several blue curves on the right. Image from https://www.ritchievink.com/blog/2017/04/23/understanding-the-fourier-transform-by-example/ 

In the Fourier transformed image, we record two numbers, amplitude and phase in the order of frequency from low to high. For example, if we have a real image with image size 100x100 and pixel size=2 Å, the Fourier transform of one row in the image would be 100/2=50 sine waves ordered from 0 frequency to the Nyquist frequency which is 0.25 Å-1 (1/(pixel size*2)).


------
