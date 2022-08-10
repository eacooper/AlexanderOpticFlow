# AlexanderOpticFlow

This repository contains data and code to support the manuscript titled "Spatial Biases in Optic-Flow Sampling for Self-Motion Estimation in Natural Environments." Each folder contains data and code (Jupyter notebooks) pertinent to the methods and results reported in the manuscript. 

Raw video frames of the self-motion dataset from the zebrafish habitat can be downloaded at Zenodo (10.5281/zenodo.6604547).

The notebooks have been confirmed to work with the following Python version and library versions:
XYZ

## OpticalFlowSimulations

## CameraCalibration

This folder contains the calibration files from each camera used to collect self-motion videos from the zebrafish habitat, and a notebook that illustrates how to load, plot, and use the calibration files to undistortion video frames.

Note that the "camIntrinsics" files use the Matlab OpenCV Toolbox and are not appropriate for loading into Python. The values in these files are included in the manuscript directly.

## FieldSites

This folder contains images taken at each of the field sides as well as a schematic of the mechanical arm.

## LarvalZebrafishFlow

## LarvalZebrafishBehavior

This folder contains the data from the larval zebrafish OMR behavioral experiment and a notebook that loads and plots these data.
