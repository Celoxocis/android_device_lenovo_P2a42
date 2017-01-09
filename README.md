## TWRP device tree for Lenovo P2 (P2a42)

Add to `.repo/local_manifests/P2a42.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
 <remote  name="Celoxocis"
           fetch="https://github.com/Celoxocis" />
 <remote  name="omnirom"
           fetch="https://github.com/omnirom" />
 <remote  name="CyanogenMod"
           fetch="https://github.com/CyanogenMod" />
    <project path="device/lenovo/P2a42" name="android_device_lenovo_P2a42" remote="Celoxocis" revision="cm-13.0" />
    <project path="bootable/recovery-twrp" name="android_bootable_recovery" remote="omnirom" revision="android-7.1" />
    <project path="external/busybox" name="android_external_busybox" remote="omnirom" revision="android-7.1" />
    <remove-project path="external/f2fs-tools" name="CyanogenMod/android_external_f2fs-tools" groups="pdk" />
    <project path="external/f2fs-tools" name="android_external_f2fs-tools" remote="omnirom" revision="android-7.1" />
    <project path="device/qcom/common" name="android_device_qcom_common" remote="CyanogenMod" revision="cm-13.0" />
</manifest>
```

Then run `repo sync` to check it out.

To build:

```sh
. build/envsetup.sh
lunch cm_P2a42-eng
make -j1 recoveryimage
```
