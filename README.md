# Tracking and Data Analysis of Single Amyloid Fibrils in a Thermophoretic Trap

## Contents

- [Discription](#discription)
- [Repository Contents](#repository-contents)
- [System Requirements](#system-requirements)
- [Installation Guide](#installation-guide)
- [Instructions for Use](#instructions-for-use)
- [Notebooks](#Notebooks)
- [License](./LICENSE)


# Discription

This repository provides a framework for the tracking and the data analysis of single amyloid fibrils in a thermophoretic trap. 
Within the framework the [TrackerLab](./TrackerLab) implements a GUI for the image processing and tracking of single amyloid fibrils. 
The directory [Notebooks](./Notebooks) contains a collection of Jupyter Notebooks for the data analysis.  

# Repository Contents

- [TrackerLab](./TrackerLab): A graphical user interface for the tracking of single amyloid fibrils based on the PyQt and PyQtGraph libary.
- [Data](./Data): A small dataset to demonstate the framework.
- [Notebooks](./Notebooks): Collection of Juypter Notebooks for the data analysis.


# System Requirements

## Hardware Requirements

The framework requires a standard computer with about 2 GB of RAM.

## Software Requirements

This package is supported for Windows, Mac OS and Linux. The package has been tested on the following systems:

Windows: 10
Mac OS: 10.12  
Linux:   

# Installation Guide

The software requires the [Anaconda](https://www.anaconda.com/download/) framework with Python 3.6 to be installed. 

## Required Packages:

The following packages are required:

- nptdms
- pyqtgraph
- trackpy

To install the packages open the Anaconda Prompt and type: pip install "package"

The typical the install time, including all packages, does not exceed 30 minutes.

# Instructions for Use

To start the TrackerLab run the script: TrackerLab.py
To open a data file click the 'Open' button and located the 'Set1_001_video.tdms' in the [Data](./Data) directory.  

[[https://github.com/MolecularNanophotonics/TTT/blob/master/Screenshots/Screenshot-01.png]]

This is a custom TDMS file used to store data with our custom LabVIEW image aquisistion containing the image data and some metadata 
Beside these TDMS file the software also supports stacked TIFF files for general use.
In the pre-processing box a media filter and a circular mask can be applied to the image. 
In the tracking tab the parameters for the connected-componente labeling can be adjusted.
To run the tracking . The tracking data will be stored in a CSV or HDF5 depending on the selected setting under 'Settings'.

