# x220-coreboot-image-and-guide
My personal ThinkPad X220 coreboot image and installation guide. 
This repository is mainly intended as a way for me to document my personal coreboot efforts for later reference. With that, it may be helpful to other people looking to coreboot their ThinkPad X220.

# References
This guide is heavily based on michaelmob's guide and Tyler Cipriani's guide. These guides may have more details concerning any issues you encounter. As previously mentioned I am writing this guide mainly for myself and the resources I used for corebooting. Regardless, Enjoy!

# Items needed
- Thinkpad X220
- Raspberry Pi (Any model works fine, I used a Model 3 B V 1.2)
- 8-pin soic-clip
- 6 Female to Female jumper cables
- Philips head screwdriver

# Understanding How Corebooting Works
In short, coreboot is free and open-source software that can be compiled and used as an alternative to your computer's default BIOS. For laptops with older model Intel processors this software also allows for the Intel Management Engine to be stripped from you system. For someone interested in technology and privacy this is a relatively small step you can take to securing your personal technology while learning more about your computer. To learn more about coreboot, the systems it supports, and personal computing privacy check out the coreboot webpage.

# Preparing to coreboot
The big difference between my guide and the ones I referenced is where I compiled my coreboot image. Those guides have you set up all of the software to compile a coreboot image on the raspberry pi itself. This is extremely time-consuming given the strength of rapsberry pi's. In my process, I will be compiling the image on a separate image, and use the pi as a tool only for flashing.

# Laptop Disassembly: Accessing the BIOS chip 
Before disassembly of any system make sure it is unplugged and that the battery is removed. 
Unscrew the seven screws on the bottom of your X220 used to hold down the keyboard and palm rest. 
After unscrewing, flip your X220 over and remove the keyboard and palm rest. 
After removing the keyboard and palm rest peel back the corner of the black protective plastic to find the BIOS chip we will be flashing.
