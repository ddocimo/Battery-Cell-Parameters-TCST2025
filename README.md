# Battery-Cell-Parameters-TCST2025
This repository contains data describing fitted lithium iron phosphate 
battery cell parameters.

This data contains model parameters for lithium iron phosphate battery 
cells as described in the following article. If you make use of this data, 
follow the appropriate licensing rules described by GNU General Public 
License v3.0, and please cite the article:

# ----------------------Article Information------------------------------ #
P. T. Abadie, T. R. Jahan and D. J. Docimo, "A Joint Analysis and 
Estimation Effort for Cell-to-Cell Variations in Lithium-Ion Battery 
Packs," in IEEE Transactions on Control Systems Technology, vol. 33, no. 2,
pp. 760-774, March 2025, doi: 10.1109/TCST.2024.3516364.
# ----------------------------------------------------------------------- #

Notes for the lithium-iron phosphate 18650 battery cells' data:

- The cells are from 2 different manufacturers, and the rows are such that 
  every dataset in the same row is from the same manufacturer.

- Each structure in the mat file is data for an individual cell. Saved in 
  each structure is the nominal capacity of the cell and a standard SOC 
  map, along with the parameter maps that depend on this SOC: the open-
  circuit voltage (OCV), the ohmic resistance (R), the 3 relaxation state 
  time constants (tau), and the 3 relaxation capacitances (C).

- There are 66 batteries' parameters total, separated into two batches: 50 
  cells are from Manufacturer 1 (row 1) and 16 cells are from Manufacturer 
  2 (row 2). A cell's data structure can be accessed by indexing the 
  "cell_data_LFP18650.mat" variable in MATLAB. For example, the capacity of
  the 10th cell from Manufacturer 2 would be found like so:
        load('cell_data_LFP18650.mat')
        cell_capacity = cell_data_LFP18650{2,10}.Q;
  
  Similarly, if one wanted to plot the open-circuit voltage curve:
        open_circuit_voltage = cell_data_LFP18650{2,10}.OCV;
        SOC_map = cell_data_LFP18650{2,10}.SOC;
        plot(SOC_map,open_circuit_voltage)

- As described in the article, the capacity was determined from both charge
  and discharge profiles. The other parameter maps were fitted using the 
  discharge profile only. Parameter maps based on the charge profile, as 
  well as averaged maps, are available upon request.

- If a different file format is requested for this data, please reach out 
  and we'll do our best to accommodate reasonable requests.
