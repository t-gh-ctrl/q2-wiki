# Q2 power consumption and power supply replacement

## Power consumption

| | DC side | AC side |
|-|-|-|
| Standby | 30W | 60W |
| Nozzle heater | 64W | 87W |
| Bed heater | 264W | 478W |
| Enclosure heater | - | 272W |

Notes:

- Standby was measured after a print, with fans on.
- Heaters were operating at full PWM duty.
- The enclosure's heater is hard-wired to AC, controlled with a solid state relay (the enclosure's fan in on DC).

Those measurements show that:

- The total consumption at full duty on the DC side is more than the original PSU's rating (350W). Indeed, users report that with all the heaters operating at full duty the DC voltage sags by a couple volts.

- The original PSU's power factor (PF) is bad.

## PSU replacement

Issues with the original PSU ([CZL-350D-24](https://www.leadpowers.com/product-CZL-350D_Series_Built_in_LED_Power_Supply.html)):

- Bad power factor
- Always on, noisy fan
- "Electrical noise" heard on upstream UPS'es, inverters, etc.

Given the above, a popular replacement for the original PSU is the Mean Well [LRS-350-24](https://www.meanwell.com/Upload/PDF/LRS-350/LRS-350-spec.pdf). The unit has dynamic fan control and is [reported](https://www.inkcut.org/blog/2025/11/qidi-Q2-silent-power-supply-upgrade) to operate silently below a given temperature. Some users also replaced the Mean Well PSU's fan with a better quality third party fan (eg. 92mm Arctic F9 fan).

Given that the printer operates at or at more than the PSU's rating, the [LRS-350N2-24](https://www.meanwell.com/Upload/PDF/LRS-350N2/LRS-350N2-spec.pdf) PSU may be favored over the LRS-350-24, as it has better boost characteritics than the LRS-350.

The LRS series don't have active power factor correction though. The Mean Well [RSP-320-24](https://www.meanwell.com/Upload/PDF/RSP-320/RSP-320-spec.pdf) PSU has active PFC and the same dimension as the original PSU, but unfortunately doesn't work because the printer operates at ~350W, and the 30W rating difference with the LRS-350 is enough to make the RSP-320 stop/restarts when the heaters are started at the same time (note- the PSU works when manually delaying the nozzle and bed heaters by a couple of seconds).

Also note that the LRS (and RSP) series don't have a terminal protection cover. Printing a cover (or finding an appropriate piece of plastic) is recommended over taping the terminals with electrical tape.
