up2-grovepi
=================

Based on scripts provided by [onandoffables](https://github.com/onandoffables/avrdude-linuxgpio) and modified to use the latest avrdude with x86 boards.

This repository provides scripts that install and patch avrdude to flash the grovePi+ shield with a Firmata sketch on RPi compatibles such as the UP2 board. Works with Ubilinux & Ubuntu.

Ensure your board has a working internet connection.

Clone this repository from github and run 'install_avrdude.sh':

    git clone https://github.com/intel-iot-devkit/up2-grovepi.git
    cd up2-grovepi
    ./install_avrdude.sh

Provide your password when asked for apt to install all the required dependencies.

Plug-in the GrovePi+ shield and ensure it is properly aligned with pin 1 (indicated by arrow) before pressing it down, otherwise it will cause the board to reset.
Run the following command to flash the Firmata sketch:

    avrdude -v -c linuxgpio -p m328p -U flash:w:firmata.hex

The red LED on the shield will turn on meaning it's held in reset. After flashing remove the shield and plug in a cross-over Grove 4 pin cable between the connectors labeled SERIAL and RPISER.
Plug the shield back in. You can now add the GrovePi+ shield as a subplatform from MRAA on "/dev/ttyS1".

For code examples using Firmata visit http://mraa.io.
