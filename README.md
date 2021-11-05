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