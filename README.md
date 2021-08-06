# Adversarial-Variational-Autoencoder-Training-for-CFD-Simulations

Experimental Repo for Using adversarial training to improve forecasts of data-driven surrogate models of CFD simulations with integration of DA of experimental data.
The Adv. VAE is trained on the CO2_tracerfields of the pub simulation which serves as proxy for exposure to Covid19. The mode accuracy is compared to a simple PCA decomposition thereof and the space reconstructed by the Adv.VAE. Optionally, we construct a pre-processing step where images of the experimental data can be assimilated with the CFD simulation.  

## Requirements

python 3

tensorflow 2.4.0

scikit-learn 0.23.2


## Pre Processing
The folder Pre-Processing contains the scripts to assimilate experimental data with the CFD simulation. In a first step the CFD is saved as a sequence of images, in a second step the images are combined with the images of experimental data using a DA procedure.
<img src="https://github.com/PNadler-Imperial/Adversarial-Variational-Autoencoder-Training-for-CFD-Simulations/blob/main/preprocessing/da_example.png" width="600" height="450">

## Main Model
The model is trainable without the pre-processing and requires execution of the scripts as outlined in the main model folder. If in the previous step the assimilated state was saved, there is an option of da_state to integrate this into the network architecture altough this is still experimental.
The main fils for the CFD simulations can be found `here <https://imperiallondon-my.sharepoint.com/:f:/g/personal/pn18_ic_ac_uk/Es2ro2y21TREpxGD52c-yQMBDWfbZtkGBJRazHEZ7b6PEg?e=IMBW1g>`_. (Imperial Access Only)

These are the CO2_tracer fields of the CFD simulation to be learned:
![alt text](https://github.com/PNadler-Imperial/Adversarial-Variational-Autoencoder-Training-for-CFD-Simulations/blob/main/model_main/ground_gif.gif?raw=true)


## Post Analysis
The corresponding folder provides additional figures and plots as well as a script to integrate the fields generated by the Adv. VAE back into the vtu files of the pub.
These are the CO2_tracer fields reconstructed from the Autoencoder:
![alt text](https://github.com/PNadler-Imperial/Adversarial-Variational-Autoencoder-Training-for-CFD-Simulations/blob/main/model_main/vae_gif.gif?raw=true)
