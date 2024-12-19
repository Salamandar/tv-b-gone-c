# TV-B-Gone-C

This is a compact USB-C powered TV-B-Gone.

See <https://www.tvbgone.com> for details.

Thank you Mitch Altman for this amazing project!

## Flashing

It is suggested to use an Arduino as ISP.

Burn the FUSE bits for the external 8MHz oscillator option:
```
avrdude -cavrisp -b 19200 -P /dev/ttyUSB0 -pattiny85 -U lfuse:w:0xfe:m -U hfuse:w:0xdf:m -U efuse:w:0xff:m
```

Then flash the firmware:
```
avrdude -cavrisp -b 19200 -P /dev/ttyUSB0 -pattiny85 -U flash:w:tvbgone.hex
```
