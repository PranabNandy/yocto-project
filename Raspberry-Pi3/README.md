Booting Process in Raspberry Pi3
---------------------------------

Broadcom BCM2837:

	CPU 	-	1.2GHz 64-bit quad-core ARMv8 Cortex-A53
 
	GPU 	-	Broadcom VideoCore IV
 
	SDRAM	-	1024 MiB

When you power the device
Stage 1 Booting - OnChip ROM
----------------------------
	GPU - On, CPU - Off, SDRAM - Off

	When the Pi is powered up the first thing that starts working is the GPU core and ARM CPU is 		held in reset

	The GPU core is the main part responsible for the first booting steps of the Pi. 

	Inside Broadcom’s SoC, there is a small boot ROM, its programmed by default to look for a file 	called bootcode.bin on the SD Card

	It loads bootcode.bin into L2 Cache memory
			

Stage 2 Booting - bootcode.bin
------------------------------

	GPU - On, CPU - Off, SDRAM - On

	Executed on VideoCore GPU
	Enables SDRAM
	Loads the third stage bootloader start.elf into SDRAM

Stage 3 Booting - start.elf
----------------------------

	GPU - On, CPU - On, SDRAM - On

	start.elf is actually a full fledge proprietary operating system for GPU known as VCOS      		(VideoCore OS).
	It starts by reading config.txt  which contains configuration parameters for
	VideoCore (Video/HDMI modes, memory, console frame buffers etc) and
	Linux Kernel (load addresses, device tree, uart/console baud rates etc)
	kernel = kernel7.img
	It also loads a file cmdline.txt if it exists, and will pass its contents as kernel command line
	Finally enables the ARM CPU and loads the kernel image which is executed on the ARM CPU
	It also loads the dtb file
		
	
Booting in Raspberry Pi3
---------------------------

	GPU Core
	first stage bootloader, which is stored in ROM on the SoC
	bootcode.bin
	start.elf
	config.txt
	cmdline.txt
	kernel7.img
	
IMAGE_ROOTFS_EXTRA_SPACE
------------------------

Adds extra free space to the root filesystem image.

The variable specifies the value in kilobytes

Default value : 0

For example, to add an additional 4 GB of space, set the variable to IMAGE_ROOTFS_EXTRA_SPACE = "4194304"
