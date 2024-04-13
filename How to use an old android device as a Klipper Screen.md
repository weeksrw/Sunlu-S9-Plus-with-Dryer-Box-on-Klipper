# How to use an old android device as a Klipper Screen
I followed this YouTube video.

[Use your old Android phone as a touchscreen for your 3D printer!](https://youtu.be/TcgTrkA8Oj0?si=0PBab_s7WIJYJUTM)  

Here are some other YouTube videos that may be helpful.  
[How to Run Klipper Screen on an Android Phone Connected to BigTreeTech's Manta M5P+CB1](https://www.youtube.com/watch?v=rdovXqrKivU)  

### Using devices other than an android  
[Touch Screen Remote For Your 3D Printer - Klipper Screen - Chris's Basement - 2024](https://www.youtube.com/watch?v=QCAFqK_juQs)  
[Pad 7 - Klipper Touch Screen - BigTreeTech - Chris's Basement - 2023](https://www.youtube.com/watch?v=72ia-LH4vXQ)  
[Multiple Klipper Instances on Pad7 or KlipperScreen](https://www.youtube.com/watch?v=Dxjh4iVUL-4)  
  
## Sources for the needed APK files
SourceForge for APK files for XServer:  
https://sourceforge.net/projects/libsdl-android/files/apk/XServer-XSDL/  

Or APKPure  
https://apkpure.com/xserver-xsdl/x.org.server/download/1.20.41  I needed 1.20.41 because my android was 4.2.2  
https://apkpure.com/autostart-no-root/com.autostart  

I could not connect to APKMirror from a factory reset android device.  I also could not connect to the Play Store and had to side load the programs.
The first video describes how to do it all.

## These are the instructions for the KlipperScreen install
https://klipperscreen.readthedocs.io/en/latest/Android/
1.	Install KlipperScreen on PC using KIAUH.SH
2.	Install XServer-XSDL on the Android device
3.	Choose USB(ADB) or WI-FI
    
  `sudo apt-get install android-tools-adb`  
  `cd ~/KlipperScreen/scripts`  
  `cp sample-android-adb.sh launch_KlipperScreen.sh`  
  `nano launch_KlipperScreen.sh`  
  ---  In my case, I changed the display to 6003: `adb forward tcp:6100 tcp:6003`  
  `chmod +x ~/KlipperScreen/scripts/launch_KlipperScreen.sh`  
  
## I had these problems:
The YouTube video got me 99% there but I had a couple of problems. Here are the solutions  
1. When I installed KlipperScreen on the PC, it booted directly to KlipperScreen instead of the desktop. To undo and go back to the desktop environment on the host machine:
`sudo systemctl set-default graphical.target && sudo reboot`
Here are the docs: https://klipperscreen.readthedocs.io/en/latest/Installation/#first-steps

2. I just had to reinstall my Mint machine and run through this whole process again and I have a few more comments. 
* First, MAKE SURE you have enabled SSH on your machine BEFORE you install KlipperScreen or you will be starting all over again. Ask me how I know ;(  
* Second, With the current (at least when I did it) KlipperScreen install, you must choose to install it as a service or not.
  1. If you choose not to install as a service, then the KlipperScreen will be startable from the Menu and does not start automatically.  It will be a window on your linux desktop.  Perhaps you could setup the adroid as a second linux screen and move the window there, but I haven't tried it, plus it would be a manual process.  One potentially interesting observation is that the KlipperScreen started in portrait mode.
  2. If you choose to install as a service, you need to choose X for Xserver. Then be ready with another machine via SSH already setup to quickly issue `sudo service KlipperScreen stop` or your machine will be blanking the screen and rebooting over and over (at least that's what happened for me).  With the service stopped, you can reset the display `sudo systemctl set-default graphical.target` and finish the adroid-adb setup.  

3. Although the video did it (almost) correctly, I had some problems getting the android to connect. It was confusing because there are two ways to connect to the android Xserver XSDL,
either via USB (ADB) or WIFI which the video did not explain.
The information on the android bluescreen is for connecting via WIFI. If you use USB, you ignore the information on the android (except maybe the screen number 6003).
`https://klipperscreen.readthedocs.io/en/latest/Android/`  
Also confusing is when you look at the `KlipperScreen/scripts` directory,
there is a `sample-android-adb.sh` file and a `sample-launch_klipperscreen.sh` (lower case). The latest KlipperScreen install is just a bit different from the video. You now edit `sample_android_adb.sh` and copy it into `launch_KlipperScreen.sh` (upper case). Just follow the directions carefully to create the correct `launch_KlipperScreen.sh` (upper case) and it will work.  In my case, I did edit the screen id to 6003 as described in the video.




