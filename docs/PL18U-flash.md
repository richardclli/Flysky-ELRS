# Flashing PL18U Internal Module
The stock firmware of the PL18U internal module has a bug that will prevent the flasher to work properly.
I have included a workaround procedure that can resolve this problem without any side effects.

The procedures for flashing to ELRS or back to AFHDS3 are more or less the same,
the only differences is whether the file ELRS.bin present in the same folder of the flashing tools or not.
If the file is presents, then it will read in the file and flash to ELRS, if the file is missing it will flash back to AFHDS3.
User can build the firmware with preferred options and rename it to ELRS.bin and put in the same folder of the flashing tools for updateing to a new version.

Note: Please note that when you flash to ELRS, all the models information in the internal module will be discarded. You may need to rebind all the receivers after flash back.  Flysky Assistant did not provide a way to backup all the model settings at this moment.

## Fixing the buggy firmware of the PL18U internal module
**Please skip this step if you has updated the Flysky stock firmware to version 2.2.18 and used this firmware to update the TX firmware to 1.7, only old TX firmware 1.6 that comes with Flysky stock firmware 2.1.11 is buggy.**
1. Switch on the PL18U in bootloader mode.
2. Select "RF USB Access", press the TX DFU button (the right top button hidden under the rubber grip), and click the "Enable".
3. Now the TX module is in the DFU mode, we need to keep the bootloader and flash the firmware with something else.
4. Use the STM32CubeProgrammer to connect to the MCU of the TX module, it is a STM32F072 MCU.
5. Open the ELRS.bin and change the start address to "0x08006000" and flash it, this will overwrite the firmware and keep the bootloader intact.
   
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/pl18u-fix.png)
6. Now the PL18U internal module is in a proper state that you can use the following procedures to flash it to ELRS or AFHDS3.

## Flashing to ELRS (Same as EL18 procedure)
1. Ensure the file ELRS.bin is present in the same folder of the flashing tools.
2. Switch on EL18 in bootlloader mode.
3. Select "RF USB Access" and click on it.
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/EL18-flash1.jpg)
4. Click on the "Enable" until it changed to "Disable"
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/EL18-flash2.jpg)
5. Plugin USB cable
6. Run the flashing tools, please note that the ELRS.bin is read successfully
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/EL18-flash3.png)
7. Click update and wait for the update to finish.

## Flashing back to AFHDS3 (Same as EL18 procedure)
1. Ensure the file ELRS.bin is not present in the same folder of the flashing tools, you may rename it to another name for disabling.
2. Switch on EL18 in bootlloader mode.
3. Select "RF USB Access" and click on it.
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/EL18-flash1.jpg)
4. Click on the "Enable" until it changed to "Disable"
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/EL18-flash2.jpg)
5. Plugin USB cable
6. Run the flashing tools, please note that the ELRS.bin did not appear in the UI
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/EL18-flash4.png)
7. Click update and wait for the update to finish.

