# Links

A collection of USB hacking–related links.

Another good list:
["USB Reverse Engineering: Down the rabbit hole" by Glenn Grant](https://devalias.net/devalias/2018/05/13/usb-reverse-engineering-down-the-rabbit-hole/).

Follow [@andreyknvl](https://twitter.com/andreyknvl) on Twitter or [@xairy@infosec.exchange](https://infosec.exchange/@xairy) on Mastodon to be notified of updates.

## Contents

- [Essentials](#essentials)
- [Workshops](#workshops)
- [Hardware](#hardware)
	- [Facedancer boards](#facedancer-boards)
	- [Linux boards](#linux-boards)
		- [Raspberry Pi Zero](#raspberry-pi-zero)
		- [BeagleBone Black](#beaglebone-black)
		- [USB Armory](#usb-armory)
		- [OpenStick](#openstick)
		- [Android](#android)
	- [Arduino boards](#arduino-boards)
		- [Teensy](#teensy)
		- [Digispark](#digispark)
		- [CJMCU BadUSB](#cjmcu-badusb)
		- [WiFi Duck](#wifi-duck)
	- [Dedicated BadUSB](#dedicated-badusb)
		- [Rubbery Ducky](#rubber-ducky)
		- [Bash Bunny](#bash-bunny)
		- [Cactus WHID](#cactus-whid)
		- [Flipper Zero](#flipper-zero)
		- [Other BadUSB](#other-badusb)
	- [Malicious cables](#malicious-cables)
	- [Keyloggers](#keyloggers)
	- [Sniffers and analyzers](#sniffers-and-analyzers)
		- [USB](#usb)
		- [USB Power Delivery](#usb-power-delivery)
	- [Other hardware](#other-hardware)
- [Linux USB stack](#linux-usb-stack)
	- [usbmon](#usbmon)
	- [Gadget subsystem](#gadget-subsystem)
		- [Raw Gadget](#raw-gadget)
- [Tools](#tools)
- [Research](#research)
- [Misc](#misc)

## Essentials

["USB 101: An Introduction to Universal Serial Bus 2.0" by Robert Murphy](https://www.cypress.com/file/134171/download) [book]

["USB in a NutShell" by Craig Peacock](https://www.beyondlogic.org/usbnutshell/usb1.shtml) [articles]

[USB: Document Library](https://www.usb.org/documents)


## Workshops

["Hacking the USB World with FaceDancer" by Kate Temkin](https://usb.ktemkin.com/) [workshop]


## Hardware

### Facedancer boards

(Hardware and tools compatible with the [modern Facedancer framework](https://github.com/greatscottgadgets/facedancer) and its older versions.)

[Cynthion: Multi-tool for building, analyzing, and hacking USB devices](https://www.crowdsupply.com/great-scott-gadgets/cynthion) [hardware]

[GreatFET One](https://greatscottgadgets.com/greatfet/one/) [hardware]

[Facedancer21](https://goodfet.sourceforge.net/hardware/facedancer21/) [hardware]

[Raspdancer: Facedancer21 expansion board for Raspberry Pi](https://wiki.yobi.be/index.php/Raspdancer) [hardware]

[BeagleDancer: Facedancer21 expansion board for BeagleBone](https://github.com/dominicgs/BeagleDancer) [hardware]

[Hydradancer: HydraUSB3-based backend for Facedancer](https://github.com/HydraDancer/hydradancer_fw) [hardware] [upcoming]
[[article](https://blog.quarkslab.com/hydradancer-faster-usb-emulation-for-facedancer.html)]

[2012: "Emulating USB Devices with Python" by Travis Goodspeed](https://travisgoodspeed.blogspot.de/2012/07/emulating-usb-devices-with-python.html) [article]

[2012: "Emulating USB DFU to Capture Firmware" by Travis Goodspeed](https://travisgoodspeed.blogspot.de/2012/10/emulating-usb-dfu-to-capture-firmware.html) [article]

[2017: "FaceDancer 2.0" by Dominic Spill](https://www.youtube.com/watch?v=L3Ug9591Vag) [video]

[2023: "Facedancer with Antoine"](https://www.youtube.com/watch?v=kjxvIssPN7Y) [video]

[Facedancer: Modern framework for all Facedancer boards](https://github.com/greatscottgadgets/facedancer) [github]

[goodfet: Legacy framework for Facedancer21 and GoodFET boards](https://github.com/travisgoodspeed/goodfet) [github]

[umap: USB host security assessment tool for Facedancer21 and GoodFET boards](https://github.com/nccgroup/umap) [github]

[umap2: Version 2 of umap](https://github.com/nccgroup/umap2) [github]

[nu-map: Fork of umap2 based on modern Facedancer framework](https://github.com/usb-tools/nu-map)[github]

[badusb2-mitm-poc: USB MitM with two Facedacer21 boards](https://github.com/withdk/badusb2-mitm-poc) [github]

[facewhisperer: USB host add-on for the ChipWhisperer side-channel analysis tool](https://git.approximate.life/facewhisperer.git/) [git]
[[video](https://www.youtube.com/watch?v=TeCQatNcF20)]
[[article](https://blog.securityinnovation.com/glitching-firmware-over-usb-using-facewhisperer)]

[raw_gadget/Facedancer: Prototype of Raw Gadget–based Facedancer backend for Linux boards](https://github.com/xairy/raw-gadget?tab=readme-ov-file#facedancer-backend) [github]

[packetry: Fast, intuitive USB 2.0 protocol analysis application for use with Cynthion](https://github.com/greatscottgadgets/packetry) [github]


### Linux boards

(A multitude of Linux boards can be used for USB device emulation.
This section focuses on the most used and historically-relevant of them.)

#### Raspberry Pi Zero

(The cheapest and most compact of the Raspberry Pi boards.)

[Raspberry Pi Zero](https://www.raspberrypi.com/products/raspberry-pi-zero/) [hardware]

[Turning your Raspberry PI Zero into a USB Gadget](https://learn.adafruit.com/turning-your-raspberry-pi-zero-into-a-usb-gadget) [article]

[Raspberry Pi Zero OTG Mode](https://gist.github.com/gbaman/50b6cca61dd1c3f88f41) [article]

[P4wnP1: Highly customizable USB attack platform based on Rasbperry Pi Zero](https://github.com/mame82/P4wnP1) [github]
[[writeup](https://github.com/mame82/P4wnP1/blob/master/writeup_lockpicker.md)]
[[Kali image](https://twitter.com/_binkybear/status/919324503020150784)]

[poisontap: Malicious Ethernet USB devices based on Raspberry Pi Zero](https://github.com/samyk/poisontap) [github]

[RaspberryPiZero_HID_MultiTool: Scripts for turning Raspberry Pi Zero into various USB devices](https://github.com/darrylburke/RaspberryPiZero_HID_MultiTool/) [github]

[rspiducky: Turns Rasberry Pi Zero into Rubber Ducky](https://github.com/msjmeyer/rspiducky) [github]

[sahara_emulator: Emulates Qualcomm Sahara using Raspberry Pi Zero](https://github.com/bkerler/sahara_emulator) [github]

[Raspdancer: Facedancer21 expansion board for Raspberry Pi](https://wiki.yobi.be/index.php/Raspdancer) [hardware]


#### BeagleBone Black

(The first board that was used for implementing USB-related tools.)

[BeagleBone Black](https://www.beagleboard.org/boards/beaglebone-black) [hardware]

[2014: "USB write blocking with USBProxy" by Dominic Spill](https://dominicspill.com/presentations/2014/Spill_BSidesLV_USBProxy_slides.pdf) [slides]

[2016: "USBiquitous: USB intrusion toolkit" by Benoit Camredon](https://www.sstic.org/media/SSTIC2016/SSTIC-actes/usb_toolkit/SSTIC2016-Article-usb_toolkit-camredon.pdf) [article]

[USBProxy-legacy: Proxy for USB devices based on libusb and GadgetFS](https://github.com/usb-tools/USBProxy-legacy) [github]

[USBSniffer: USB sniffer based on libusb and GadgetFS](https://www.elinux.org/BeagleBoard/GSoC/2010_Projects/USBSniffer) [article]
[[blog](https://beagleboard-usbsniffer.blogspot.com/)]
[[BeagleBoard-xM](https://github.com/matlo/bb_usb_sniffer)]

[usbq: Python framework for monitoring and modifying USB communications](https://github.com/ivision-research/usbq) [github]

[BeagleDancer: Facedancer21 expansion board for BeagleBone](https://github.com/dominicgs/BeagleDancer) [hardware]


#### USB Armory

[USB Armory](https://inversepath.com/usbarmory) [hardware]

[2015: "USB Armory as an Offensive Attack Platform"](https://raw.githubusercontent.com/wiki/inversepath/usbarmory/contrib/USB%20Armory%20as%20an%20Offensive%20Attack%20Platform%20Jeroen_van_Kessel-and-Nick_Triantafyllidis.pdf) [paper]

[2016: "Forging USB armory" by Andrea Barisani](https://www.blackhat.com/docs/asia-15/materials/asia-15-Barisani-Forging-The-USB-Armory.pdf) [slides]
[[video](https://www.youtube.com/watch?v=MsK2V_iO9Z4)]

[2016: "Snagging creds from locked machines" by Rob Fuller](https://room362.com/post/2016/snagging-creds-from-locked-machines/) [article]

[2017: "How to Build a USB Analyzer with USB Armory? - Creating an Armory Sandbox" by Pedro Vilaca](https://www.sentinelone.com/blog/armory-sandbox-building-usb-analyzer-usb-armory/) [article]


#### OpenStick

[OpenStick](https://github.com/OpenStick/OpenStick) [github]
[[wiki](https://www.kancloud.cn/handsomehacker/openstick/2636505)]
[[blobs](https://github.com/OpenStick/stick-blobs)]

[2022: "Hackable $20 Modem Combines LTE And Pi Zero W2 Powe" by Arya Voronova](https://hackaday.com/2022/08/03/hackable-20-modem-combines-lte-and-pi-zero-w2-power/) [article]

[2022: "OpenStick: Some Preliminary Investigations"](https://www.zianet.com/jgray/openstick/) [article]

[2023: "P4wnP1-LTE" by Rogan Dawes](https://sensepost.com/blog/2023/p4wnp1-lte/) [article]

[2022: "OpenStick" by Zoltan Mizsei](https://extrowerk.com/2022-07-31/OpenStick.html) [article]

[UF896 - Qualcomm MSM8916 LTE router ~384MiB RAM/2.4GiB flash, Android: OpenWrt?](https://forum.openwrt.org/t/uf896-qualcomm-msm8916-lte-router-384mib-ram-2-4gib-flash-android-openwrt/131712) [forum]

[OpenStick WIP notes](https://github.com/colemickens/mobile-nixos/tree/openstick/devices/openstick) [github]

[openstick-stuff](https://github.com/Mio-sha512/openstick-stuff/releases) [github]


#### Android

[android-keyboard-gadget: Convert Android device into USB keyboard/mouse](https://github.com/pelya/android-keyboard-gadget) [github]

[DroidDucky: Simple DuckyScript interpreter in Bash](https://github.com/anbud/DroidDucky) [github]
[[article](https://web.archive.org/web/20201108135130/http://zx.rs/6/DroidDucky---Can-an-Android-quack-like-a-duck/)]


### Arduino boards

(Many Arduino boards and their clones can be used for USB device emulation.
This section provides only a few notable links; there is too many to list all.)

[Arduino Classic boards](https://www.arduino.cc/en/hardware#classic-family) [hardware]

[BadUSB DIY](https://www.youtube.com/playlist?list=PL2YepVFF1azFjaLd5PYCYg2lKeB6t1xcj) [playlist]


#### Teensy

[Teensy 3.2](https://www.pjrc.com/store/teensy32.html) [hardware]

[Teensy 2.0](https://www.pjrc.com/store/teensy.html) [hardware]

Teensy USB docs:
[USB Serial](https://www.pjrc.com/teensy/td_serial.html),
[USB Keyboard](https://www.pjrc.com/teensy/td_keyboard.html),
[USB Mouse](https://www.pjrc.com/teensy/td_mouse.html),
[USB Joystick](https://www.pjrc.com/teensy/td_joystick.html),
[USB MIDI](https://www.pjrc.com/teensy/td_midi.html),
[USB Flight Sim](https://www.pjrc.com/teensy/td_flightsim.html)
[docs]

[Getting started with Teensy](https://spuder.wordpress.com/2010/10/21/getting-started-with-teensy-usb-rubber-ducky/) [article]

[2010: "Programmable HID USB Keystroke Dongle: Using the Teensy as a pen testing device"](https://www.irongeek.com/i.php?page=security/programmable-hid-usb-keystroke-dongle) [article]
[[slides](https://www.irongeek.com/downloads/defcon-phid.pdf)]

[cores: Teensy Core Libraries for Arduino](https://github.com/PaulStoffregen/cores) [github]

[Pateensy: Rubber Ducky–like payload for Teensy](https://github.com/Screetsec/Pateensy) [github]

[Brutal: Various payloads for Teensy](https://github.com/Screetsec/Brutal) [github]

[USBdriveby: DNS spoofer payload for Teensy](https://github.com/samyk/usbdriveby) [github]

[Kautilya: HID payloads for Teensy](https://github.com/samratashok/Kautilya) [github]


#### Digispark

[Digispark: Tiny, Arduino-enabled, USB development board](https://www.kickstarter.com/projects/digistump/digispark-the-tiny-arduino-enabled-usb-dev-board) [hardware]
[[aliexpress](https://aliexpress.com/w/wholesale-Digispark.html)]

[Configuring Digispark for Arduino IDE and upgrading bootloader](https://gist.github.com/Ircama/22707e938e9c8f169d9fe187797a2a2c) [article]

[Attiny85: Rubber Ducky payloads for Digispark ATtiny85](https://github.com/MTK911/Attiny85) [github]

[Duckyspark: Translator from USB Rubber Ducky payloads to Digispark code](https://github.com/toxydose/Duckyspark) [github]

[micronucleus: ATtiny USB bootloader with strong emphasis on bootloader compactness](https://github.com/micronucleus/micronucleus) [github]


#### CJMCU BadUSB

[CJMCU BadUSB](https://aliexpress.com/w/wholesale-CJMCU-BadUSB.html) [hardware]

[bad_ducky: Instructions for CJMCU BadUSB](https://github.com/mharjac/bad_ducky) [github]
[[wiki](https://github.com/mharjac/bad_ducky/wiki)]

[CJMCU_ATMEGA32U4_BADUSB: Guide on using DuckyScript with CJMCU BadUSB](https://github.com/asciiterminal/CJMCU_ATMEGA32U4_BADUSB) [github]


#### WiFi Duck

[Malduino](https://maltronics.com/collections/malduinos) [hardware]

[DSTIKE WiFi Duck](https://dstike.com/collections/frontpage/products/dstike-wifi-duck) [hardware]

[WiFiDuck: Wireless keystroke injection attack platform](https://github.com/SpacehuhnTech/WiFiDuck) [github]


### Sniffers and analyzers

(See also the [Facedancer Boards](#facedancer-boards) and [Linux Boards](#linux-boards) sections.)


#### USB

Beagle:
[USB 12](https://www.totalphase.com/products/beagle-usb12/),
[USB 480](https://www.totalphase.com/products/beagle-usb480/),
[USB 480 Ultimate](https://www.totalphase.com/products/beagle-usb480-power-ultimate/),
[USB 5000 v2 Ultimate](https://www.totalphase.com/products/beagle-usb5000-v2-ultimate/)
[hardware]

[OpenVizsla](http://openvizsla.org/) [hardware]
[[github](https://github.com/openvizsla/ov_ftdi)]
[[shop](https://shop.sysmocom.de/OpenVizsla-v3.x-USB-Protocol-Analyzer-PCBA/openvizsla-pcba-v3.4)]

[LambdaConcept USB2 SNIFFER](https://shop.lambdaconcept.com/home/35-usb2-sniffer.html) [hardware]

[PhyWhisperer-USB](https://www.crowdsupply.com/newae/phywhisperer-usb) [hardware]
[[github](https://github.com/newaetech/phywhispererusb)]

[Low-cost USB Sniffer](https://github.com/ataradov/usb-sniffer) [hardware]


#### USB Power Delivery

[Twinkie: USB-PD Sniffer](https://www.chromium.org/chromium-os/developer-library/guides/hardware-schematics/twinkie/) [hardware]

[Twonkie: USB-PD sniffer/injector/sink based on Twinkie](https://github.com/dojoe/Twonkie) [hardware]
[[shop](https://shop.3mdeb.com/shop/open-source-hardware/twonkie-usb-c-sniffer/)]

[twebkie: USB Power Delivery analyzer directly from web](https://chromium.googlesource.com/chromiumos/twebkie/) [github]

[usb.org: USB Power Delivery Compliance](https://www.usb.org/usbc#:~:text=download%20here.-,USB%20Power%20Delivery%20Compliance,-The%20USB%20PD) [hardware]


### Dedicated BadUSB

(Hardware developed specifically for BadUSB attacks and related tools.)

#### Rubber Ducky

[Rubber Ducky](https://shop.hak5.org/products/usb-rubber-ducky) [hardware]

https://docs.hak5.org/hak5-usb-rubber-ducky

https://github.com/hak5/usbrubberducky-payloads


#### Bash Bunny

[Bash Bunny](https://shop.hak5.org/products/bash-bunny) [hardware]

https://docs.hak5.org/bash-bunny

https://wiki.bashbunny.com/#!index.md

https://github.com/hak5/bashbunny-payloads

https://github.com/golem445/bunny_payloads


#### Cactus WHID

[Cactus WHID: Wi-Fi HID Injector — USB Rubber Ducky / BadUSB On Steroids](https://github.com/whid-injector/WHID) [hardware]

[WHID Elite: GSM-enabled Open-Source Multi-Purpose Offensive Device](https://github.com/whid-injector/whid-31337) [hardware]

[Cactus Micro Rev2](https://wiki.aprbrother.com/en/Cactus_Micro_Rev2.html) [hardware]

[ESPloitV2: Wi-Fi Keystroke Injection Tool designed for Cactus WHID](https://github.com/exploitagency/ESPloitV2) [github]


#### Flipper Zero

(Technically, not only for BadUSB.)

[Flipper Zero](https://flipperzero.one/) [hardware]

[Bad USB - Flipper Zero](https://docs.flipper.net/bad-usb) [docs]

[Flipper-Zero-BadUSB: Flipper Zero BadUSB payloads](https://github.com/I-Am-Jakoby/Flipper-Zero-BadUSB) [github]

[badusb: Flipper Zero BadUSB payload library](https://github.com/FalsePhilosopher/badusb) [github]


### Other BadUSB

[LAN Turtle](https://hak5.org/products/lan-turtle) [hardware]
[[docs](https://docs.hak5.org/lan-turtle)]
[[modules](https://github.com/hak5/lanturtle-modules)]

[rpk2: Evil Mass Storage](https://rootkit.es/buy_rpk2/) [hardware]
[[github](https://github.com/therealdreg/evilmass_at90usbkey2)]
[[article](https://web.archive.org/web/20211022034816/https://www.driverentry.com/node/104)]


### Malicious cables

[2020: "List of current USB cables with implants for keystroke injection attacks & more" by Marcus Mengs](https://x.com/mame82/status/1221093466463182849) [picture]

[O.MG Cable](https://o.mg.lol/) [hardware]
[[video review](https://www.youtube.com/watch?v=mPF9f-PLDPc)]
[[payloads](https://github.com/hak5/omg-payloads)]

[USBNinja](https://www.crowdsupply.com/rfid-research-group/usbninja) [hardware]

[Evil Crow Cable](https://github.com/joelsernamoreno/EvilCrow-Cable) [hardware]

[Evil Crow Cable Pro](https://github.com/joelsernamoreno/EvilCrowCable-Pro) [hardware]

[USBSamurai](https://infosecwriteups.com/usbsamurai-a-remotely-controlled-malicious-usb-hid-injecting-cable-for-less-than-10-ebf4b81e1d0b) [hardware]
[[article](https://infosecwriteups.com/usbsamurai-for-dummies-4bd47abf8f87)]

[AirDrive Forensic Keylogger Cable & Module](https://www.keelog.com/forensic-keylogger/) [hardware]

[KeyGrabber Forensic Keylogger Cable & Module](https://www.keelog.com/keygrabber-forensic/) [hardware]


### Keyloggers

AirDrive:
[Keylogger](https://www.keelog.com/hardware-keylogger/),
[Forensic Keylogger](https://www.keelog.com/airdrive-keylogger/)
[hardware]

KeyGrabber:
[Pico](https://www.keelog.com/keygrabber-pico/),
[USB](https://www.keelog.com/usb-keylogger/),
[TimeKeeper](https://www.keelog.com/timestamp-keylogger/),
[Forensic Keylogger](https://www.keelog.com/keygrabber-keylogger/)
[hardware]

[Forensic Keylogger Keyboard](https://www.keelog.com/keylogger-keyboard/) [hardware]

[Key Croc](https://shop.hak5.org/products/key-croc) [hardware]

[KEYVILBOARDs](https://www.tindie.com/stores/keyvilboard/) [hardware]

[Maltronics WiFi KeyLogger Internal](https://web.archive.org/web/20211023150651/https://maltronics.com/products/wifi-keylogger-internal) [hardware] [discontinued]


### Other hardware

[USB Killer](https://usbkill.com/) [hardware]

[Daisho: SuperSpeed USB 3.0 FPGA platform](https://greatscottgadgets.com/daisho/) [hardware]

[Tomu: An ARM board that fits inside your USB connector](https://www.crowdsupply.com/sutajio-kosagi/tomu) [hardware]

[USB 2.0 Hi-Speed Isolator](https://intona.eu/en/products/7054) [hardware]

[PortaPow blockers](https://portablepowersupplies.co.uk/) [hardware]

[USG](https://github.com/robertfisk/USG) [hardware]

[C2C caberQU: USB C cable tester](https://www.kickstarter.com/projects/electr/c2c-caberqu-usb-c-cable-tester) [hardware]


## Linux USB stack

kernel.org documentation:
[all](https://www.kernel.org/doc/Documentation/usb/),
[HTML index](https://www.kernel.org/doc/html/latest/usb/index.html),
[USB API](https://www.kernel.org/doc/html/latest/driver-api/usb/index.html)
[docs]

[linux-usb.org](http://www.linux-usb.org/) [docs]

[What actually happens when you plug in a USB device?](https://www.technovelty.org/linux/what-actually-happens-when-you-plug-in-a-usb-device.html) [article]

[Bootstrap Yourself with Linux-USB Stack: Design, Develop, Debug, and Validate Embedded USB](https://www.goodreads.com/book/show/11292815-bootstrap-yourself-with-linux-usb-stack) [book]

[2009: "Linux USB drivers" by Michael Opdenacker](https://bootlin.com/doc/legacy/linux-usb/linux-usb.pdf) [slides]

[2018: "USB System Design in Sitara Devices Using Linux: Debug USB in Linux" by Bin Liu](https://www.ti.com/content/dam/videos/external-videos/en-us/3/3816841626001/5771584353001.mp4/subassets/USB-M7-Debug-USB-in-Linux.pdf) [slides]

[2020: "USB General Guide Linux v3.8"](https://docs.google.com/viewer?url=https://processors.wiki.ti.com/index.php/USB_General_Guide_Linux_v3.8) [article]


### usbmon

[kernel.org: usbmon](https://www.kernel.org/doc/html/latest/usb/usbmon.html) [docs]

[Ubuntu wiki: Debugging USB Problems](https://wiki.ubuntu.com/Kernel/Debugging/USB) [article]

[How to install Wireshak on Linux and capture USB traffic?](https://stackoverflow.com/questions/31054437/how-to-install-wireshak-on-linux-and-capture-usb-traffic) [stackoverflow]


### Gadget subsystem

kernel.org documentation:
[all](https://www.kernel.org/doc/Documentation/usb/),
[HTML index](https://www.kernel.org/doc/html/latest/usb/index.html),
[USB Gadget API for Linux](https://www.kernel.org/doc/html/latest/driver-api/usb/gadget.html)
[docs]

[linux-usb.org: USB Testing on Linux](http://www.linux-usb.org/usbtest/) [docs]

[linux-usb.org: Linux-USB Gadget API Framework](http://www.linux-usb.org/gadget/):
[usb.c](http://www.linux-usb.org/gadget/usb.c),
[usbstring.c](http://www.linux-usb.org/gadget/usbstring.c),
[usbstring.h](http://www.linux-usb.org/gadget/usbstring.h)
[docs and examples]

[2010: "The USB composite framework" by Michal Nazarewicz](https://lwn.net/Articles/395712/) [article]

[2014: "Make your own USB gadget: Kernel and userspace"](https://events.static.linuxfound.org/sites/events/files/slides/LinuxConNA-Make-your-own-USB-gadget-Andrzej.Pietrasiewicz.pdf) [slides]

[2014: "Kernel USB Gadget Configfs Interface" by Amit Pundir](https://elinux.org/images/e/ef/USB_Gadget_Configfs_API_0.pdf) [slides]

[2015: "ConfigFS Gadgets: An Introduction" by Amit Pundir](https://static.linaro.org/connect/sfo15/Presentations/09-23-Wednesday/SFO15-311-%20ConfigFS%20Gadgets-%20An%20Introduction.pdf) [slides]

[2016: "Create your own USB gadget with GadgetFS" by Gregory Soutade](https://blog.soutade.fr/post/2016/07/create-your-own-usb-gadget-with-gadgetfs.html) [article]

[2018: "USB System Design in Sitara Devices Using Linux: Use USB in Device Mode" by Bin Liu](https://www.ti.com/content/dam/videos/external-videos/en-us/3/3816841626001/5771561603001.mp4/subassets/USB-M6-USB-in-Device-Mode.pdf) [slides]

[2019: "Modern USB gadget on Linux & how to integrate it with systemd" by Andrzej Pietrasiewicz](https://www.collabora.com/news-and-blog/blog/2019/02/18/modern-usb-gadget-on-linux-and-how-to-integrate-it-with-systemd-part-1/) [article]
[[part 2](https://www.collabora.com/news-and-blog/blog/2019/03/27/modern-usb-gadget-on-linux-and-how-to-integrate-it-with-systemd-part-2/)]
[[video](https://www.youtube.com/watch?v=3aNlLec9YqY)]

[2019: "Using dummy-hcd to play with USB gadgets" by Andrzej Pietrasiewicz](https://www.collabora.com/news-and-blog/blog/2019/06/24/using-dummy-hcd/) [article]

[2020: "Modern USB Gadget with Custom USB Functions" by Andrzej Pietrasiewicz](https://ostconf.com/system/attachments/files/000/001/708/original/Andrzej_Pietrasiewicz_LinuxPiter-2019.pdf) [slides]
[[video](https://www.youtube.com/watch?v=mQYh4xYG5a4)]

[2021: "USB On-The-Go (OTG)"](https://trac.gateworks.com/wiki/linux/OTG) [article]

[2023: "A tour of USB Device Controller (UDC) in Linux" by Herve Codina](https://bootlin.com/pub/conferences/2023/eoss/codina-a-tour-of-usb-device-controller/codina-a-tour-of-usb-device-controller.pdf) [slides]
[[video](https://www.youtube.com/watch?v=LJuE2RhfgnA)]

[2023: "Test a Linux kernel USB Device Controller driver with testusb" by Herve Codina](https://bootlin.com/blog/test-a-linux-kernel-usb-device-controller-driver-with-testusb/) [article]

[2024: "A comprehensive list of all ConfigFS, FunctionFS, USB Gadget API, etc. tools and libraries on Github"](https://www.reddit.com/r/linux/comments/1annx0u/a_comprehensive_list_of_all_configfs_functionfs/) [article]

[libusbgx: New USB Gadget ConfigFS Library](https://github.com/linux-usb-gadgets/libusbgx) [github]

[libusbg: Old USB Gadget ConfigFS Library](https://github.com/libusbg/libusbg) [github]

[gt: Command-line tool for creating USB gadgets via ConfigFS](https://github.com/linux-usb-gadgets/gt) [github]

[ptp-gadget: FunctionFS-based gadget that implement PTP (Picture Transfer Protocol)](https://github.com/linux-usb-gadgets/ptp-gadget) [github]

[gadgetd: System-wide USB gadgets and FunctionFS based services manager](https://github.com/gadgetd/gadgetd) [github]
[[motivation](https://github.com/gadgetd/gadgetd/wiki/Motivation)]

[libusb-gadget: Simple wrapper library to access GadgetFS](https://github.com/ueno/libusb-gadget) [github]

[keyboard-gadget: Simple HID keyboard gadget via ConfigFS](https://github.com/qlyoung/keyboard-gadget) [github]


#### Raw Gadget

[raw-gadget: Low-level interface for the Linux USB Gadget subsystem](https://github.com/xairy/raw-gadget)

[usb-proxy: USB proxy based on Raw Gadget and libusb](https://github.com/AristoChen/usb-proxy) [github]

[2022: "Fuzzing USB with Raw Gadget" by Andrey Konovalov](https://docs.google.com/presentation/d/1sArf2cN5tAOaovlaL3KBPNDjYOk8P6tRrzfkclsbO_c/edit?usp=sharing) [slides]
[[video](https://www.youtube.com/watch?v=AT3PQjKxa_c)]


## Tools

(Assorted tools that don't belong to any of the sections above.)

[libusb: Cross-platform library to access USB devices](https://github.com/libusb/libusb) [github]

[usbipd-win: USB/IP for Windows](https://github.com/dorssel/usbipd-win) [github]

[ViewSB: Open-source USB analyzer toolkit for variety of capture hardware](https://github.com/greatscottgadgets/ViewSB) [github]

[usbrip: Simple CLI forensics tool for tracking USB events on GNU/Linux](https://github.com/snovvcrash/usbrip) [github]

[hidviz: Tool for in-depth analysis of USB HID devices communication](https://github.com/hidviz/hidviz) [github]

[vusb-analyzer: Virtual USB Analyzer](https://github.com/a-sf-mirror/vusb-analyzer) [github]
[[sourceforge](https://vusb-analyzer.sourceforge.net/)]

[usb-device-fuzzing: Some tools for testing USB devices](https://github.com/ollseg/usb-device-fuzzing) [github]

[usbguard: Software framework for implementing USB device authorization policies](https://github.com/USBGuard/usbguard) [github]

[usb-canary: Linux/OSX tool that uses psutil to monitor devices while your computer is locked](https://github.com/errbufferoverfl/usb-canary) [github]

[usbkill: Anti-forensic kill-switch that waits for change on USB ports and then immediately shuts down computer](https://github.com/hephaest0s/usbkill) [github]

[uhubctl: USB hub per-port power control](https://github.com/mvp/uhubctl) [github]

[hub-ctrl.c: Control USB power on port by port basis on some USB hubs](https://github.com/codazoda/hub-ctrl.c) [github]

[webcam-tools: Update of the UVC webcam tools](https://github.com/cshorler/webcam-tools) [github]

[USBDescriptorKitchen: USB Descriptor creation and maintainance tool](https://github.com/zonque/USBDescriptorKitchen) [github]

[usbwall: Control LDAP users access to USB devices](https://github.com/Turanic/usbwall) [github]

[usbrply: Replay USB messages from Wireshark (.cap) files](https://github.com/JohnDMcMaster/usbrply) [github]

[ukip: USB Keystroke Injection Protection](https://github.com/google/ukip) [github]

[UDEFuzz: Windows USB drivers fuzzing using UDE technology](https://github.com/0x123456789/UDEFuzz) [github]

[usbsas: Tool and framework for securely reading untrusted USB mass storage devices](https://github.com/cea-sec/usbsas) [github]

[virtual-fido: Virtual FIDO2 USB Device](https://github.com/bulwarkid/virtual-fido) [github]

[LOGITacker: Tool to enumerate and test vulnerabilities of Logitech Wireless Input devices via RF](https://github.com/RoganDawes/LOGITacker) [github]
[[branch](https://github.com/RoganDawes/LOGITacker/blob/USB_host_enum/fingerprint_os.md)]

[python-usb-protocol: USB Protocol Library for Python](https://github.com/greatscottgadgets/python-usb-protocol)

[Psychson: Phison 2251-03 (2303) Custom Firmware & Existing Firmware Patches (BadUSB)](https://github.com/brandonlw/Psychson) [github]
[[article](https://vivibit.net/psychson2307final-en/)]

[MTPwn: PoC exploit for arbitrary file read/write in locked Samsung Android device via MTP (SVE-2017-10086)](https://github.com/smeso/MTPwn) [github]

[usb_cdc: Single/Multi-channel Full Speed USB interface for FPGA and ASIC designs](https://github.com/ulixxe/usb_cdc) [github]


## Research

[2024: "iOS: a journey in the USB networking stack" by Florian Le Minoux](https://www.synacktiv.com/publications/ios-a-journey-in-the-usb-networking-stack) [article]

[2023: "Automotive USB Fuzzing" by Euntae Jang et al.](https://www.youtube.com/watch?v=W_vQ5s1bB30) [video]

[2023: "Physical Attacks Against Smartphones" by Christopher Wade](https://media.defcon.org/DEF%20CON%2031/DEF%20CON%2031%20presentations/Christopher%20Wade%20-%20Physical%20Attacks%20Against%20Smartphones.pdf) [slides]
[[video](https://www.youtube.com/watch?v=31xrNuH1RV4)]

[2023: "Intel BIOS Advisory – Memory Corruption in HID Drivers"](https://research.nccgroup.com/2023/08/08/intel-bios-advisory-memory-corruption-in-hid-drivers/) [article]

[2023: "REUnziP: Re-Exploiting Huawei Recovery With FaultyUSB" by Lorant Szabo](https://labs.taszk.io/articles/post/reunzip/) [article]

[2023: "Hardware investigation of wireless keyloggers" by Antoine Cervoise](https://www.synacktiv.com/en/publications/hardware-investigation-of-wireless-keyloggers.html) [article]

[2023: "The Impostor Among US(B): Off-Path Injection Attacks on USB Communications" by Robert Dumitru et al.](https://www.usenix.org/conference/usenixsecurity23/presentation/dumitru) [paper]
[[code](https://github.com/0xADE1A1DE/USB-Injection)]

[2022: "Exploiting the Wii U's USB Descriptor parsing"](https://garyodernichts.blogspot.com/2022/06/exploiting-wii-us-usb-descriptor-parsing.html) [article]

[2022: "Hacking Some More Secure USB Flash Drives" by Matthias Deeg](https://blog.syss.com/posts/hacking-usb-flash-drives-part-1/) [article]
[[part 2](https://blog.syss.com/posts/hacking-usb-flash-drives-part-2/)]

[2022: "Keystroke Reflection: Inside a Side-Channel Exfiltration Technique"](https://cdn.shopify.com/s/files/1/0068/2142/files/hak5-whitepaper-keystroke-reflection.pdf) [article]

[2022: "Breaking Secure Boot on Google Nest Hub (2nd Gen) to run Ubuntu" by Frederic Basse](https://fredericb.info/2022/06/breaking-secure-boot-on-google-nest-hub-2nd-gen-to-run-ubuntu.html) [article]

[2022: "PrIntFuzz: Fuzzing Linux Drivers via Automated Virtual Device Simulation" by Zheyu Ma et al.](https://dl.acm.org/doi/pdf/10.1145/3533767.3534226) [paper]

[2022: "FUZZUSB: Hybrid Stateful Fuzzing of USB Gadget Stacks" by Kyungtae Kim et al.](https://lifeasageek.github.io/papers/kyungtae-fuzzusb.pdf) [paper]

[2022: "CVE-2021-45608 | NetUSB RCE Flaw in Millions of End User Routers" by Max Van Amernngen](https://www.sentinelone.com/labs/cve-2021-45608-netusb-rce-flaw-in-millions-of-end-user-routers/) [article]

[2021: "Achieving Linux Kernel Code Execution Through a Malicious USB Device" by Martijn Bogaard and Dana Geist](https://i.blackhat.com/EU-21/Thursday/EU-21-Bogaard-Geist-Achieving-Linux-Kernel-Code-Execution-Through-A-Malicious-USB-Device.pdf) [slides]

[2020: "Cheating in eSports: How to cheat at virtual cycling using USB hacks" by Brad Dixon](https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20presentations/DEFCON-27-Brad-Dixon-Cheating-in-eSports-How-to-cheat-at-virtual-cycling-using-USB-hacks.compressed.pdf) [slides]
[[video](https://www.youtube.com/watch?v=pq9t0VEIMio)

[2020: "A file system for safely interacting with untrusted USB flash drives" by Ke Zhong et al.](https://www.usenix.org/conference/hotstorage20/presentation/zhong) [paper]

[2020: "USBFuzz: A Framework for Fuzzing USB Drivers by Device Emulation" by Hui Peng and Mathias Payer](https://www.usenix.org/conference/usenixsecurity20/presentation/peng) [paper]

[2019: "Making USB Accessible: Developing Ultra-low-cost, Open USB Tools"](https://greatscottgadgets.com/slides/making-usb-accessible-teardown-2019.pdf) [slides]
[[video](https://greatscottgadgets.com/2019/06-26-making-usb-accessible-teardown-2019/)]

[2019: "BadUSB in Routers"](https://docs.google.com/viewer?url=https://github.com/tenable/router_badusb/raw/master/slides.pdf) [slides] [[github](https://github.com/tenable/router_badusb)]

[2019: "eyeDisk. Hacking the unhackable. Again"](https://www.pentestpartners.com/security-blog/eyedisk-hacking-the-unhackable-again/) [article]

[2019: "Coverage-Guided USB Fuzzing with Syzkaller" by Andrey Konovalov](https://docs.google.com/presentation/d/1z-giB9kom17Lk21YEjmceiNUVYeI6yIaG5_gZ3vKC-M/edit) [slides]
[[video](https://www.youtube.com/watch?v=1MD5JV6LfxA)]
[[docs](https://github.com/google/syzkaller/blob/master/docs/linux/external_fuzzing_usb.md)]
[[related](https://github.com/google/syzkaller/blob/master/docs/linux/external_fuzzing_usbip.md)]

[2019: "USB Fuzzing: A USB Perspective" by Dave Jing Tian](https://davejingtian.org/2019/07/17/usb-fuzzing-a-usb-perspective/) [article]

[2019: "Simple AV Evasion Symantec and P4wnP1 USB"](https://initroot.me/advance-av-evasion-symantec-and-p4wnp1-usb) [article]

[2019: "Hacking microcontroller firmware through a USB"](https://securelist.com/hacking-microcontroller-firmware-through-a-usb/89919/) [article]

[2019: "Virtual Media Vulnerability in BMC Opens Servers to Remote Attack"](https://eclypsium.com/2019/09/03/usbanywhere-bmc-vulnerability-opens-servers-to-remote-attack/) [article]
[[github](https://github.com/eclypsium/USBAnywhere)]

[2019: "Command Injection With USB Peripherals" by Danny Rosseau](https://carvesystems.com/news/command-injection-with-usb-peripherals/) [article]

[2019: "DeviceVeil: Robust Authentication for Individual USB Devices Using Physical Unclonable Functions" by Kuniyasu Suzaki et al.](https://users.encs.concordia.ca/home/m/mmannan/publications/DeviceVeil-dsn2019.pdf) [paper]

[2019: "Technical analysis of the checkm8 exploit"](https://habr.com/en/companies/dsec/articles/472762/) [article]

[2018: "ATtention Spanned: Comprehensive Vulnerability Analysis of AT Commands Within the Android Ecosystem"](https://www.usenix.org/conference/usenixsecurity18/presentation/tian) [paper]

[2018: "USB Hub Bug Hunting & Lessons Learned"](https://www.pjrc.com/usb-hub-bug-hunting-lessons-learned/) [article]

[2018: "Tick Group Weaponized Secure USB Drives to Target Air-Gapped Critical Systems"](https://researchcenter.paloaltonetworks.com/2018/06/unit42-tick-group-weaponized-secure-usb-drives-target-air-gapped-critical-systems/) [article]

[2018: "Discovering and Plotting Hidden Networks created with USB Devices"](https://www.exploit-db.com/docs/english/44947-discovering-and-plotting-hidden-networks-created-with-usb-devices.pdf) [paper]

[2018: "Advanced USB key phishing"](https://blog.sevagas.com/?Advanced-USB-key-phishing) [article]

[2018: "Android: directory traversal over USB via injection in blkid output"](https://bugs.chromium.org/p/project-zero/issues/detail?id=1583) [article]

[2018: "Opening Black Box Systems with GreatFET+FD"](https://greatscottgadgets.com/slides/TR18_AR_RE-Black-Box-Systems-GreatFET-Facedancer.pdf) [slides]

[2018: "Preventing USB Attacks with linux-hardened"](https://blog.lizzie.io/preventing-usb-attacks-with-linux-hardened.html) [article]

[2018: "Here's a List of 29 Different Types of USB Attacks" by Catalin Cimpanu](https://www.bleepingcomputer.com/news/security/heres-a-list-of-29-different-types-of-usb-attacks/) [article]

[2018: "Massive scale usb device driver fuzz without device"](https://www.slideshare.net/mobile/MSbluehat/bluehat-v18-massive-scale-usb-device-driver-fuzz-without-device) [slides]

[2018: "OATmeal on the Universal Cereal Bus: Exploiting Android phones over USB"](https://googleprojectzero.blogspot.com/2018/09/oatmeal-on-universal-cereal-bus.html) [article]

[2018: "Oh No, Where's FIDO? - A Journey into Novel Web-Technology and U2F Exploitation"](https://www.youtube.com/watch?v=pUa6nWWTO4o) [video]

[2018: "SoK: “Plug & Pray” Today – Understanding USB Insecurity in Versions 1 through C" by Dave (Jing) Tian et al.](https://par.nsf.gov/servlets/purl/10085547) [paper]

[2017: "USB Snooping Made Easy: Crosstalk Leakage Attacks on USB Hubs" by Yang Su et al.](https://www.usenix.org/conference/usenixsecurity17/technical-sessions/presentation/su) [paper]

[2017: "USBGuard: authorization for USB" by Nur Hussein](https://lwn.net/Articles/738306/) [article]

[2017: "POTUS: Probing Off-The-Shelf USB Drivers with Symbolic Fault Injection" by James Patrick-Evans et al.](https://www.usenix.org/conference/woot17/workshop-program/presentation/patrick-evans) [paper]

[2017: "Exploiting USB/IP in Linux" by Ignat Korchagin](https://www.blackhat.com/docs/asia-17/materials/asia-17-Korchagin-Exploiting-USBIP-In-Linux.pdf) [slides]

[2017: "FirmUSB: Vetting USB Device Firmware using Domain Informed Symbolic Execution"](https://arxiv.org/pdf/1708.09114.pdf) [paper]

[2016: "Understand USB (in Linux)" by Opasiak Krzysztof](https://elinux.org/images/a/aa/Understand_USB_in_Linux_Opasiak_Krzysztof.pdf) [slides]

[2016: "Preventing USB Attacks with Grsecurity"](https://blog.lizzie.io/preventing-usb-attacks-with-grsecurity.html) [article]

[2016: "Making USB Great Again with USBFILTER"](https://www.usenix.org/conference/usenixsecurity16/technical-sessions/presentation/tian) [paper]

[2016: "A Monitor Darkly: Reversing and Exploiting Ubiquitous OSD Controllers" by Ang Cui](https://redballoonsecurity.com/presentation/DEFCON24_A_Monitor_Darkly.pdf) [slides]
[[video](https://www.youtube.com/watch?v=zvP2FEfOSsk)]
[[code](https://github.com/RedBalloonShenanigans/MonitorDarkly)]

[2016: "IRON-HID: Create Your Own Bad USB Device" by Seunghun Han](https://archive.conference.hitb.org/hitbsecconf2016ams/sessions/iron-hid-create-your-own-bad-usb-device/) [paper]
[[code](https://github.com/kkamagui/IRON-HID)]

[2016: "Universal Serial aBUSe: Remote Physical Access Attacks" by Rogan Dawes and Dominic White](https://media.defcon.org/DEF%20CON%2024/DEF%20CON%2024%20presentations/DEF%20CON%2024%20-%20Rogan-Dawes-Dominic-White-Universal-Serial-aBUSe-Remote-Attacks.pdf) [slides]
[[video](https://www.youtube.com/watch?v=QLEpwra_9o8)]
[[article](https://sensepost.com/blog/2016/universal-serial-abuse/)]
[[code](https://github.com/sensepost/USaBUSe)]

[2016: "CVE-2016-2384: exploiting a double-free in the usb-midi linux kernel driver" by Andrey Konovalov](https://xairy.github.io/blog/2016/cve-2016-2384) [article]

[2015: "USB Attack to Decrypt Wi Fi Communications" by Jeremy Dorrough](https://media.defcon.org/DEF%20CON%2023/DEF%20CON%2023%20presentations/DEFCON-23-Jeremy-Dorrough-USB-Attack-to-Decrypt-Wi-Fi-Communications.pdf)
[[video](https://www.youtube.com/watch?v=UWOxzfRUwis)]

[2015: "Introduction to USB and Fuzzing" by Matt DuHarte](https://github.com/CryptoMonkey/Conference-Presentations/blob/master/Defcon%2023%20(2015)%20-%20Introduction%20to%20USB%20and%20Fuzzing/Matt%20DuHarte%20-%20HHV%20-%20Introduction%20to%20USB%20and%20Fuzzing.pdf)
[[video](https://www.youtube.com/watch?v=KWOTXypBt4E)]

[2015: "Don't Trust Your USB! How to Find Bugs in USB Device Drivers" by Sergej Schumilo et al.](https://www.blackhat.com/docs/eu-14/materials/eu-14-Schumilo-Dont-Trust-Your-USB-How-To-Find-Bugs-In-USB-Device-Drivers.pdf)
[[paper](https://www.blackhat.com/docs/eu-14/materials/eu-14-Schumilo-Dont-Trust-Your-USB-How-To-Find-Bugs-In-USB-Device-Drivers-wp.pdf)]
[[video](https://www.youtube.com/watch?v=OAbzN8k6Am4)]
[[github](https://github.com/schumilo/vUSBf)]

[2015: "Defending Against Malicious USB Firmware with GoodUSB"](https://www.cise.ufl.edu/~butler/pubs/acsac15.pdf) [paper]

[2015: "USB - An Attack Surface of Emerging Importance"](https://tubdok.tub.tuhh.de/bitstream/11420/1286/1/USB%20-%20An%20Attack%20Surface%20of%20Emerging%20Importance.pdf) [thesis]

[2014: "BadUSB - On Accessories that Turn Evil" by Karsten Nohl and Jakob Lell](https://assets-global.website-files.com/6098eeb4f4b0288367fbb639/62bc77a987dd057cc3e28599_SRLabs-BadUSB-Pacsec-v2.pdf)
[[video](https://www.youtube.com/watch?v=nuruzFqMgIw)]
[[wiki](https://opensource.srlabs.de/projects/badusb/wiki)]

[2014: "USB Attacks Need Physical Access Right? Not Any More..." by Andy Davis](https://www.blackhat.com/docs/asia-14/materials/Davis/Asia-14-Davis-USB-Attacks-Need-Physical-Access-Right-Not-Any-More.pdf)
[[video](https://www.youtube.com/watch?v=90MIjgh5ESU)]

[2014: "USB for All!!1" by Jesse Michael and Mickey Shkatov](https://www.defcon.org/images/defcon-22/dc-22-presentations/Michael-Shkatov/DEFCON-22-Jesse-Michael-Mickey-Shkatov-USB-for-All!!-UPDATED.pdf) [slides]

[2014: "Mouse Trap: Exploiting Firmware Updates in USB Peripherals" by Jacob Maskiewicz et al.](https://www.usenix.org/conference/woot14/workshop-program/presentation/maskiewicz) [paper]

[2014: "Lowering the USB Fuzzing Barrier by Transparent Two-Way Emulation" by Rijnard van Tonder and Herman Engelbrecht](https://www.usenix.org/conference/woot14/workshop-program/presentation/van-tonder) [paper]

[2014: "Implementing an USB Host Driver Fuzzer" by Daniel Mende](https://www.troopers.de/media/filer_public/66/27/6627d987-0de1-4e1a-97a1-9acaa696253f/troopers14-implementing_an_usb_host_driver_fuzzer-daniel_mende.pdf) [slides]

[2014: "HubCap: pwning the ChromeCast"](https://fail0verflow.com/blog/2014/hubcap-chromecast-root-pt1/) [article]

[2014: "USB connection vulnerabilities on Android smartphones" by Andre Fernando Lopes Pereira](https://repositorio-aberto.up.pt/bitstream/10216/76109/2/32399.pdf) [thesis]

[2013: "iSeeYou: Disabling the MacBook Webcam Indicator LED"](https://jscholarship.library.jhu.edu/bitstream/handle/1774.2/36569/camera.pdf) [paper]

[2012: "Fuzzing the USB in your devices" by Olle Segerdahl](https://olle.nxs.se/software/usbdevfuzz/fuzzing-usb-devices.pdf) [slides]

[2011: "USB Fuzzing for the Masses"](https://labs.withsecure.com/publications/usb-fuzzing-for-the-masses) [article]

[2011: "USB Security Challenges" by Joanna Rutkowska](https://blog.invisiblethings.org/2011/05/31/usb-security-challenges.html) [article]

[2011: "Exploiting USB Devices with Arduino"](https://media.blackhat.com/bh-us-11/Ose/BH_US_11_Ose_Exploiting_USB_Devices_WP.pdf) [article]

[2009: "USB Attacks: Fun with Plug and 0wn" by Rafael Dominguez Vega](https://www.defcon.org/images/defcon-17/dc-17-presentations/defcon-17-rafael_vega-usb_attacks.pdf) [slides]

[2009: "USB Device Drivers: A Stepping Stone into your Kernel" by Moritz Jodeit and Martin Johns](http://jodeit.org/research/DeepSec2009_USB_Device_Drivers.pdf) [slides]


## Misc

[USB Complete: Everything You Need to Develop USB Peripherals](https://www.goodreads.com/book/show/122692.USB_Complete) [book]

[Attacks via physical access to USB (DMA...?)](https://security.stackexchange.com/questions/118854/attacks-via-physical-access-to-usb-dma) [stackexchange]

[Can webcams be turned on without the indicator light?](https://security.stackexchange.com/questions/6758/can-webcams-be-turned-on-without-the-indicator-light) [stackexchange]

[Turning off the blue status LED on the logitech C920 usb camera?](https://raspberrypi.stackexchange.com/questions/43118/turning-off-the-blue-status-led-on-the-logitech-c920-usb-camera) [stackexchange]

[USB 3.x SS enumeration](https://electronics.stackexchange.com/questions/297031/usb-3-x-ss-enumeration/297373#297373) [stackexchange]

[Wikipedia: Juice jacking](https://en.wikipedia.org/wiki/Juice_jacking) [article]

[2024: "Unlocking secret ThinkPad functionality for emulating USB devices" by Andrey Konovalov](https://xairy.io/articles/thinkpad-xdci) [article]

[2024: "Adding a USB Port to the ThinkPad X1 Nano (the Hard Way)" by Joshua Stein](https://jcs.org/2024/05/29/x1usb) [article]

[2024: Clearing up misinformation about USB-C](https://x.com/_MG_/status/1797461630437241318) [thread]

[2024: "Making USB devices - end to end guide to your first gadget" by Uros Popovic](https://popovicu.com/posts/making-usb-devices/) [article]

[2024: Why USB hubs suck by Michael Ossmann](https://mastodon.social/@mossmann/112514231563904529) [tweet]

[2024: Reading Apple HID flash over USB](https://x.com/marcnewlin/status/1771568442564309151) [tweet]

[2024: "Evolution of UNC4990: Uncovering USB Malware's Hidden Depths" by Diana Ion et al.](https://cloud.google.com/blog/topics/threat-intelligence/unc4990-evolution-usb-malware/) [article]

[2023: "Getting JTAG on the iPhone 15" by Thomas Roth](https://www.youtube.com/watch?v=D8UGlvBubkA) [video]

[2023: "See the minimum needed for a USB device to list in Device Manager"](https://www.youtube.com/watch?v=VG5bWzEPfsg) [video]

[2023: "Driver adventures for a 1999 webcam" by Ben Cox](https://blog.benjojo.co.uk/post/quickcam-usb-userspace-driver) [article]
[[code](https://github.com/benjojo/qc-usb-userspace)]

[2022: "Tech Stuff - USB and Firewire"](http://www.zytrax.com/tech/pc/serial.html) [article]

[2022: "USB: Reverse Engineering and Writing Drivers"](https://www.youtube.com/watch?v=is9wVOKeIjQ) [video]

[2022: "All About USB-C: Introduction For Hackers" by Arya Voronova](https://hackaday.com/2022/12/06/usb-c-introduction-for-hackers/) [article]

[2022: "Illegal USB Type-C" by Sergey Korablin](https://brs.im/weird-usb-type-c/) [article]

[2022: "A Chip To Bridge The USB 2 – USB 3 Divide" by Arya Voronova](https://hackaday.com/2022/03/07/a-chip-to-address-the-fundamental-usb-3-0-deficiency/) [article]

[2021: "USB On-The-Go (OTG) Basics"](https://www.cypress.com/file/44851/download) [article]

[2021: "USB-C Cable Colour Codes (alpha)"](https://sa.lj.am/usbccccc/) [article]

[2021: "How does USB device discovery work?" by Ben Eater](https://www.youtube.com/watch?v=N0O5Uwc3C0o)

[2021: "How does a USB keyboard work?" by Ben Eater](https://www.youtube.com/watch?v=wdgULBpRoXk)

[2021: "How does n-key rollover work?" by Ben Eater](https://www.youtube.com/watch?v=2lPzTU-3ONI)

[2020: "Reverse Engineering Firmware (in Mice)"](https://8051enthusiast.github.io/2020/04/14/001-USB_Firmware.html) [article]
[[part 2](https://8051enthusiast.github.io/2020/04/14/002-Sensor_Firmware.html)]
[[part 3](https://8051enthusiast.github.io/2020/04/14/003-Stream_Video_From_Mouse.html)]

[2020: "USB Type-C is Coming: 3 Things You’ve Just Gotta Know"](https://web.archive.org/web/20201020204043/https://www.diodes.com/design/support/technical-articles/pericoms-articles/usb-type-c-is-coming-3-things-youve-just-gotta-know/) [article] [archive]

[2020: "USB3: why it's a bit harder than USB2" by Kate Temkin](https://lab.ktemkin.com/post/why-is-usb3-harder/) [article]

[2020: "Would You Exchange Your Security for a Gift Card?"](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/would-you-exchange-your-security-for-a-gift-card/) [article]

[2020: "USB PHY on FPGA" by Andrew Strokov](https://docs.google.com/viewer?url=https://github.com/glitchcore/usbproxy/releases/download/1/USB.PHY.on.FPGA.pdf) [slides]
[[code](https://github.com/glitchcore/usbproxy)]

[2019: "Now how many USB-C™ to USB-C™ cables are there?" by Benson Leung](https://people.kernel.org/bleung/now-how-many-usb-c-to-usb-c-cables-are-there-usb4-update-september-12) [article]

[2019: "Reverse Engineering USB Devices with Kate Temkin and Mikaela Szekely"](https://unnamedre.com/episode/25) [podcast]

[2019: "Writing userspace USB drivers for abandoned devices" by Ben Cox](https://blog.benjojo.co.uk/post/userspace-usb-drivers) [article]
[[code](https://github.com/benjojo/userspace-vga2usb/)]

[2019: Making Pioneer DDJ-RB USB audio work on Linux](https://www.youtube.com/watch?v=cUVuTBH51GY)
[[part 2](https://www.youtube.com/watch?v=nevJHGFx0yA)]

[2018: "Understanding HID report descriptors"](https://who-t.blogspot.com/2018/12/understanding-hid-report-descriptors.html) [article]

[2016: "Alternate Mode for USB Type-C: Going beyond USB"](http://www.ti.com/lit/wp/slly021/slly021.pdf) [article]

[2013: "What is the difference between /dev/ttyUSB and /dev/ttyACM?" by Samuel Tardieu](https://rfc1149.net/blog/2013/03/05/what-is-the-difference-between-devttyusbx-and-devttyacmx/) [article]

[2008: "USB Made Simple: A Series of Articles on USB"](http://www.usbmadesimple.co.uk/index.html) [articles]
