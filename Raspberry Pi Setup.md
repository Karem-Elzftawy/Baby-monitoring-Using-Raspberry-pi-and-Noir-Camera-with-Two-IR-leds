### Raspberry Pi Setup

This guide is tested on RPI 3.

### How to setup the Raspberry Pi

* Download a RASPBIAN image from [here](https://www.raspberrypi.org/downloads/raspbian/).
* Follow [these instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to install the RASBIAN OS. 
* Once the sd card is ready and the system has rebooted.

*Now you need to open the Raspberry Pi Config screen using the `raspi-config` program you will have used when you first set up your Raspberry Pi.
   ```
   sudo raspi-config
   ```  
The `sudo`  is required because you will be changing files that you do not own as the `pi` user.
![raspi-config](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/raspi-config.png)

> Expand the filesytem and reboot.


*Execute the following instructions on the command line to download and install the latest kernel, GPU firmware, and applications. You'll need an internet connection for this to work correctly.
```
sudo apt-get update
sudo apt-get upgrade
```
* 
