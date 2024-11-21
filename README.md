<h4 align="center">LibSGM: Semi-Global Matching algorithm library </h4>

<p align="center">
  <a href="https://www.python.org/downloads/release/python-380/"><img src="https://img.shields.io/badge/python-v3.8+-blue.svg"></a>
  <a href="https://github.com/CNES/Pandora_libSGM/actions"><img src="https://github.com/CNES/Pandora_libSGM/actions/workflows/libsgm_ci.yml/badge.svg?branch=master"></a>
  <a href="https://codecov.io/gh/CNES/Pandora_libSGM"> <img src="https://codecov.io/gh/CNES/Pandora_libSGM/branch/master/graph/badge.svg?token=OZCYI843JH"/></a>
  <a href="https://opensource.org/licenses/Apache-2.0/"><img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg"></a>
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#install">Install</a> •
    <a href="#usage">Usage</a> •
  <a href="#related">Related</a> •
  <a href="#references">References</a>
</p>

## Overview

libSGM is an implementation of Semi-Global Matching (SGM) algorithm based on [[Hirschmuller, 2008]](#1.), [[Ernst, Ines & Hirschmüller, 2008]](#2.) and [[Hirschmüller, Buder & Ernst, 2012]](#3.).

The main algorithm is written in C++ and is wrapped with cython to provide a `libSGM` python module.

An experimental less efficient python only module `libsgm_python` is available for study purposes only.

## Install

**libsgm** is available on Pypi and can be installed by:

```bash
pip install libsgm
```

From source in dev mode, clone the public repository then :

```bash
make install 
source venv/bin/activate # Libsgm is installed in virtualenv
```

## Usage

libSGM is a library only and must be used as a package :

```python
import c_libsgm
...
cost_volumes_out = c_libsgm.sgm_api(cost_volume_in, p1, p2, directions, invalid_value, segmentation=optimization_layer, cost_paths=False, overcounting=False)
```

Let's see [pandora_plugin_LibSGM](https://github.com/CNES/pandora_plugin_libsgm) for real life exemple.

## Documentation

To build library documentation, `doxygen` must be installed on your system.
After installation from source, dependencies are installed in the virtualenv.
Documentation can be generated by:

```bash
source venv/bin/activate
make docs
```

## Related

[Pandora](https://github.com/CNES/Pandora) - A stereo matching framework  
[Plugin_LibSGM](https://github.com/CNES/pandora_plugin_libsgm) - Stereo Matching Algorithm plugin for Pandora  

## References

Please cite the following paper when using libsgm:
*Cournet, M., Sarrazin, E., Dumas, L., Michel, J., Guinet, J., Youssefi, D., Defonte, V., Fardet, Q., 2020. Ground-truth generation and disparity estimation for optical satellite imagery. ISPRS - International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences.*

<a id="1.">[Hirschmuller, 2008]</a>
*H. Hirschmuller, "Stereo Processing by Semiglobal Matching and Mutual Information," in IEEE Transactions on Pattern Analysis and Machine Intelligence, vol. 30, no. 2, pp. 328-341, Feb. 2008. doi: 10.1109/TPAMI.2007.1166*

<a id="2.">[Ernst, Ines & Hirschmüller, 2008]</a>
*Ernst, Ines & Hirschmüller, Heiko. (2008). Mutual Information Based Semi-Global Stereo Matching on the GPU. Proceedings of the International Symposium on Visual Computing. 5358. 10.1007/978-3-540-89639-5_22.*

<a id="3.">[Hirschmüller, Buder & Ernst, 2012]</a>
*Hirschmüller, Heiko & Buder, Maximilian & Ernst, Ines. (2012). Memory Efficient Semi-Global Matching. ISPRS Annals of Photogrammetry, Remote Sensing and Spatial Information Sciences. I-3. 10.5194/isprsannals-I-3-371-2012.*
