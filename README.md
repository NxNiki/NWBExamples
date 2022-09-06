# NWB Example

This repository is an example and exploration of using NWB files for storing human single neuron data.

## Overview

The [Neurodata Without Borders](https://www.nwb.org/) format is standardized file format for
storing neurophysiological data.

This repository includes some overview examples of creating and using NWB files, and
related analyses and tools that demonstrate the utility of NWB files.

## Repository Layout

This repository contains a series of examples, organized into Jupyter notebooks.

The following notebooks are included:
- 01 introduces the basics of the NWB file format
- 02 explores uses NWB files for human spiking data
- 03 explores analyzing a data stored in NWB format
- 04 explores group level analyses using NWB files
- 05 explores spike sorting data stored in NWB files
- A1 explores metadata files to use with data conversion

Note that notebooks 01, 02, & 05 use simulated data, whereas 03 & 04 use an openly available dataset described below.

## Requirements

This repository uses Python (>=3.7).

This repository requires the following modules:
- [numpy](https://github.com/numpy/numpy)
- [pynwb](https://github.com/NeurodataWithoutBorders/pynwb)

Additional optional dependencies are:
- [spikeinterface](https://github.com/SpikeInterface/spikeinterface) for the spike sorting demo
- [pyyaml](https://github.com/yaml/pyyaml) for the metadata file appendix

## Data

Some of the examples use an openly available NWB-formatted dataset, which contains single
unit recordings from human patients during a 'Recognition Memory' (RM) task.

Data & associated files for this release are available at
- Data: [OSF repository](https://osf.io/hv7ja/)
    - To download the NWB files, click on the `NWBData.zip` file in the file list
- Code: [Github repository](https://github.com/rutishauserlab/recogmem-release-NWB)

This dataset is described in the following paper:
- [Chandravadia et al, 2020 - A NWB-based dataset](https://doi.org/10.1038/s41597-020-0415-9)

## Other Resources

Relevant links:

- The [NWB](https://www.nwb.org/) website
- A [training course](https://training.incf.org/collection/neurodata-without-borders-neurophysiology-nwbn) from INCF
- The [HDF5](https://www.hdfgroup.org/solutions/hdf5/) website
- Materials for [PyNWB](https://pynwb.readthedocs.io/en/stable/), the Python interface for NWB files
- Materials for [MatNWB](https://neurodatawithoutborders.github.io/matnwb/doc/index.html), the Matlab interface for NWB files

Citations & relevant papers:
- [Buccino et al, 2020 - SpikeInterface](https://doi.org/10.7554/eLife.61834)
    - This paper describes the SpikeInterface ecosystem, that can spike sort from NWB files
- [Rübel et al, 2021 - The NWB ecosystem](https://doi.org/10.1101/2021.03.13.435173)
    - This is the most recent NWB related paper, describing the overall NWB ecosystem
- [Rübel et al, 2019 - NWB:N 2.0](https://dx.doi.org/10.1101/523035)
    - This paper describes the updated 2.0 version of the NWB neurophysiology data standard
- [Teeters et al, 2015 -  NWB 1.0](https://dx.doi.org/10.1016/j.neuron.2015.10.025)
    - This paper describes the original goals and 1.0 version of the NWB format
