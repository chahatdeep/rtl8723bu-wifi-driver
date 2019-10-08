# rtl8723bu-wifi-driver
Driver for Realtek RTL8723BU Wireless Adapter with Hardware ID `0bda:b720`. Tested with EDIMAX N150 WiFi-Bluetooth 4.0 USB adaptor on Intel Up board.

- Original Author: [lwfinger](https://github.com/lwfinger/rtl8723bu)


## Instructions
Get it from Github repository with the following command in the Linux terminal.
```
git clone https://github.com/chahatdeep/rtl8723bu-wifi-driver.git
cd rtl8723bu-wifi-driver
```
## Concurrent or Non-Concurrent Mode
By default driver operates the hardware as a station AND as an access point *simultaneously*.  This will show two devices when you run the `iwconfig` command.

If you do not want two devices (station and an access point) *simultaneously*, then follow these instructions.

- **Step 1: Run the following command in the Linux terminal.**
```
vim Makefile
```

- **Step 2: Find the line that contains `EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE` and insert a `#` symbol at the beginning of that line. This comments that line and disables concurrent mode.**


## Manual install
Run the following commands in the Linux terminal.

```
make
sudo make install
sudo modprobe -v 8723bu
```
