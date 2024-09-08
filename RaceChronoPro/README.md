## Summary

[RaceChrono Pro](https://racechrono.com/) is a smartphone app for logging vehicle data on track.  To collect vehicle data, an OBD-II adapter is needed; consult "Which OBD-II adapter should I buy?" in the [FAQ](https://racechrono.com/support#).

If your smartphone has a built-in GPS receiver, it may suffice for your needs, but an external GPS receiver is desirable; consult the "Which external GPS should I buy?" in the [FAQ](https://racechrono.com/support#).

## RaceChrono Pro configuration file

The channels chosen are not intended to be comprehensive, as more channels can often slow down the update rate.

To import the .rcz file, click the upper right corner of the main screen and select "Import".  Use the File browser to pick the file, and then press the Start button.  In the resultant Vehicle profile screen, click the Save button (after making any desired changes).

## RaceChrono Pro manual values

For users who want to enter values manually (or adapt this data to other software):

|channel name                 |"OBD-II header" aka CANbus ID|PID     |equation                   |
|-----------------------------|-----------------------------|--------|---------------------------|
|Accelerator position (%)     |0x7E2                        |0x22E004|bytestoUint(raw,10,1)/2.0  |
|Battery level BMS (%)        |default                      |0x220101|bytestoUint(raw,5,1)/2.0   |
|Battery current (amps)       |default                      |0x220101|bytestoInt(raw,11,2)/10.0  |
|Batt Voltage (volts)         |default                      |0x220101|bytestoUint(raw,13,2)/10.0 |
|Battery temperature max      |default                      |0x220101|bytestoInt(raw,15,1)       |
|Battery temperature min      |default                      |0x220101|bytestoInt(raw,16,1)       |
|Rear Motor RPM               |default                      |0x220101|bytestoInt(raw,54,2)       |
|Front Motor RPM              |default                      |0x220101|bytestoInt(raw,56,2)       |
|Battery level (%)            |default                      |0x220105|bytestoUint(raw,32,1)/2.0  |
|Steering angle (deg)         |0x730                        |0x22F010|bytestoIntLe(raw,13,2)/10.0|

I found [this source](https://github.com/Esprit1st/Hyundai-Ioniq-5-Torque-Pro-PIDs) of IONIQ 5 data to be tremendously useful.

