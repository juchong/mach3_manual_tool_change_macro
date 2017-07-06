## BE CAREFUL. THIS MACRO IS FAR FROM BEING FINISHED. USE IT ON YOUR OWN RISK!

# Mach3 Manual Tool Change Macro
In this repository a tool change macro for Mach3 is developed. The focus of this macro is for manual tool change, i.e., the following steps are executed when the M6 T... G-Code is called:
* automatic spindle is stopped (default of Mach3)
* the gantry moves to a tool change position
* the gantry moves over the tool length sensor and executes measurements

Since there are no good macros out there which also include tool measurement, it is developed in this repository. Any help is appreciated!

## Requirements
* CNC router or CNC mill
* Mach3
* Preferred: limit switches for all axes
* Very few programming skills

## How the macro works
Detailed steps:
* automatic spindle is stopped (default of Mach3)
* the gantry moves to a tool change position
* after user confirmation that the tool has been changed, the gantry moves over the tool length sensor
* tool length is measured with high speed
* gantry moves up a bit
* tool length is measured with slow speed

## How to install the macros to Mach3
