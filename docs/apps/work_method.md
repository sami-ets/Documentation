# Work method

## Computer and workstation
A good work habits is to have your code at only one place. Since a Mac cannot run any CUDA-enabled code, it's not a
good platform to chose to run and debug your deep learning code since it will likely use GPU acceleration and NVIDIA's
APEX library. But, macOS stays one of the best desktop environment for programming and working, making it an excellent
developer platform along with Linux.

If you want to work on macOS, your code should be only on your Mac and synchronized automatically with your desired 
deployment server or your personal Lab workstation. With PyCharm, this is very easy to achieve. This way, you will
never be out of sync and your code will never be overridden by obsolete versions of your code. Follow the [JetBrains
initial configuration steps](jetbrains.md) to get started.

This method is also a good way to get a couple of hundreds of Megabytes of more of VRAM on your personal workstation. By
using your personal laptop as desktop environment, you can disable the GNOME desktop environment which free up video 
resources on the GPU. Sometimes, it's all what it takes to fit your model into the limited 8 GB of VRAM we have on the
lab's GPUs.

Unfortunately, as a drawback, you'll likely have to get a dock for connecting two monitors and peripherals on your 
computer. Also, ensure your computer can run multiple external displays. For instance, a MacBook Air cannot have more 
than one external monitor, while MacBook Pro can have a maximum of two external monitors, making a three-display 
setup possible. 


## Virtualenv


## Git

