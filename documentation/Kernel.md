Kernel
==

## Native Compilation

Check your current Kernel version

```sh
    user@Minnowboard:~$ uname -a
    Linux Minnowboard A.BB.CC ...
```

Update and upgrade system packages and install Kernel Development packages

```sh
    root@Minnowboard:~# apt-get update
    root@Minnowboard:~# apt-get upgrade
    root@Minnowboard:~# apt-get install linux-headers-$(uname -r) kernel-package libncurses5 libncurses5-dev git
```

Clone, compile and install Mainline Linux Kernel

```sh
    user@Minnowboard:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
    user@Minnowboard:~$ cd linux
    user@Minnowboard:~$ make olddefconfig
    user@Minnowboard:~$ make
    root@Minnowboard:~# make modules_install
    root@Minnowboard:~# make install
```

Ready! Reboot the board and check again Kernel Version

```sh
    user@Minnowboard:~$ uname -a
    Linux Minnowboard X.YY.ZZ ...
```

# Update and Installation

```sh
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
```