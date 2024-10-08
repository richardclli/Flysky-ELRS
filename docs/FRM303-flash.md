# Flashing FRM303
The procedures for flashing to ELRS or back to AFHDS3 are more or less the same,
the only differences is whether the file ELRS.bin present in the same folder of the flashing tools or not.
If the file is presents, then it will read in the file and flash to ELRS, if the file is missing it will flash back to AFHDS3.
User can build the firmware with preferred options and rename it to ELRS.bin and put in the same folder of the flashing tools for updateing to a new version.

## Flashing to ELRS
1. Backup the models using Flysky assistant.
2. Ensure the file ELRS.bin is present in the same folder of the flashing tools.
3. Plugin USB cable
4. Run the flashing tools, please note that the ELRS.bin is read successfully
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/FRM303-flash1.png)
5. Click update and wait for the update to finish.   

## Flashing back to AFHDS3
1. Ensure the file ELRS.bin is not present in the same folder of the flashing tools, you may rename it to another name for disabling.
2. Plugin USB cable
3. Run the flashing tools, please note that the ELRS.bin did not appear in the UI
   ![image](https://github.com/richardclli/Flysky-ELRS/blob/main/docs/images/FRM303-flash2.png)
4. Click update and wait for the update to finish.
5. Restore the models using Flysky assistant.
