# Acer-One-S1003-N16H1-Linux

# Which distro to install?
The easiest one to install was Fedora Workstation 33.

# After installation, my touchscreen doesn't work?!
Update your OS from "Software"

# Bluetooth starts but I can't find / devices can't find me?!
Type this in your terminal
```
dmesg | grep -i 'blue'
```
You might find a line saying
```
[5.763779] bluetooth hci0: Direct firmware load for brcm/BCM4343A0.hcd failed with error -2
[5.763789] Bluetooth: hci0: BCM: Patch brcm/BCM4343A0.hcd not found
```
Or something similar.
Download BCM4343A0.hcd from this repo and go to Downloads (or where it downloads) and open up a terminal there and type
```
sudo cp BCM43430A0.hcd /lib/firmware/brcm/
```
Do a reboot and it should work!
In case it doesn't, rename the file to whatever it's asking for (as long as your bluetooth is based on BCM43430A0)
