# ADB notes

# fix verification error when installing apk

Run
```sh
adb shell settings put global verifier_verify_adb_installs 0
adb shell settings put global package_verifier_enable 0
```

# uninstall system apps

```
adb shell pm uninstall -k --user 0 [package name]
```
