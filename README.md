[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/prerakdhawan/Luxembourg-course-2026/HEAD) ![Notion](https://shields.io)

# Optical modelling and Simulation workshop - Luxembourg 2026
This repository provides the packages and assigments for the lecture *Optical Simulation and Modelling*  at **Optics of Solar Cell 2026` workshop at Laboratory of Photovoltaics, UNIVERSITÉ DU LUXEMBOURG**.

To get started with the assignment, use the `launch binder` icon above and look at the two notebooks.

<span style="color:red"> Please note : Since the Binder version runs on the cloud, it will delete your progress and the generated files within 2-3 hours of an active session and **within 10 minutes** of an inactive/idle session. Please save your notebooks, scripts and plots regularly to avoid data loss and progress. </span>


## Task 1 : Gradient refractive index for solar cells
It is commonly accepted in the photovoltaics community that a gradient refractive index profile can outperform a standard anti-reflection coating of same thickness in increasing the incoupling of light into the solar cell. It does so by gradually decreasing the impedance mismatch at each sub-layer thereby minimizing reflection from the front-interface. The refractive index smoothly varies from $n_{absorber}$ to $n_{air}$ as a function of distance above the semiconductor. 

There are several ways to create a smooth gradient in the refractive index n(h), where n is the refractive index at height h above the substrate. One of the methods is to create a quintic refractive index profile where the refractive index is dependent on 4th order polynomial of the height [**[1]**](https://doi.org/10.1364/OE.16.009332).

<div align="center">
<img src="task1_tmm.jpg" width="800">
</div>
    
1.  Use the Transfer Matrix Method (TMM) code provided to you in this repository (`TMM.py`) for simulating a quintic refractive profile above a semi-infinite absorbing cSi layer and show that it can minimize back-reflection at normal incidence. The refractive index of your coating must smoothly vary from $n_{max}=3.5$ to $n_{min}=1$. 
2.  Compare your results with an anti-reflection coating of same thickness and refractive index n=1.5. Keep the thickness of the coating (consisting of 50-100 sub-layers) to be $d=0.6\mu\text{m}$.

**An example of the usage can be found in `tmm_assignment.ipynb`**

## Task 2 Scattering from cylindrical obstacle
Whispering gallery modes (WGMs) are resonances that occur when waves, acoustic or electromagnetic, are confined due to continuous total internal reflection along a curved boundary. These modes form standing wave patterns with high quality factors, enabling strong field localization predominantly near the perimeter of circular or cylindrical structures. A common example of this phenomenon is seen in the Whispering Gallery of St Paul’s Cathedral (figure below), where even faint whispers can travel clearly across the dome due to the acoustic WGMs supported by the circular architecture. 
<div align="center">
<img src="task2_mie_cylindrical.jpg" width="600">
</div>

Researchers have created nanoscale dielectric resonators of $\text{ZnO}$, $\text{SiO}_2$, $\text{TiO}_2$ to excite such resonances and used it for light trapping in solar cells. These nanostructures diffractively couple incident sunlight into WGM modes, circulating it within the active material thus increasing the optical path length and thereby higher photocurrent [**[2]**](https://doi.org/10.1039/C3CP53162G).

Built in 1708, this gallery demonstrates the same underlying physics that governs Mie resonances in **infinitely long dielectric cylinders**.
1.  Use the Mie code provided to you To study scattering from an infinitely long cylindrical scatterer, the Maxwell’s equations must first be re-written in cylindrical coordinates (2D). Using $x^2  (d^2 y)/(dx^2)+x dy/dx-(v^2-x^2 )y=0$, describe the ansatz for the Maxwell’s equations in cylindrical coordinates. 

2. Using the function .. , extract the Mie coefficient `a` and plot the scattering cross-section $Q_{scattering}$ as a function of varying wavelength and diameter while keeping the refractive index to be $n=2.5$.

**An example of the usage can be found in `mie_cylindrical_assignment.ipynb`**

3. **[BONUS]** : Given the same wavelength range, for what value of radii, is it possible to excite a Whispering Gallery Mode in the obstacle? Illustrate this effect by plotting the fields for TM polarization for a fixed radii and wavelength for the optimal case. 