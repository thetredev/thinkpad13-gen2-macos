# Lenovo ThinkPad 13 Gen2: Clover EFI partition

**- Currently only macOS Sierra is supported -**


## What's working OOB - even when installing the OS?
* Trackpad
* Graphics
* Battery
* NVMe
* Ethernet, but:
    * The notebook does not provide an Ethernet port
    * Lenovo forces you to use a docking station for that
    * The network settings show the Ethernet connection, so I *guess* everything is working as it should

## Screenshots
### 1. System Info
![01_system_info](/Screenshots/01_system_info.png?raw=true "System Info")

### 2. Trackpad
![02_trackpad_1](/Screenshots/02_trackpad_1.png?raw=true "Trackpad 1")
![02_trackpad_2](/Screenshots/02_trackpad_2.png?raw=true "Trackpad 2")
![02_trackpad_3](/Screenshots/02_trackpad_3.png?raw=true "Trackpad 3")

### 3. Network Settings
![03_network_settings](/Screenshots/03_network_settings.png?raw=true "Network Settings")

## TODO
* HDMI
    * This should work with some `config.plist` tweaks, however, I couldn't bother with it any longer so I just left it as it is (if it's currently working, it's highly unstable)
    * If you can find a way to enable it or make it stable, feel free to create a pull request!
    * I'll work on it every now and then, too

## Wat does not work?
* WiFi
    * The builtin Intel AC-7265 card is not supported by macOS (and supposedly never will be)
    * The search for a replacement was unsuccessful (at least here in Germany)
    * So I went with a generic *USB-C to Ethernet* adapter with a builtin Realtek NIC (drivers: https://www.realtek.com/en/component/zoo/category/network-interface-controllers-10-100-1000m-gigabit-ethernet-usb-3-0-software)
* Sound
    * I'm using a USB audio interface so I don't care about the builtin speakers or headphone jack
    * If you can find a way to enable the builtin sound, feel free to create a pull request!
