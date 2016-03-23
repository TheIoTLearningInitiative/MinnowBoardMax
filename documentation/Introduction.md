# Introduction

## Resources

- [Minnowboard-MAX Website](http://www.minnowboard.org/meet-minnowboard-max/)
- [Minnowboard-MAX Public Wiki New](http://wiki.minnowboard.org/MinnowBoard_Wiki_Home)
- [Minnowboard-MAX Public Wiki Old](http://elinux.org/Minnowboard:MinnowMax)
- [Public Bug List:](https://wiki.yoctoproject.org/wiki/Minnow_Bug_Triage)
- [The extras](https://github.com/MinnowBoard/minnow-max-extras)
- [Firmware Sources](http://firmware.intel.com/projects/minnowboard-max)
- [Google+ Page MinnowBoard](https://plus.google.com/+MinnowboardOrg/posts)
- [Mailing List](http://lists.elinux.org/mailman/listinfo/elinux-minnowboard)
- IRC channel
  - #minnowboard@irc.freenode.net.  
- [Mouser, MinnowBoard Lures](http://www.mouser.com/new/MinnowBoard/minnowboard-max-lures/)
- [Tin Can Tools, Silverjaw Lure](http://www.tincantools.com/MinowBoard_Max_Add-ons/Silverjaw_Lure.html)

If you want Lures not currently listed contact CircuitCo at sales@circuitco.com.
For a list of currently planned Lures see:
 http://elinux.org/Minnowboard:MaxLures
 
## UEFI

> UEFI devleopment on MinnowBoard covers firmware, pre-OS applications, drivers, and OS loaders.
> MinnowBoard allows development of low-level features on Intel® architecture in an open source
> environment.

[Intel® Architecture Firmware Resource Center - Minnowboard MAX](https://firmware.intel.com/projects/minnowboard-max)

## Debian

> Debian (/ˈdɛbiən/)[3] is a Unix-like computer operating system and a Linux
> distribution that is composed entirely of free and open-source software,
> most of which is under the GNU General Public License, and packaged by a
> group of individuals known as the Debian project. Currently, the Debian
> project offers three branches named "stable", "testing" and "unstable".

[Debian Homepage](https://www.debian.org/)

## Debian Advanced Packaging Tool

> The Advanced Package Tool, or APT, is a free software user interface that
> works with core libraries to handle the installation and removal of software
> on the Debian GNU/Linux distribution and its variants.

    root@minnowboard:~# apt-get install pip

## Programming

Tbd

## Python

> Python is a widely used general-purpose, high-level programming language

[Python Homepage](https://www.python.org/)

## Python PIP Package Management System

> pip is a package management system used to install and manage software
> packages written in Python. Many packages can be found in the Python Package
> Index (PyPI).

    root@minnowboard:~# pip install psutil plotly

## Lures

> MinnowBoard Lure Daughter cards are provided separately. They can be custom developed to expose features and interfaces as required for developer applications. They are “stackable” up to a depth of four devices.

[Minnowboard Max Lures](http://elinux.org/Minnowboard:MaxLures)

## Sensors

Tbd

## Interfaces

* GPIO General Purpose Input Output
* I2C Inter-Integrated Circuit
* AIO Analog Input & Output
* PWM Pulse Width Modulation
* SPI Serial Peripheral Interface
* UART Universal Asynchronous Receiver Transmitter

## Github

> GitHub is the best place to share code with friends, co-workers, classmates, and complete strangers. Over eight million people use GitHub to build amazing things together.

Want to learn GIT? [GIT --distributed-even-if-your-workflow-isnt](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

[](https://ms-iot.github.io/content/images/PinMappings/MBM_Pinout.png)

# End of File

Kernel update and installation

    user@Minnowboard:~$ uname -a
    Linux minnowboard 4.1.0-rc7+ #4 SMP ... x86_64 GNU/Linux
    user@Minnowboard:~$ cd linux
    user@Minnowboard:~$ git pull
    user@Minnowboard:~$ git checkout -b 4.1 v4.1
    Checking out files: 100% (13004/13004), done.
    Switched to a new branch '4.1'
    user@Minnowboard:~$ rm .config
    user@Minnowboard:~$ wget https://raw.githubusercontent.com/xe1gyq/minnowboardmax/master/.config
    user@Minnowboard:~$ make
    user@Minnowboard:~# make modules_install
    user@Minnowboard:~# make install
    user@Minnowboard:~# reboot
    user@Minnowboard:~$ uname -a

BIOS Configuration

Taken from http://elinux.org/Minnowboard:MaxBios#BIOS_menu

- Reboot your board and keep pressing F2 until you get into the BIOS menu, make sure the below configurations are set


    LPSS & SCC Devices Mode (ACPI Mod)
    PCI Mode / __ACPI Mod__

    LPSS 1 Configuration
    LPSS HSUART #1 Support
    Disable / Enable
    Note: Controls the state of Low-speed pins #6, #8, #10, #12
    LPSS HSUART #1 FlowCtrl
    Enable / Disable
    Note: This is only available when HSUART #1 is on
    LPSS HSUART #2 Support
    Disable / Enable
    Note: Controls the state of Low-speed pins #17, #19. HSUART #2 does not have hardware FlowControl due to lack of CTS/RTS lines being pulled out
    LPSS HSUART #2 FlowCtrl
    Enable / Disable
    Note: This is only available when HSUART #2 is on
    Note: Hardware Flow Control is not available, since CTS / RTS are not pulled out and available



