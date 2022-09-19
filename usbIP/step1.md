### Get USB Redirect installation files (both server and client):
```
wget https://www.incentivespro.com/usb-redirector-linux-x86_64.tar.gz

tar -xvzf usb-redirector-linux-x86_64.tar.gz 

cd usb-redirector-linux-x86_64

./installer.sh install-client
```{{exec}}

### On machine **with physical USB drive** in it install redirector **server** (windows example): https://www.incentivespro.com/usb-redirector.zip

Run and right click on USB drive to share/Share USB Device

Get server external IP here: https://www.whatismyip.com/

On **killercoda** machine run:

`usbclnt -add-server YourServerIPFromWhatismyip.com:32032`{{exec}}

### On machine with physical USB (server): Remote Control/ Connect USB device to USB Client

### Useful info:
### To uninstall on linux:

`/usr/local/usb-redirector/uninstall.sh`{{exec}}

[Browse files]({{TRAFFIC_HOST1_32032}})

