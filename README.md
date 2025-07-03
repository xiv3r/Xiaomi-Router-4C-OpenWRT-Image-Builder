## Openwrt stable image rebuild guide for Xiaomi Mi Router 4C
> you can rebuild any openwrt stable released firmware for any specific router using this guide.

### Ubuntu/Debian Dependencies 
```sh
sudo apt install build-essential file libncurses-dev zlib1g-dev gawk git gettext libssl-dev xsltproc rsync wget unzip python3 python3-distutils -y
```
## Download image builder:
> choose your desired version to build either a snapshot or the latest version from here: `https://archive.openwrt.org/releases`
```sh
wget https://archive.openwrt.org/releases/24.10.1/targets/ramips/mt76x8/openwrt-imagebuilder-24.10.1-ramips-mt76x8.Linux-x86_64.tar.zst
```
## Unpack:
```sh
tar --zstd -xvf openwrt-imagebuilder-*.tar.zst
```
```sh
cd openwrt-imagebuilder-*/
```     
## List installed packages from Openwrt stable released
> pulled from the 22.03.7 stable release version
```sh
echo $(opkg list-installed | sed -e "s/\s.*$//")
```
## Default Package Build
> you can add any package you want

`make image PROFILE="xiaomi_mi-router-4c" PACKAGES="abase-files ca-bundle dnsmasq dropbear firewall4 fstools kmod-gpio-button-hotplug kmod-leds-gpio kmod-mt7603 kmod-nft-offload libc libgcc libustream-mbedtls logd mtd netifd nftables odhcp6c odhcpd-ipv6only opkg ppp ppp-mod-pppoe swconfig uci uclient-fetch urandom-seed urngd wpad-basic-mbedtls uboot-envtools luci kmod-mt76 kmod-mtd-rw iw-full hostapd-full UDPspeeder zram-swap nano"`

# Clean existing configuration
```sh
make clean
```
