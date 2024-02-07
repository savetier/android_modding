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

Links:

https://lineage.razuuu.de/devices/a7y18lte.html

https://drive.google.com/drive/folders/1b-s_1GhU0FYjiWkPSkdyjO6glefOWsKa

https://community.e.foundation/t/unofficial-build-samsung-galaxy-a7-2018-a7y18lte-for-e-os-r/53207


Experiences:

Lineage OS 18.1 and DotOS work, in eOS the Wifi doesn't work, Elixier and ArrowOS freeze

## Samsung Galaxy Tab 9.6

Download Mode: Vol- + Home + Power

Recovery Mode: Vol+ + Home + Power

Switch off: Vol- + Power


Links:

https://xdaforums.com/t/unofficial-rom-lineageos-14-1-for-galaxy-tab-e-sm-t561-sm-t560.3903780

https://androidfilehost.com/?fid=7161016148664852950

https://xdaforums.com/t/t560-kitkat-01-jan-2020-v10-lightrom.3716039/


Experiences:

Lineage 14.1 works but is very slow; LightROM is the better choice, as it is much faster
