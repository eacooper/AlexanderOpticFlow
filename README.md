# AlexanderOpticFlow

This repository contains data and code to support the manuscript titled "Spatial Biases in Optic-Flow Sampling for Self-Motion Estimation in Natural Environments." Each folder contains data and code (Jupyter notebooks) pertinent to the methods and results reported in the manuscript. 

Raw video frames and optic flow fields of the self-motion dataset from the zebrafish habitat can be downloaded [here](10.5281/zenodo.6604547).

## Computational Pipeline

The analysis pipeline is broken into several stages, across the following directories:  
>	CameraCalibration:  
>>		For image reprojection and linearization  
>>		code:	plots camera calibration  
>>		data:	camera calibration parameters, demo images, field site data  
>	GeneralFlowSimulation:	  
>>		For simulating general flows, evaluating errors  
>>		code:	run simulation, visualize errors, and error histograms for local and global flow  
>>		data:	simulated flow errors  
>	LarvalZebraFishBehavior:  
>>		For showing large-field zebrafish OMR response  
>>		code: 	plot tailbeat responses to stimuli  
>>		data:	tailbeats collected in behavioral experiment  
>	CalculateFlows:  
>>		For measuring optic flow from our natural underwater video dataset  
>>		code: 	calculates optic flow with 2 methods  
>>		data:	relies on image dataset and generates flows (see [dataset](10.5281/zenodo.6604547))  
>	NaturalFlowModel:  
>>		For describing sparsity and noise in natural underwater optic flow  
>>		code:	fits noise models to flows  
>>		data:	relies on calculated flows (see [dataset](10.5281/zenodo.6604547))  
>	NaturalFlowSimulation:  
>>		For evaluating self motion estimation on zebrafish naturalistic optic flow  
>>		code: 	run simulation and visualize errors for local and global flow  
>>		data:	simulated flow errors  
>	NaturalFlowDirect:  
>>		For evaluating self motion estimation directly on natural underwater optic flow dataset  
>>		code:	estimate self motion from video samples, compare to simulation and behavior  
>>		data:	relies on calculated flows (see [dataset](10.5281/zenodo.6604547))  
		

## Generating Figures

The figure plots can be generated with the following notebooks:  
>	Graphical abstract:	NaturalFlowDirect/Comparison figure.ipynb  
>	Fig1:			GeneralFlowSimulation/global flow - run simulation.ipynb, GeneralFlowSimulation/global flow - visualize errors.ipynb, GeneralFlowSimulation/global flow - error histograms.ipynb, GeneralFlowSimulation/local flow - run simulation.ipynb, GeneralFlowSimulation/local flow - visualize errors.ipynb, GeneralFlowSimulation/local flow - error histograms.ipynb  
>	Fig2:			GeneralFlowSimulation/global flow - visualize errors.ipynb, GeneralFlowSimulation/global flow - error histograms - Fig2.ipynb, GeneralFlowSimulation/local flow - visualize errors.ipynb, GeneralFlowSimulation/local flow - error histograms - Fig2.ipynb  
>	Fig3: 			LarvalZebrafishBehavior/plot_tailbeats.ipynb  
>	Fig4:			NaturalFlowModel/Noise Model - LK.ipynb, NaturalFlowModel/Noise Model - FS.ipynb   
>	Fig5:			NaturalFlowSimulation/fish sim - visualize errors.ipynb  
>	Fig6:			NaturalFlowDirect/flow analysis.ipynb  
>	Fig7:			NaturalFlowSimulation/fish sim - visualize errors.ipynb  
>	FigS1:			CameraCalibration/demo_image_transforms.ipynb  
>	FigS2:			NaturalFlowModel/Noise Model - LK.ipynb, NaturalFlowModel/Noise Model - FS.ipynb, NaturalFlowModel/param comparison.ipynb  
>	FigS3:			NaturalFlowModel/Noise Model - LK.ipynb  
>	FigS4:			NaturalFlowSimulation/fish sim - visualize errors.ipynb  
>	FigS5:			NaturalFlowSimulation/fish sim - visualize errors.ipynb  
>	FigS6:			NaturalFlowSimulation/fish sim - visualize errors.ipynb  
>	FigS7: 			LarvalZebrafishBehavior/plot_tailbeats.ipynb  	


## Note on field sites

Note that camera orientation relative to the robot varied across sites, leading to the reversal of some motion components at some sites. This was partially addressed with negative frame numbering of images, but note that the following changes should be made to estimated motion components: Oct15 and Oct19 have negative Wy on the circular trajectories, and translations are negative on Oct13, Oct14, and all circular trajectories. Further, we exclude Wy_20 on Oct17 due to systematically low speeds. See RealData/flow analysis.ipynb.

For an illustration of each field site and a schematic of the robotic arm used to collect this data, see CameraCalibration/field_sites.

## Versions

The notebooks have been confirmed to work with the following Python version and library versions:  
	python		 : 3.8.8  
	jupyter-notebook : 6.3.0  
	ipython          : 7.22.0  
	numpy		 : 1.20.1  
	cv2		 : 4.0.1  
	matplotlib	 : 3.3.4  
	scipy		 : 1.6.2  
	pandas		 : 1.2.4  