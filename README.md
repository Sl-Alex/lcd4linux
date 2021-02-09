# LCD4Linux

This is a fork of LCD4Linux repository with additional support for [SlAlexUSBLCD][SlAlexUSBLCD_repo]
(USB LCD based on STM32F103C8T6 "BluePill" board and ST7565R-based 128x64 LCD). Original lcd4linux
website does not work anymore, but there is an (un)official [LCD4Linux Wiki][wiki], which has a lot
of information about the configuration, plugins and drivers, which can be used in LCD4Linux.

## Build

The build procedure is very simple if all required packages are installed.

```console
sudo apt install autotools-dev automake make gettext libtool-bin libgd-dev libusb-dev
./bootstrap
./configure
make
```

After build is done you can check which plugins and drivers were included:

```console
./lcd4linux -l
```

In order to check if everything works you can it like this (assuming you have SlAlexUSBLCD assembled):

```console
chown root:root ./SlAlexUSBLCD/lcd4linux.conf
chmod 600 ./SlAlexUSBLCD/lcd4linux.conf
sudo ./lcd4linux -F -vv -f ./SlAlexUSBLCD/lcd4linux.conf
```

[SlAlexUSBLCD_repo]: https://github.com/Sl-Alex/SlAlexUSBLCD
[wiki]: https://wiki.lcd4linux.tk/doku.php
