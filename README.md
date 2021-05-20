# x220-coreboot-image-and-guide
My personal ThinkPad X220 coreboot image and installation guide. 
This repository is mainly intended as a way for me to document my coreboot efforts for later reference. With that, it may be helpful to other people looking to coreboot their ThinkPad X220.

## References and Resources
This guide is heavily based on [michaelmob's guide](https://github.com/michaelmob/x220-coreboot-guide) and [Tyler Cipriani's guide](https://tylercipriani.com/blog/2016/11/13/coreboot-on-the-thinkpad-x220-with-a-raspberry-pi/). These guides may have more details concerning any issues you encounter.

### Other Helpful Resources:
- [coreboot documentation](https://doc.coreboot.org/)
- [Tripcode7's X220 coreboot video](https://www.youtube.com/watch?v=ExQKOtZhLBM)
- [coreboot subreddit](https://www.reddit.com/r/coreboot/)

## Items Needed
- Thinkpad X220
- Raspberry Pi (Any model works fine, I used a Model 3 B V 1.2)
- A seperate computer running Linux (Used for compiling)
- Internet connection
- [8 pin soic clip](https://www.pomonaelectronics.com/products/test-clips/soic-clip-8-pin)
- [6 Female to Female jumper cables](https://www.amazon.com/GenBasic-Piece-Female-Jumper-Wires/dp/B01L5ULRUA)
- Philips head screwdriver

## Understanding What Coreboot is
In short, coreboot is free and open-source software that allows for the compilation of a custom image computer's proprietary BIOS. For laptops with older model Intel processors this software also allows for the Intel Management Engine to be stripped from your system. For someone interested in technology and privacy this is a relatively small step you can take to securing your technology while learning more about your computer. To learn more about coreboot, the systems it supports, and personal computing privacy check out the [coreboot webpage](https://www.coreboot.org/).

## Pre-compilation Preparation
The big difference between my guide and the ones I referenced is where I compiled my coreboot image. Those guides have you set up all of the software to compile a coreboot image on the raspberry pi itself. This is extremely time-consuming given the strength of Rapsberry Pi's. Compilation on the Pi itself takes hours. In my process, I will be compiling the image on a separate computer, and use the pi as a tool only for flashing.

### Laptop Disassembly: Accessing the BIOS chip 
1. Before disassembly of any system make sure it is unplugged and that the battery is removed. 
2. Unscrew the seven screws on the bottom of your X220 used to hold down the keyboard and palm rest. 
3. After unscrewing, flip your X220 over and remove the keyboard and palm rest. 
4. After removing the keyboard and palm rest peel back the corner of the black protective plastic to find the BIOS chip we will be flashing.

A helpful video highlighting the specifics of disassembly: [X220 Teardown](https://www.youtube.com/watch?v=iJs01Q8EuDw) 

### Raspberry Pi Setup: Internet Connection, SPI, and SSH
1. Install the corresponding Raspbian (Raspberry Pi OS) image onto your pi. Graphical interface only really matters if you are planning on using your Pi for more. For this project you will need just the terminal and an internet connection. See the Raspberry Pi website for an [imaging guide](https://www.raspberrypi.org/documentation/installation/installing-images/).
2. If you haven't already during your installation and setup process make sure your Pi is connected to the internet, the proceeding steps will depend on an internet connection.
3. Enabling SPI is a crucial step, this will allow for use of the [GPIO](https://www.raspberrypi.org/documentation/usage/gpio/) pins on the top of your Pi.
```
sudo raspi-config

# Go to the "Interfacing Options Menu"
# Enable "SPI

# Optional: Enable SSH
# I was able to SSH without enabling SSH, but if you have issues enable SSH in the same menu

reboot
```
5. Update General Dependencies
```
sudo apt update && sudo apt upgrade
```
4. Install Flashrom
```
sudo apt install flashrom
```
### Installing Dependencies on A Seperate Computer
## Coreboot Compilation

## Flashing
