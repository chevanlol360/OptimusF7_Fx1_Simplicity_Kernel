1. Android buid
  - Download original android source code ( Jelly Bean 4.1 ) from http://source.android.com
  - Unzip opensource packages of LGLG870_JB_android.zip into downloaded android source directory 
  - And, merge the source into the android source code(Jelly Bean)
  - Run following scripts to build android
    a) . build/envsetup.sh
    b) lunch	
    c) make -j4                                                      
  - When you compile the android source code, you have to add google original prebuilt source(toolchain) 
    into the android folder 
    ( add prebuilt/linux-x86/toolchain/arm-eabi-4.4.3/bin to PATH )
  - After build, you can find output at out/target/product/generic  
  
2. Kernel Build
  - Unzip using following command at the android folder
  - When you compile the kernel source code, you have to add google original prebuilt source(toolchain) 
    into the android folder.
  - cd kernel
  - export ARCH=arm
  - export TARGET_PRODUCT=fx1s_spr_us
  - export CROSS_COMPILE=../prebuilt/linux-x86/toolchain/arm-eabi-4.4.3/bin/arm-eabi-
  - make fx1s-perf_defconfig
  - make zImage

3. After Build, You Can find the build image at arch/arm/boot
