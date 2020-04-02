# Fixing Backlight

So what this SSDT does is create a PNLF device for macOS to play with, specifically one with a hardware ID of `APP0002`. WhateverGreen will handle the rest of the work


No configuration required for most, just drop the prebuilt file into your EFI:
* [SSDT-PNLF](https://github.com/khronokernel/Getting-Started-With-ACPI/blob/master/extra-files/SSDT-PNLF.aml)
   * For most users
* [SSDT-PNLF-CFL](https://i.applelife.ru/2019/12/463488_SSDT-PNLFCFL.aml.zip)
   * For Coffeelake users if the regular SSDT doesn't work, try SSDT-PNLF first and do not mix together

Note: there are some rare cases where the iGPU is called `GPU0` or `VID`in the DSDT, you can double check by searching for `PCI0.GFX0`, `PCI0.VID` and `PCI0.GPU0`. Whichever shows up is your device

If Windows has been installed on the device, you can also do the following:

```text
Device Manager -> Display Adapters -> Properties -> Details > BIOS device name
```