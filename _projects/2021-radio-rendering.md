---
layout: project
title: Torque Wrench Design and Ansys FEM
description: Designed a torque wrench and chose a suitable material based on analytical calculations. Created a CAD model of the wrench and used Ansys to perform a FEM of the wrench under torque.
technologies: [Autodesk Fusion, Ansys, Matlab]
image: /assets/images/Wrench-FEM-Deformation.jpg
---

For a class, I was tasked with designing a torque-wrench to meet certain specifications at a given maximum torque. I iterated using analytical calculations to find the necessary material and wrench dimensions to satisfy my specifications, and then I used CAD software to create a model of my chosen design. Using Ansys, I performed an FEM analysis of my design with the given applied force, applying boundary conditions and carefully analyzing and recording the results with several material metrics. By comparing the results of my FEM analysis to the results of my hand calculations, I gained an understanding of the limits of hand calculations, as well as the use cases of FEM analysis. Finally, I performed several mesh refinement studies to look at the impact of mesh size on the results of the FEM analysis.

A look at the CAD model I designed. It is a fairly simplistic model, lacking complex geometry and contours that would be present on an actual wrench, however this enabled me to readily perform hand calculations of the design.

![CAD Model](/assets/images/Wrench-CAD-Model.jpg)

The material used in my wrench design is an aluminum alloy, Aluminum 7010-T7451. Material selection was done iteratively, looking at several different families of alloys and narrowing down possibilities using material properties. The aluminum alloy chosen is ideal for several reasons. It has a fairly high yield strength relative to other aluminum alloys, allowing us to achieve the desired safety factor for yield. However, its Young's Modulus is at a reasonable 10.5e3 ksi, which allows larger deformation and the strain gauge placed on the wrench to achieve the minimum required output. Finally, the fracture toughness and fatigue strength are high enough to achieve the desired safety factors respectively.

The load was applied distributively over the end surface over the wrench, using F = M/L to calculate the necessary magnitude to achieve the desired moment. Boundary conditions were imposed to dictate no rotation at the wrench drive.

![Load and Boundary Conditions](/assets/images/Wrench-Boundary-Condition_Analysis.jpg)

Normal strain contours are shown here:

![Normal Strain Contours](/assets/images/Wrench-FEM-Normal-Strain.jpg)

Maximum principle stress contours are shown here:

![Max Principal Stress Contours](/assets/images/Wrench-FEM-Maximum-Principal-Stress-Contours.jpg)

Maximum normal stress contours are shown here, with the maximum normal stress occurring at stress concentration locations on and at the base of the wrench drive:

![Max Normal Stress Contours](/assets/images/Wrench-FEM-Normal-Stress.jpg)

Load point deflection is shown here, with greatest deflection occurring on the end where the load is applied, as expected:

![Load Point Deflection](/assets/images/Wrench-FEM-Deformation.jpg)

I chose the SGD-1.5/120-LY11 strain gauge from Omega Engineering. It is a linear strain gauge with a size of 4.7mm, which will fit within the area of the wrench where it will be placed. The strain at the gauge ends up being very similar to the results of my hand calculations, with a strain of 0.001, which corresponds to 1.039 mV/V.