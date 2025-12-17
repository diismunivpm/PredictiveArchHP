# PredictiveArchHP
# Archetypes of Model Predictive Control for real Heat Pumps
PredictiveArchHP contains advanced control archetypes (i.e., Model Predictive Controls, MPCs) for real residential Heat Pumps (HPs). The objective of the MPC is to minimise primary energy consumption over a forecast horizon, while maintaining the indoor air temperature in an imposed comfort range.
Three different archetypes, depending on the type of heating system, are available. 
  1. Archetype 1: MPC for Heat Pump with low temperature radiators.
  2. Archetype 2: MPC for Heat Pump with low temperature radiators and a hot water tank as sensible Thermal Energy Storage.
  3. Archetype 3: MPC for Heat Pump with underfloor heating. 
  4. Archetype 4 (new): MPC for Heat Pump with underfloor heating and a hot water tank as sensible Thermal Energy Storage.

Archetypes are based on grey-box models. In the uploaded version of HeatPumpsOptControl, reference is made to a typical Belgian residential building, however, the models can easily be adapted for other case studies. Different performances curves can be easily incorporated to model different HPs. In the uploaded version of PredictiveArchHP the HP is a real water-water HP.
The effectiveness of archetypes has been validated through experimental tests.

# Dependencies
PredictiveArchHP is implemented in Python 3.9 and uses the packages os, numpy, pandas, xlsxwriter, which are all generally available. Moreover, PredictiveArchHP need GEKKOOptimizationSuite* (gekko.readthedocs.io/en/latest/).

*Beal L.D.R., Hill D.C., Martin R.A., Hedengren J.D. 2018. GEKKO Optimization Suite. Processes, 6, 106. https://doi.org/10.3390/pr6080106

# Structure of each archetype
Each of the four available archetypes consists of two files .py:
  1.	MPC.py -> allows the control settings to be defined (forecast interval, intervals granted to the air temperature, initial conditions of decision variables and states) and collects the control actions to be sent to the controlled Heat Pump.
  2.	AuxiliaryFunctions.py → contains all functions for modeling the dynamic behavior of the building (via a grey-box model with lumped parameters), the dynamic variability of Heat Pump performance (via polynomial regression), and the implementation and solution of the optimization problem. Each archetype also includes an .xlsx file with the climate forecast data:
     - For archetypes 1, 2, and 3: ClimateData_TypWeek.xlsx
     - For archetype 4: ClimateData_TypWeek_no_price.xlsx
    	
# Revision history
- Oct 25, 2023: First version (Archetypes 1, 2 and 3)
- Dec 11, 2025: Loading new Archetype 4
   
# References
Please cite PredictiveArchHP using the information below:

Mugnini A., Evens M., Arteconi A., Model predictive controls for residential buildings with heat pumps: Experimentally validated archetypes to simplify the large-scale application, Energy and Buildings., Volume 320, 2024, 114632, ISSN 0378-7788, doi.org/10.1016/j.enbuild.2024.114632

(This paper is the reference for Archetypes 1, 2, and 3. The reference for Archetype 4 is in preparation)


# Acknowledgment
The implementation and validation of the archetypes 1,2 and 3 was made possible by a grant for a scientific stay in Flanders funded by Research Foundation Flanders - FWO.

