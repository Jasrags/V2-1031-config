# Pronter (V2-1031) Klipper Config

![Pronter (V2-1031)](./images/Pronter-V2-1031.png)

Klipper configs for this printer running fluidd.

Most the files in /configs are from [eecue's klipper configs](https://github.com/eecue/klippper-config)

# Table of Contents
**(!)** = has important warning
- [**(!)** Change Log](#change-log)
- [Printer Mods](#printer-mods)
- [Klipper Plugins](#klipper-plugins)

# Change Log

Changes will be noted here by date, title if needed, files changed, summary of changes. 

_**Note: only changes of signifigance will be added.**_


- **2021-11-08:** _The one where I try klicky probe again._
    * Enabled
        * `configs/dockable_probe.cfg`
        * `configs/z_calibration.cfg`
    * Disabled
        * `configs/probe.cfg`
	* `configs/bed_mesh.cfg` 
        * Use dense bed mesh
            * `probe_count: 5,5` -> `probe_count: 9,9`
            * `relative_reference_index: 24` -> `relative_reference_index: 77`
	* `configs/klipper_expander.cfg`
        * Updated pin aliases 
            * `MOSFET0=PA0, MOSFET2=PA1, MOSFET3=PA2, MOSFET4=PA3,` -> `MOSFET0=PA0, MOSFET1=PA1, MOSFET2=PA2, MOSFET3=PA3`
	* `configs/main_printer.cfg`
        * Updated pin aliases 
            * `LED-R=PB6, LED-G=PB5, LED-B=PB7, LED_NEOPIXEL=PD3,` -> `LED_R=PB6, LED_G=PB5, LED_B=PB7, LED_NEOPIXEL=PD3`
	* `configs/steppers.cfg`
        * Slow down probing
            * `homing_retract_dist: 3` -> `homing_retract_dist: 2`
            * `second_homing_speed: 5` -> `second_homing_speed: 2`
	* `macros/printing.cfg`
        * Moved `PRINT_START` calibration commands to `CALIBRATE` in `macros/calibration.cfg`
    * `macros/calibration.cfg`
        * File created
            * Added `CALIBRATE`
                * Run printer calibration based on config. (quad_gantry_level,auto_z_offset,bed_mesh)
            * Added `TEST_CALIBRATE` 
                * Command to test CALIBRATE macro
    * `macros/uncategorized.cfg`
        * Renamed `SPEED_TEST` to `TEST_SPEED` and added description
	* `moonraker.conf`
        * Added `KlipperScreen` to `update_manager`
    * `flash_klipper.sh` Added script to flash klipper on to all mcu instances.
- **2021-11-05:** _The one with square corners._
    * `configs/main_printer.cfg`
        * `square_corner_velocity: 5.0` -> `square_corner_velocity: 8.0`
- **2021-11-04:** _The one where I try to improve probing accuracy._
    * `configs/bed_mesh.cfg`
        * `relative_reference_index: 12` -> `relative_reference_index: 24`
    * `configs/probe.cfg`
        * `y_offset: 25.0` -> `y_offset: 23.0`
        * `samples: 3` -> `samples: 4`
    * `macros/printing.cfg`
        * `PRINT_END`
            * Modifed end position to be `rear center`
            * Added `SONG_SINGLE_BEEP` near the end

# Printer Mods

* [AB-BN-30- Improved afterburner hotend](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Badnoob/AB-BN)
* [VEFACH - Voron Exhaust Filter Activated Coal + Hepa](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/KevinAkaSam/VEFACH)
* [SexBolt - Alternative Z endstop](https://github.com/hartk1213/MISC/tree/main/Voron%20Mods/Voron%202/2.4/Voron2.4_SexBolt_ZEndstop)
* [Pins Mod](https://github.com/hartk1213/MISC/tree/main/Voron%20Mods/Voron%202/2.4/Voron2.4_Pins_Mod)
* [GE5C Z Joint bearings](https://github.com/hartk1213/MISC/tree/main/Voron%20Mods/Voron%202/2.4/Voron2.4_GE5C)
* [Umbilical Strain Relief](https://github.com/hartk1213/MISC/tree/main/Voron%20Mods/Voron%202/2.4/Voron2.4_umbilical_strain_relief)
* [Afterburner Toolhead PCB](https://github.com/VoronDesign/Voron-Hardware/tree/master/Afterburner_Toolhead_PCB)
* [Klipper Expander](https://github.com/VoronDesign/Voron-Hardware/tree/master/Klipper_Expander)
* [Hour Counter](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/MarcPot/Skirt_Mods)


# Klipper Plugins

* frame_expansion_compensation
* gcode_shell_command