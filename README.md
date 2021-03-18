# Logitech G203 Mouse LED controller for Windows

Avoid installing logitech mouse software just to turn off the bright LED on the mouse.

Based on [G203 LED for Linux](https://github.com/smasty/g203-led), but edited to work in Windows instead of Linux.

Essentially, I removed all usage of kernels from the script and added instructions for how to use Zadig usb.

## Installation

1) Install python
2) pip install pyusb
3) pip install libusb
4) Move libusb.dll file from "C:\Users\username\AppData\Roaming\Python\Python27\site-packages\libusb\_platform\_windows\x64\"
    to "C:\Windows\System32"
5) Install Zadig usb
6) In Zadig usb, install libusb-win32 driver for "interface 1" (LED interface) of mouse. Do not modify mouse "interface 1".
7) See usage for information on how to use the script.

## Usage

Note: Each time you want to make a modification to the LED control (one script run), you have to physically unplug and replug the mouse to update the driver.

For example, to completely turn off the LED.
1) Run: python mouse.py intro off
2) Unplug and replug mouse
3) Run: python mouse.py breathe 666666 60000 0
4) Unplug and replug mouse
5) Now the mouse LED should not turn on, regardless of what computer you plug it into.

## Todo

1) Automate plug and unplug process to avoid physical step.
