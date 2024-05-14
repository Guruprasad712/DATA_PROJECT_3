# ELECTROCHEMICAL ANALYSIS OF SUPERCAPACITOR ELECTRODES
## Table of contents
- [Project Overview](#project-overview)
- [Data source](#Data-source)
- [Analysis Tools used](#Analysis-Tools-used)
- [Methodology](#project-methodology)
- [Results and findings](#results-and-findings)
- [Conclusion](#conclusion)
  
## Project Overview
This project analyzes the electrochemical performance of graphene-coated copper mesh electrodes with varying porosities for supercapacitor applications.

## Data source
The electrochemical analysis was done at the Crystal Growth Centre in the College of Engineering, Guindy. OrigaLys was used to retrieve the data.

## Analysis Tools used
Python (Matplotlib, SciPy)

## Project Methodology
The tests that were conducted to analyze the electrochemical performance are :

### Cyclic Voltammetry (CV)
It was employed at a constant scan rate of 25 mV/s to investigate the charge storage mechanism of the electrode materials. The resulting CV plots (current vs. potential) provided insights into the dominant processes involved in storing electrical energy within the electrodes.

### Galvanostatic Charge Discharge(GCD)
It was conducted using a constant current density of 5 mA to evaluate the charge/discharge rates and areal capacitance of the electrodes. The resulting GCD curves (potential vs. time) provided the data necessary to calculate these crucial performance parameters.

### Electrochemical Impedance Spectroscopy(EIS) 
It was employed to analyze the behavior of the electrode-electrolyte interface. The data was then plotted as a Nyquist plot (real impedance, Zr, vs. imaginary impedance, -Zi), providing insights into the interfacial processes such as charge transfer kinetics and ionic transport resistance.

The data were collected and plotted using OrigaLys and MatplotLib respectively.

An exampmle Python code for plotting these graphs : 
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





