# Tracking and Data Analysis of Single Amyloid Fibrils in a Thermophoretic Trap

## Contents

- [Discription](#discription)
- [Repository Contents](#repository-contents)
- [Data Availability](#data-availability)
- [System Requirements](#system-requirements)
- [Installation Guide](#installation-guide)
- [Instructions for Use](#instructions-for-use)
- [Notebooks](#Notebooks)
- [License](./LICENSE)


## Discription

This is the maintained version of the Supplementary Software for *"Thermophoretic Trap for Single Amyloid Fibril and Protein Aggregation Studies"*

This repository containes a collection of Python scripts and Jupyter Notebooks for the tracking and the data analysis of single amyloid fibril in a thermophoretic trap. 

## Repository Content

- [TrackerLab](./TrackerLab): GUI for the image processing and tracking of single amyloid fibrils based on the PyQt and PyQtGraph libary.
- [Jupyter-Notebooks](./Jupyter-Notebooks): Juypter Notebooks for the data analysis.
- [COMSOL](./COMSOL): COMSOL files for the FEM simulations of the temperature distribution.

## Data Availability
A sample dataset for demonstration of the software can be downloaded at:  
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1414296.svg)](https://doi.org/10.5281/zenodo.1414296)

## System Requirements

### Hardware Requirements

The software requires a standard computer with about 2 GB of RAM.

### Software Requirements

The software is supported for Windows, Mac OS and Linux. The software has been tested on the following systems:

Windows: 10  
Mac OS: 10.12  
Linux:   

## Installation Guide

The software requires the [Anaconda](https://www.anaconda.com/download/) framework with Python 3.* to be installed. 

### Required Packages:

The following packages are required:

- nptdms
- pyqtgraph

Typically, the install time of [Anaconda](https://www.anaconda.com/download/) and the required packages does not exceed 45 minutes.

## Instructions for Use

First, create a new directory `Data` download the sample dataset at:  
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1414296.svg)](https://doi.org/10.5281/zenodo.1414296)

Then, run the TrackerLab.py script. With all packages installed properly you should see a GUI similar to the screenshot below. 
To open a video file click `Open...` and select all `*_video.tdms` in the sample dataset.

![Screenshot](https://github.com/Molecular-Nanophotonics/Thermophoretic-Trap-for-Protein-Aggregation-Studies/blob/master/Images/Screenshot.PNG)

The `*video.tdms` files are TDMS files recored with LabVIEW containing the image series and metadata such as the binning and the exposure time. For more information about the TDMS file format see [The NI TDM File Format](http://www.ni.com/white-paper/3727/en/)  
Beside these TDMS files the software also supports stacked TIFF files for general use.  
  
In the pre-processing panel a media filter and a circular mask can be applied to the image.
In the tracking tab the parameters for the connected-componente labeling can be adjusted. For detail on the image processing and fibril tracking see Supplementary Note 7.  

To run the tracking algorithm for all selected files click `Batch`. Typically, the processing of 1000 frames takes about 10 s. The tracking data will be stored as a DataFrame named `features` in a HDF5 file along with the metadata. The DataFrame has the following structure:  

```
frame   x      y      area    max_intensity    phi    major_axis_length   minor_axis_length
0       ...    ...    ...     ...              ...    ...                 ...
1       ...    ...    ...     ...              ...    ...                 ...
```
Here, `frame` is the frame number, `x` and `y` the center of mass positions in pixel, `area` the number of pixels of the detected region, `max_intensity` the maximum intentiy in the detected region, `phi` the angle between the x axis and the major axis of the ellipse fitting the region, ranging from `-pi/2` to `pi/2`, and `major_axis_length`, `minor_axis_length` the length of the ellipse major and minor axes in pixel.


## Notebooks

...
