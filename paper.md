---
title: 'Gala: A Python package for galactic dynamics'
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

# Optional fields if submitting to a AAS journal too, see this blog post:
# https://blog.joss.theoj.org/2018/12/a-new-collaboration-with-aas-publishing
aas-doi: 10.3847/xxxxx <- update this with the DOI from AAS once you know it.
aas-journal: Astrophysical Journal <- The name of the AAS journal.
---

# Summary

SubZero is a conceptually new sea ice model geared to explicitly simulate the life cycles of individual floes by using complex discrete elements with time-evolving shapes. SubZero is being developed as part of an ONR multi-university research initiative to investigate the mathematics and data science for improved physical modeling and prediction of sea ice. This unique model uses parameterizations of floe-scale processes, such as collisions, fractures, ridging, and welding. Figure \autoref{fig:seaice_timeloop} is a schematic representing the SubZero model as a flow chart and what happens over any given time-step. 


![Operational flow chart for the SubZero sea ice model. The shaded gray boxes represent the different sections of the program, the red outlined boxes are processes that are executed every at specified intervals, and the black outlined boxes are processes that occur at every time-step.\label{fig:seaice_timeloop}](Subzero_timeloop_georgy.pdf)

SubZero was developed on Matlab and leverages several of Matlab's built-in features, such as polyshapes. In contrast with existing sea ice DEMs, our approach is based on floes conceptualized as complex-in-shape time-evolving elements instead of specifying a large number of stiffly-bonded simple elements to represent floes. We argue that the model capability of developing floe shapes naturally, due to specific physical processes at play, might bring us closer to direct model validation with floe-scale observations. 
# Statement of need

SubZero is designed as an alternative to continuous rheology models. Our goal is to develop a model that could be used with floe-scale satellite and in situ observations for floe-scale sea ice predictions and process studies. SubZero consists of several mechanical and thermodynamic components focused on developing a set of floe interaction rules that could lead to realistic sea ice mechanics, including distributions of floe sizes, thicknesses, and shapes.



# Figures

Figure sizes can be customized by adding an optional second parameter:
![Caption for example figure.](figure.png){ width=20% }

# Acknowledgements

We acknowledge contributions from Brigitta Sipocz, Syrtis Major, and Semyeong
Oh, and support from Kathryn Johnston during the genesis of this project.

# References
