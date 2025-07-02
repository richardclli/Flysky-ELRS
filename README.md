# Flysky Hardware Support for ExpressLRS
Flysky made very good TX hardware, stable and power efficient.  And the RF chip used is SX1280, which is the same as what 2.4GHx ELRS used.  I have many friends who are interested in seeking a way to flash their Flysky TX hardware with ELRS firmware.  However, the ELRS team will not accept any new STM32 targets to their repository.  And this is the reason why this repository is here to serve as an entry point for those who are interested to flash Flysky TX hardware with ELRS.

The Flysky hardware support will be supported as a fork from the original ExpressLRS repository (Thanks to the opensource GPL-3 license), you may found the latest update based on their master branch in the following link:

https://github.com/richardclli/ExpressLRS/tree/Flysky

And for major release versions of ELRS, a branch based on that release will be created, the branches for stable releases listed as follows:

* [ExpressLRS v3.4.3](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.4.3)
* [ExpressLRS v3.5.0](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.0)
* [ExpressLRS v3.5.1](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.1)
* [ExpressLRS v3.5.2](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.2)
* [ExpressLRS v3.5.3](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.3)
* [ExpressLRS v3.5.4](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.4) Start to have PL18U support
* [ExpressLRS v3.5.5](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.5)
* [ExpressLRS v3.5.6](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.5.6)

# Features
* STM32F072 MCU support, this MCU is used in Flysky EL18 internal module and FRM303
* Optimized bi-directional DMA serial driver, can support up to 5.25M baud flawlessly with a 48MHz MCU
* Compatible with Flysky bootloader, user can choose to flash the hardware to ELRS or back to AFHDS3 without limitations
* Unsupported features: All Wifi and Bluetooth related features

# Supported Flysky Hardware

The following Flysky hardware are supported:
* Flysky EL18 internal module
* Flysky FRM303
* Flysky PL18 internal module (added support since v3.5.4)

# Building Firmware

You need to install an environment for building the firmware, just install VSCode and PlatformIO will works.  The following is a simple procedure for firmware building:

1. Clone a branch of a version that you want to build
2. Open the src directory using VSCode
3. Choose proper environment
   * For building EL18 TX firmware, choose env:Flysky_EL18_TX_for_FlyskyBL
   * For building FRM303 TX firmware, choose env:Flysky_FRM303_TX_for_FlyskyBL
   * For building PL18U TX firmware, choose env:Flysky_PL18U_TX_for_FlyskyBL

4. Edit the user_defines.txt file to specify your build options
5. Build the firmware

If you use PlatformIO cli to build the firmware, you can execute the following command in the "src" folder
  > pio run --environment \<Name of the environment\>

For example if you build the firmware for EL18, the command is like this
  > pio run --environment Flysky_EL18_TX_for_FlyskyBL

Note: If pio is not in the executable paths, you may need to replace the command "pio" with a full path instead.

  

You can find the file firmware.bin in the platformio build folder src/.pio/build/Flysky_XXXXXX_TX_for_FlyskyBL, just copy it to the same folder of flashing tools and rename it to ELRS.bin and flash.


# Flashing AFHDS3/ELRS Procedures

User can choose to flash the supported Flysky hardware to ELRS or back to AFHDS3, the flashing tools are located here:

https://github.com/richardclli/Flysky-ELRS/tree/main/flasher

And for flashing instructions, please refer the following links for details:

* [Flysky EL18 internal module](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/EL18-flash.md)
* [Flysky FRM303](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/FRM303-flash.md)
* Flysky PL18U internal module: Just use similar procedure as EL18 internal module with PL18U specific flashing tools.

