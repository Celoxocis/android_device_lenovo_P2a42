## TWRP device tree for Lenovo P2 (P2a42)

Add to `.repo/local_manifests/P2a42.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
 <remote  name="TeamWin"
           fetch="https://github.com/TeamWin" />
	<project path="device/lenovo/P2a42" name="android_device_lenovo_P2a42" remote="TeamWin" revision="android-6.0" />
</manifest>
```

Then run `repo sync` to check it out.

To build:

```sh
. build/envsetup.sh
lunch omni_P2a42-eng
make -j1 recoveryimage
```

