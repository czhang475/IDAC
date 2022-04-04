# Processing Infinite Dilution Activity Coefficients (IDACs)

## Description
Contains a series of scripts to (1) clean and process experimental IDAC values scraped from existing literature, (2) generate datasets for input into OpenEye's Orion platform, (3) compute estimated IDAC values from results generated via Orion's solvation free energy floes and (4) visualize differences in experimental and computational IDAC values for different molecules.

Data was taken from the paper:
Kojima, K.; Zhang, S.; Hiaki, T. Measuring methods of infinite dilution activity coefficients and database for systems including water. *Fluid Phase Equilibria* **1997**, *131* (1-2), 145–179. DOI: 10.1016/S0378-3812(96)03210-4


## Data Preparation
The website [pdftables.com](https://pdftables.com/) was used to convert individual pages of the PDF text into Excel files.  Data was reorganized by unmerging cells and concatenating their contents, then subsequently arranged into one long table on a single .csv file “table#.csv” in each folder.

Solvent names were dragged down to cover all applicable rows. For table 2, many solvent names included a footnote – these were added in manually prior to exporting the data.


## Folders
Each folder, labeled Tables 1, 2 and 3, contains the relevant raw Excel files for the respective data table, a .csv file with all the compiled raw data (the file imported into Python), the script used to clean the data, and the finished data table.


## Scripts
The three scripts are very similar to each other with minor differences based on how the data within each table was formatted. No experimental methods were given for values in Table 2.

The main functions used to clean the data files, `clean_temp()` and `clean_measure()`, are functions that are coded depending on the format of the raw data. These functions are by no means generalizable for all data sets.

The majority of the code involves simple manipulations using the Pandas package in Python. What could not be cleaned via the script was ultimately addressed by hard coding the proper values within the code.
