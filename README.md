# SUNLU S9 PLUS WITH DRYBOX CONFIGURATION FILES

The [printer.cfg](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/printer.cfg) file is currently functional on my Sunlu S9 Plus.  It contains the pin mappings for the SUNLU S9 Plus including the Drybox. 

This printer uses an AVR atmega2560 16MHz chip and is a Ramps v1.0 board. To use this config, the Klipper firmware should be compiled for the AVR atmega2560. 
You can flash it over USB using kiauh. [Instructions on how to create and load the Klipper firmware for the S9 are here](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/blob/main/How%20to%20build%20the%20firmware.md).

The S9 LCD uses a DWIN 480xRGBx272 DMG48270C043_03WTR but it is not supported by Klipper so you will not be able to use the LCD display.  However you can setup a KlipperScreen on another device.  See below.

I chose to use an old desktop computer (or laptop) running Mint or Ubuntu rather than purchase a Raspberry Pi and I used an old android device for the KlipperScreen.  I did the upgrade for $0.  See below.

This is still a work in progress but I wanted to get the printer.cfg file up here so people can have access to it.

# SUNLU S9 PLUS DRYER BOX
The heater on the connected Dryer Box works well, however the humidity sensor is not configured correctly.
If you can get the humidity sensor working, please share.
The funtionality to run the Drybox, however, is present.
You can add a `SET_HEATER_TEMPERATURE HEATER=drybox TARGET=50` (or whatever temp you want)
to your Machine Start G-code and `SET_HEATER_TEMPERATURE HEATER=drybox TARGET=0` to the end g-code to automatically activate the Dryer Box.

# SOME EXTRAS
I found this post to be VERY HELPFUL (finally) in making the pin mappings. https://reprap.org/forum/read.php?13,837190  
The Marlin souce code is available at https://3dsunlu.com/en/NewsList/10.html  

Here is a picture of the S9 motherboard.  
![image](https://github.com/weeksrw/Sunlu-S9-Plus-with-Dryer-Box-on-Klipper/assets/166277940/a2d88f45-0b8a-4060-86cc-89763b9a97ca)

## How to use an old computer instead of a Raspberry Pi as host
more to come

## How to use an old android device as a KlipperScreen
more to come

## Direct Drive
In case you haven't seen it yet, you can easily change your S9 Plus Bowden filament feed into a Direct Drive feed for free.  It's pretty cool. [Check out this 3D print.](https://cults3d.com/en/3d-model/tool/support-direct-drive-sunlu-s9)
You will need to extend the wires for both the extruder and filament detector by 15-18 inches (38-45 cm) and then feed them both through the gantry wire loom. The size of the new filament tube is 80 mm.

## Christian Vick's Klipper Macros
more to come

## GerGO PRINT 3D's Gantry Leveling Macro
more to come
