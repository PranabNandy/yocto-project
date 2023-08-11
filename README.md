# yocto-project

 ## $ Ubuntu 20.04.6 LTS and pocky dunfell branch
     $ sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \
     build-essential chrpath socat cpio python python3 python3-pip python3-pexpect \
     xz-utils debianutils iputils-ping libsdl1.2-dev xterm


     $ git clone git://git.yoctoproject.org/poky

     $ git checkout dunfell

     $ ssource poky/oe-init-build-env [ build_directory ]

     $ bitbake core-image-minimal
     
     $ runqemu qemux86_64 nographic

