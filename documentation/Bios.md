BIOS
==

> The MinnowBoard MAX uses a UEFI system level firmware, and provides both the UEFI shell, and a typical BIOS style menu interface. [Elinux Minnowboard MAX BIOS](http://elinux.org/Minnowboard:MaxBios)

## UEFI

> UEFI devleopment on MinnowBoard covers firmware, pre-OS applications, drivers, and OS loaders.
> MinnowBoard allows development of low-level features on Intel® architecture in an open source
> environment.

[Intel® Architecture Firmware Resource Center - Minnowboard MAX](https://firmware.intel.com/projects/minnowboard-max)

## BIOS Configuration Example

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

