# Grus Ultrasound Proximity Fix

<img width="1080" height="2340" alt="Screenshot_20260913-010156_KernelSU-Next" src="https://github.com/user-attachments/assets/771dcb1b-2115-4c0d-bd04-393661fb4250" />


Native Xiaomi ultrasonic proximity restoration for the **Xiaomi Mi 9 SE (`grus`)**, with Bluetooth A2DP multimedia compatibility for AlphaDroid.

**Current stable release: v1.5 Final**

## ⬇️ Download

[Download Grus Ultrasound Proximity Fix v1.5 Final](https://github.com/ariellourdes52-collab/grus_ultrasound_hal/releases/latest)

## 🔐 File verification

Official v1.5 Final SHA-256:

`5c671f760d4bb0ee126a1b632d2914b5896b7a0c2a88ab3dae3c92c7dfc49d45`

Use this checksum to verify that the downloaded ZIP matches the official v1.5 Final release.

## 📱 Tested device

* **Device:** Xiaomi Mi 9 SE
* **Codename:** `grus`
* **ROM:** AlphaDroid
* **Tested build:** `16-20260713-gapps-grus-v4.6`
* **Root:** KernelSU Next
* **Vendor firmware base:** `V12.5.1.0.RFBMIXM`
* **Installation:** KernelSU + OverlayFS

## ✅ What this module fixes

The module restores the native Xiaomi/Elliptic ultrasonic proximity implementation required by the Mi 9 SE.

Tested functionality includes:

* ✅ Normal phone-call proximity
* ✅ WhatsApp call proximity
* ✅ WhatsApp voice-note proximity
* ✅ Consecutive WhatsApp voice notes
* ✅ Elliptic ultrasonic proximity communication
* ✅ Native Xiaomi ultrasound TX/RX path
* ✅ Ultrasound TX through PCM 11
* ✅ Ultrasound RX through PCM 38
* ✅ Android proximity display behavior
* ✅ Bluetooth A2DP multimedia compatibility on AlphaDroid
* ✅ Bluetooth multimedia remains functional while the proximity fix is installed

## 🎧 Bluetooth fix

Version **1.5 Final** includes an isolated MIUI A2DP compatibility fix for Bluetooth multimedia on AlphaDroid.

The implementation keeps the ROM's generic Bluetooth libraries in place while adding only the compatibility components required by the Xiaomi Mi 9 SE audio stack.

This prevents the proximity restoration from breaking Bluetooth multimedia playback.

## 🔧 Technical implementation

The module uses:

* Compatible Xiaomi Mi 9 SE Audio HAL
* Required 32-bit vendor audio dependencies
* Native Elliptic ultrasonic proximity stack
* KernelSU systemless installation
* Read-only OverlayFS mounting
* SELinux-compatible vendor file handling
* No permanent modification of `/vendor`

Included compatibility components:

```text
vendor/lib/hw/audio.primary.sdm710.so
vendor/lib/btaudio_grus_if.so
vendor/lib/liba2dpgrus.so
vendor/lib/libaudio_log_utils.so
vendor/lib/libaudioroute_ext.so
```

## 🧩 Root cause

The affected AlphaDroid configuration did not provide the complete Xiaomi audio-side implementation required for the Mi 9 SE ultrasonic proximity system.

The Elliptic stack could request ultrasonic proximity operation, but the required native audio path was incomplete.

The Mi 9 SE uses Xiaomi's ultrasonic/Elliptic proximity implementation instead of relying only on a conventional physical proximity sensor.

Version **1.5 Final** restores the required audio-side components and ultrasonic TX/RX path while maintaining Bluetooth multimedia compatibility.

## 📦 Installation

### Requirements

* Xiaomi Mi 9 SE (`grus`)
* KernelSU / KernelSU Next
* OverlayFS support
* Compatible AlphaDroid installation

### Install

1. Download the latest module ZIP from **Releases**.
2. Open KernelSU Manager.
3. Go to **Modules**.
4. Choose **Install from storage**.
5. Select the module ZIP.
6. Reboot the device.

After rebooting, test proximity during:

* A normal phone call
* A WhatsApp call
* WhatsApp voice-note playback
* Bluetooth multimedia playback

## ⬇️ Download

**Latest stable release:**

[Download Grus Ultrasound Proximity Fix](https://github.com/ariellourdes52-collab/grus_ultrasound_hal/releases/latest)

## 🔄 Uninstall / Rollback

The installation is systemless.

To completely revert the modification:

1. Open KernelSU Manager.
2. Disable or remove **Grus Ultrasound Proximity Fix**.
3. Reboot.

The original ROM files will be used again automatically.

## ⚠️ Compatibility

This module has been validated specifically on:

```text
Xiaomi Mi 9 SE (grus)
AlphaDroid 16-20260713-gapps-grus-v4.6
KernelSU Next
Vendor firmware V12.5.1.0.RFBMIXM
```

Compatibility with other ROMs, firmware bases or AlphaDroid builds has **not yet been confirmed**.

Do not install this module on devices other than the Xiaomi Mi 9 SE (`grus`).

## 🛡️ Safety

The module does not permanently overwrite the vendor partition.

All modifications are applied systemlessly through KernelSU and OverlayFS and can be reverted by removing the module and rebooting.

## 🏷️ Module information

```text
ID: grus_ultrasound_hal
Name: Grus Ultrasound Proximity Fix
Version: 1.5 Final
VersionCode: 15
```

## 👨‍💻 Author

**Ariel Torres**

Instagram: **@draccesoriosrd**

DR Accesorios RD

## 🐛 Issues and testing

If you test the module on another AlphaDroid build or compatible ROM, please report:

* Device / ROM build
* Android version
* KernelSU version
* Whether normal-call proximity works
* Whether WhatsApp calls work
* Whether WhatsApp voice notes work
* Whether Bluetooth multimedia works

Reports can be submitted through the GitHub **Issues** section.

---

If this module restores proximity on your Mi 9 SE, consider starring ⭐ the repository. It helps other `grus` users find the fix.
