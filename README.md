First stable release of the native ultrasound proximity repair for **Xiaomi Mi 9 SE (`grus`)** running the tested AlphaDroid build.



<img width="1080" height="2340" alt="Screenshot_20260913-010156_KernelSU-Next" src="https://github.com/user-attachments/assets/a6ab1802-8cc4-482e-88b4-97ecd6a4d310" />




### Tested on

```text
Device: Xiaomi Mi 9 SE
Codename: grus
ROM: AlphaDroid
Build: 16-20260713-gapps-grus-v4.6
Root: KernelSU Next
Vendor firmware base: V12.5.1.0.RFBMIXM
```

### Fixed

* ✅ Normal phone-call proximity
* ✅ WhatsApp-call proximity
* ✅ WhatsApp voice-note proximity
* ✅ Native `audio_hw_socket`
* ✅ Elliptic ultrasound communication
* ✅ Ultrasound TX using PCM 11
* ✅ Ultrasound RX using PCM 38
* ✅ Android proximity display handling

### Technical implementation

* Compatible grus Audio HAL
* Required 32-bit vendor dependencies
* KernelSU systemless module
* Read-only OverlayFS implementation
* SELinux-safe `vendor_file` labeling
* No permanent write to `/vendor`

### Root cause

The ROM's audio HAL did not provide the complete native Xiaomi ultrasound implementation required by the Mi 9 SE.

Elliptic could request:

```text
ultrasound-proximity=1
```

but communication failed through:

```text
/dev/socket/audio_hw_socket
```

with `Connection refused`.

v1.5 restores the native audio-side implementation and the complete ultrasound TX/RX path.

### Important

This release has been validated specifically on:

**AlphaDroid `16-20260713-gapps-grus-v4.6`**

Compatibility with other ROMs or AlphaDroid versions has not yet been confirmed.

### Author

**Ariel Torres**
Instagram: **@draccesoriosrd**

DR Accesorios RD
