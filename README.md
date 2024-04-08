# SUNLU S9 PLUS WITH DRYBOX CONFIGURATION FILES

The `printer.cfg` file is currently functional on my Sunlu S9 Plus although only just.  It contains the pin mappings for the SUNLU S9 Plus including the Drybox. 

This printer uses an AVR atmega2560 16MHz chip and is a Ramps v1.0 board. To use this config, the firmware should be compiled for the AVR atmega2560. 
You can flash it over USB. Using kiauh: regular flashing method, make flash (default), USB.  More to come.

The S9 LCD uses a DWIN 480xRGBx272 DMG48270C043_03WTR but it is not supported by klipper so you will not be able to use the LCD display.  However you can setup a KlipperScreen on another device.  More to come.

I chose to use an old desktop computer (or laptop) running Mint or Ubuntu rather than purchase a Raspberry Pi and I used an old android device for the KlipperScreen.  I did the upgrade for $0.  More to come.

This is still a work in progress but I wanted to get the printer.cfg file up here so people can have access to it.

more to come. 

# SUNLU S9 PLUS DRYER BOX
The heater on the connected Dryer Box works well, however the humidity sensor is not configured correctly.
If you can get the humidity sensor working, please share.
The funtionality to run the Drybox, however, is present.
You can add a `SET_HEATER_TEMPERATURE HEATER=drybox TARGET=45` 
to your Machine Start G-code and `SET_HEATER_TEMPERATURE HEATER=drybox TARGET=0` to the end g-code to automatically activate the Dryer Box.

I found this post to be VERY HELPFUL in making the pin mappings. https://reprap.org/forum/read.php?13,837190 

The Marlin souce code is available at http://3dsunlu.com/en/NewsDetail/3912708.html
