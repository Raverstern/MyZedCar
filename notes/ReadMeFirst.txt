-----------------------------About this file------------------------------

This file is a general guideline for the whole procedure.



-----------------------------Files in this folder-------------------------

The files "wifi.dts" and "zed_wifi2_defconfig" are delivered from Black-shirt TA.
The former one has been used by us, but the later one hasn't, which be as a reference.




-----------------------------Required Resourses----------------------------

1. Linux kernel delivered from XUP;
2. Xilinx u-boot;
3. Device tree given by Black-shirt TA;
4. fsbl and bitstream files which can be found in the zrobot_v1 folder;
5. Some helping documents in this folder.



-----------------------------Preparing for Boot partition-------------------------

1. pull the u-boot repository. Before compiling it, modify some files according to "./u_boot_config.txt" first;
2. compile the u-boot, check "http://www.wiki.xilinx.com/Build+U-Boot" for details;
3. pull the linux repository. Again, you should change something following "./kernel_config.txt" before compiling;
4. check whether the "mkimage" utility is available on your computer. If it's not, download and install it, by which
	the uImage can be generated;
5. compile the kernel, check "http://www.wiki.xilinx.com/Build+kernel" for details;
6. get "fsbl.elf" and "bitstream.bit", which can be found in "zrobot_v1/source" folder;
7. generate "BOOT.BIN", using "u-boot.elf" together with "fsbl" and "bitstream", by Xilinx SDK;
8. generate "devicetree.dtb", using the "wlan.dts" in this folder;
9. copy "BOOT.BIN", "uIamge" and "devicetree.dtb" to FAT partition of SD card.

Reference:
	wiki.xilinx.com
	嵌入式系统软硬件协同设计实战指南，基于Xilinx Zynq，2013年1月第一版



-----------------------------Building up File System------------------------------

	you can build up your own file system by qemu, following "make_fs_qemu.txt", or use the existing fs, which has 
been well configured, but is too large to upload to github.



-----------------------------Using and Running the car----------------------------

	If you are using the existing fs delivered from the course of Smart Hardware, you may normally use the wifi by
modifying some files following "wlan.txt".
	If the fs you're using is a new one, you need to install some softwares and build up a boa server by yourself.

Reference:
	嵌入式系统软硬件协同设计实战指南，基于Xilinx Zynq，2013年1月第一版

