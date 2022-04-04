# Drawing Robot Tool by Antiflix

This is the official repository for the Drawing Robot Inkscape extension.

## Purpose

This extension work for the [Drawing Robot - Arduino Uno + CNC Shield + GRBL](https://www.thingiverse.com/thing:2349232)

* This is made for Inkscape 1.0 and above.
* This machin is using GRBL Control with CNC Arduino Shield

## Installation

Download the source code) and copy the plotter-lod.inx and plotter-lod.py into the Inkscape extensions folder.

 Inkscape lists the location of your extensions folder under **Edit** > **Preferences** > **System**.

Restart Inkscape and you're done.

## Gcode Panel

> Inside `Inkscape > Extension > Generate GCode for Drawing Robot > Drawing Robot tool by Antiflix`

![Drawing Robot tool panel](img/GcodePanel.png)

| Name | Definition | Default | Gcode Result |
|---|---| --- | --- |
| **Drawing On Command** | Gcode commande to lower down the Z-axis | `M5` | `M5 S0` |
| **Drawing Off Command** | Gcode commande to upper the Z-axis | `M3` | `M3 S90` |
| **Pen Up Travel speed** | Travel speed with Pen Up | `3000` | `G1 F3000` |
| **Pen Down Travel speed** | Travel speed when drawing | `3000` | `G1 F3000` |
| **Pen Up Degree** | Degree of servo for upper position | `90` | `M3 S90` |
| **Pen Down Degree** | Degree of servo for lower position | `0` | `M5 S0` |
| **Pen On Delay** | Delay after moving and before drawing | `0,1` | `G4 P0.1` |
| **Pen Off Delay** | Delay after drawing and before moving | `0,1` | `G4 P0.1` |
| **Directory** | path directory to save your file in absolute | | |
| **Filename + numeric value** | the numeric value increment your file with the same name | `output.gcode` | |
| **All Units** | **Important** Be sure to setting everything up to the same unit inside Inkscape - Document Units, Inkscape Units and </br>this output units otherwise it mae some stranges things | `mm` | |

### Custom G-code Header and Footer

Add "header" and "footer" text files without extensions in your destination directory to add custom commands. Don't forget to add a new line at the end of these two files.

If no files are detected the default values are :
- Header : G90 ; Absolute positioningon the
- Header : G0 Z0 ; Display path inside GRBL Control
- Footer : G1 X0 Y0 ; Move to X0 Y0

## For developers

Pull requests are welcome.

## Credits

This inkscape extension is adapted from [J-Tech-Photonics-Laser-Tool](https://github.com/JTechPhotonics/J-Tech-Photonics-Laser-Tool) inkscape extension and from [LY-Drawbot-Tool-by-LOD](https://github.com/love-open-design/LY-Drawbot-Tool-by-LOD).

Thanks to [StuartB44](https://www.instructables.com/member/StuartB44/) for his work and infos on [Instructables](https://www.instructables.com/Fix-for-Image-Not-Showing-in-GRBLControl/) to display GCode inside GRBL Control
