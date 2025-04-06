# EvilCrow-Cable
BadUSB cable based on Attiny85 microcontroller with data line enabled.

![EvilCrow](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/Logo1.png)

**Idea:** Joel Serna & Ernesto Sánchez

**Development and implementation:** Joel Serna & Ernesto Sánchez

**PCB design:** AprilBrother

**Manufacturer and distributor:** AprilBrother (@aprbrother).

**Distributor from United Kingdom:** KSEC Worldwide (@KSEC_KC).

**Other collaborators:** Ignacio Díaz & Forensic Security, Innovart & Jorge Mata, Roland Santiago, Luca Bongiorni, Marcus Mengs, Mike Groover...

The developers and collaborators of this project do not earn money with this. 
You can invite me for a coffee to further develop Low-Cost hacking devices. If you don't invite me for a coffee, nothing happens, I will continue developing devices.

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/E1E614OA5)

**Available with April Brother (shipping from China):** 

* USB-A to USB-C:

	* Aliexpress: https://www.aliexpress.us/item/3256806547844804.html
	* Tindie: https://www.tindie.com/products/aprbrother/evil-crow-cable-typec/

* USB-A to MicroUSB:

	* Aliexpress: https://www.aliexpress.us/item/3256806547863881.html
	* Tindie: https://www.tindie.com/products/aprbrother/evil-crow-cable/

**Available with SAPSAN Cybersec & Military (shipping from EU, Poland):**

* USB-A to USB-C:
	
	* https://sapsan-sklep.pl/en/products/evil-crow-cable

* USB-A to MicroUSB:

	* https://sapsan-sklep.pl/en/products/evil-crow-cable

**Available with KSEC Worldwide (shipping from United Kingdom):**

* USB-A to USB-C:

	* https://labs.ksec.co.uk/product/evil-crow-cable-usb-c/

* USB-A to MicroUSB:

	* https://labs.ksec.co.uk/product/evil-crow-cable/

**Available with Tienda Espía (shipping from Mexico):**

* USB-A to MicroUSB and USB-A to USB-C:

	* https://tiendaespia.com.mx/producto/evil-crow-cable-badusb/

**Summary:**
1. Acknowledgement
2. Introduction
3. Disclaimer
4. Installation
	* Bootloader
	* Basic requirements (Ubuntu and Windows)
	* Installation of Digispark USB Driver (Only Windows)
	* Installation and update of Micronucleus Windows (Only Windows, not tested)
	* Installation and update of Micronucleus Ubuntu (Only Ubuntu)
	* Upload Payloads (Ubuntu and Windows)
	* Payloads (Ubuntu and Windows)
 	* VM for dummies
5. Data line information
6. Attack options

# Acknowledgement

**PCB design first version (Rev0):** Innovart & Innovart

	* Jorge Mata: @jor_mata

	* Innovart: @innovart_cc

	* https://innovart.cc

**PCB design Rev version (Rev1, Rev2, Rev3 and Rev3.1):** Ignacio Díaz & ForensicSecurity

	* Ignacio Díaz: @Ignacio Díaz Álvarez

	* Forensic & Security: @ForensicSec

	* https://forensic-security.com
	
**PCB design final version, manufacturer and distributor:** AprilBrother

	* Website: https://aprbrother.com
	
	* Twitter: @aprbrother
	
**Tests and information:**

	* Roland Santiago (@Santpapen)
	
	* Luca Bongiorni (@LucaBongiorni)
	
	* Marcus Mengs (@mame82)
	
	* Mike Groover (@_MG_)

# Introduction
Evil Crow cable is a BadUSB device based on Attiny85 microcontroller with data line enabled.
For more information you can read the following repository:

https://github.com/joelsernamoreno/BadUSB-Cable

![Evil Crow cable 1](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/evilcrowcable1.jpeg)

![Evil Crow cable 2](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/evilcrowcable2.jpg)

# Disclaimer
Evil Crow Cable is a basic device for professionals and cybersecurity enthusiasts. This device was developed to show security breaches in USB peripherals.

AprilBrother and the collaborators of this project are not responsible for the incorrect use of Evil Crow cable. 

We recommend using this device for testing, learning and fun :D

# Installation

