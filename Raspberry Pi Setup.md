### Raspberry Pi Setup

This guide is tested on RPI 3.

### How to setup the Raspberry Pi

* Download a RASPBIAN image from [here](https://www.raspberrypi.org/downloads/raspbian/).
* Follow [these instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to install the RASBIAN OS. 
* Once the sd card is ready and the system has rebooted.

* Now you need to open the Raspberry Pi Config screen using the `raspi-config` program you will have used when you first set up your Raspberry Pi.
   ```
   sudo raspi-config
   ```  
The `sudo`  is required because you will be changing files that you do not own as the `pi` user.

![raspi-config](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/raspi-config.png)

1. **Moving around the menu**
2. **Expand the filesytem**
You will need to reboot the Raspberry Pi to make this available. Note that there is no confirmation: selecting the option begins the partition expansion immediately.

3. **Enable Camera**
In order to use the Raspberry Pi Camera Module, you must enable it here. Select the option and proceed to `Enable`. This will make sure at least 128MB of RAM is dedicated to the GPU.

* Execute the following instructions on the command line to download and install the latest kernel, GPU firmware, and applications. You'll need an internet connection for this to work correctly.
```
sudo apt-get update
sudo apt-get upgrade
```
   Use the up and down arrow keys to move the highlighted selection between the options available. Pressing the right arrow key will jump out of the Options menu and take you to the <Select> and <Finish> buttons. Pressing left will take you back to the options. Alternatively, you can use the Tab key to switch between these.

