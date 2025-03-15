# KoRC - Korad Remote COntrol
KoRC - free software for controlling the Korad KD3305P power supply from a computer with Windows 7/8/10/11.It can be used as a replacement for software provided by the manufacturer, which requires the installation of the Labview environment to work.

## Features
* connection via USB or LAN
* two-way communication: computer <-> power supply
* ability to save voltage and current settings

## Installation
Installation is not required. Simply:
* [download](https://github.com/Code2xZ/KoRC/releases/download/KoRC/korc-1_0.zip)
* unpack the ZIP archive
* run

## Requirements

The program requires at least .NET Framework version 4.7.2 to run. In Windows versions lower than 10, its installation may be necessary. The "Offline" installer can be downloaded from here.
[download .NET](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net481-offline-installer)

# Manual

### Keyboard shortcuts

* CTRL+1 - selection of the voltage setting field for CHANNEL 1
* CTRL+2 - selection of the current setting field for CHANNEL 1
* CTRL+3 - selection of the voltage setting field for CHANNEL 2
* CTRL+4 - selection of the current setting field for CHANNEL 2
* CTRL+NUMPAD 1 - turn on/off CHANNEL 1
* CTRL+NUMPAD 2 - turn on/off CHANNEL 2
* CTRL+NUMPAD 0 - turn on/off both channels

### Connection via USB:

* Connect the Korad power supply to the USB port
* turn it on
* install the drivers provided by the manufacturer. Unless they were installed previously
* in the CONFIG tab, select USB in the CONNECTION TYPE field
* In the "COM port" field, enter the port number assigned to the device (e.g. com3). You can check it in the "Device Manager" in the "COM & LPT Ports" section
* click SAVE & APPLY

## Connection via LAN:

NOTE: To connect via LAN, it is necessary to add rules for incoming and outgoing UDP connections on port 18190 (the default application port) to the Windows firewall before configuration. This can be done, for example, by running the command line (CMD) with administrator rights and entering the commands:

for incoming connection:
```
netsh advfirewall firewall add rule name="KoRC_UDP_port" dir=in action=allow protocol=UDP localport=18190
```

for outgoing connection:
```
netsh advfirewall firewall add rule name="KoRC_UDP_port" dir=out action=allow protocol=UDP localport=18190
```

* connect the Korad power supply via USB as above. (Only the first time to upload IP addresses to the device)
* complete the LAN connection parameters:
  * IP - a free address in your network, e.g. 192.168.1.50
  * SUBMASK - subnet mask, e.g. 255.255.255.0
  * GATEWAY - default gateway, e.g. 192.168.1.1
  * PORT - port number, default 18190
* click SAVE & APPLY
* change CONNECTION TYPE to LAN
* click SAVE & APPLY
* now you can disconnect the USB cable

# Screenshots
![Screen Main](https://korc.code-zz.eu/g/zrzuty/www___03.03.2025_212244.jpg)
![Screen Config](https://korc.code-zz.eu/g/zrzuty/www___03.03.2025_212246.jpg)
