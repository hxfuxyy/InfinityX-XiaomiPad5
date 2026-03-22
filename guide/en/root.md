# Rooting guide

## Method 1: KernelSu-Next
For install KernelSu-Next you just need to download latest manager [```Here```](https://github.com/KernelSU-Next/KernelSU-Next/releases)

## Finished!


## Method 2: Magisk

# Prerequisites
- [```Recovery Image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
### Reboot to **fastboot** 
- Boot your NABU into **fastboot** by holding down the **`volume down`** button during reboot

- Connect it to your PC/Laptop using a cable

### Boot the modded recovery
> While in fastboot mode, replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Flash magisk 
- Download [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) onto your PC/Laptop 
> Replace `path\to\magisk.apk` with the actual path of the magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Reboot into Android
> If it doesn't boot, reboot manually by press and hold power button
```cmd
adb reboot
```

### Finishing setup
- Set up your device, then download and install [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), if it isn't already installed.
- Open the **Magisk** app and follow the instructions on the screen, and your device should reboot after a few seconds.


## Finished!


