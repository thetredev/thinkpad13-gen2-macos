# Lenovo ThinkPad 13 Gen2: OpenCore EFI partition

**- Currently only macOS Catalina is supported -**

This EFI partition contains relatively reasonably working drivers for the notebook. The stability does by no means come close to a real MacBook, however, it's a good place to start in my opinion.

Be sure to change the following entries in [`EFI/OC/config.plist`](/EFI/OC/config.plist) to properly use your notebook:
* `PlatformInfo/Generic/MLB`
* `PlatformInfo/Generic/SystemSerialNumber`
* `PlatformInfo/Generic/SystemUUID`

I marked them all with `CHANGEME`.

## What does definitely not work?
* USB-C: Connecting anything to USB-C will directly crash the system and make it unresponsive.

## What's working OOB - even during OS installation?
* Trackpad
* Graphics
* Battery
* NVMe
* USB-A ports
* Built-in Audio
* WiFi (https://github.com/OpenIntelWireless/itlwm)
    * The driver converts the WiFi connection to a virtual Ethernet connection, hence macOS thinks an Ethernet cable is plugged in. This can be a bit janky sometimes, though it's stable more often than not.
    * You could experience some random disconnects here and there - you have been warned.
* Ethernet, but:
    * The notebook does not provide an Ethernet port
    * Lenovo forces you to use a docking station for that
    * The network settings show the Ethernet connection, so *I guess* everything is working as it should
    * I went with a generic *USB-A 3.0 to Ethernet* adapter with a builtin Realtek NIC (drivers: https://www.realtek.com/en/component/zoo/category/network-interface-controllers-10-100-1000m-gigabit-ethernet-usb-3-0-software)
* HDMI, but:
    * The secondary monitor only gets recognized when plugged in or turned on *after* the system already booted up (after loggin in is the safest bet).
    * There's probably something wrong with macOS not realizing that the second monitor is present during bootup.
    * Maybe it's a Catalina bug, maybe it's an OpenCore bug, not quite sure.

## Screenshots
### 1. System Info
![01_system_info](/Screenshots/01_system_info.jpg?raw=true "System Info")

### 2. Trackpad
![02_trackpad_1](/Screenshots/02_trackpad_1.jpg?raw=true "Trackpad 1")
![02_trackpad_2](/Screenshots/02_trackpad_2.jpg?raw=true "Trackpad 2")
![02_trackpad_3](/Screenshots/02_trackpad_3.jpg?raw=true "Trackpad 3")

### 3. Network Settings
![03_network_settings](/Screenshots/03_network_settings.jpg?raw=true "Network Settings")

## What could work? (Untested)
* SD card slot
* AUX audio jack
* ThinkPad docking station (don't have one)
* Any macOS newer than Catalina when using a newer OpenCore version. But that was a bit too risky for me so I haven't tried it yet.
