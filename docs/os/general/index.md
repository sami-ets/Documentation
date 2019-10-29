# Security

A development machine should be secured against threats as well as any other machine (or even especially a research
 machine). Therefore, depending on your operating system, you should consider:

- choosing a known, secure Linux distribution with secure system settings
- installing and configuring a firewall
- setup disk encryption on your workstations


## Linux distribution

Chose a known and recognized Linux distribution. ÉTS officially supports [Linux Ubuntu](http://ubuntu.com) so all
lab machines are running this operating system.


## Firewall

### macOS
To turn on the built-in firewall on macOS:

1. Choose Apple menu () > System Preferences, then click Security & Privacy.
2. Click the Firewall tab.
3. Click the Lock button, then enter an administrator name and password.
4. Click Turn On Firewall.


### Ubuntu
To turn on firewall on Ubuntu:

1. Install the firewall-config package. 
2. Ensure the firewalld service is up and running.
3. Configure interface with the firewall GUI app.

 
## Disk encryption

You will have in your possession a lot of medical images. While these images have been anonymized, it's still personal 
data from patients.

It is strongly recommended you activate disk encryption on your workstations, especially on a mobile computer. If you 
travel a lot and take your notebook with you (including all your source codes), you might consider travelling with disk
encryption enabled.


### macOS
To activate disk encryption on macOS:

1. Choose Apple menu () > System Preferences, then click Security & Privacy.
2. Click the FileVault tab.
3. Click the lock button, then enter an administrator name and password.
4. Click Turn On FileVault.

See [official Apple support page](https://support.apple.com/en-us/HT204837) and 
[About encrypted storage on Mac](https://support.apple.com/en-us/HT208344) for more details. 


### Ubuntu
On Ubuntu, disk encryption should be set upon installing the operating system.


### Backup

Backing up your data is always the best thing you can do to preserve your data integrity in case of disaster. Since 
these backups can also contain medical images, it is strongly recommended to activate disk encryption on the media
you are backing up your data. 

On macOS, make sure you have an encrypted Time Machine Backup.


# Hardware

Our lab strongly relies on hardware accelerators for computing models in a reasonable time.

Libraries used and developed in the lab are strongly coupled to NVIDIA GPUs. 
[Kerosene](https://github.com/banctilrobitaille/kerosene/tree/master/kerosene) uses 
[NVIDIA apex](https://github.com/NVIDIA/apex) library for FP16 - Half precision floating point units. This library only 
supports the following generations of GPUs (see [GPU compatibility list](#gpu-compatibility-list) below). Consider 6 or 8 GB of VRAM to be 
the minimum requirement for doing research with 3D medical images (volumetric data). Consider a minimum of 16 GB of 
system RAM to be the minimum requirement.


## GPU compatibility list

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