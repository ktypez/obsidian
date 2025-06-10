> [!important] 
>  **PREREQUISITES:**
>  - Check Project treble compatibility using [Treble Info](https://play.google.com/store/apps/details?id=tk.hack5.treblecheck)
>  - Must have A/B partitioning or System-As-Root support
>  - Must fit into ARM64 architecture requirement. (Future builds may include A64 support)
>  - Must have at least VNDK28 support.
1. Get [Platform Tools](https://developer.android.com/studio/releases/platform-tools#downloads)
2. Get vbmeta.img from Stock ROM or [Google](https://dl.google.com/developers/android/qt/images/gsi/vbmeta.img)
3. Get Elixir GSI
4. Boot into bootloader mode:

```
adb reboot bootloader
```

6. Flash the vbmeta you got from step two

```
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
```

7. Boot into fastbootd

```
fastboot reboot fastboot
```

8. Flash GSI

```
fastboot flash system GSI-FILENAME.img
```

> [!warning] 
> - If fastboot tells you there isn't enough place, you can try to delete product/system_ext partitions.
> - I recommend flash an empty image on thems to avoid problems with magisk.
> - Download File : [placebo](https://drive.google.com/file/d/1HqW-9zE2VgUI2KQcae2F4-82wOyL0HbP/view?usp=sharing)

```
fastboot flash product placebo.img
```

```
fastboot flash system_ext placebo.img
```

9. And try to flash GSI again
10. Go back to recovery, then perform "Factory reset / Wipe data"
11. Reboot and enjoy :D