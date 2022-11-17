---
title: 'SubZero: a Discrete element sea ice model that simulates floes as evolving concave polygons'
tags:
  - Sea Ice Modeling
  - Collisions, Fractures, Deformation
  - Discrete Element Methods
  - Deformable Polygonal Elements 
  - Floe Size Distribution
  - Ice Thickness Distribution
  
authors:
  - name: Brandon P. Montemuro
    orcid: 0000-0003-1946-4916
    equal-contrib: true
    affiliation: 1
  - name: Georgy E. Manucharyan
    orcid: 0000-0001-7959-2675
    equal-contrib: true # (This is how you can denote equal contributions between multiple authors)
    affiliation: 1
affiliations:
 - name: School of Oceanography, University of Washington, Seattle, WA
   index: 1

date: 05 October 2022
bibliography: paper.bib

---

# Summary

SubZero is a conceptually new discrete element sea ice model geared to explicitly simulate the life cycles of individual floes by using polygonal elements with time-evolving boundaries. This unique model uses parameterizations of floe-scale processes, such as collisions, rafting, ridging, fracturing, and welding, to simulate the behavior on sea ice floes subject to mechanical and thermodynamical forcing in confined or periodic domains. Figure \autoref{fig:Nares} are snapshots from a validation study using SubZero simulating floes moving through a channel. A complete model description, along with example process studies demonstrating its capabilities, can be found in [@Manucharyan:2022], and the model source code has been archived to Zenodo([@Montemuro:2022]) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7222680.svg)](https://doi.org/10.5281/zenodo.7222680). 

![The evolution of sea ice floes as they pass through the Nares Strait, including (a) initial floe state with the inset showing the location of Nares Strait, (b) floes shortly after sea ice breakup that occurred after about three days, and (c) floe state after ten days when many floes have passed through the Nares Strait. The initial distribution of floes was generated using Voronoi tessellation, and the subsequent evolution of floe shapes is only subject to floe fractures. The green box in (a) shows the part of Nares Strait being simulated. The blue arrows represent sea ice velocity after averaging floe momentum on an Eulerian grid.\label{fig:Nares}](Nares_Floes.png)

SubZero was developed using MATLAB [@MATLAB:2020] and leverages its built-in functions operating with polygons. In contrast with existing sea ice DEMs, our approach is predicated on floes conceived as complex time-evolving elements instead of using simple elements of pre-defined shapes to represent sea ice floes. Due to specific physical processes at play, we argue that the model capability of developing floe shapes naturally might bring us closer to direct model validation with floe-scale observations. SubZero consists of several mechanical and thermodynamic components focused on developing a set of floe interaction rules that could lead to realistic sea ice mechanics, including distributions of floe sizes, thicknesses, and shapes. 

# Statement of need

Sea ice dynamics span a wide range of scales. At length scales O(10--100) km and smaller, sea ice exhibits granular behavior as individual floes and fracture networks become evident  [@Rothrock:1984; @Zhang:2015; @Stern:2018]. Sea ice motion at relatively large scales, O(100 km), is commonly represented in climate models using continuous rheological models [@Hibler:1979; @Hunke:1997; @Rampal:2016]. The assumptions under which continuum sea ice models are applicable formally require the grid box size to be significantly larger than the characteristic floe size such that floe interactions can be represented statistically [@Hibler:1977; @Feltham:2008]. Nonetheless, high-resolution continuous simulations can generate discontinuities that resemble observed linear kinematic features [@Hutter:2020; @Mohammadi:2020; @Mehlmann:2021; @Hutter:2022]. Despite the major progress of continuum sea ice models on large scales and the ongoing developments in pushing their applicability limits to ever higher resolution, the rheological models are not designed to represent the scales of motion at which individual floes start to influence dynamics [@Coon:2007]. As such, the validation against floe-scale observations for continuous models is only possible using large-scale sea ice motion or statistical characteristics since the rheological parameters parameterize the cumulative effects of floe interactions. Consequently, explicit comparisons of continuous models to observations of individual floe behavior are challenging.

Developed initially in the context of granular assembles and rock dynamics [@Cundall:1979; @Potyondy:2004}], Discrete Element Models (DEMs) are an alternative to continuous rheology models. DEMs can be computationally demanding because they represent media as a collection of many colliding and/or bonded elements with specified shapes and contact laws. DEMs resort to setting the interaction laws between their elements and strive to calibrate them using micro-scale observations because the continuous equations of motion are often unknown. Existing floe-scale sea ice DEMs use bonded elements of simple preset shapes like disks [@Herman:2013; @Damsgaard:2018; @Chen:2021], polygons [@Kulchitsky:2017], or tetrahedra [@Liu:2018] to represent complex floe geometries. However, floe-scale modeling remains challenging due to difficulties reconciling discrete elements' idealized nature with complex floe-scale observations. Observations indicate that ice floes vary dramatically in size and shape and change over time due to various processes like fractures, rafting/ridging, lateral growth/melt, welding, etc. Therefore, using prescribed element shapes creates ambiguity about what elements and bonds between them represent physically. Do elements approximate the behavior of aggregates of floes (analogous to rheologies in a continuous model), or perhaps they represent bonded members of floes or some other metric of a sea ice state? It is difficult to search for direct correspondence between the state variables of the DEM and sea ice observations without a clear understanding of what an individual DEM element represents. SubZero is designed as an alternative to continuous rheology models and traditional DEMs that could be used with floe-scale satellite and in situ observations for floe-scale sea ice predictions and process studies. 




# Acknowledgements

B.P.M and G.E.M gratefully acknowledge support from the Office of Naval Research (ONR) grant N00014-19-1-2421. The authors highly appreciate the insightful discussions at the online workshop ``Modeling the Granular Nature of Sea Ice'' organized by the School of Oceanography, University of Washington as part of the ONR MURI project N00014-19-1-2421. 

# References
