## Android
[[ADB WIFI]]
###### App Language
```
adb shell settings put global settings_app_locale_opt_in_enabled false
```

## Windows
[[Uninstall Offline Windows OS Drivers with Dism Command]]
[[WSL2 Firewall Fixed]]

## Linux
###### Format blank disk
```
lsblk
sudo mkfs.ntfs /dev/sdb1
dd if=/dev/sdX of=/dev/null bs=1M
```
