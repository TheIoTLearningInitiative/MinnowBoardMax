Serial Peripheral Interface
==

- [Bill Traynor Flashing MinnowBoard MAX With the SPI Hook in Linux](http://billtraynor.com/post/2015/11/12/flashing-minnowboard-max-with-the-spi-hook-in-linux/)

```sh
    CC [M]  drivers/iio/adc/mcp320x.o
    CC [M]  drivers/spi/spidev.o
    CC [M]  drivers/spi/spi-dw.o
    CC [M]  drivers/spi/spi-gpio.o
    CC [M]  drivers/spi/spi-pxa2xx.o
    CC [M]  drivers/spi/spi-pxa2xx-dma.o
    LD [M]  drivers/spi/spi-pxa2xx-platform.o
    CC [M]  drivers/spi/spi-pxa2xx-pci.o
    Kernel: arch/x86/boot/bzImage is ready  (#4)
    Building modules, stage 2.
    MODPOST 3034 modules
    CC      drivers/iio/adc/mcp320x.mod.o
    LD [M]  drivers/iio/adc/mcp320x.ko
    CC      drivers/spi/spi-dw.mod.o
    LD [M]  drivers/spi/spi-dw.ko
    CC      drivers/spi/spi-gpio.mod.o
    LD [M]  drivers/spi/spi-gpio.ko
    CC      drivers/spi/spi-pxa2xx-pci.mod.o
    LD [M]  drivers/spi/spi-pxa2xx-pci.ko
    CC      drivers/spi/spi-pxa2xx-platform.mod.o
    LD [M]  drivers/spi/spi-pxa2xx-platform.ko
    CC      drivers/spi/spidev.mod.o
    LD [M]  drivers/spi/spidev.ko
```
