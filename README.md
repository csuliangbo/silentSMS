SilentSMS
===

An Android-app that can send silent text messages and tell you if the other party received them (= the recipient phone is turned on). It uses reflection and has quite an ugly piece of code in it, but it works ;-). If you want to make it better, fork it and send me a pull request.

It also includes a little telnet-like service which could be used to send silent text messages from any device that can connect to your Android phone (your PC via USB tethering, your other Android device via WiFi tethering etc.). This feature is used for sending automated text messages together with the tmsi-buster tool creating an easy and automated way to uncover a phone number's TMSI.

This code is for educational purposes only, there is no warranty on it, nothing. The author is not responsible for how this code is being used. It's released under GPL (I would have used MIT license, but since there are some paid silent SMS apps I don't want anyone to pay for this code, so GPL it is). I haven't checked this code with anyone else yet, so I am going to say it is alpha quality code, a little bit better than a PoC. You have been warned ;-).

I would like to express my greatest gratitude to Vorex & Kaiyou from Virtualabs for creating ZeroSMS which is the base of SilentSMS. Also a shout out to dnet for creating nfcat which served as a base for the network-service part of the app.

How to install it?
===

1. You will need to turn off code signing on your phone (it is a security risk of course, but you can do it from the recovery menu) OR install Cyanogenmod ROM AND you will need ROOT access to your phone.

2. Download the APK file (signed or unsigned) and connect your phone to your PC

3. Activate USB storage mode and copy the APK over to your phone

4. Open up an adb shell

5. Enter the following commands:

```
shell@android:/ # su
shell@android:/ # mount -o rw,remount /system
shell@android:/ # cp /storage/sdcard0/SilentSMS-signed.apk /system/app/SilentSMS-signed.apk
shell@android:/ # reboot
```

Your phone will reboot and after it has started up you will see a new app in the menu called SilentSMS

How to remove it?
===
1. Open up an adb shell

2. Enter the following commands:

```
shell@android:/ # su
shell@android:/ # mount -o rw,remount /system
shell@android:/ # rm /system/app/SilentSMS-signed.apk
shell@android:/ # reboot
```

Troubleshooting
===

1. I can't see the app in the menu
You need to turn off code signing or use Cyanogenmod. If you use the signed APK on a ROM other than Cyanogenmod the app will simply not show up (because of incorrect signatures) or if you use the unsigned APK when code signing is enabled again the app will not show up (because of incorrect signatures)
