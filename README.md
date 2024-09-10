# README

## Project Overview

### Research Objective
This study aims to investigate the strain energy changes caused by mining-induced fault coseismic slip, specifically at the Yuejin coal mine in China. It seeks to quantify how mining activities, such as longwall mining, affect the spatial distribution of strain energy and how fault coseismic slip contributes to seismic events like rockbursts.

**Software:** The research utilizes PyLith 2.2.2, a finite element software well-suited for modeling crustal deformations and simulating earthquake faulting. The Computational Infrastructure for Geodynamics (CIG) provides this source code free of charge, with the hope that it will advance geophysics research.

**Licence:** PyLith is an open-source software licensed under the GNU General Public License (GPL) version 2.0.

**Methodology:** Numerical simulations were carried out to model coseismic slip on faults in a two-dimensional plane-strain condition. The '0 model' concept was introduced to provide a baseline for understanding how fault-induced seismic events influence strain energy distribution. Different fault types, including Mohr-Coulomb Fault (MCF) and Slip-Weakening Fault (SWF), were analyzed.

**Key Innovation:** The main innovation of this study is the introduction of the '0 Model' as a benchmark for strain energy distribution prior to fault slip. This provides a controlled reference for analyzing how mining-induced fault slip alters strain energy in the fault-mining zone. Additionally, this study integrates fault coseismic slip data with mining-induced stress variations to uncover the potential contribution of fault slip to rockburst and coal burst events, a novel consideration in mining safety protocols.

**Execution:**
- Three distinct fault models were tested: Virtual Fault (VF), Mohr-Coulomb Fault (MCF), and Slip-Weakening Fault (SWF).
- The mechanical response of these models was explored under different fault dip angles and distances from the mining face.
- Strain energy was computed by solving stress-strain relations through finite element simulations, with results visualized in terms of spatial distribution along the fault.

This approach allows for a deeper understanding of how coseismic fault slip contributes to localized strain energy concentrations and the potential triggering of rockbursts in mining environments. The findings have direct implications for improving seismic risk mitigation strategies in underground mining operations.

## Analysis Parameters

### Table 1: Mechanical Parameters in the Numerical Model  
  
| Parameters                       | Values                            | Parameters                           | Values                            |  
|----------------------------------|-----------------------------------|--------------------------------------|-----------------------------------|  
| Young’s modulus, E (GPa)         | 15                                | Mining thickness (m)                 | 10                                |  
| Poisson’s ratio, ν               | 0.25                              | Mining distance, Dm (m)              | -210 to 210                       |  
| Shear modulus, G (GPa)           | 6.5                               | Panel width (m)                      | 200                               |  
| Cohesion stress, C (MPa)         | (0)<sup>c</sup>                   | Dynamic friction coefficient, μd     | 0.6                               |  
| Density, ρ (kg/m³)               | 2400                              | Static friction coefficient, μs      | 0.7 (0.6)<sup>a</sup>             |  
| Background stress ratio, rb      | 2                                 | Critical slip distance, Dc (m)       | 0.02                              |  
| Depth, h (m)                     | 0-1600                            | Fault dip angle, φ (°)               | 30 (increments of 10° from 20° to 80°)<sup>b</sup> |  
| Mining level (m)                 | 1000                              |                                      |                                   |  
  
**Note**:  
- <sup>a</sup> The value is used to analyze the influence of μ on MCF.  
- <sup>b</sup> The values are used to analyze the influence of φ on VF.  
- <sup>c</sup> In this study, we assume that the cohesion along the fault is zero, which is a common simplification frequently applied in modeling shallow earthquakes (e.g., Buijze et al. 2019).

## Running Guide

1. Refer to the official PyLith documentation to ensure the correct installation of PyLith version 2.2.2.
2. In the project root directory, start the simulation process with the following command:

```bash
cd /YOUR_PYLITH_PATH/pylith
source setup.sh

cd /YOUR_MODEL_PATH
pylith step00.cfg
```
After the simulation is complete, all results will be output to the `output` folder.
