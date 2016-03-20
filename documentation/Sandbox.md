# SandBox

# Operating System Installation

> The general process of setting up Linux for the MinnowBoard MAX is quite similar to setting up Linux on any other computer:
>
1. You make a bootable installer USB flash drive for your distro of choice
2. Plug in the storage volume you want to install to (i.e. a larger SATA or USB HDD, MicroSD card, etc.,)
3. Install to that drive
>
> However, there are a few things to keep in mind...

To continue reading please go to Minnowboard Max Wiki: http://elinux.org/Minnowboard:MinnowMaxDistros
 
We do not want to rewrite things :)

# BIOS

http://elinux.org/Minnowboard:MaxBios

# Hardware
<center><img src="https://ms-iot.github.io/content/images/PinMappings/MBM_Pinout.png"></center>

# Kernel Compilation

__All these steps in your Minnowboard MAX__

Check your current Kernel version

    user@Minnowboard:~$ uname -a
    Linux Minnowboard A.BB.CC ...

Update and upgrade system packages and install Kernel Development packages

    root@Minnowboard:~# apt-get update
    root@Minnowboard:~# apt-get upgrade
    root@Minnowboard:~# apt-get install linux-headers-$(uname -r) kernel-package libncurses5 libncurses5-dev git

Clone, compile and install Mainline Linux Kernel

    user@Minnowboard:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
    user@Minnowboard:~$ cd linux
    user@Minnowboard:~$ make olddefconfig
    user@Minnowboard:~$ make
    root@Minnowboard:~# make modules_install
    root@Minnowboard:~# make install

Ready! Reboot the board and check again Kernel Version

    user@Minnowboard:~$ uname -a
    Linux Minnowboard X.YY.ZZ ...

## Kernel Menuconfig

    user@Minnowboard:~$ cd linux
    user@Minnowboard:~$ make menuconfig


Universal Asynchronous Receiver-Transmitter
==

## Issues

- [MinnowBoard UART ports configuration issues](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150601/001597.html)
 - [MinnowBoard UART ports configuration issues **Answer**](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150601/001607.html)
 - [MinnowBoard UART ports configuration issues **Sequence**](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150720/001774.html)
- [MinnowBoard Problem with UART](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150615/001657.html)
- [MinnowBoard Using UART2 as terminal output](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20140421/000088.html)
- [MinnowBoard UART and COM ports problem](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150622/001676.html)
 - [MinnowBoard UART and COM ports problem __Sequence__](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150629/001693.html)
- [MinnowBoard Problem with UART](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150622/001662.html)
- [MinnowBoard Using HS UARTs in UEFI](http://lists.elinux.org/pipermail/elinux-minnowboard/Week-of-Mon-20150817/001826.html)