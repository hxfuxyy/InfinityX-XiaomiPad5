[← Back to main page](/README.md)

# InfinityX Installation Guide

> [!WARNING]
> These instructions are for InfinityX on the Xiaomi Pad 5 (nabu). They will only work if you follow every section and step precisely. Do not skip steps.

## Prerequisites

Download the following files from [**Releases**](https://github.com/hxfuxyy/infota/releases/latest):

- **InfinityX.zip** — ROM package for ADB sideload
- **boot.img**, **vendor_boot.img**, **dtbo.img** — required only for **Option A (ADB Sideload)**

If you plan to use the **Auto Installer**, you only need to download it from the **pinned message** in the [t.me/InfinityXnabu](https://t.me/InfinityXnabu) Telegram chat — no other files required.

---

## Step 1: Flash Recovery

> [!NOTE]
> This step is only required for **Option A (ADB Sideload)**. If you plan to use the **Auto Installer**, skip to [Option B](#option-b-auto-installer-pc-scripts).
> You can also skip this step if you already have a compatible custom recovery installed.

1. On your computer, open a command prompt (Windows) or terminal (Linux/macOS) and type:
```cmd
adb -d reboot bootloader
```
> You can also power off the device and hold **Volume Down + Power** to boot into fastboot.

2. Once in fastboot mode, verify the device is detected:
```cmd
fastboot devices
```

3. Flash the downloaded image files:
```cmd
fastboot flash boot boot.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash dtbo dtbo.img
```

4. Reboot into recovery:
```cmd
fastboot reboot recovery
```

> [!WARNING]
> Do **not** reboot into the existing OS — it will overwrite the recovery you just flashed.

---

## Step 2: Flash ROM

Choose one of the two methods below.

### Option A: ADB Sideload

> [!NOTE]
> This option can also be used for update installation.

**For clean / first-time installation only:**
- In recovery, tap **Factory Reset > Format data** and confirm.
- This removes encryption and wipes all internal storage.
- **Skip this step** if you are updating.

1. On the device, tap **Apply Update > Apply from ADB**.

2. On your computer, run:
```cmd
adb -d sideload InfinityX.zip
```

3. After installation, if recovery prompts you to reboot back into it for additional packages — select **"No"** and tap **Reboot to system**.

---

### Option B: Auto Installer (PC scripts)

> [!NOTE]
> Download the Auto Installer ZIP from the **pinned message** in the [t.me/InfinityXnabu](https://t.me/InfinityXnabu) Telegram chat.

<details>
<summary>Windows</summary>

1. **Extract** the Auto Installer `.zip` to a folder with no spaces or special characters in the path.

2. Boot your tablet into fastboot mode:
```cmd
adb -d reboot bootloader
```
> Or hold **Volume Down + Power** until the bootloader screen appears.

3. Verify the device is detected:
```cmd
fastboot devices
```
> If not listed, try a different USB cable/port or reinstall [Google USB Drivers](https://developer.android.com/studio/run/win-usb).

4. Run the appropriate script:
   - `install_..._windows.bat` — clean installation
   - `update_..._windows.bat` — update existing ROM

Follow on-screen instructions carefully.

> [!WARNING]
> **Do not disconnect your tablet during script execution.** Interruption can leave the device unbootable.

</details>

<details>
<summary>Linux / macOS</summary>

1. **Extract** the Auto Installer `.zip` to a folder with no spaces or special characters in the path.

2. Boot your tablet into fastboot mode:
```cmd
adb -d reboot bootloader
```

3. Verify the device is detected:
```cmd
fastboot devices
```

4. Open terminal in the extracted folder and run:
```bash
sudo bash ./install_..._linux.sh    # clean installation
sudo bash ./update_..._linux.sh     # update existing ROM
```

> [!WARNING]
> **Keep the terminal open and monitor progress.** Closing it early can interrupt flashing.

</details>

> [!WARNING]
> First boot may take **5–10 minutes**. Do not panic or interrupt the process.

---

## Update Installation

If you are updating to a newer version, a factory reset is **not required**.

- **Via OTA:** *Settings > System > Update*
- **Via Recovery:** Follow [Option A](#option-a-adb-sideload) without performing Factory Reset.
- **Via Auto Installer:** Run the `update_...` script from the Auto Installer ZIP.

> [!WARNING]
> Always verify that the ZIP or OTA file matches your device (nabu). Installing a wrong build may cause a boot loop.
