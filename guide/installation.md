# InfinityX Installation Guide
> [!Warning]
> The provided instructions are for InfinityX running on Xiaomi Pad 5 (nabu). These will only work if you follow every section and step precisely.

## Pre-installation

Download the following files from [```Releases```](https://github.com/hxfuxyy/infota/releases/):
- **InfinityX.zip** — ROM file for ADB sideload
- **boot.img**, **vendor_boot.img**, **dtbo.img** — required only for **Option A (ADB Sideload)**

If you plan to use the **Auto Installer** (PC script-based installation), you only need to download it from the **pinned message** in the [t.me/InfinityXnabu](https://t.me/InfinityXnabu) Telegram chat — no other files required.

---

## Step 1: Flash Recovery

> [!Note]
> This step is only required for **Option A (ADB Sideload)**. If you plan to use the **Auto Installer**, skip directly to [Option B](#option-b-auto-installer-pc-scripts).
> This step can also be skipped if you already have a compatible custom recovery installed.

1. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) and type:
```cmd
adb -d reboot bootloader
```
> You can also power off the device and boot into bootloader mode by holding **Volume Down + Power**.

2. Once the device is in fastboot mode, verify your PC detects it:
```cmd
fastboot devices
```

3. Flash the downloaded image files to your device:
```cmd
fastboot flash boot boot.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash dtbo dtbo.img
```

4. Reboot into recovery to verify the installation:
```cmd
fastboot reboot recovery
```

> [!Warning]
> Do **not** reboot into the existing OS — it will overwrite the recovery you just installed.

---

## Step 2: Flash ROM

Choose one of the two methods below.

### Option A: ADB Sideload

> [!Note]
> This option can also be used for update installation.

**For clean / first-time installation only:**
- Tap **Factory Reset > Format data** and continue with the formatting process.
- This will remove encryption and delete all files stored in internal storage.
- This step can be **skipped** for update installation.

1. On the device, tap **Apply Update > Apply from ADB** to begin sideload.

2. On the host machine, sideload the package:
```cmd
adb -d sideload InfinityX.zip
```

3. After installation, recovery may prompt you to reboot back into it for additional packages — select **"No"** and tap **Reboot to system**.

---

### Option B: Auto Installer (PC scripts)

> [!Note]
> Download the Auto Installer ZIP from the **pinned message** in the [t.me/InfinityXnabu](https://t.me/InfinityXnabu) Telegram chat.

<details>
<summary>Windows</summary>

> Only use this method if you are familiar with connecting your tablet to a computer and running scripts. Using Fastboot incorrectly can erase essential system partitions.

1. **Extract** the Auto Installer `.zip` to a location you can easily access.
   - Avoid paths with spaces or special characters to prevent script errors.

2. Connect your tablet in **Fastboot mode**:
```cmd
adb -d reboot bootloader
```
> Or power off the device and hold **Volume Down + Power** until the bootloader screen appears.

3. Verify the device is detected:
```cmd
fastboot devices
```
> If the device does not appear, check USB connection, try another cable, or install proper drivers.

4. Run the appropriate script from the extracted folder:
   - `install_..._windows.bat` — for first-time installation
   - `update_..._windows.bat` — for updating an existing ROM

- Follow the on-screen instructions carefully.

> [!Warning]
> **Do not disconnect your tablet during script execution.** Interruption can leave your device unbootable.

</details>

<details>
<summary>Linux / macOS</summary>

> Only use this method if you are familiar with connecting your tablet to a computer and running scripts. Using Fastboot incorrectly can erase essential system partitions.

1. **Extract** the Auto Installer `.zip` to a location you can easily access.
   - Avoid paths with spaces or special characters to prevent script errors.

2. Connect your tablet in **Fastboot mode**:
```cmd
adb -d reboot bootloader
```
> Or power off the device and hold **Volume Down + Power** until the bootloader screen appears.

3. Verify the device is detected:
```cmd
fastboot devices
```
> If the device does not appear, check USB connection, try another cable, or install proper drivers.

4. Open terminal in the extracted folder and run:
```bash
sudo bash ./install_..._linux.sh    # first-time installation
```
```bash
sudo bash ./update_..._linux.sh     # update existing ROM
```
> Scripts require root privileges (`sudo`) to access USB devices.

> [!Warning]
> **Keep your terminal open and monitor progress.** Closing the terminal early can interrupt flashing.

</details>

> [!Warning]
> First boot may take **5–10 minutes**. Do not panic or interrupt the process.

---

## Update Installation

If you're updating to a newer version, a factory reset is **not required**.

- **Via OTA:** Use the built-in Updater — *Settings > System > Update*
- **Via Recovery:** Follow [Option A](#option-a-adb-sideload) above without performing Factory Reset.
- **Via Auto Installer:** Run the `update_...` script from the Auto Installer ZIP.

> [!Warning]
> Always verify that the ZIP or update file matches your current ROM version. Installing an incompatible version may cause boot loops or permanent damage.

> Maded by [tvorogo](github.com/tvorogo) and [hxfuxyy](https://github.com/hxfuxyy/)