## Bootloader
AprilBrother burned the bootloader at Evil Crow cable. You don't have to do anything in this section.

## Basic requirements (Ubuntu and Windows)

### Ubuntu

1. Update Ubuntu packages with the following commands (only Ubuntu):
	* sudo apt update
	* sudo apt upgrade
2. Download Arduino IDE: https://www.arduino.cc/en/Main/Software
3. Install libusb and lib32stdc with the following commands (only Ubuntu):
	* sudo apt install libusb-dev
	* sudo apt install lib32stdc++6
4. Install build-essential with the following command (only Ubuntu):
	* sudo apt install build-essential
5. Download DigisparkKeyboard library with multiple layout support: https://github.com/ernesto-xload/DigisparkKeyboard
6. Unzip library in Arduino/libraries/directory
7. Edit DigiKeyboard.h file and uncomment #define kbd_es_es
8. Change #define kbd_es_es for your keyboard layout and save the changes
9. Run Arduino IDE with the following commands (**NOTE:** Don't install the Arduino IDE, just run it!)
	* cd arduino-1.X.XX-linux64/arduino-1.X.XX/ (example: cd arduino-1.8.10-linux64/arduino-1.8.10/)
	* ./arduino (**NOTE:** Do not run the Arduino IDE with root permissions!)
10. Click File and then Preferences
11. Add the JSON URL to the Additional Boards Manager text box: http://digistump.com/package_digistump_index.json
12. Click OK
13. Click Tools > Board > Board Manager
14. Search and Install: Digistump AVR Boards
15. Close the Arduino IDE

### Windows

1. Download Arduino IDE: https://www.arduino.cc/en/Main/Software	
2. Install drivers: https://raw.githubusercontent.com/digistump/DigistumpArduino/master/tools/micronucleus-2.0a4-win.zip
3. Download DigisparkKeyboard library with multiple layout support (Ubuntu and Windows): https://github.com/ernesto-xload/DigisparkKeyboard
4. Unzip library in Arduino/libraries/directory
5. Edit DigiKeyboard.h file and uncomment #define kbd_es_es
6. Change #define kbd_es_es for your keyboard layout and save the changes
10. Run Arduino IDE
11. Click File and then Preferences
12. Add the JSON URL to the Additional Boards Manager text box: http://digistump.com/package_digistump_index.json
13. Click OK
14. Click Tools > Board > Board Manager
15. Search and Install: Digistump AVR Boards
16. Close the Arduino IDE

## Installation of Digispark USB Driver (only Windows)

1. Download Arduino for Digispark which come with USB driver: http://sourceforge.net/projects/digistump/files/
2. Extract the file (DigisparkArduino-Win32-1.0.4-March29.zip) to any folder
3. Execute DigisparkArduino-Win32\DigisparkWindowsDriver\InstallDriver.exe to start installing the USB driver

## Installation and update of Micronucleus Windows (only Windows, not tested)

https://github.com/micronucleus/micronucleus

## Installation and update of Micronucleus Ubuntu (only Ubuntu)

1. Create the 49-micronucleus.rules file in the /etc/udev/rules.d/ directory.
2. Copy the contents to the file you just created: https://github.com/micronucleus/micronucleus/wiki/Ubuntu-Linux
3. Reboot the computer or run the following command to update the UDEV rules: udevadm control --reload-rules
4. Download Micronucleus with the following command: git clone https://github.com/micronucleus/micronucleus.git
5. Access the micronucleus/commandline directory with the following command: cd micronucleus/commandline
6. Compile with the following command: make
7. Access the .arduino15/packages/digistump/tools/micronucleus/2.0a4 directory with the following command: cd ~/.arduino15/packages/digistump/tools/micronucleus/2.0a4/
8. Create a backup of Micronucleus with following command: mv micronucleus micronucleus.old
9. Copy the latest version of Micronucleus to this directory with the following command: cp ~/PATH/micronucleus/commandline/micronucleus .
10. Reboot

## Upload Payloads (Ubuntu and Windows)

### Ubuntu

1. Download payloads: https://github.com/joelsernamoreno/badusb_examples/tree/master/attiny85_digispark
2. Run Arduino IDE with the following commands (**NOTE:** Don't install the Arduino IDE, just run it!)
	* cd arduino-1.X.XX-linux64/arduino-1.X.XX/ (example: cd arduino-1.8.10-linux64/arduino-1.8.10/)
	* ./arduino (**NOTE:** Do not run the Arduino IDE with root permissions!)
3. Open Payload with Arduino IDE
4. Click tools and select Board: Digispark (Default - 16.5 Mhz)
5. Click Upload
6. Connect the BadUSB cable when the Arduino IDE says to connect it.

### Windows

1. Download payloads: https://github.com/joelsernamoreno/badusb_examples/tree/master/attiny85_digispark
2. Run Arduino IDE
3. Open Payload with Arduino IDE
4. Click tools and select Board: Digispark (Default - 16.5 Mhz)
5. Click Upload
6. Connect the BadUSB cable when the Arduino IDE says to connect it.

**Demo video:** https://twitter.com/JoelSernaMoreno/status/1181296289323130882?s=19

![Sketch](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/upsketch.jpg)

## Payloads (Ubuntu and Windows)

You can get payloads in the following repository:

https://github.com/joelsernamoreno/badusb_examples/tree/master/attiny85_digispark

# VM for dummies 

1. Download VM: https://mega.nz/#!dtBmgQIY!4iiRBmrM1v42V-EDzVBr9dvOznbAHK-9jp3wK9BgMlo
2. Download and install VMWare: https://www.vmware.com/
3. Run VMware
4. Import Ubuntu.ova
5. Install VMWare-Tools: https://vitux.com/how-to-install-vmware-tools-in-ubuntu/
6. Add serial port with the following steps:
	* Click on VM -> Settings
	* Click on +Add...
	* Select serial port
	* Click on finish

![Serial Port](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/serial-port.png)

7. Add USB controller with the following steps:
	* Click on VM -> Settings
	* Click on +Add...
	* Select USB controller
	* Click on finish

![USB Controller](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/usb-controller.png)

8. Run Ubuntu VM
9. Enter password (password: evilcrowcable)
10. Open a terminal (CTRL+ALT+T)
11. Run Arduino IDE with the following commands:
	* cd arduino-1.8.10-linux64/arduino-1.8.10/
	* ./arduino (**NOTE:** Do not run the Arduino IDE with root permissions!)
12. Open a payload /home/evilcrowcable/attiny85_digispark/
13. Click tools and select Board: Digispark (Default - 16.5 Mhz)
14. Click Upload
15. Connect the BadUSB cable when the Arduino IDE says to connect it.

**Demo video:** https://twitter.com/JoelSernaMoreno/status/1181296289323130882?s=19	

# Data line information
Before using the data line in Evil Crow cable, read the following information:

The data line has been enabled with the published basic schema. Controlling the data line in Evil Crow cable is difficult because it does not have a USB hub inside.

When you connect a multimedia device (e.g. smartphone, mp3, etc.) to Evil Crow cable, the data line is in front of the Attiny85 microcontroller. This blocks the execution of the payload while the multimedia device is connected.

You can understand this with the following basic image. Anyway, in the section "Attack options", you can see the payload execution situations with/without the data line:

![Data Line](https://github.com/joelsernamoreno/EvilCrow-Cable/blob/master/images/dataline.PNG)

# Attack options

The following attack scenarios show the correct use of payload and data line execution:

1. **Evil Crow cable is connected to a PC:** the payload is executed.
2. **Evil Crow cable and a multimedia device are connected at the same time to a PC:** The data line is enabled and you can see the Mass Storage of the multimedia device, but the payload does not run.
3. **Evil Crow cable is connected to a PC and after running the payload, you connect a multimedia device:** The data line is enabled, but you have to wait 10-15 seconds before connecting the multimedia device. If you connect before 10-15 seconds the multimedia device, you may have errors.
4. **First Evil Crow cable and a multimedia device connect to a PC at the same time (Mass Storage enabled), then disconnect the multimedia device:** the payload is executed.

**Demo video:** https://twitter.com/JoelSernaMoreno/status/1189658626929111040?s=19

**Note:** You can consider the data line as proof of concept (PoC). In future versions the data line may be more advanced.

*Contact for questions:*
	* Twitter: @JoelSernaMoreno
