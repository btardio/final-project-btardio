### Project Goals

After successfully creating images for Raspberry PI 5 and OpenWRT, configure K3s and an ingress. Additionally succeed at creating an image processing application in python using an algorithm that puts the system under load. 

### Motivation

Have yet to solve setting up an ingress for K3s. This project will also give me the opportunity to work on a ramdisk, I noticed the docker did not let me create new files and was limited to 65535mb. Additional learning objectives will be to load an image onto NAND, using UART to bring up a console, using a boot sector tool other than grub/lilo.



### Link to wiki:

https://github.com/btardio/final-project-btardio/wiki

### Link to project:

https://github.com/btardio/final-project-btardio/projects?query=is%3Aopen

### Link to repository:

https://github.com/btardio/final-project-btardio


### Short Synopsis

This project will contain a RPI 5 buildroot that creates the ramdisk image. The image will run SystemInitV init and init.rc will connect to ethernet network, download an opkg ipk file and install the necessary .so's for docker and kubernetes. It will start kubernetes using overlay config file specifying containerd runc option NoPivotRoot. Alternatively it will run docker images using DOCKER_RAMDISK=true. It will be bootable using a dnsmasq tftp server on another embedded device, openwrt. The openwrt, if successful, will be a buildroot that contains a network ingress for kubes. The goal is to send a request to the openwrt containing an image, and the response will be the image modified using image processing.
