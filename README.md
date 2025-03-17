# soundscape
This repository contains scripts and information to reproduce the results from global soundscape data.
Scripts are in 3 zip files that open to separate directories pipeline, scripts, and figscripts.

![Slide1](https://github.com/psomervuo/soundscape/assets/39729972/9d434ea3-85dc-4b1e-ac4e-f367e08c6e37)

The data to reproduce the statistical analyses and figures (step 3 in figure above) are in zip file 'datatable.zip' that will be available once the data are published.

Scripts are implemented using Bash, Perl, Python, and R. Two binaries 'convertLifeplanFileFormat' and 'audioMothName' are not included in pipeline.gz since they contain private data encryption key to convert DAT files into WAV files. However, when starting data processing from WAV files, they are not needed. YamNet and BirdNET-Analyzer are run under virtual environment that user must create. User must also install required Python packages. Script 'bnet_filelist.py' from pipeline can be copied under BirdNET-Analyzer directory after its downloading and installing. Soundscape indices are computed using Python package Acoustic_Indices. In the present pipeline, 5 indices are computed (ACI, ADI, Bio, H, NDSI) that are defined in file 'acuconfig.yaml'. YamNET is used to calculate mean and maximum probabilities of 6 AudioSet classes Speech, Vehicle, Silence, Wind, Rain, and Animal. BirdNET-Analyzer is used to detect all of its classes and site-specific lists are used to filter the results when summarizing the data before making the analyses.

## Reproducing the analyses results and figures

Data analyses have been done using R version 4.4.2. in a laptop running Linux Ubuntu OS. Required R packages are maps, MASS, colorspace, and suncalc.
All analyses scripts are in file figscripts.zip and its downloading takes few seconds.
After uncompressing the zip file, there is a separate script for each analysis in order to reproduce all analyses done in the manuscript.
Short description of each script is given below.
Running the analysis with a data table with 1.5M rows takes few minutes with the exception of permutation test used for assessing the statistical significance (script1d and script2d) and calculating sunrise-sunset times (script2a) that take several hours.
All R scripts should be run in the same directory where the data table is (directory datatable).
Output files are named after the script names and they are written in the same directory where the data is.

Data table will be inserted in this github page once the paper is accepted.
Meanwhile, reviewers can access the data table in zenodo using a private link.

***
* script1a: show all sampling sites on world map, output pdf file 
* script1b: fit local and global time series models for all response variables using wall clock times, output pdf file
* script1c: fit global time series models for 15 response variables and show predictions for selected latitudes using wall clock times, output pdf file
* script1d: calculate permutation test for R2 values, this takes several hours
* script1e: calculate R2 values for 15 response variables using wall clock times, output pdf file
* script1f: calculate urban-natural difference for 15 response variables using wall clock times, output pdf file
***
* script2a: convert wall clock times to sunset-sunrise times (this takes several hours), output files of this script are needed in scripts 2b-2e, note: these are precomputed in the datatable directory
* script2b: fit local and global time series models for all response variables using sunset-sunrise times, output pdf file
* script2c: fit global time series models for 15 response variables and show predictions for selected latitudes using sunset-sunrise times, output pdf file
* script2d: calculate permutatation test for R2 values, this takes several hours
* script2e: calculate R2 values for 15 response variables using sunset-sunrise times, output pdf file
* script2f: calculate urban-natural difference for 15 response variables using sunset-sunrise times, output pdf file
***
* script3: correlation between 15 response variables, output pdf file
***
* script4: differences of bird species richnesses between urban and natural sites (analyses based on species accumulation curves), output pdf file
***
* script5: bird trait differences between urban and natural sites (Wilcoxon signed rank test for proportions of community weighted means of AVONET traits), output pdf file and text file containing the results
***
