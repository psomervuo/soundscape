# soundscape
This repository contains scripts and information to reproduce the results from global soundscape data.
Scripts are in 3 zip files that open to separate directories pipeline, scripts, and figscripts.

![Slide1](https://github.com/psomervuo/soundscape/assets/39729972/9d434ea3-85dc-4b1e-ac4e-f367e08c6e37)

The data to run the statistical analyses and produce figures (step 3 in figure above) is in zip file 'datatable.zip' that will be available once the data are published.

Scripts are implemented using Bash, Perl, Python, and R. Three binaries (convertLifeplanFileFormat, audioMothName, readHeaderDAT) are not included in pipeline.gz since they contain private data encryption key to convert DAT files into WAV files. However, when starting data processing from WAV files, they are not needed. YamNet and BirdNET-Analyzer are run under virtual environment that user must create. User must also install required Python packages. Script 'bnet_filelist.py' from pipeline can be copied under BirdNET-Analyzer directory after downloading and installing BirdNET-Analyzer. Soundscape indices are computed using Python package Acoustic_Indices. In the present code, 5 indices are computed (ACI, ADI, Bio, H, NDSI) that are defined in file 'acuconfig.yaml'. YamNET is used to calculate mean and maximum probabilities of 6 AudioSet classes Speech, Vehicle, Silence, Wind, Rain, Animal. BirdNET-Analyzer is used to detect all of its classes and site-specific lists are used to filter the results when summarizing the data.
