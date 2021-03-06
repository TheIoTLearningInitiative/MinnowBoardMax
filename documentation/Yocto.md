Yocto
==

> It's not an embedded Linux distribution – it creates a custom one for you. The Yocto Project is an open source collaboration project that provides templates, tools and methods to help you create custom Linux-based systems for embedded products regardless of the hardware architecture. It was founded in 2010 as a collaboration among many hardware manufacturers, open-source operating systems vendors, and electronics companies to bring some order to the chaos of embedded Linux development.

> The Yocto Project is a Linux Foundation workgroup whose goal is to produce tools and processes that will enable the creation of Linux distributions for embedded software that are independent of the underlying architecture of the embedded software itself.

- [Yocto Project Homepage](https://www.yoctoproject.org/)
- [Yocto Project Quick Start Guide](http://www.yoctoproject.org/docs/2.0/yocto-project-qs/yocto-project-qs.html)
- [Yocto Developer Manual](http://www.yoctoproject.org/docs/1.6.1/dev-manual/dev-manual.html)
- [Yocto Kernel Developer Manual](http://www.yoctoproject.org/docs/1.6.1/kernel-dev/kernel-dev.html)
- [Yocto Project and Embedded OS Webinar](http://www.intel.com/content/www/us/en/education/university/galileo-university-curricula/yocto-project-and-embedded-os-webinar-replay.html#)
- [Yocto Manage a Private Opkg Repository](http://www.jumpnowtek.com/yocto/Managing-a-private-opkg-repository.html)
- [Code Project Adding 3rd Party Components to Yocto/OpenEmbedded Linux](http://www.codeproject.com/Articles/774826/Adding-rd-party-components-to-Yocto-OpenEmbedded-L)
- [Yocto Git Server](http://git.yoctoproject.org/)

## Building Yocto Minnnowboard MAX

> The MinnowBoard MAX is supported by the Yocto Project and the meta-intel intel-corei7-64 and intel-core2-32 Board Support Packages (BSP) [Minnowboard MAX Wiki Yocto Project](http://wiki.minnowboard.org/Yocto_Project)

- [Minnowboard Wiki Yocto Project](http://wiki.minnowboard.org/Yocto_Project)
- [Minnowboard Wiki Maker Yocto](http://wiki.minnowboard.org/Projects/Maker_Yocto)

```sh
    user@host:~$ mkdir source
    user@host:~$ cd source
    user@host:~$ git clone -b fido git://git.yoctoproject.org/poky
    user@host:~$ cd poky
    user@host:~$ git clone -b fido git://git.yoctoproject.org/meta-intel
    user@host:~$ source oe-init-build-env yocto-x86-minnowmax
    user@host:~$ bitbake-layers add-layer "$HOME/source/poky/meta-intel"
    user@host:~$ echo 'MACHINE = "intel-corei7-64"' >> conf/local.conf
    user@host:~$ bitbake core-image-minimal
    user@host:~$ ls tmp/deploy/images/intel-corei7-64/
    ...
    core-image-minimal-intel-corei7-64.hddimg
    $ sudo $HOME/source/poky/scripts/contrib/mkefidisk.sh HOST_DEVICE \
    tmp/deploy/images/intel-corei7-64/core-image-minimal-intel-corei7-64.hddimg \
    TARGET_DEVICE
```

