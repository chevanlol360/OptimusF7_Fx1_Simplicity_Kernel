How to Build
====================
**This short guide assumes you're on Ubuntu 11.04 or above** and have your Android build enviroment setup already.

Getting SimplicityXL Kernel source & tools

First, we need to create directories for the build so open Terminal and issue the follow commands:
    $ cd 
    $ mkdir -p ~/Android
    $ cd Android
    $ mkdir Kernel
    $ cd Kernel
    $ mkdir Device
    $ cd Device
    $ mkdir LG870
    $ cd LG870
    $ mkdir SmpXlKernel
    $ cd SmpXlKernel

    $   git clone https://github.com/chevanlol360/Simplicity_kernel_Fx1_LG870

Now that you have the kernel source, you need to get toolchains:
    $ cd /Android
    $ mkdir toolchains
    $ git clone https://github.com/DooMLoRD/android_prebuilt_toolchains

**Building
Issue the following commands to build the kernel
    $ cd
    $ cd Android/Kernel/Device/LG870/SmpXlKernel
    $ export ARCH=arm
    $ export CROSS_COMPILE=~/android/kernel/toolchains/arm-eabi-linaro-4.6.2/bin/arm-eabi-
    $ make clean 
    $ make 1chaos_defconfig
    $ make menuconfig

When the Menu pops up scroll down to "Kernel Hacking" and press enter
Scroll down to the 5th option called "Warn from stack frames larger than" press enter
Change the # from 1024 to 1032 and press enter
use your arrow keys and exit it out of the config menu when ask to save changes select yes and press enter

Continue Issuing commands
    $ make -j4
When its done you'll find you zlmage under /arch/arm/boot

Head over to "Link here" to find out how to loki it and flash it.


