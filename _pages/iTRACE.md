---
layout: page
permalink: /iTRACE/
title: iTRACE
description:
nav: true
nav_order: 4
---


*iTRACE is an isotope-enabled Transient Climate Experiment for the last deglaciation*

## About
The iTRACE project offers a publicly accessible collection of climate model simulations, providing explicit simulations of water isotopes and climate change during the last deglaciation. Its primary objective is to comprehend deglacial climate change by comparing the modeled water isotope against paleoclimate proxies. The project also proves valuable in investigating the distinct roles played by ice sheets, greenhouse gases, orbital insolation, and meltwater fluxes in shaping past climate change.

Conducted in iCESM1.3, the iTRACE simulations are driven by realistic forcings. The dataset comprises four simulations, with all forcing run: [ice_ghg_orb_wtr](s), and 3 factorized-forcing runs [ice_ghg_orb](s), [ice_orb](s), and [itrace.0x](s). For in-depth technical information, interested users can refer to the accompanying paper or dissertation.


He, C., Liu, Z., Otto-Bliesner, B. L., Brady, E. C., Zhu, C., Tomas, R., Clark, P. U., Zhu, J., Jahn, A., &Gu, S. (2021), Hydroclimate footprint of pan-Asian monsoon water isotope during the last deglaciation, *Science Advances*, *7*(4), eabe2611.

He, C. (2021), Deciphering the deglacial evolution of water isotope and climate in the Northern Hemisphere, The Ohio State University, 2021.


We kindly ask that you acknowledge the CESM Project and CISL supercomputing resources (doi:10.5065/D6RX99HX) and reference He et al. (2021) when presenting results based on the iTRACE in either oral or written form.



<br/><br/>

<p align='center'>
    <img style="width: 70%; height: 70%" src="/assets/img/itrace_1.png" alt="" title="example image"/>
</p>
<div class="col three caption">
    The iTRACE simulation quantitatively reproduced the last deglacial water isotope and hydroclimate change in the Asian monsoon system (He et al. 2021).
</div>

<br/><br/>


## Project details

- **Simulation names:**
- [all-forcing run] *b.e13.Bi1850C5.f19\_g16.xxka.itrace.ice\_ghg\_orb\_wtr.0x.cam.h0.**variable**.model-year.nc*

- [ice+ghg+orb run] *b.e13.Bi1850C5.f19\_g16.xxka.itrace.ice\_ghg\_orb.0x.cam.h0.**variable**.model-year.nc*

- [ice+orb run] *b.e13.Bi1850C5.f19\_g16.xxka.itrace.ice\_orb.0x.cam.h0.**variable**.model-year.nc*

- [ice run] *b.e13.Bi1850C5.f19\_g16.xxka.itrace.0x.cam.h0.**variable**.model-year.nc*

- *[NOTE] Some runs named in **ice\_ghg\_orb\_mwtr** are also available at Climate Data Gateway. These are failed test runs, so please neglect them.*
- *[NOTE] For all-forcing runs, please see the [roadmap](https://docs.google.com/spreadsheets/d/10WhscwRmVM3FJIPymjcbT6aGKRisAkQ-dnpmxr7Psso/edit?usp=sharing)*


- **Model version:** iCESM1.3
- **Resolution:** f19\_g16
- **Period:** 20,000-11,000 years before present
- **Time frequencies saved:** monthly
- **Machine:** Cheyenne
- **Compset:** *Bi1850C5*

## Data Acquisition

The data is available on the NCAR Casper **/glade/campaign/cesm/collections/iTRACE** and from the Climate Data Gateway at NCAR.

The following are step by step directions on how to download iTRACE data from the Climate Data Gateway.

Proceed to the [iTRACE page](https://www.earthsystemgrid.org/dataset/ucar.cgd.ccsm4.iTRACE.html).

Scroll to the bottom of that page under Child Datasets, and click on the component and time frequency you are interested in.

The files are organized by variable, listed at the end of each link. Click on the variable you are interested in.

Click on the Download Options button. At this point, if you have not logged into the Climate Data Gateway you can do so now. If you have not registered before, registration is free and quick.

Upon logging in you will see a ridiculously long list of files. Scroll down until you see files that start with the simulation names identified above. Once you have identified a file that you would like to download, click on the check box to the left of the file name. Note that you can select multiple files on this page at once. When you are finished selecting files, scroll to the top (or bottom) of the page and click on the Download Options for Selection box.

Click the Request File Transfer from Archive or choose an alternative method, and follow the status of the file transfer request


## Some Known issues

Due to the abrupt ocean bathymetry change at 14 and 12ka, our model produced unrealistic short and abrupt shocks in some regions. Independent sensitivity experiments were conducted over several hundred years at 14 and 12ka, with ice-sheet and bathymetry changes implemented approximately 200 years apart. The results of these experiments reveal that the shock responses can be predominantly regarded as a linear superposition of the bathymetry and ice-sheet changes.


<br/><br/>

<br/><br/>

## Publications using iTRACE

<div class="publications">
 {% bibliography -f chengfei --query @*[tag2=itrace] --group_by type %}
</div>