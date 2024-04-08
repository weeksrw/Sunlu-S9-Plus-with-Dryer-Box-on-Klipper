# How to use an old android device as a Klipper Screen
I followed this YouTube video.

[Use your old Android phone as a touchscreen for your 3D printer!](https://youtu.be/TcgTrkA8Oj0?si=0PBab_s7WIJYJUTM)
  
## Sources for the needed APK files
SourceForge for APK files for XServer:  
https://sourceforge.net/projects/libsdl-android/files/apk/XServer-XSDL/  

Or APKPure  
https://apkpure.com/xserver-xsdl/x.org.server/download/1.20.41  
https://apkpure.com/autostart-no-root/com.autostart  

I could not connect to APKMirror from a factory reset android device.  I also could not connect to the Play Store and had to side load the programs.
The video describes how to do it all.

## These are the instructions for the KlipperScreen install
https://klipperscreen.readthedocs.io/en/latest/Android/
1.	Install KlipperScreen on PC using KIAUH.SH
2.	Install XServer-XSDL on the Android device
3.	Choose USB(ADB) or WI-FI

## I had these problems:
The YouTube video got me 99% there but I had a couple of problems. Here are the solutions  
1. When I installed KlipperScreen on the PC, it booted directly to KlipperScreen instead of the desktop. To undo and go back to the desktop environment on the host machine:
`sudo systemctl set-default graphical.target && sudo reboot`
Here are the docs: https://klipperscreen.readthedocs.io/en/latest/Installation/#first-steps
2. Although the video did it correctly, I had some problems getting the android to connect. It was confusing because there are two ways to connect to the android Xserver XSDL,
either via USB (ADB) or WIFI which the video did not explain.
The information on the android bluescreen is for connecting via WIFI. If you use USB, you ignore the information on the android.  
Also confusing is when you look at the KlipperScreen/scripts directory,
there is a sample-android-adb.sh file and a sample-launch_klipperscreen.sh (lower case). Just follow the directions carefully to create the correct launch_KlipperScreen.sh (upper case) and it will work.
https://klipperscreen.readthedocs.io/en/latest/Android/



