### Get USB Redirect installation files (both server and client):
```
wget https://www.incentivespro.com/usb-redirector-linux-x86_64.tar.gz

tar -xvzf usb-redirector-linux-x86_64.tar.gz 

cd usb-redirector-linux-x86_64

./installer.sh install-client
```{{exec}}



### On remote machine install tailscale for ubuntu 20.04 - the killercoda version, to be able to connect to 32032 port directly:

```
curl -fsSL https://pkgs.tailscale.com/stable/ubuntu/focal.noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null

curl -fsSL https://pkgs.tailscale.com/stable/ubuntu/focal.tailscale-keyring.list | sudo tee /etc/apt/sources.list.d/tailscale.list

sudo apt update

sudo apt install tailscale
```{{exec}}

Run tailscale service:

`sudo tailscale up`{{exec}}


Click on link displayed in terminal to authrize and connect you host (server) machine to tailscale as well.

All tailscale IPs can be found here:

https://login.tailscale.com/admin/machines

On machine with physical USB drive in it install redirector server (windows example): https://www.incentivespro.com/usb-redirector.zip

Run and right click on USB drive to share/Share USB Device

Get server external IP from tailscale tray: Click on This device to copy the IP

### Or
If connecting without tailscale (make sure ports are opened on the server machine to the internet:

https://www.whatismyip.com/

On killercoda machine run:

`usbclnt -add-server YourServerIPFromTailscaleTray:32032`{{}}

On machine with physical USB (server): Remote Control/ Connect USB device to USB Client/Click on IP in the list starts with 100.

On remote killercoda machine usb will appear as sda

`lsblk -f`{{exec}}

'fdisk -l /dev/sda'{{exec}}

```
mkdir /media/usb

mount /dev/sda1 /media/usb

ls /media/usb
```{{exec}}

Test usb speed:

`hdparm -tTv /dev/sda`{{exec}}

### Useful info:
To uninstall on linux:

`/usr/local/usb-redirector/uninstall.sh uninstall`{{exec}}

To install server and client uninstall first and then run:

`./installer.sh install`{{exec}}
