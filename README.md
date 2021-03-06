# Lps
Code and files related to the Local Position System boards from Loligo (http://shop.loligo.se/products/store)

Installing with board manager
-----------------------------
1. Add the following url to the list of additional board managers under file/preferences: 
https://github.com/loligo/lps/raw/master/package_loligo_lps_index.json
2. Next, go to the Tools menu, Board and Boards Manager.
3. Find Lps by Loligo and install. 

Installing without the board manager
------------------------------------
Place a symlink in your arduino/hardware directory pointing to this directory. For example (linux):
sudo ln -s ~/HOME/git/lps.git/ /usr/share/arduino/hardware/lps

ROS
----
Under linux you can setup udev to map your attached tags in a way that serial_talker can find them. Make sure to 
check and update the serial attributes to correspond. The serial of the ftdi chip is listed after connecting in dmesg.

```
SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6001", ATTRS{serial}=="AK04SUSC", SYMLINK+="ttyUSB.tag0"
...
SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6001", ATTRS{serial}=="AK04SUSI", SYMLINK+="ttyUSB.tag3"
```

Uploading hex files directly using the Chrome app AVRChick
----------------------------------------------------------
In the chrome webstore there is an application called AVRChick. This can upload the hexfiles
provided to your LPS board. You need to connect your LPS board to the computer before starting
AVRChick as it does not refresh it's list of devices. This is a link to the Chrome webstore for

AVRChick:
https://chrome.google.com/webstore/detail/avrchick/kpbgbcocfgjbmnpplcjlcammjdkgogba?hl=en
