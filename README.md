# ⚙️ Project NERV Installation Guide (One UI 7 Port for Galaxy A21s)

Welcome to the comprehensive, step-by-step guide for installing **Project NERV**—the highly anticipated **One UI 7 Custom ROM Port** for the Samsung Galaxy A21s.

This repository contains the full installation tutorial and links to all necessary files, including the custom ROM, Atlas Kernel, Repartitioner, and TWRP.

---

## ⚠️ CRITICAL COMPATIBILITY WARNING

**This custom ROM is ONLY compatible with the following device models:**
* **Samsung Galaxy A21s (SM-A217F)**
* **Samsung Galaxy A21s (SM-A217M)**

**Flashing this port on an incompatible device WILL cause a hard brick.** Neither the maintainer (Mustafa) nor the creator of this guide assumes responsibility for any damages to your device.

---

## 📦 What You'll Need

Ensure you have the following ready before starting the process:

* A compatible Samsung Galaxy A21s device (**A217F or A217M**)
* USB Cable
* Computer or Laptop
* Odin3 software
* **Required Files (Linked in this repository):**
    * The Custom ROM Zip (Project NERV)
    * Repartitioner
    * Atlas Kernel
    * `vbmeta_c.tar` (If needed)
    * TWRP Custom Recovery

---

## 1. Getting Started: Preparing Your Device

1.  Navigate to **Settings** > **About Phone** > **Software Information**.
2.  Tap on **Build Number** 4-5 times until a prompt confirms that **Developer mode has been enabled**. *(If you have a passcode, you will be required to enter it).*
3.  Return to the main **Settings** menu and find **Developer Options** at the bottom. Click on it.
4.  Tick both **OEM Unlock** and **USB Debugging** to 'On'. *(An internet connection may be required for **OEM Unlock** to appear or function).*
5.  Completely power off your phone.

---

## 2. Unlocking the Bootloader

1.  Hold down both the **Volume Up** and **Volume Down** buttons simultaneously.
2.  While holding the buttons, connect your phone to your Computer/Laptop using the USB cable.
3.  You should see a **Warning Screen**.
4.  To proceed, **hold down the Volume Up button**. You will see a screen asking, "Unlock Bootloader?".
5.  Press **Volume Up** again to confirm and proceed with the unlock.

***

**⚠️ NOTE: All data will be erased during this bootloader unlocking process.**

**CRITICAL STEP:** After the factory reset completes and the screen turns off, **DO NOT** let your phone power on again. Immediately hold both **Volume Up** and **Volume Down** buttons to re-enter Download Mode.

***

## 3. Flashing TWRP Custom Recovery

1.  Once you are back in **Download Mode**, press the **Volume Up** button.
2.  On your PC, open **Odin3**. A successful connection is indicated if you see `[ID:COM XX]` light up.
3.  Download the `TWRPV2.tar` file from this GitHub repository.
4.  In Odin3, select the **BL** slot and load the `TWRPV2.tar` file.
5.  Go to the **Options** tab in Odin3 and **UNCHECK** the box next to **"Automatic Restart"**.
6.  Click **"Begin"**. The flashing process should take only a few seconds.

---

## 4. Entering TWRP

Since we unchecked "Automatic Restart" in Odin, your phone should now be off and have TWRP flashed. Now, we need to boot directly into it.

1.  Hold down the **Volume Down** and **Power** buttons.
2.  **IMMEDIATELY** after the screen turns off (which happens as the phone reboots), quickly release those buttons and hold down **Power** and **Volume Up**.
3.  If done correctly, you should now see the **TWRP Splash Screen**, confirming you have entered recovery mode.

---

## 5. Flashing The Repartitioner

The repartitioner is required to properly size the partitions for the new One UI 7 ROM.

You can transfer and flash the `repartitioner.zip` using an external storage method (SD Card/USB) or by using ADB Sideload.

### Method A: External Storage (SD Card / USB OTG)

1.  Insert your **SD Card** or **USB OTG** drive containing the `repartitioner.zip`.
2.  In TWRP, tap **Install** > **Select Storage** > **SD Card/USB OTG**.
3.  Select the `repartitioner.zip` file.
4.  **Swipe to flash** the zip file.

### Method B: ADB Sideload

1.  In TWRP, tap **Advanced** > **ADB Sideload**.
2.  **Swipe to Start Sideload**.
3.  On your computer, execute the following command:
    ```bash
    adb sideload /path/to/the/repartitioner.zip
    ```

### Completion
Once flashing is complete, you must reboot back into recovery:
* Tap **Reboot** > **Recovery**.

---

## 6. Flashing Project NERV and Atlas Kernel

*(If you see mount errors from your device during this step, it is normal and should resolve itself afterwards.)*

### Step 6.1: Flash Project NERV ROM (`nerv.zip`)

Use the same method you used in Step 5 (External Storage or ADB Sideload) to flash the main ROM file.

#### Method A: External Storage (SD Card / USB OTG)
1.  In TWRP, tap **Install** > **Select Storage** > **SD Card/USB OTG**.
2.  Select the **`nerv.zip`** file.
3.  **Swipe to flash** the zip file.

#### Method B: ADB Sideload
1.  In TWRP, tap **Advanced** > **ADB Sideload**.
2.  **Swipe to Start Sideload**.
3.  On your computer, execute the following command:
    ```bash
    adb sideload /path/to/the/nerv.zip
    ```

### Step 6.2: Flash Atlas Kernel (`atlas_kernel.zip`)

Immediately after the ROM flash completes, flash the Atlas Kernel **without rebooting**.

1.  Still in the TWRP Install menu, tap the **"Add more Zips"** button (if available) or go back and tap **Install** again.
2.  Select the **`Atlas Kernel`** zip file.
3.  **Swipe to flash** the kernel.

### Step 6.3: Wipe and Reboot

This is the final cleaning step before booting the new ROM.

1.  Go to the main TWRP menu and tap **Wipe**.
2.  Tap **Advanced Wipe**.
3.  Select the following partitions:
    * **Dalvik/ART Cache**
    * **Cache**
    * **Data**
4.  **Swipe to Wipe** the selected partitions.
5.  Finally, tap **Reboot** > **System**.

---

## 7. Flashing vbmeta_c (Troubleshooting First Boot)

***

**⚠️ ONLY PERFORM THIS STEP IF YOUR DEVICE REVERTS TO DOWNLOAD MODE INSTEAD OF BOOTING THE CUSTOM ROM (With Errors).**

***

If your device fails to boot into Project NERV after Step 6 and drops back to Download Mode, it indicates that the stock recovery/firmware is trying to revert the changes. Use this step to resolve the issue:

1.  Ensure your phone is still connected to the computer and is in **Download Mode**.
2.  On your PC, open **Odin3**. Confirm the device is detected (`[ID:COM XX]` is lit).
3.  Click the **BL** button and load the **`vbmeta_c.tar`** file.
4.  Click **"Start"**.

After the flash completes, your device should reboot automatically. If you see the "Powered by Android" screen and the device proceeds to the setup, **CONGRATULATIONS!** You have successfully installed Project NERV on your A21s.
