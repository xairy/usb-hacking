USB Hacking
===========

Materials for my "Introduction to USB hacking" talk and a [collection of USB hacking–related links](https://github.com/xairy/hardware-village/blob/master/LINKS.md).

Last iteration of the talk:

* [Online 2020](https://docs.google.com/presentation/d/1yeQigRsWQLko3TXNg8zsKT_45aHrcZgYhsKJvFc2yQk/edit?usp=sharing) [slides] [[video](https://www.youtube.com/watch?v=0bMxAdq1adc)]

Older iterations:

* [PHDays 2019](https://docs.google.com/presentation/d/1BP1wNSa0MvMdlZuRURw9VsWC198IgrtDFujgI2-2Fto/edit?usp=sharing) [slides] [[video](https://www.youtube.com/watch?v=lLQ55aW7uyw)]
* [Chaos Constructions 2018](https://docs.google.com/presentation/d/1C0Mfh9kcHQvqaLd6hbx6ilM_blYwg05YVW5rRS6Z8yQ/edit?usp=sharing) [slides]
* [PHDays 2018](https://docs.google.com/presentation/d/1S1yNeehSXOvtC_QmtqETSF3frlMLgka6v3XQVupJXTQ/edit?usp=sharing) [slides]
* [Chaos Constructions 2017](https://docs.google.com/presentation/d/1N_o5ghhXPZc48pWqQNkzzsiQUH1aINkzCiZrVWoHqcA/edit?usp=sharing) [slides]
* [ZeroNights 2016](https://docs.google.com/presentation/d/1w57rf1-LfP2h2cOeRdHqdmyFLfQiy9MpT3nI6HhMwSY/edit?usp=sharing) [slides]

Snippets for demos are [here](https://github.com/xairy/hardware-village/blob/master/usb/DEMOS.md).

Also see [xairy/dma-attacks](https://github.com/xairy/dma-attacks) for my "Introduction to PCIe and DMA attacks" talk.


## Hardware

Demonstrated during the talk.

[USB Kill](https://usbkill.com/) (90$)

[Rubber Ducky](https://hakshop.com/products/usb-rubber-ducky-deluxe) (45$)

[Bash Bunny](https://hakshop.com/products/bash-bunny) (100$)

[LAN Turtle](https://hakshop.com/products/lan-turtle) (55$)

[Digispark ATtiny85](https://www.aliexpress.com/item/Free-shipping-1pcs-Digispark-kickstarter-development-board-ATTINY85-module-for-Arduino-usb/32697283942.html) (1.3$)

[CJMCU BadUSB](https://www.aliexpress.com/item/CJMCU-virtual-Keyboard-Badusb-USB-TTF-memory-Keyboard-ATMEGA32U4-module/32817551271.html) (10$)

[Cactus WHID](https://www.aliexpress.com/item/Cactus-Micro-compatible-board-plus-WIFI-chip-esp8266-for-atmega32u4/32318391529.html) (16$)

[Cactus Micro Rev2](https://www.aliexpress.com/item/Cactus-Micro-Rev2-Pro-Micro-atmega32u4-WIFI-ESP8266-module-ESP-11-ESP-03/32804236925.html) (35$)

[Teensy 3.2](https://www.pjrc.com/store/teensy32.html) (20$)

[Facedancer21](http://goodfet.sourceforge.net/hardware/facedancer21/) (85$)

[GreatFET One](https://greatscottgadgets.com/greatfet/one/) (110$)

[Raspberry Pi Zero](https://www.raspberrypi.org/products/raspberry-pi-zero/) (5$)

[Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/) (10$)

[BeagleBone Black](https://beagleboard.org/black) (70$)

[Nexus 7 2013 (Wi-Fi) tablet](https://en.wikipedia.org/wiki/Nexus_7_(2013)) (150$)

[USB Armory](https://inversepath.com/usbarmory) (150$)

[EC3380-AB](http://www.bplus.com.tw/Adapter/EC3380-AB.html) (180$)

[OpenVizsla](http://openvizsla.org/) (140$)

[AirDrive Keylogger Max](http://www.keelog.com/hardware-keylogger/) (100$)

[Maltronics WiFi KeyLogger Internal](https://maltronics.com/products/wifi-keylogger-internal) (45$)


## Agenda

This is the full agenda, each iteration of the talk may cover different parts.

### Part 1: USB 101

* Follow [USB 101](http://www.cypress.com/file/134171/download)

#### Demos

1. Looking at syslog (`dmesg`) when a new USB device is connected.
2. Checking connected devices and their descriptors with `lsusb`.
3. Sniffing and decoding USB packets with a logic analyzer.
4. Sniffing USB via usbmon with wireshark.

### Part 2: USB attack surface

* Device -> host: electrical, firmware, kernel, logical
* Host -> device: firmware, android, ios
* Host -> device -> host: original BadUSB
* Remote: USB/IP, WebUSB, USBAnywhere

### Part 3: Linux USB subsystem

* Linux USB stack
* USB sysfs, usbfs
* libusb, pyusb

### Part 4: BadUSB

* BadUSB: consumer-ready vs self-designed
* BadUSB: microcontroller-based vs Facedancer vs Linux-based

#### Demos

Consumer-ready:

1. Rubber Ducky.
2. Bash Bunny.
3. Lan Turtle.

Microcontroller-based:

1. Teensy 3.2.
2. ATtiny55 board.
3. CJMCU BadUSB.
4. Cactus WHID.

### Part 5: Facedancer

* Facedacer software overview
* Facedancer21 and GreatFET One

#### Demos

1. Emulating USB keyboard with Facedancer.
2. USB reconnaissance with Facedancer.

### Part 6: Linux USB Gadget subsystem

* Linux USB Gadget subsystem
* Legacy Gadget Modules 
* USB Gadget ConfigFS
* GadgetFS
* Raw Gadget

#### Demos

1. Emulating mass storage drive through `g_mass_storage.ko` on Raspberry Pi Zero.
2. Emulating keyboard with ConfigFS on Raspberry Pi Zero.
3. Emulating keyboard through GadgetFS on Raspberry Pi Zero.
4. Emulating keyboard through Raw Gadget on Raspberry Pi Zero.
5. Emulating keyboard from an Android device.

### Part 7: USB fuzzing

* Fuzzing, hardware vs virtual
* vUSBf, QEMU and usbredir
* syzkaller, Raw Gadget and `dummy_hcd.ko`

#### Demos

1. Fuzzing USB with Facedancer.
2. Fuzzing USB with vUSBf.
3. Fuzzing USB with syzkaller.
4. Crashing a Linux machine via a bug in a USB driver.
5. Crashing a Windows machine via a bug in a USB driver.

### Part 8: USB sniffing

* Hardware vs software sniffers
* "Low-level" vs "high-level" sniffers
* Beagle analyzers
* USBProxy, USBProxy 'Nouveau'
* OpenVizsla
* Hardware keyloggers (AirDrive, Maltronics)

#### Demos

0. Sniffing with usbmon already demoed in part 1.
1. Sniffing with a logic analyzer already demoed in part 1.
2. Sniffing USB with USBProxy on BeagleBone Black.
3. Sniffing USB with USBProxy 'Nouveau' with Facedancer.
4. Sniffing USB with OpenVizsla.
5. Sniffing keyboard via AirDrive Keylogger.
