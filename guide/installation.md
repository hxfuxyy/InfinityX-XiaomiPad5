# InfinityX Installation Guide
> [!Warning]
> The provided instructions are for InfinityX running on Xiaomi Pad 5 (nabu). These will only work if you follow every section and step precisely.

## Pre-installation

Download the latest ROM file (referred to as InfinityX.zip) and support files (boot.img, vendor_boot.img and dtbo.img) in [```Releases```](https://github.com/hxfuxyy/infota/releases/)

# Step 1: Flash Recovery
> [!NOTE]
> This step can be skipped if you have compatible custom recovery.

1. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:
```cmd
adb -d reboot bootloader
```
(You can also power off the device, and boot it into bootloader mode by holding Volume Down + Power)

2. Once the device is in fastboot mode, verify your PC finds it by typing:
```cmd
fastboot devices
```
3. Flash the downloaded image files to your device by typing:
```cmd
fastboot flash boot boot.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash dtbo dtbo.img
``` 
Now reboot into recovery to verify the installation. Do not reboot into the existing OS, since it will overwrite the recovery you just installed!
simply type:
```cmd
fastboot reboot recovery
```

# Step 2: Flash ROM
> [!NOTE]
> This step can be also used for update installation

For clean / first-time installation - Tap Factory Reset > Format data and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one). This step can be skipped for update installation.

On the device, tap Apply Update > Apply from ADB to begin sideload.

On the host machine, sideload the package using:
```cmd
adb -d sideload InfinityX.zip
``` 
After installation recovery should prompt you to reboot back into it for installing additional packages, just select "No" and click "Reboot to system"

# Update Installation
If you're updating to a newer version, you can either:
Via OTA: Use the in-built Updater. (Settings > System > Update)
Via Recovery: Follow Step 2 above without factory reset.

