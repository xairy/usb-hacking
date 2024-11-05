# Demos

Snippets for some of the demos.

## Common setup

``` bash
sudo apt install python3-venv
python3 -m venv p3env
source p3env/bin/activate

pip install wheel

sudo apt-get install python-dev python3-dev
```


## Part 1: USB 101

### Sniffing USB with usbmon

Based on [kernel.org/doc/Documentation/usb/usbmon.txt](https://www.kernel.org/doc/Documentation/usb/usbmon.txt).

``` bash
mount -t debugfs none /sys/kernel/debug/
modprobe usbmon
cat /sys/kernel/debug/usb/usbmon/0u
cat /dev/usbmon0 | xxd
```

### Sniffing USB via usbmon with wireshark

Follow [How to install Wireshak on Linux and capture USB traffic?](https://stackoverflow.com/questions/31054437/how-to-install-wireshak-on-linux-and-capture-usb-traffic).

```
# Wireshark filter to see Control transfers
usb.transfer_type == 2
```

### Sending USB control messages to a hub with USB PPPS support

``` bash
git clone https://github.com/mvp/uhubctl
sudo apt-get install libusb-1.0-0-dev
make
```

``` bash
$ cat /etc/udev/rules.d/98-hub.rules 
SUBSYSTEM=="usb", ATTR{idVendor}=="05e3", ATTR{idProduct}=="0608", MODE="0664", GROUP="plugdev"
$ sudo udevadm control --reload-rules
; replug hub
```

### Sending USB control messages to a Logitech web camera

Based on [Turning off the blue status LED on the logitech C920 usb camera?](https://raspberrypi.stackexchange.com/questions/43118/turning-off-the-blue-status-led-on-the-logitech-c920-usb-camera).

``` bash
sudo apt-get install uvcdynctrl cheese
cheese &
sudo uvcdynctrl -i /usr/share/uvcdynctrl/data/046d/logitech.xml
sudo uvcdynctrl -s 'LED1 Mode' 0
```

## Part 3: Linux USB subsystem

`ctrl.py`:

``` python
#!/usr/bin/env python3

import array
import binascii
import sys
import time

import usb.core
import usb.util

VENDOR_ID = 0x046d
PRODUCT_ID = 0xc077

dev = usb.core.find(idVendor=VENDOR_ID, idProduct=PRODUCT_ID)

if dev is None:
	raise ValueError('Device not found')

def log(write, bRequest, wValue, wIndex, msg, e):
	print('%s, request = 0x%02x, value = 0x%02x, index = 0x%02x' % \
		('write' if write else 'read', bRequest, wValue, wIndex))
	if msg:
		if write:
			print(' => success: %d' % (msg,))
		else:
			print(' => success: %d' % (len(msg),))
			print('   ', binascii.hexlify(msg))
	if e:
		print(' => %s' % (str(e),))

write = False
bmRequestType = usb.util.CTRL_TYPE_STANDARD | \
		usb.util.CTRL_RECIPIENT_DEVICE | \
		(usb.util.CTRL_OUT if write else usb.util.CTRL_IN)
bRequest = 0x6  # Get Descriptor
wValue = 0x100  # Device Descriptor
wIndex = 0x0
wLength = 18

try:
	msg = dev.ctrl_transfer(bmRequestType=bmRequestType, bRequest=bRequest,
				wValue=wValue, wIndex=wIndex,
				data_or_wLength=wLength)
	log(write, bRequest, wValue, wIndex, msg, None)
except usb.core.USBError as e:
	log(write, bRequest, wValue, wIndex, None, e)
```

``` bash
./ctrl.py
strace ./ctrl.py
```


## Part 4: BadUSB

### Rubber Ducky

``` bash
wget https://github.com/hak5darren/USB-Rubber-Ducky/raw/master/duckencoder.jar
java -jar duckencoder.jar -i payload.txt -o inject.bin
# copy inject.bin to SD card
```

```
DELAY 1000
CTRL-ALT t
DELAY 1000
STRING echo pwned!
ENTER
```

### Bash Bunny

https://github.com/hak5/bashbunny-payloads/tree/master/payloads/library/recon/LinuxInfoGrabber

```
...
#RUN UNITY xterm
Q CTRL-ALT t
...
Q STRING export bunnydir=/media/\$USER/BashBunny
Q ENTER
...
Q STRING sync
Q ENTER
Q STRING umount \$bunnydir
Q ENTER
Q STRING exit
Q ENTER
```

https://github.com/hak5/bashbunny-payloads/tree/master/payloads/library/phishing/Captiveportal

### ATtiny85 board

Based on [1$ Rubber Ducky – Hack any PC within seconds MR.Robot style using Attiny85](http://www.khromozome.com/rubber-ducky-hack-pc-within-seconds-mr-robot-style-attiny85/).

1. Download and install [Arduino IDE](https://www.arduino.cc/en/Main/Software).
2. Follow [Connecting and Programming Your Digispark](http://digistump.com/wiki/digispark/tutorials/connecting).
3. Don't forget to add the [udev rule](https://github.com/micronucleus/micronucleus/wiki/Ubuntu-Linux).
4. Select Tools -> Programmer -> USBtinyISP.
5. Select Tools -> Board -> Digispark (default).
6. Select File -> Examples -> DigisparkKeyboard -> Keyboard.
7. Upload (plug in the device after you press the Upload button in Arduino IDE).
8. Run.

### CJMCU BadUSB

Based on [bad_ducky/wiki/Getting-Started](https://github.com/mharjac/bad_ducky/wiki/Getting-Started).

Format SD card as FAT32 and put `payload.txt` on it:

```
DELAY 1000
CTRL ALT t
DELAY 1000
STRING echo pwned!
ENTER
```

1. Download and install [Arduino IDE](https://www.arduino.cc/en/Main/Software).
2. Clone [bad_ducky](https://github.com/mharjac/bad_ducky) and open `bad_ducky.ino` in Arduino IDE.
3. Select Tools -> Board -> Arduino Leonardo.
4. Select Tools -> Port - > ttyACM0 (choose the right one).
5. Select Tools -> Programmer -> AVRISP mkII.
6. Upload.
7. Select Tools -> Serial Monitor.
8. Input mode: `a`.
9. Input language: `en`.
10. Input payload: `PAYLOAD.TXT`.
11. Replug the board.

### Cactus WHID

Based on [github.com/whid-injector/WHID](https://github.com/whid-injector/WHID).

1. Plug in Cactus WHID.
2. Connect to WiFi network `Exploit` with password `DotAgency`.
3. Go to http://192.168.1.1/duckuino.
4. Enter payload, convert to ESPloit format and copy.
5. Go to http://192.168.1.1/livepayload.
6. Paste and run payload.

### Teensy 3.2

Based on [Getting started with Teensy](https://spuder.wordpress.com/2010/10/21/getting-started-with-teensy-usb-rubber-ducky/).

1. Download and install [Arduino IDE](https://www.arduino.cc/en/Main/Software).
2. Download and install [Teensyduino](https://www.pjrc.com/teensy/td_download.html).
3. Run Arduino IDE.
4. Select Tools -> Board -> Teensy 3.2 / 3.1.
5. Select Tools -> USB Type -> Keyboard.
6. Select File -> Examples -> Teensy ->  USB_Keyboard -> Simple.
7. Upload and run.

Note: LED pin is pin #13 on Teensy 3.2.


## Part 5: Facedancer

### Emulating USB keyboard with Facedancer

``` bash
pip install greatfet pyserial
git clone https://github.com/greatscottgadgets/Facedancer
cd Facedancer
pip install .
```

#### Facedancer21

To flash: https://github.com/travisgoodspeed/goodfet#firmware

``` bash
BACKEND=goodfet ./legacy-applets/facedancer-keyboard-interactive.py
```

#### GreatFET One

``` bash
BACKEND=greatfet ./legacy-applets/facedancer-keyboard-interactive.py
```

### USB reconnaissance

#### Facedancer21

Device driver scanning:

``` bash
git clone https://github.com/nccgroup/umap2.git
cd ./umap2/
pip install .
umap2scan -P fd:/dev/ttyUSB0
```

OS fingerprinting:

``` bash
git clone https://github.com/nccgroup/umap.git
cd ./umap/
python umap.py -P /dev/ttyUSB0 -O
```


## Part 6: Linux USB Gadget subsystem

### Raspberry Pi Zero

#### Setup

``` bash
echo "dtoverlay=dwc2" | sudo tee -a /boot/config.txt
echo "dwc2" | sudo tee -a /etc/modules
sync
reboot
```

#### Emulating mass storage device through `g_mass_storage`

Based on [Raspberry Pi Zero OTG Mode](https://gist.github.com/gbaman/50b6cca61dd1c3f88f41).

``` bash
dd if=/dev/zero of=image.bin bs=512 count=2880
mkdosfs ./image.bin
mkdir mnt
sudo mount ./image.bin ./mnt -o loop
echo hi | sudo tee ./mnt/file
sudo umount ./mnt
sudo modprobe g_mass_storage file=./image.bin stall=0
sudo modprobe -r g_mass_storage
```

#### Emulating keyboard with ConfigFS

Based on [RaspberryPiZero_HID_MultiTool](https://github.com/darrylburke/RaspberryPiZero_HID_MultiTool/blob/master/gadget/hid/mkdevice.sh) and [Linux USB HID gadget driver](https://www.kernel.org/doc/Documentation/usb/gadget_hid.txt).

``` bash
./start.sh
ls /dev/hidg0
gcc hid_gadget_test.c -o hid
./hid /dev/hidg0 keyboard
./stop.sh
```

`start.sh`:
``` bash
#!/bin/bash

set -eux

modprobe libcomposite

mkdir -p /sys/kernel/config/usb_gadget/my_gadget
cd /sys/kernel/config/usb_gadget/my_gadget

echo 0x1d6b > idVendor # Linux Foundation
echo 0x0104 > idProduct # Multifunction Composite Gadget
echo 0x0100 > bcdDevice # v1.0.0
echo 0x0200 > bcdUSB # USB2
echo 0xEF > bDeviceClass
echo 0x02 > bDeviceSubClass
echo 0x01 > bDeviceProtocol

mkdir -p strings/0x409
echo "fedcba9876543210" > strings/0x409/serialnumber
echo "wtfwasthat" > strings/0x409/manufacturer
echo "Linux USB Device" > strings/0x409/product
mkdir -p configs/c.1/strings/0x409

echo "Config 1: ECM network" > configs/c.1/strings/0x409/configuration
echo 250 > configs/c.1/MaxPower

mkdir -p functions/hid.usb0
echo 1 > functions/hid.usb0/protocol
echo 1 > functions/hid.usb0/subclass
echo 8 > functions/hid.usb0/report_length
echo -ne "\\x05\\x01\\x09\\x06\\xA1\\x01\\x05\\x07\\x19\\xE0\\x29\\xE7\\x15\
\\x00\\x25\\x01\\x75\\x01\\x95\\x08\\x81\\x02\\x95\\x01\\x75\\x08\\x81\\x03\
\\x95\\x05\\x75\\x01\\x05\\x08\\x19\\x01\\x29\\x05\\x91\\x02\\x95\\x01\\x75\
\\x03\\x91\\x03\\x95\\x06\\x75\\x08\\x15\\x00\\x25\\x65\\x05\\x07\\x19\\x00\
\\x29\\x65\\x81\\x00\\xC0" > functions/hid.usb0/report_desc
ln -s functions/hid.usb0 configs/c.1/

ls /sys/class/udc > UDC
```

`stop.sh`:
``` bash
#!/bin/bash

set -eux

cd /sys/kernel/config/usb_gadget/my_gadget

echo "" > UDC

rmdir configs/c.1/strings/0x409/
rmdir strings/0x409/
rm configs/c.1/hid.usb0
rmdir configs/c.1/
rmdir functions/hid.usb0/
cd ..
rmdir my_gadget/

modprobe -r usb_f_hid
modprobe -r libcomposite
```

#### Emulating a simple device through GadgetFS

Based on [Create your own USB gadget with GadgetFS](http://blog.soutade.fr/post/2016/07/create-your-own-usb-gadget-with-gadgetfs.html).

``` bash
mkdir /dev/gadget
mount -t gadgetfs gadgetfs /dev/gadget
```

Get sources from the article linked above.

Patch `USB_DEV`:

``` c
#define USB_DEV "/dev/gadget/20980000.usb"
```

``` bash
gcc -g -o usb device.c -lpthread
./usb
umount /dev/gadget
modprobe -r gadgetfs
```


## Part 7: USB fuzzing

### Fuzzing USB with Facedancer21

``` bash
mkdir sandbox && cd sandbox/
umap2stages -P fd:/dev/ttyUSB0 -C keyboard -s keyboard.stages
umap2kitty -s keyboard.stages &
umap2fuzz -P fd:/dev/ttyUSB0 -C keyboard
```

### vUSBf

``` bash
sudo apt-get install qemu-system-x86 qemu-kvm qemu-utils
git clone https://github.com/schumilo/vUSBf.git
mkdir workdir
...
```


## Part 8

### Sniffing USB with USBProxy on BeagleBone Black

Get a shell on the BBB following [this](http://blog.tonywall.com/2013/11/beaglebone-black-serial-debug-connection/).

(Note: to boot from micro-SD card hold the button when applying power.)

#### Preimaged

Get the image from [USBProxy releases](https://github.com/dominicgs/USBProxy/releases/) and flash onto an SD card.

Boot BBB, build USBProxy, run `sudo ./usb-mitm -l`.

#### Rebuild image

https://beagleboard.org/latest-images

http://gimx.fr/wiki/index.php?title=Bbb_sniffer

https://github.com/dominicgs/USBProxy/tree/master/doc

https://github.com/dominicgs/USBProxy/issues/50

### Sniffing USB with USBProxy 'Nouveau' with GreatFET One

https://github.com/usb-tools/Facedancer.git

``` bash
pip install greatfet pyserial
git clone https://github.com/greatscottgadgets/Facedancer.git
cd Facedancer
pip install .
# BACKEND=greatfet ./legacy-applets/facedancer-keyboard-interactive.py
BACKEND=greatfet ./facedancer-usbproxy.py -v 046d -p c077
```

### Sniffing USB with OpenVizsla

https://github.com/openvizsla/ov_ftdi#getting-started

``` bash
sudo apt-get install libusb-1.0-0-dev
pip3 install crcmod
```

```
diff --git a/software/host/fastftdi.c b/software/host/fastftdi.c
index c2bb6ab..398af7c 100644
--- a/software/host/fastftdi.c
+++ b/software/host/fastftdi.c
@@ -97,7 +97,7 @@ FTDIDevice_Open(FTDIDevice *dev)
     return err;
   }
 
-  libusb_set_option(dev->libusb, LIBUSB_OPTION_LOG_LEVEL, 2);
+  // libusb_set_option(dev->libusb, LIBUSB_OPTION_LOG_LEVEL, 2);
 
   dev->handle = libusb_open_device_with_vid_pid(dev->libusb,
                                                OV_VENDOR,
```

``` bash
./software/host/ovctl.py sniff ls
```

### Sniffing USB with OpenVizsla and ViewSB

https://github.com/usb-tools/ViewSB

https://github.com/usb-tools/pyopenvizsla

``` bash
git clone https://github.com/usb-tools/pyopenvizsla.git
pip install -r ./requirements.txt
pip install .
```

```
diff --git a/libov/fastftdi.c b/libov/fastftdi.c
index c2bb6ab..398af7c 100644
--- a/libov/fastftdi.c
+++ b/libov/fastftdi.c
@@ -97,7 +97,7 @@ FTDIDevice_Open(FTDIDevice *dev)
     return err;
   }
 
-  libusb_set_option(dev->libusb, LIBUSB_OPTION_LOG_LEVEL, 2);
+  // libusb_set_option(dev->libusb, LIBUSB_OPTION_LOG_LEVEL, 2);
 
   dev->handle = libusb_open_device_with_vid_pid(dev->libusb,
                                                OV_VENDOR,
```

``` bash
git clone https://github.com/usb-tools/ViewSB.git
git checkout 04048292ff0b1113b6cc5dbfe5744deaad50c402
pip install -r ./requirements.txt
./viewsb.sh openvizsla --speed=low
```

### Sniffing USB with USBProxy 'Nouveau'

``` bash
./facedancer-usbproxy.py -v 046d -p c077
```
