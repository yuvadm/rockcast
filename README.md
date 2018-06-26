# Rockcast

We're playing with cheap hardware [again](https://github.com/yuvadm/DG-M1Q/). This time it's [this magnificent piece of DLNA/Miracast dongle](https://www.banggood.com/AnyCast-M2-Plus-WiFi-Display-Dongle-Miracast-TV-Dongle-HDMI-DLNA-AirPlay-1080P-p-982127.html) which looks like a Chinesium clone of the Wecast C2.

Since the RK3036 SoC in this device seems to have relatively good open source kernel and toolchain support, it might be a nice target for custom firmware.

## Hardware 

- [Rockchip RK3036](datasheets/rk3036.pdf) Dual core ARM Cortex-A7 SoC
- [Macronix MX25L12845E](datasheets/mx25l12845e.pdf) 16M (128Mbit!) CMOS flash memory
- [Hynix HY5PS1G1631C](datasheets/hy5ps1g1631c.pdf) 1GB DDR2 SDRAM

### Pics

 - [front.jpg](imgs/front.jpg)
 - [back.jpg](imgs/back.jpg)

## Dump

Use [Flashrom](https://www.flashrom.org/Flashrom) from latest git master to enjoy significant speedup.

Dumping the flash via Bus Pirate:

```bash
$ flashrom -p buspirate_spi:dev=/dev/ttyUSB0,spispeed=8M -c MX25L12835F/MX25L12845E/MX25L12865E -o log.txt -r rom.bin
```

## Notes

- Booting with button pressed -> mask rom mode
- Booting with SPI out pin 8 shorted to ground -> mask rom mode

## Open Questions

- What the fuck is going on with the storage? Why is the ROM dump so sparse?
- Where are the UART pads / pins hiding?
