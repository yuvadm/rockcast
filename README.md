# Rockcast

We're playing with shitty hardware [again](https://github.com/yuvadm/DG-M1Q/). This time it's [this magnificent piece of DLNA/Miracast dongle](https://www.banggood.com/AnyCast-M2-Plus-WiFi-Display-Dongle-Miracast-TV-Dongle-HDMI-DLNA-AirPlay-1080P-p-982127.html)

## Flash

ROM chip is a [Macronix MX25L12845E](datasheet/mx25l12845e.pdf) 16M (128Mbit!) CMOS flash memory.

### Dump

Use [Flashrom](https://www.flashrom.org/Flashrom) from latest git master to enjoy significant speedup.

Dumping the flash via Bus Pirate:

```bash
$ flashrom -p buspirate_spi:dev=/dev/ttyUSB0,spispeed=8M -c MX25L12835F/MX25L12845E/MX25L12865E -o log.txt -r rom.bin
```

