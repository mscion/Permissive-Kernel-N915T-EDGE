# Permissive-Kernel-N915T-EDGE:  
Kernel and background information provided such that you can set kernel to permissive for Note Edge N915T

I compiled this kernel so that it had the option to be set to permissive by following an extremely useful tutorial (Many thanks to the author!)

http://graemehill.ca/compiling-permissive-android-kernel/

The tutorial generally explains how to compile a kernel with the option of being permissive by only modifing the Makefile as described below. 

Additional details

The kernel is obtained from samsung
http://opensource.samsung.com/reception/receptionSub.do?method=sub&sub=F&searchValue=SM-N915T


To make this kernel I utilized the following toolchain
https://github.com/SaberMod/arm-eabi-4.7-32bit

The boot image was unpacked and packed using
https://github.com/xiaolu/mkbootimg_tools

The actual code of the kernel was not changed. Only an option in the Makefile for the kernel was modified.

The make file is in

security/selinux/Makefile

Change

EXTRA_CFLAGS += -DCONFIG_ALWAYS_ENFORCE=true

to 

EXTRA_CFLAGS += -DCONFIG_ALWAYS_ENFORCE=false

When you compile the kernel a zImage is created that you pack back into the kernel using the mkboot program. The graemehill tutorial illustrates the major points.


