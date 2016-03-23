# MRAA

> Also known as libmraa, a Low Level Skeleton Library for Communication on GNU/Linux platforms

> Low Level Skeleton Library for IO Communication on GNU/Linux platforms

> C/C++ library with bindings to JavaScript and Python to interface with the I/O on the Intel® Galileo board, Intel® Edison board, and other platforms. With board detection done at runtime, you can create portable code that works across multiple platforms.

* AIO Sensors requiring an ADC value to be read
* I2C Modules using the i2c bus
* SPI Modules using the SPI bus
* GPIO Modules using GPIOs directly
* PWM Modules using a PWM capable GPIO pin
* UART Modules using a serial connection (RX/TX)

- [MRAA Github](https://github.com/intel-iot-devkit/mraa)

## Manual Installation

Clone, compile and install mraa 

```sh
    root@Minnowboard:~# apt-get update
    root@Minnowboard:~# apt-get install cmake
    user@Minnowboard:~$ git clone https://github.com/intel-iot-devkit/mraa.git
    user@Minnowboard:~$ mkdir mraa/build && cd $_
    user@Minnowboard:~$ cmake ..
    user@Minnowboard:~$ make
    root@Minnowboard:~# make install
```

Configure the environment to have mraa available

```sh
    root@Minnowboard:~# ldconfig
    root@Minnowboard:~# ldconfig -p | grep mraa
    root@Minnowboard:~# export PYTHONPATH=$PYTHONPATH:$(dirname $(find /usr/local -name mraa.py))
    root@Minnowboard:~$ nano ~/.bashrc
    export PYTHONPATH=$PYTHONPATH:$(dirname $(find /usr/local -name mraa.py))
```

Let's compile and execute one example

```sh
    root@Minnowboard:~# cd mraa/examples
    root@Minnowboard:~# gcc -lmraa hellomraa.c -o hellomraa
    root@Minnowboard:~# ./hellomraa
    hello mraa
     Version: v0.7.2-2-g1c4be07
     Running on MinnowBoard MAX
```
