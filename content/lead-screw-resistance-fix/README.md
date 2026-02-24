# Fixing Z-axis lead screw rotation resistance

On a brand new printer, perhaps because of bad Q/C or rough handling during
shipping, it is possible that the bed's lead screw guide(s) and the stepper
motor loose alignment, resulting in increased rotation resistance of one (or
both) z-axis lead screw as the bed travels to the bottom of the enclosure.

In the worst case, the mechanical resistance becomes so important that stepper
motor's overcurrent detection is triggered - as if the bed made contact with
the bottom of the enclosure (or calibration blocks). With one lead screw
stopped and the other still rotating, the bed is heavily tilted to one side.

Automatic Bed Leveling (ABL) then fails with "No trigger on probe after full
movement" - which is expected given the heavy lean. The wiki's [suggested
fixes](https://wiki.qidi3d.com/en/Q2/Leveling-Error) won't work because the
cause isn't a calibration issue.

A temporary fix is to put two equal-height objects below the bed (eg. soda
cans). This obviously restricts printing height.

The long-term solution is to loosen the screws holding the stepper motor(s) and
the bed's lead screw guide, lower the bed, and retighten.

This [official Qidi
video](https://drive.google.com/drive/folders/1HHgrOTxmV4UaDpfuViA4hCU_qMdz1EFn?usp=sharing)
shows the procedure recommended by Qidi's support.

However, they retighten the screws with the bed at mid-height, which isn't
optimal. Instead, tighten all accessible screws with the bed still at the
bottom of the enclosure: in that position, only two of each stepper motor
screws are accessible, but tightening them is enough to keep the stepper motors
in place. Then move the bed higher and tighten the remaining screws.
