# Simulation-of-water-flow-by-using-rainfall-based-model

Summary:
A continuous rainfall runoff model is used to estimate and forecast the floods for various rainfall events, to help with successful flood risk assessment and management. The model was developed for the simulation of flood events at a half-hourly time scale based on a variety of rainfall amounts and consists of two components: the first is a soil water balance model that simulates the soil moisture temporal pattern and sets the initial conditions for the second component, which is an event-based rainfall-runoff model for flood hydrograph simulation. Pre-simulated events are stored in the rainfall runoff database according to the quantity of rainfall, starting moisture conditions, and initial discharge. The capability of the model to predict extreme discharge conditions was assessed by coupling the rainfall-runoff model with the rainfall based on observed rainfall with the temperature and runoff data. Therefore, the frequency of annual maximum discharge for the two basins is compared with observed data from two gauged river sections in the Yarmouk River basin (Jordan). The agreement between observed and modelled discharge is quite good, both in the calibration and validation periods.

The following files are distributed:

1) MATLAB codes
1.1) "model.m": model code
1.2) "model _calibration.m": code for model calibration 

2) Secondary file:
2.1) "fixed_par.txt": contains
     a) the area of the basin (km^2)
     b) the computational time step (for flood event simulation), 0.2 is OK
2.2) "IUH.txt": contains the coordinates of the dimensionless IUH (Instantaneous Unit Hydrograph)
2.3) "X_opt_ model.txt": parameter values of model     
     W_p       = PAR(1); % initial conditions, fraction of W_max (0-1)
     W_max     = PAR(2); % Field capacity
     m2        = PAR(3); % exponent of drainage
     Ks        = PAR(4); % Ks parameter of infiltration and drainage
     Nu        = PAR(5); % fraction of drainage versus interflow
     gamma1    = PAR(6); % coefficient lag-time relationship
     Kc        = PAR(7); % parameter of potential evapotranspiration
     lambda    = PAR(8); % initial abstraction coefficient
     Sr_coeff  = PAR(9); % multiplicative coefficient for Sr

3) INPUT file :
3.1) "section.txt": example file for section (64 km^2)
     It contains 4 columns
     a) date (in numeric Matlab format)
     b) rainfall depth (in mm)
     c) air temperature (°C)
     d) observed discharge data (m^3/s)

4) OUTPUT file:
4.1) "section.png": figure with the model output
     
     Upper figure: relative soil moisture timeseries
     Middle figure: rainfall timeseries
     Lower figure: Observed vs simulated discharge
-------------------------------------------------------------------
To run the model for your own catchment the following steps have to be done:
1) creation of input file, e.g. "section.txt" and change the basin area in the "fixed_par.txt" file
2) model calibration with " model _calibration.m"
4) Run of the model with " model.m"


