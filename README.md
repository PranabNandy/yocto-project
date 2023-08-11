# yocto-project

## Execution of build qemux86-64 image on QEMU [Demo Video](https://www.youtube.com/watch?v=lqIe4PWa61g&ab_channel=PranabNandy)

 ## $ Ubuntu 20.04.6 LTS and pocky dunfell branch
     $ sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \
     build-essential chrpath socat cpio python python3 python3-pip python3-pexpect \
     xz-utils debianutils iputils-ping libsdl1.2-dev xterm


     $ git clone git://git.yoctoproject.org/poky

     $ git checkout dunfell

     $ ssource poky/oe-init-build-env [ build_directory ]

     $ bitbake core-image-minimal
     
     $ runqemu qemux86_64 nographic


## To add a particular package in your root file system


    Open your local.conf file and add the recipe name below

    IMAGE_INSTALL += "recipe-name"

    E.g.  IMAGE_INSTALL_append = " usbutils" for lsusb

## Yocto Project uses Poky to build images (kernel, system, and application software) for targeted hardware



    This folder contains
    first-level bootloader MLO,
    second-level bootloader u-boot
    kernel image,
    device tree blobs,
    a root filesystem archive, and
    a modules archive.

