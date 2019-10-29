# Hardware

Our lab strongly relies on hardware accelerators for computing models in a reasonable time.

Libraries used and developed in the lab are strongly coupled to NVIDIA GPUs. 
[Kerosene](https://github.com/banctilrobitaille/kerosene/tree/master/kerosene) uses 
[NVIDIA apex](https://github.com/NVIDIA/apex) library for FP16 - Half precision floating point units. This library only 
supports the following generations of GPUs (see Table 1). Consider 6 or 8 GB of VRAM to be the minimum requirement for 
doing research with 3D medical images (volumetric data). Consider a minimum of 16 GB of system RAM to be the minimum 
requirement.


#### Table 1 : GPU compatibility list

| Code name | Compute capability (version) | Common model name                                                                                                |
|-----------|------------------------------|------------------------------------------------------------------------------------------------------------------|
| Pascal    | 6.0                          | GTX 1060, GTX 1070, GTX 1080, GTX 1080Ti, Titan X, Titan Xp, Tesla P100                                          |
| Volta     | 7.0                          | Titan V, Tesla V100                                                                                              |
| Turing    | 7.5                          | GTX 1660, RTX 2060, RTX 2060 Super, RTX 2070, RTX 2070 Super, RTX 2080, RTX 2080 Super,  RTX 2080 Ti, RTX Titan  |


## Drivers and CUDA version

One thing to make sure is the compatibility between your NVIDIA Display driver and the CUDA version. Ensure you install 
versions which are compatible with each other. Generally, having the latest display driver version installed along with
CUDA 10.1, both installed from binary UNIX installer, is the best suited configuration. 


## Library compilation

PyTorch library should be compiled manually on each of your workstation and deployment server for optimal performance.


## Singularity containers (under development)

A solution using Singularity containers with pre-compiled libraries and GPU passthrough are under development and will
soon be installed and released on department's servers. Documentation on how to use these GPU-accelerated 
containers will follow.