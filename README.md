# **Disclaimer**

This guide is provided for educational purposes only.
I am not responsible for any damage, data loss, or issues that may occur as a result of following these instructions.

Proceed at your own risk. Make sure to back up your data and understand each step before continuing.

---

# Rooting with Magisk on Motorola Edge 30 (XT2203-1)

## ⚙️ 1. Requirements

* Bootloader unlocked
* ADB and Fastboot installed
* USB debugging enabled
* Correct firmware downloaded (same system version)

---

## 📥 2. Get the boot.img

* Download stock firmware (e.g., RETBR U1RDS34...)
* Extract it:

```
unzip firmware.zip
```

* Locate:

```
boot.img
```

---

## 📲 3. Push to device

```
adb push boot.img /sdcard/
```

---

## 📱 4. Patch with Magisk

On the phone:

* Open Magisk
* Tap **Install**
* Select **Select and Patch a File**
* Choose `boot.img`

---

## 💻 5. Pull patched file to PC

```
adb pull /sdcard/Download/magisk_patched*.img
```

---

## 🔄 6. Reboot into fastboot

```
adb reboot bootloader
```

---

## ⚡ 7. Flash patched boot

```
fastboot flash boot magisk_patched.img
```

---

## 🔁 8. Reboot device

```
fastboot reboot
```

---

## ✅ 9. Verification

* Open Magisk
* It should show **Installed**

Test root:

```
su
```

👉 Grant permission when prompted

---

## 🛟 10. Recovery (if something goes wrong)

```
fastboot flash boot boot.img
fastboot reboot
```
## References 

- https://github.com/topjohnwu/Magisk
  
- https://en-us.support.motorola.com/app/standalone/bootloader/unlock-your-device-a/
