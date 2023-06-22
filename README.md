# Home Assistant Operating System (HAOS) build repository for the Orange Pi 4 LTS (RK3399)

REL-10 branch: HAOS 10.3 (linux 6.1.34) (u-boot 2023.01)

# Working:

- Ethernet (YT8531c)
- Wifi + Bluetooth (UWE5622)
- HDMI
- USB ports
- eMMC
- SD Card Reader

# Untested:

- Sound input/output (ES8316)

# Notes:

To install the image directly to the internal eMMC device (if available), use an Armbian `https://www.armbian.com/orange-pi-4-lts/` or Manjaro `https://manjaro.org/download/` image for OrangePi 4 LTS pre-installed on an SD card, then copy the HAOS image to the live system. Extract the image using `unxz` then use `lsblk` to determine the correction location to write the image to the internal eMMC (look for the eMMC size in the output which matches your board size). Write the image to eMMC using `dd`, for example: `sudo dd if=haos.img of=/dev/mmcblk0 bs=10MB`

Once the image is written, power off the device and remove the SD card. Connect an ethernet cable, power on the device. Wait a few minutes and then connect to http://homeassistant.local:8123 or check your router for the correct IPV4 address.

# Thanks:

Huge thank you to @agners and @citruz who helped me immensely with this effort and to all the devs who worked on patches (and continue to work) to support this board. Recommended reading for beginners of building embedded linux: `https://www.thirtythreeforty.net/series/mastering-embedded-linux`
