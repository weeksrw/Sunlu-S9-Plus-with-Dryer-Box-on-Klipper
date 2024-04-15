# SUNLU S9 PLUS WITH DRYBOX CONFIGURATION FILES

The [printer.cfg](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/printer.cfg) file is currently functional on my Sunlu S9 Plus.  It contains the pin mappings for the SUNLU S9 Plus including the Drybox. 

This printer uses an AVR atmega2560 16MHz chip and is a Ramps v1.0 board. To use this config, the Klipper firmware should be compiled for the AVR atmega2560. 
You can flash it over USB using kiauh. [Instructions on how to create and load the Klipper firmware for the S9 are here](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/How%20to%20build%20the%20firmware.md).

The S9 LCD uses a DWIN 480xRGBx272 DMG48270C043_03WTR but it is not supported by Klipper so you will not be able to use the LCD display. (If some smarter person and make it work, please share).  However you can setup a KlipperScreen on another device.  See below.

I chose to use an old desktop computer (or laptop) running Mint or Ubuntu rather than purchase a Raspberry Pi and I used an old android device for the KlipperScreen.  I did the upgrade for $0.  See below.

Well, unfortunately I made a mistake plugging in a zero documentation chinese junk usb front panel on my computer and the S9 motherboard is dead now. So I guess this is as far as I go for now on this project. The printer was working great on klipper and I was in the tuning process when I messed up.  I hope this info will be able to help someone.  Cheers.

# SUNLU S9 PLUS DRYER BOX
The heater on the connected Dryer Box works well, however the humidity sensor is not configured correctly.
If you can get the humidity sensor working, please share.
The funtionality to run the Drybox, however, is present. 
You can add a  
`SET_HEATER_TEMPERATURE HEATER=drybox TARGET=50` (or whatever temp you want)
to your Machine Start G-code and  
`SET_HEATER_TEMPERATURE HEATER=drybox TARGET=0` to the end g-code to automatically activate/deactivate the Dryer Box.

# SOME EXTRAS
* I found this post to be VERY HELPFUL (finally) in making the pin mappings. https://reprap.org/forum/read.php?13,837190  
* Here is my [mapping of the S9 Marlin pins to Klipper pins](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/S9%20Plus%20Pinouts.md).  
* The Marlin souce code is available at https://3dsunlu.com/en/NewsList/10.html  
* These are the [original S9 M503 values](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/Sunlu%20S9%20Plus%20original%20Marlin%20M503%20output.md) I downloaded from the printer via M503 before starting to make any changes.
* [Here are some macros](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/Idle%20Timeout%20Macros.md) that can keep the dryer box from shutting off too soon.

Here is a picture of the S9 motherboard.  
![image](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/assets/166277940/a2d88f45-0b8a-4060-86cc-89763b9a97ca)

## Direct Drive
In case you haven't seen it yet, you can easily change your S9 Plus Bowden filament feed into a Direct Drive feed for free.  It's pretty cool. [Check out this 3D print.](https://cults3d.com/en/3d-model/tool/support-direct-drive-sunlu-s9)
You will need to extend the wires for both the extruder and filament detector by 15-18 inches (38-45 cm) and then feed them both through the gantry wire loom. The new length of the filament tube is 80 mm.
Don't forget to change your retraction length.

## How to use an old computer instead of a Raspberry Pi as host
I used an old XP Windows machine as the Klipper host and it works great. In fact, you can run multiple printers off of just one computer depending on the capabilities of the machine.
[Here are the instructions that will guide you through the process](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/How%20to%20use%20an%20old%20computer%20as%20host.md).

## How to use an old android device as a KlipperScreen
I used a very old android tablet running version 4.2.2 that was pretty much useless but is really fantastic as a klipper screen.  
[Here is the information to implement it](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/How%20to%20use%20an%20old%20android%20device%20as%20a%20Klipper%20Screen.md).

## GerGO PRINT 3D's Gantry Leveling Macro
The Sunlu S9 uses two Z stepper motors but only has one driver. This means both stepper motors operate but they cannot be controlled individually. How do you guarantee that the gantry is actually level? If one of the steppers gets out of step or if a Z motor is manually turned, then the gantry can be crooked affecting your prints.  GerGO PRINT 3D has devised a macro that uses the bltouch to be able to test and level the gantry.  It is really helpful. If you download it, be sure to read my comment where I give the code fix required to use it on this machine. [Watch this video for more information](https://www.youtube.com/watch?v=1suV1QlMu0E). [This is the download](https://cults3d.com/en/3d-model/tool/z-markers-for-sovol-sv06-plus).

## Christian Vick's Klipper Macros
[Check out this video](https://www.youtube.com/watch?v=Xl8jR6yaWc8) talking about Adaptive Mesh. It is a way to speed up the bed mesh considerably.
