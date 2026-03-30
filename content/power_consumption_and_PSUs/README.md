# Q2 power consumption and power supply replacement

## Power consumption

| | DC side | AC side |
|-|-|-|
| Standby | 20W | 60W |
| Nozzle heater | 70W | 90W |
| Bed heater | 280W | 480W |
| Enclosure heater | 4W | 270W |

Notes:

- Standby was measured before a print, with the small MCU fan on.
- Heaters were operating at 100% PWM duty.
- The enclosure's heater is hard-wired to AC; the solid state relay controlling the heater and the fan are on DC.

Those measurements show that:

- The total consumption at full duty on the DC side is more than the original PSU's rating (350W). Indeed, users report that with all the heaters operating at full duty the DC voltage sags by a couple volts.

- The OEM PSU's power factor (PF) is bad.

## PSU replacement

Issues with the [CZL-350D-24](https://www.leadpowers.com/product-CZL-350D_Series_Built_in_LED_Power_Supply.html) OEM PSU:

- Bad power factor
- Always on, noisy fan
- "Electrical noise" heard on upstream UPS'es, inverters, etc.

A popular replacement for the original PSU is the Mean Well [LRS-350-24](https://www.meanwell.com/Upload/PDF/LRS-350/LRS-350-spec.pdf). The unit has dynamic fan control and operates silently below a given temperature. Some users also replaced the Mean Well PSU's fan with a better quality third party fan (eg. 92mm Arctic F9 fan).

Given that the printer operates at or at more than the PSU's rating, the [LRS-350N2-24](https://www.meanwell.com/Upload/PDF/LRS-350N2/LRS-350N2-spec.pdf) PSU may be favored over the LRS-350-24, as it handles boost power better than the LRS-350.

Mean Well's LRS series don't have active power factor correction though. As of writing, there doesn't seem to be a 1:1 PSU replacement that can handle 350+ W, with active PFC.
The Mean Well [RSP-320-24](https://www.meanwell.com/Upload/PDF/RSP-320/RSP-320-spec.pdf) PSU has active PFC and the same dimension as the original PSU, but unfortunately doesn't work because the printer operates at ~350W, and the 30W rating difference with the LRS-350 is enough to power cycle the RSP-320 when the heaters are started at the same time (note: interestingly the PSU works when manually delaying the nozzle and bed heaters by a couple of seconds but it power cycles at the beginning of a 3D print).

Also note that the LRS series do not have a terminal protection cover, unlike the OEM PSU. Printing a cover (or finding an appropriate piece of plastic) - or at worst, taping the terminals with electrical tape - is recommended.
