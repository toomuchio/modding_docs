Full credit to the modders at miui.vn, all I did was translate this and simpliy the steps

## Known Issues
* ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `Netflix is limited to SD since the device wont have valid a valid ESN for Widevine`
* ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `Casting doesn't currently work, but Airplay does`

## Requirements
* 19-AA Factory Image: https://www.androidfilehost.com/?fid=529152257862691887
* 16-AB Base Image: https://androidfilehost.com/?fid=961840155545569444
* -Whatever- the latest 16-AB flashable at the time of writing this https://xiaomi.eu/community/threads/xiaomi-mdz-16-ab-nougat-beta-download-source-build-1560-12-2017.42621
* Male to Male USB cord OR use 'WiFi ADB - Debug Over Air' (Far more risky if connection drops, but it does work)

## Restore to factory image with adb and root
* Extract the 19-AA image to a USB formatted with the default allocation FAT32, must be under 32GB in size
* Plug the USB
* Power the device off by removing the powercord
* While plugging the cord in press and hold the back and menu button until you see the flashing begin

## Applying 16-AB base image
* Attach the device to a PC with a male to male USB cord, or install WiFi ADB and use that
* From ADB run:
```
adb root
adb remount
adb push dump_16AB.img /sdcard/
adb shell dd if=/sdcard/dump_16AB.img of=/dev/block/mmcblk0
adb reboot recovery
```

## Flashing latest 16-AB
* Copy the latest 16-AB flashable to your USB, delete the 19-AA factory image files first
* Once in recovery either via adb reboot or by following the previous steps
* Select Apply update from EXT then pick udisk then select the flashable
* Select Wipe Data / Factory Restore then reboot and enjoy!
