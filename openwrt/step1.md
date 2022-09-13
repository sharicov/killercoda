### Install build packages
`sudo apt install -y build-essential libncurses5-dev libncursesw5-dev zlib1g-dev gawk git gettext libssl-dev xsltproc rsync wget unzip python ncdu atop python2`{{exec}}

### Download stable version of image builder for x86 64bit architecture:
`wget https://downloads.openwrt.org/releases/22.03.0/targets/x86/64/openwrt-imagebuilder-22.03.0-x86-64.Linux-x86_64.tar.xz`{{exec}}

### Extract and enter working directory:
```
tar -J -x -f openwrt-imagebuilder-*.tar.xz 

cd openwrt-imagebuilder-*/
```{{exec}}

### Optional: to see available profiles:
`make info`{{exec}}

### Set size of OpenWRT partition (ex.304MB):
`sed -i 's/CONFIG_TARGET_ROOTFS_PARTSIZE=.*/CONFIG_TARGET_ROOTFS_PARTSIZE=504/' .config`{{exec}}

### Run the build process:
`make image PROFILE="generic" PACKAGES="base-files busybox ca-bundle dnsmasq dropbear e2fsprogs firewall4 fstools kmod-amazon-ena kmod-amd-xgbe kmod-bnx2 kmod-button-hotplug kmod-e1000 kmod-e1000e kmod-forcedeth kmod-fs-vfat kmod-igb kmod-igc kmod-ixgbe kmod-nft-offload kmod-r8169 kmod-tg3 libc libgcc libustream-wolfssl logd mkf2fs mtd netifd nftables odhcp6c odhcpd-ipv6only opkg partx-utils ppp ppp-mod-pppoe procd procd-seccomp procd-ujail uci uclient-fetch urandom-seed urngd luci iperf3 kmod-usb-net-rtl8152 luci-app-samba4 samba4-server ntfs-3g block-mount luci-app-ttyd luci-app-dockerman kmod-usb-storage kmod-usb-storage-uas usbutils luci-app-aria2 aria2 fdisk lsblk htop kmod-iwlwifi iwlwifi-firmware-ax200 btrfs-progs cfdisk gdisk pciutils tune2fs resize2fs wpa-supplicant netdata iwlwifi-firmware-iwl7260 dockerd docker docker-compose kmod-veth uxc procd-ujail samba4-client" `{{exec}}
``{{exec}}

### Find all created images:

`find . -name *.gz`{{exec}}

### Copy to local PC (use https://whatismyip.com to get your local IP address):

`python2 -m SimpleHTTPServer 8080`{{exec}}


### Browse files:
[Browse files]({{TRAFFIC_HOST1_8080}})

### Or manually:

`scp bin/targets/x86/64/openwrt-22.03.0-x86-64-generic-ext4-combined-efi.img.gz user@HomeMachineIP:/Directory`{{exec}}
