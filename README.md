# ELECTROCHEMICAL ANALYSIS OF SUPERCAPACITOR ELECTRODES
## Table of contents
- [Project Overview](#project-overview)
- [Data source](#Data-source)
- [Analysis Tool used](#Analysis-Tool-used)
- [Methodology](#project-methodology)
- [Results and findings](#results-and-findings)
- [Conclusion](#conclusion)
  
## Project Overview
This project analyzes the electrochemical performance of graphene-coated copper mesh electrodes with varying porosities for supercapacitor applications.

## Data source
The electrochemical analysis was done at the Crystal Growth Centre in the College of Engineering, Guindy. OrigaLys was used to retrieve the data.

## Analysis Tool used
Python (Matplotlib)

## Project Methodology
Three samples, labeled as Sample 1, Sample 2 and Sample 3 each exhibiting different levels of porosity, underwent analysis to evaluate their electrochemical performance. The tests conducted to assess this performance included:

### Cyclic Voltammetry (CV)
It was employed at a constant scan rate of 25 mV/s to investigate the charge storage mechanism of the electrode materials. The resulting CV plots (current vs. potential) provided insights into the dominant processes involved in storing electrical energy within the electrodes.

### Galvanostatic Charge Discharge(GCD)
It was conducted using a constant current density of 5 mA to evaluate the charge/discharge rates and areal capacitance of the electrodes. The resulting GCD curves (potential vs. time) provided the data necessary to calculate these crucial performance parameters.

### Electrochemical Impedance Spectroscopy(EIS) 
It was employed to analyze the behavior of the electrode-electrolyte interface. The data was then plotted as a Nyquist plot (real impedance, Zr, vs. imaginary impedance, -Zi), providing insights into the interfacial processes such as charge transfer kinetics and ionic transport resistance.

The data were collected and plotted using OrigaLys and MatplotLib respectively.

An example Python code for plotting these graphs : 
```python
#The required libraries
import matplotlib.pyplot as plt
import pandas as pd
%matplotlib inline

#Cyclic Voltammetry

CV_1 = pd.read_excel("CV_1.xlsx")
CV_2 = pd.read_excel("CV_2.xlsx")
CV_3 = pd.read_excel("CV_3.xlsx")

plt.figure(figsize=(7, 3.5)) 

# Plot the CV curves
plt.plot(CV_1['Potential [mV]-25'],CV_1['Current [µA]-25'], label="sample 1")
plt.plot(CV_2['Potential [mV]-25'],CV_2['Current [µA]-25'], label="sample 2",color = 'yellow')
plt.plot(CV_3['Potential [mV]-25'],CV_3['Current [µA]-25'], label="sample 3",color = 'red')

# Set axis labels and title
plt.xlabel("Potential (mV)")
plt.ylabel("Current (µA)")
plt.title("Cyclic Voltammetry at 25 mV/s")
plt.legend()
```
## Results and findings

### Cyclic voltammetry
The cyclic voltammograms for samples 1, 2, and 3 exhibit similar broad, hump-shaped features in both the positive and negative scan directions suggesting a pseudo capacitance behaviour. Despite the similar features, a variation in the current response is observed. Sample 2 exhibits a slightly higher current response compared to Samples 1 and 3. This aligns with the different porosity levels of the samples. Sample 1, being non-porous, likely offers a limited surface area, potentially leading to a lower current response. Sample III, despite being porous, shows a noticeably lower current response compared to Sample II. This unexpected observation suggests that there might be an optimal range for porosity in these electrodes.
The graph : 

<img width="507" alt="CV at 25mV" src="https://github.com/Guruprasad712/DATA_PROJECT_3/assets/160844022/02981bbb-55c1-4635-a8cf-aa48b2d25887">

### Galvanostatic Charge Discharge
The charging/discharging rates were found for the sample electrodes using GCD. Also the areal capacitance was found using the following formula :

                    Ca (F/cm2) = IΔt / AΔV
Here, I = current (A), Δt = discharge time (s), A = surface area (cm2),
ΔV = Potential difference (V)

The GCD graph :                                                             
<img width="487" alt="GCD_final" src="https://github.com/Guruprasad712/DATA_PROJECT_3/assets/160844022/f73a44ee-0cca-4b3b-8dfc-3689b25b060f">

The areal capacitence of the samples are :                                                                      
<img width="300" alt="GCD_table" src="https://github.com/Guruprasad712/DATA_PROJECT_3/assets/160844022/d6ff9a22-263e-4086-9c99-af67ac16d662">

### Electrochemical Impedance Spectroscopy
The EIS graph is plotted between real impedance (Zr) and imaginary impedance (-Zi). 

The EIS plot for sample 1 and 2 :          
<img width="250" alt="EIS_final" src="https://github.com/Guruprasad712/DATA_PROJECT_3/assets/160844022/88fda55e-cd1b-460e-9477-3e2c779cdb5f">

The diameter of the semi-circle at the bottom is used to determine the resistance at the electrode – electrolyte interface. A larger diameter represents higher charge resistance. The samples I and II have a similar resistance.

## Conclusion

The analysis of three graphene - coated copper mesh electrodes with varying 
porosities revealed a complex relationship between pore structure and electrochemical performance. Sample 2, exhibiting a slight increase in capacitance (0.26 F/cm²) but slower charging/discharging rates compared to the non-porous Sample 1 (0.24 F/cm²), suggests that a moderate level of porosity can be beneficial. This indicates improved accessibility of ions to the electrode surface, enhancing charge storage. 
            However, Sample 3 with a potentially higher porosity based on the significant decrease in capacitance (0.12 F/cm²), highlights the detrimental effect of excessive porosity. These findings suggest an optimal porosity range exists for maximizing the capacitance of these electrodes.


