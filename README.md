## Mach 3 Manual Tool Change Macro with Auto-Adjusting Z
This tool change macro automates setting the Z height on manual CNC routers when performing tool changes. Many scripts available online rely on automated tool changers or don't properly add offsets to the tool table, but this macro solves both issues. 

This script was developed specifically for Mach 3 and CNC routers that use collets (ER-20) that do not retain Z height. A standard T#M6 command will call the script and automatically compensate for different tool heights. This macro assumes:
* The units are in mm, although this is easy to change by adjusting your default X,Y,Z locations to Imperial units.
* Your probe pad has already been configured as a probe input and is located in the same location on your build surface.
* The probe location is located somewhere on the surface your cutting.
* The maximum variation in length of your tools is less than 20mm.
* Your machine is always homed before calling this macro.

The script's features include:
* Automated tool measurement. Offsets are entered into the tool table and can optionally be saved.
* Automatic movement to a fixed tool change location. 
* Probe offset measurement storage in flash.
* Positive and negative tool length compensation.

## Requirements
* CNC Router or CNC Mill (Tested with an OMIOCNC X8-2200L-USB)
* Mach 3
* Limit switches and hardware used for homing CNC

## How the Macro Works
Detailed steps:
* Spindle is stopped when a tool change is called (M6 command, Mach 3 default).
* User is asked whether a probe calibration should be performed.
* Probe calibration is executed if no probe calibration data exists.
* After calibration, the gantry moves to the configured tool change position.
* The new tool is moved to the tool probe position and probed.
* Offsets are added to the tool table for the selected tool.
* Spindle moves to original location with offset added.
* Job is ready to continue.

## How to Install the Macro
Copy the `M6Start.m1s` file to your Mach 3 installation folder overwriting the original file.

## How to Test the Macro
Open `Manual Tool Change Example.tap` in Mach 3 and run the program. The example will force a probe calibration, tool change, and probe.