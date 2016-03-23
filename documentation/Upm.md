# UPM

> Sensor/Actuator repository for libmraa

> High-level repository for sensors and actuators that use libmraa. In other words, UPM gives you easy function calls to use your sensors, such as reading temperature values or writing data to an LCD screen. With over a hundred sensors and more being added, this library speeds up your development time. 

- [UPM Documentation](http://iotdk.intel.com/docs/master/upm/index.html)
- [UPM Sensor Categories](http://iotdk.intel.com/docs/master/upm/modules.html)
- [UPM Github](https://github.com/intel-iot-devkit/upm)
- [UPM Python Exampes](https://github.com/intel-iot-devkit/upm/tree/master/examples/python)

UPD Updates

- Protocols such as ModBus and BACNet
- Radio/wireless modules
- XBee socket devices
- ZigBee, WiFi, WiFly
- LoRa—the SX1276 chip
- ZWave—USB Controllers
- ISM (Industrial, Scientific & Medical) Frequency Shift Keying (FSK) at 434 and 915 MHz

## Manual Installation

Sensor/Actuator repository for libmraa

    root@Minnowboard:~# apt-get update
    root@Minnowboard:~# apt-get install cmake pkg-config swig
    user@Minnowboard:~$ git clone https://github.com/intel-iot-devkit/upm.git
    user@Minnowboard:~$ cd upm
    user@Minnowboard:~$ mkdir build
    user@Minnowboard:~$ cd build
    user@Minnowboard:~$ cmake .. -DBUILDSWIGNODE=OFF
    user@Minnowboard:~$ make
    root@Minnowboard:~# make install
