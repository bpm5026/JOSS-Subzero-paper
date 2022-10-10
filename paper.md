---
title: 'SubZero: Lifecycle representation of sea ice floes using a new discrete element model'
tags:
  - Matlab
  - Oceanography
  - Discrete Element Methods
  - Sea Ice
authors:
  - name: Brandon Montemuro
    orcid: 0000-0003-1946-4916
    equal-contrib: true
    affiliation: 1
  - name: Georgy Manucharyan
    equal-contrib: true # (This is how you can denote equal contributions between multiple authors)
    affiliation: 1
affiliations:
 - name: School of Oceanography, University of Washington, Seattle, WA
   index: 1

date: 05 October 2022
bibliography: paper.bib

---

# Summary

SubZero is a conceptually new sea ice model geared to explicitly simulate the life cycles of individual floes by using complex discrete elements with time-evolving shapes. SubZero is being developed as part of an ONR multi-university research initiative to investigate the mathematics and data science for improved physical modeling and prediction of sea ice. This unique model uses parameterizations of floe-scale processes, such as collisions, fractures, ridging, and welding. Figure \autoref{fig:timeloop} is a schematic representing the SubZero model as a flow chart and what happens over any given time-step. 


![Operational flow chart for the SubZero sea ice model. The shaded gray boxes represent the different sections of the program, the red outlined boxes are processes that are executed every at specified intervals, and the black outlined boxes are processes that occur at every time-step.\label{fig:timeloop}](Subzero_timeloop_georgy.png)

SubZero was developed on Matlab and leverages several of Matlab's built-in features, such as polyshapes. In contrast with existing sea ice DEMs, our approach is based on floes conceptualized as complex-in-shape time-evolving elements instead of specifying a large number of stiffly-bonded simple elements to represent floes. We argue that the model capability of developing floe shapes naturally, due to specific physical processes at play, might bring us closer to direct model validation with floe-scale observations. The source code for Gala has been archived to Zenodo with the linked DOI: ([@Manucharyian:2022])

# Statement of need

Sea ice dynamics span a wide range of scales and exhibit granular behavior as individual floes and fracture networks become evident at length scales O(10--100) km and smaller. Sea ice motion at relatively large scales, O(100 km), is commonly represented in climate models using continuous rheological models [@Hibler:1979; @Hunke:1997; @Rampal:2016]. However, at relatively small scales, O(10--100) km and smaller, sea ice can be viewed as a granular material consisting of a collection of interacting floes  [@Rothrock:1984; @Zhang:2015; @Stern:2018]`. Although it is technically possible to run continuum sea ice models at very high resolution, the assumptions under which they are applicable formally require the grid box size to be significantly larger than the characteristic floe size such that floe interactions can be represented statistically [@Hibler:1977; @Feltham:2008]. Nonetheless, high-resolution numerical simulations can generate discontinuities that resemble observed linear kinematic features [@Hutter:2020; @Mohammadi:2020; @Mehlmann:2021; @Hutter:2022]. But despite the major progress of continuous modeling of large-scale sea ice and the ongoing developments in pushing their applicability limits by increasing the resolution, the rheological models are not meant to represent the scales of motion at which individual floes start to affect dynamics [@Coon:2007]. Hence, the validation against floe-scale observations for continuous models is only possible using statistical characteristics or large-scale sea ice motion because the rheological parameters parameterize cumulative effects of floe interactions. Consequently, direct comparisons of continuous models to remote sensing or field observations of individual floe behavior are challenging. 

Alternatives to continuous rheology models are Discrete Element Models (DEMs), developed initially in the context of granular assembles and rock dynamics [@cundall:1979; @potyondy:2004}. DEMs represent media as a collection of a large number of colliding and/or bonded elements of specified shapes and contact laws and hence are typically computationally demanding. Since the continuous equations of motion are often unknown, DEMs resort to specifying the interaction laws between its elements and strive to calibrate them using micro-scale observations. Existing floe-scale sea ice models use bonded elements of predefined simple shapes like disks or tetrahedra to represent more complex floe geometries. However, floe-scale modeling remains challenging due to difficulties reconciling discrete elements' idealized nature with complex floe-scale observations. Observations demonstrate that floes range dramatically in shapes and sizes and evolve in time subject to a variety of processes like fractures, rafting and ridging, lateral growth/melt, welding, etc. Hence, using pre-defined element shapes brings some ambiguity about what elements and bonds between them physically represent. Are elements supposed to approximate the behavior of aggregates of floes (similar to what continuous rheological models are assuming), or perhaps they are representing bonded constituents of floes or some other metric of a sea ice state? Without a robust understanding of what a DEM element represents, it is difficult to search for direct correspondence between the state variables of the DEM and the observed sea ice. SubZero is designed as an alternative to continuous rheology models and traditional DEMs. Our goal is to develop a model that could be used with floe-scale satellite and in situ observations for floe-scale sea ice predictions and process studies. SubZero consists of several mechanical and thermodynamic components focused on developing a set of floe interaction rules that could lead to realistic sea ice mechanics, including distributions of floe sizes, thicknesses, and shapes. 



# Acknowledgements

B.P.M and G.E.M gratefully acknowledge support from the Office of Naval Research (ONR) grant N00014-19-1-2421. The authors highly appreciate the insightful discussions at the online workshop ``Modeling the Granular Nature of Sea Ice'' organized by the School of Oceanography, University of Washington as part of the ONR MURI project N00014-19-1-2421. 

# References
