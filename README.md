# The basics

## 1. Download and Installing the OS

References:

- https://www.raspberrypi.org/downloads/


### 1.1 Installing on the Raspberry Pi

Steps:

1. Begin by installing the *Raspberry Pi Imager*

2. 

## 2 Installing on a Virtual Machine

### 1.1 Getting the image

The OS can be installed on a virtual machine (or even a computer) instead, the .iso file can be found [here](https://www.raspberrypi.org/downloads/raspberry-pi-desktop/).


### 1.2 Installing the VMWare Virtual Machine

#### 1.2.1 Installing the VMWare on Linux

First, you have to give admin permissions to the file:

```shell
chmod +x ~/Downloads/VMware-Player*
``` 

It can then be installed with

```shell
sudo ~/Downloads/VMware-Player*
```

### 1.2.2 Creating a Virtual Machine on VMWare

Begin by picking the .iso image

![](VM1.png)

Pick a *Debian 10.x* image (picking other images may give you a Kernel Panic):

![](VM2.png)

Regarding the storage space, 16GB or 32GB should be more than enough. Just pick the typical size for a SD card. Now, click on *customize hardware*. Here you can modify the RAM, number of cores and so on. Pick 512mb or 2gb:

![](VM3.png)

You should see the following menu. If you chose 1gb or more of ram choose graphic install:

![](VM4.png)

You should see the following screen:

![](VM5.png)

From here on just proceed smoothly. If everything goes well you should see the following screen:

![](VM6.png)

If you picked 512 of ram you should pick the *Install* option because you will be in the low memory mode:, the process will be entirely text-based. If you encounter the following error:

![](VM7.png)

Advance to the next option:

![](VM8.png)

And just install the base system:

![](VM9.png)

You will end up in the following screen:

![](VM10.png)

If the system ever ask for it, try to use the following credentials:

* login: pi
* password: raspberry
