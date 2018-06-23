Description:
These folders contain scripts to perform Artificial Bandwidth Extension with memory inclusion using Semi-supervised Stacked Auto-encoders.

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

Copyright (C) 2018 EURECOM, France.

This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International
License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

For further details refer to following publication:
- P. Bachhav, M. Todisco, and N. Evans, "Artificial Bandwidth Extension with Memory Inclusion using Semi-supervised Stacked Auto-encoders", to appear in Proceedings of INTERSPEECH, Hyderabad, India.

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

Desctiption:

0) Folders "./Speech_files/NB" and "./Speech_files/WB" contain time aligned NB and WB files respectively

1) Feature extraction :
     - This folder should contain features extracted on 'train', 'dev' and 'test' data using the script "Feature_extraction.m" available in folder 	   	     "./../ABE_explicit_memory_ICASSP18/1_Feature_extraction". See "./../ABE_explicit_memory_ICASSP18/Readme.txt" for more details
     - Download the files from - https://drive.google.com/drive/folders/1Tj0VtCJygK05B28cbAGsyNyXzetDdqm5?usp=sharing and copy them to the folder "1_Feature_extraction"

2) Training of Semi-supervised Stacked Auto-encoder (SSAE)
     - Python script "SSAE.py" (available in folder - "2_SSAE_training) can be used to train a SSAE using the files (each for train, dev and test data) available in folder "1_Feature_extraction"
     - The keras models are saved in folder "2_SSAE_training/your_models_SSAE" after training - Requirement - keras with theano backend (keras - 2.1.4, theano - 1.0.1 and python - 3.5.3)
     - Download our already trained models from - https://drive.google.com/drive/folders/17dS8ZqFTjkF7u7iy_DCcN4Dk1cypOV-5?usp=sharing and copy them to the folder "2_SSAE_training/your_models_SSAE" 

3) GMM training :
     - Script "Build_GMM_SSAE.m" (available in "3_GMM_training") trains a gaussian mixture model (GMM) for joint vectors obtained from SSAE features and HB LP coefficients 
     - The SSAE features for GMM modelling are extracted using the trained SSAE models available in folder "2_SSAE_training/models_SSAE"
     - Choose the appropriate SSAE model name in script "Build_GMM_SSAE.m" for SSAE features extraction and subsequent GMM training

Demo:
4) "ABE_demo.m" (available in folder - "3_Extension") demonstrates the ABE using existing trained models

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


Contact information
===================

For any query, please contact:

- Pramod Bachhav (bachhav at eurecom dot fr)
- Massimiliano Todisco (todisco at eurecom dot fr)
- Nicholas Evans (evans at eurecom dotfr)

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%