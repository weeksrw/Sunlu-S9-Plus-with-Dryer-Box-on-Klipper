# How to reinstall Marlin if needed
## Using Xloader on Windows
Use [Xloader](https://github.com/binaryupdates/xLoader) to transfer the firmware [Marlin.ino.hex](https://3dsunlu.com/en/NewsList/10.html) file to the printer over a USB cable.

**_Open Xloader_**  
**Hex file:**  Point to the hex file that you downloaded from the Sunlu website.  
**Device:**  Mega(ATMEGA2560)  
**COM port:**  It is probably not COM1.  Unplug the printer USB cable and look at the list of COM ports, then plug in the printer and see what new COM port has appeared. Use that one.  
**Baud rate:** 115200  (250000 did not work for me)

## Using avrdude on Linux 
_Thanks to ropelletier for this information._  
( Can be done directly from your connected raspberry pi )   
* Install avrdude
