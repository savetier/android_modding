Android modding on Manjaro Linux

## Tools

odin4

heimdall-grimler-git

thor-flash-utility -- https://github.com/Samsung-Loki/Thor

android-tools (adb + fastboot)


## Preparations

```kate /etc/udev/rules.d/51-android.rules ```

Get vendor and device number with ```lsusb```

Add text:

```SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", MODE="0666", GROUP="plugdev"```

```SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", MODE="685d", GROUP="plugdev"```

Create group "plugdev":

```sudo groupadd plugdev```

Add user to group:

```sudo usermod -a -G plugdev $USER```


## Flash TWRP/PBRP to Phone/Tablet

```heimdall detect```

```heimdall flash --RECOVERY recovery.img```

Immediately press the buttons to enter recovery mode, else TWRP will be overwritten.


## adb

```adb sideload rom.img``` - Flash ROM

```adb reboot download``` - Reboot into Download Mode

```adb start-server``` ```adb kill-server```


## Fastboot

```fastboot flash recovery recovery.img```

## Samsung Galaxy A7 (2018)

Download Mode: Vol+ + Vol- + Power
Recovery Mode: Vol+ + Power
Switch off: Vol- + Power

Lineage OS 18.1 and DotOS work, Elixier and ArrowOS freeze
