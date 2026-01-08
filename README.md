# # Install Magisk with ADB
This guide walks you through installing **Magisk** on your **Android** device using **ADB** and **Fastboot**.
Follow the steps carefully to safely root your device.

---

## Requirements

Before you begin, make sure you have the following:

1. [**Android Platform Tools**](https://developer.android.com/tools/releases/platform-tools)  
> [!WARNING]
> **(Ensure ADB and Fastboot are properly installed and added to your system PATH, this step is Optional, but you have to have the Platform-Tools folder and open a terminal in this specific path)**

2. A compatible Android Device with an **Unlocked Bootloader**.

4. The **official `boot.img`** file for your device’s current ROM or firmware.  
> [!NOTE]
> If you’re using a *Custom ROM* like [LineageOS](https://lineageos.org/), download its `boot.img` for your device.

5. The latest **[Magisk APK](https://github.com/topjohnwu/Magisk)** file.

---

## Step-by-Step Installation

1. **Developer Options and USB Debugging**
```
Settings -> About Phone -> Tap on Build number 7 times, then System -> Developer options -> USB debugging and Enable it
```

2. **Connect your phone to your PC with USB.**
3. **Verify the Connection**
Check that your phone is recognized by **fastboot**:
```
fastboot devices
```
If your device appears in the list, you’re good to go.

---

## Obtain boot.img
Download the correct *boot.img* for your device from your OEM or ROM provider’s website
> [!CAUTION]
> Always use the boot image that matches your current ROM version exactly

## Install Magisk on Your Phone
- Install the *Magisk APK* on your Android Device.
- Open the app and tap Install on the Magisk (the first option).
- Under Method, choose **Select and Patch a File**.
- Select your downloaded **boot.img**
- Tap **LET’S GO** and let **Magisk** patch the file.
Copy the patched image (magisk_patched_boot.img) from your device’s Downloads folder to your computer.
You can use:

    LocalSend
    A USB data cable
    Or any file transfer method you prefer

After patching, Magisk creates a new file named something like `magisk_patched-XXXX.img`.

## Transfer the Patched File
Copy the patched image (**magisk_patched_boot.img**) from your device’s **Downloads** folder to your computer and move it to the Platform Tools folder.
You can use:
- [LocalSend](https://localsend.org/) - Recommended
- A USB data cable
- Or any file transfer method of your choice

Move the patched boot file to your platform-tools directory

## Reboot Your Phone into Fastboot Mode
Run this command from your PC terminal (ensure ADB is working)
```
adb reboot fastboot
```
Your phone should now be in Fastboot mode.

## Flash the Patched Boot Image
Flash the patched image
```
fastboot flash boot magisk_patched_boot.img
```

Done, you rooted your Device ❤️🎉
