### Introduction

This readme file describes how to build kernel source. there a lot of useful information is already described in Atmel Linux For SAM website. 
The relevant source codes are maintained on GitHub. it is highly recommended the user to visit those sites.  

   * Atmel Linux For SAM Site : [http://www.at91.com/linux4sam](http://www.at91.com/linux4sam)
   * GitHub Linux For SAM Site : [http://github.com/linux4sam](http://github.com/linux4sam)
   

***

### How To Build Kernel    
There are several versions of Linux kernel in Linux For SAM site. And some versions are made for prebuilt  
image. This document will utilize following prebuilt image as a reference.  

ftp://www.at91.com/pub/demo/

>This document does not describe general information on the AT91Bootstrap and  
>U-Boot because it can be used without modification from prebuilt image.  

User better to check out the same branch source, to compare with the prebuilt image.  


##### Getting Kernel Source  
Get kernel source by the following command.
~~~~
$ git clone git://github.com/linux4sam/linux-at91.git  
$ cd linux-at91  
$ git checkout origin/linux-3.10-at91 -b linux-3.10-at91  
~~~~
>For a reference, the branch of “linux-3.10-at91” was used and verified for WILC1000 hardware.  

##### Kernel Build  
The followings show how to build the kernel.  
```
$ make ARCH=arm  CROSS_COMPILE=arm-linux-gnueabi-  

$ make ARCH=arm  CROSS_COMPILE=arm-linux-gnueabi- zImage  

$ make -j9 ARCH=arm  CROSS_COMPILE=arm-linux-gnueabi- dtbs  
```
  
Then, the outputs are generated like the below.  
   * linux-at91/arch/arm/boot/zImage  
   * linux-at91/arch/arm/boot/dts/at91-sama5d3_xplained.dtb  
   * linux-at91/drivers/net/wireless/atmel/wilc1000/wilc1000.ko  

  
