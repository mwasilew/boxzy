**Home Position.** BoXZY homes to the back left corner, with the platform all the way up. This is Machine Zero. Home buttons and G28 will send the axes to their minimum limit switches, not to the offset which we refer to as the "User Home" position.

**Fusion Post Processor.** Fusion G-code outputs offset to 0 at the beginning of the G-code script. The machine must be at your desired 0, 0, 0 user position or the G92 X0 Y0 Z0 must be removed from the script. Sequential toolpaths with tool changes should be done using individual G-code scripts for each tool, not a pause function. Z offset will need to be reset after each tool change.

**BoXZY defaults to absolute coordinates.** Use standard G90 or G91 codes to change between absolute and relative coordinate modes.

**Inches vs Millimeters.** Use standard G20 and G21 codes to switch between modes. Warning; Your manual control window will no longer operate in millimeters when the machine is switched to inches. This can be concerning if you have forgotten that you've changed modes.

**Setting Tool Offset.** Manually move the Z axis and set the face of the bit onto the surface of your material blank, where the bottom edge of the Makita body is flush with the bottom of the Attachment Mount. Use G92 Z0 to set the position as 0 (you can also enter a specific coordinate or distance after the axis designation, but this isn't recommended). Click [HERE](Setting_User_Home_for_Milling.md) for a guide to easily accomplish this. Offset can be used in any axis.

**Limit switch function:** The minimum limit switch is used for homing. When not executing homing commands, switches stop movement any further in that direction, but do not stop other commands or movements. The entire machine will not stop when a switch is hit. The machine will continue all other movements as if it were able to complete the commands that pushed it into a limit switch. Positioning will be affected whenever a switch is activated where it is not expected to be. It will no longer be maintaining accurate positioning in that axis.

**BoXZY G-code Formatting:**
 * BoXZY G-code cannot have line numbers.
 * Spaces are required between command designation (G1, G2 etc.), axis+coordinates and any accessory commands (ex: L100).
 * Can only have one G command per line.
 * Command designations (G1, G2 etc.) are required for every single command line even if identical from one line to the next.
 * Federate needs to be stated for each change between command designations (each time you use a different G command from previous line).

**Example of Proper Code Format:**

G1 X10 Y10 Z-10.5 L50 F200

G1 X10 Y5 Z0 L50

G0 X4 Y4 F1000

 * E is extruder distance/coordinate for line (dependent on absolute or relative mode), ex: G1 X4 E20
 * L is laser power 0-100. Laser power can be done in multiple blocks ex: G1 X4 F200 L50, L100, L20, L30. Assuming the axis is moving 4mm, each laser power level represents one millimeter of movement. This can break down as far as .1mm per laser power level. It can be added to any G1 or G0 command line, but does not work with other G commands including G2/G3).

**Implemented Codes:**

G0 -> G1

G1 - Coordinated Movement X Y Z E

G2/G3 - Arc

G20 - Units for G0/G1 are inches.

G21 - Units for G0/G1 are mm.

G28 - Home all axes or named axis.

G90 - Use absolute coordinates.

G91 - Use relative coordinates.

G92 - Set current position to coordinates given.
