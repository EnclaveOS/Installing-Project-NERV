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

1.  Navigate to **Settings** $\to$ **About Phone** $\to$ **Software Information**.
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
