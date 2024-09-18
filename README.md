# Flysky Hardware Support for ExpressLRS
Flysky made very good TX hardware, stable and power efficient.  And the RF chip used is SX1280, which is the same as what 2.4GHx ELRS used.  I have many friends who are interested in seeking a way to flash their Flysky TX hardware with ELRS firmware.  However, the ELRS team will not accept any new STM32 targets to their repository.  And this is the reason why this repository is here to serve as an entry point for those who are interested to flash Flysky TX with ELRS.

The Flysky hardware support will be supported as a fork from the original ExpressLRS repository (Thanks to the opensource GPL-3 license), you may found the latest update based on their master branch in the following link:

https://github.com/richardclli/ExpressLRS/tree/Flysky

And for major release versions of ELRS, a branch based on that release will be created, the branchs for stable releases listed as follows:

* [ExpressLRS v3.4.3](https://github.com/richardclli/ExpressLRS/tree/Flysky-v3.4.3)

# Supported Flysky Hardware

The following Flysky hardware are supported:
* Flysky EL18 internal module
* Flysky FRM303

# Building Firmware

# Flashing AFHDS3/ELRS Procedures

User can choose to flash the supported Flysky hardware to ELRS or back to AFHDS3, please refer the following links for details:

* [Flysky EL18 internal module](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/EL18-flash.md)
* [Flysky FRM303](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/FRM303-flash.md)

