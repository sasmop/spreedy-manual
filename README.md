# spreedy-manual
## Material

### Lego MINDSTORMS EV3 

Buy your Lego MINDSTORMS EV3 robot through the [Official website](http://shop.lego.com/en-DE/LEGO-MINDSTORMS-EV3-31313) or e.g. via [Amazon](http://www.amazon.com/LEGO-6029291-Mindstorms-EV3-31313/dp/B00CWER3XY).

### ODROID-C1 

Buy your ODROID-C1 via [Hardkernel](http://www.hardkernel.com/main/products/prdt_info.php) and don't forget to buy an [USB-DC Plug Cable](http://www.hardkernel.com/main/products/prdt_info.php?g_code=G141637559827) (2.5x0.8mm). You need the cable to connect the ODROID to the USB power-bank. 

### USB power-bank

Buy a power- bank with a 1A-port and a 2A-port (e.g. made by [digibuddy] (http://www.amazon.de/digibuddy-Powerbank-11000mAh-Ladeger%C3%A4t-Smartphone-Wei%C3%9F-Grau/dp/B00M2TPNLS)).

### USB Camera

We recommend to buy the [Logitech C920 cam] (http://www.amazon.com/Logitech-Webcam-Widescreen-Calling-Recording/dp/B006JH8T3S) or a similar one. 

### Micro SD Cards

Buy two Micro SC Cards (e.g. via [Amazon] (http://www.amazon.com/b?node=3015433011)) for ODROID-C1 and EV3.

### USB wifi adapter

Last but not least you need an [USB wifi adapter] 
(http://www.bestbuy.com/site/networking/wireless-usb-adapters/abcat0503007.c?id=abcat0503007).

### Optional

USB power-adapter for Lego EV3 (see construction manual [here] (url))




## Build Lego robot

### Choose robot type

In general, the looks of your robot are chosen by yourself. However, it still has to meet some requirements. First of all it needs two large and separated motors which are indispensable for unfettered navigation. The power supply is accomplished by the PCB and USB power-bank.
The Lego models we recommend that fit the requirements are e.g. BOBB3E, KRAZ3 or EV3D4. For a better stability you can use caterpillar tracks or add a support wheel.

### Further requirements

The robot needs to be large enough to keep all extra components, namely the USB power-bank in the middle, the ODROID-C1 on the back and the camera on top. Just give it a burst until you find the best fitting construction. Make sure the EV3 brick display and controls are easily accessible as well as the PC plug on top. Plug in the USB cable to make sure in the beginning.
In case you decide for two wheels you will need a gyroscope. The gyroscope controls your balance and gives a signal when your bot is not upright. You can inactivate the gyroscope if you are using more than two wheels. 
You can also replace the detachable wheel with a movable ball whereby the bot can turn in every possible direction. 




## Add ODROID C-1

Integrate the ODROID into the prepared holder and make sure that the connectors are accessible. Especially look after the power supply connection cable. Make also sure that the ODROID can easily be removed or added again (of which more later). 
Connect the EV3 Brick through the USB cable with the ODROID-C1. Stow the remaining cable length within your robot. 

Install Ubuntu as well as WebRTC Publisher and WebRTC Bot on one of the SD cards.
The WebRTC Bot enables your bot to drive and accept commands via Spreed.ME chat. To add further features you need the WebRTC Publisher. It allows your bot to accept calls, audio and video transmission.

The additional installation of Chrome Extension facilitates the command feed and handling. The Chrome Extension recognizes the communication with the bot automatically and replaces the input field of the chat with control buttons. Moreover the pressed cursor is now able to conduct a command as long as you wish (the usual duration of a command is 20ms). 

To connect the robot with your computer and Spreed.ME you need a wifi stick. The webcam needs to be connected, too.




## Add USB power-bank

Due to its weight the USB power-bank containing the PCB should be put in the middle of the robot. Like this the robot stays balanced and doesn't fall easily, even with the power-bank. If you power-bank has an on button make sure it's accessible. This is the button to turn your robot on. Also make sure that the USB connector has enough space to be usable.
Now connect the ODROID C-1 USB-DC Plug Cable with the power-bank. Turn the power-bank on and see if the ODROID powers up (check the ODROIDs LEDs). 

Optional
In case you built the EV3 power-adapter connect it now with the other port of the power-bank. If you have decided to use batteries make sure they are easily replaceable. 




## Add camera

Mount the camera on the top of your robot. Choose the position carefully and use the cameras' weight to balance you robot. Choose the position carefully and use the camera weight to balance your robot. Make sure that it's fixed properly and does not fall off even when your robot looses balance. 
Now connect the USB cable of the camera to the ODROID-C1. The cables need to be fixed to your bot. Use the cameras' cable as a tie. 




## Software

### ODROID-C1

The ODROID runs Linux. You can put one of the images provided by [Hardkernel] (http://odroid.com/dokuwiki/doku.php?id=en:c1_release_linux_ubuntu) on the SD Card and make sure that the ODROID boots.

### EV3

The EV3 runs Linux as well. Prepare one of the micro SD cards with [ev3dev] (http://www.ev3dev.org/). You can't use the Lego software on the EV3 (SD card required) so make sure the EV3 boots into ev3dev. s. ANLEITUNG SD KARTEN REINSTEKCEN RICHTIG




## Configuration

### Tethering EV3 and ODROID-C1

The communication between ODROID and EV3 is based on the master/slave model. The ODROID has unidirectional control over the EV3. It provides networking to the EV3 through USB tethering. Therefore you need to enable USB tethering on the EV3 (see the documentation on the [website](http://www.ev3dev.org/docs/tutorials/using-bluetooth-tethering/)). Activate the USB Network for tethering on ODROID. Connect the EV3 to the ODROID by SSH ([Secure Shell](http://en.wikipedia.org/wiki/Secure_Shell)) and try to build a connection to the EV3 through the tethering network interface.
DO NOT CONTINUE UNTIL IT WORKS. The EV3 has no connection to any other device except through the ODROID.  

### Adding Proxy

Consequently the ODROID needs to provide Proxy to the EV3. 

### Advanced Packaging Tool

Add the ODROID Proxy into Apt configuration of the EV3. Check the Apt's internet access and install required tools on the EV3.

### Robot software

Install the bot software and dependencies on the ODROID.
Configure software. If the EV3 beeps it is ready for action and available in the Spreed.ME room you configured before.

### Communication

The Odroid C1 communicates with the EV3 via the EV3 bridge. The EV3 bridge is a software component which starts WebRTC Bot on the Odroid. The file ev3-bridge.py is currently included in the bots' index within the Chrome Extension. The transmitted command is evaluated and exploited by the EV3 receiver on the EV3. 
Most PCs and Macs have a x86_64 CPU architecture. The Odroids' is armhf. Therefore you need to translate the program code to the machine language (cross-compiling).




## Play

### Calls & webcam

Connect the bot to the configured server and Spreed.ME room. Make sure the bot has booted and make a call from your computer. If all went fine the bot will pick up and you see the cameras' picture. 

### Chat commands

By default the bot understands chat commands.




## Develop

### Add your own commands

Own commands can be added by python scripts.

### Modify software

Modify the bots' software for custom tasks and custom robots.
