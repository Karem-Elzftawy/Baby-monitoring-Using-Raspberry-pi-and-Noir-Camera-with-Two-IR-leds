### Raspberry Pi Setup

This guide is tested on RPI 3.

### How to setup the Raspberry Pi

* Download a RASPBIAN image from [here](https://www.raspberrypi.org/downloads/raspbian/).

* Follow [these instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to install the RASBIAN OS. 

* Once the sd card is ready and the OS burned on the SD.

* Enable SSH on a headless Raspberry Pi (add file to SD card on another machine"PC")
>For headless setup, `SSH` can be enabled by placing a file named ssh, without any extension, onto the boot partition of the SD card from another computer. When the Pi boots, it looks for the `ssh` file. If it is found, SSH is enabled and the file is deleted. The content of the file does not matter; it could contain text, or nothing at all.

If you have loaded Raspbian onto a blank SD card, you will have two partitions. The first one, which is the smaller one, is the boot partition. Place the file into this one.

* configure your Wifi network.
For Wifi configuration, `Wifi` can be configured by adding a file named `wpa_supplicant.conf` The file should contain the following details:
#### For **Raspbian Jessie:**
```
network={
    ssid="YOUR_NETWORK_NAME"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}
```
#### For **Raspbian Stretch:**
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
network={
    ssid="YOUR_NETWORK_NAME"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}
```
With this file in place, Raspbian will move it in `/etc/wpa_supplicant/` when the system is booted.

* The next step is to put the SD Card into the Raspberry pi and plug in the power to start working on the Raspberry pi.

* Detecting IP address of Raspberry Pi on your network
> To get IP of any device currently active on your network, you can use free utility **[Advanced IP Scanner]**(http://www.advanced-ip-scanner.com/), scan the network and you will find your Raspberry Pi IP as shown below.


![IP](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/raspberry-pi-ip.png)

* `SSH` using Windows; open **[putty]**(http://www.putty.org/) on your Windows.

* Add your Raspberry Pi as a host
>PuTTY does not include an installer package: it is a stand-alone .exe file. When you run it, you will see the configuration screen below:

![putty](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/ssh-win-config.png)

Type the IP address of the Pi into the `Host Name` field and click the `Open` button. If nothing happens when you click the `Open` button, and you eventually see a message saying `Network error: Connection timed out`, it is likely that you have entered the wrong IP address for the Pi.

* Connect
>When the connection works you will see the security warning shown below. You can safely ignore it, and click the 'Yes' button. You will only see this warning the first time PuTTY connects to a Raspberry Pi that it has not seen before.

![warning](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/ssh-win-warning.png)

You will now see the usual login prompt. Log in with the same username and password you would use on the Pi itself. The default login for Raspbian is `pi` with the password `raspberry`.

You should now have the Raspberry Pi prompt which will be identical to the one found on the Raspberry Pi itself.

``
pi@raspberrypi ~ $
``

![ssh](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/ssh-win-window.png)

* Now you need to open the Raspberry Pi Config screen using the `raspi-config` program you will have used when you first set up your Raspberry Pi.
   ```
   sudo raspi-config
   ```  
The `sudo`  is required because you will be changing files that you do not own as the `pi` user.

![raspi-config](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/raspi-config.png)

#### Moving around the menu

>Use the `up` and `down` arrow keys to move the highlighted selection between the options available. Pressing the `right` arrow key will jump out of the Options menu and take you to the `<Select>` and `<Finish>` buttons. Pressing `left` will take you back to the options. Alternatively, you can use the `Tab` key to switch between these.

#### 1. Expand the filesytem

>You will need to reboot the Raspberry Pi to make this available. Note that there is no confirmation: selecting the option begins the partition expansion immediately.

#### 2. Interfacing opitions

##### Enable Camera

>In order to use the Raspberry Pi Camera Module, you must enable it here. Select the option and proceed to `Enable`. This will make sure at least 128MB of RAM is dedicated to the GPU.

##### Enable SSH

>Enable/disable remote command line access to your Pi using SSH.

##### Enable VNC

>VNC is a graphical desktop sharing system that allows you to remotely control the desktop interface of one computer (running VNC Server) from another computer or mobile device (running VNC Viewer). VNC Viewer transmits the keyboard and either mouse or touch events to VNC Server, and receives updates to the screen in return.

You will see the desktop of the Raspberry Pi inside a window on your computer or mobile device. You'll be able to control it as though you were working on the Raspberry Pi itself.

![VNC](https://github.com/Karem-Elzftawy/Baby-monitoring-Using-Raspberry-pi-and-Noir-Camera-with-Two-IR-leds/blob/master/images/raspberry-pi-connect.png)


* Execute the following instructions on the command line to download and install the latest kernel, GPU firmware, and applications. You'll need an internet connection for this to work correctly.
```
sudo apt-get update
sudo apt-get upgrade
sudo raspi-update
```
