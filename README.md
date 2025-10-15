# Openwrt stable firmware image builder for Xiaomi Mi Router 4C
> This repo is alternative to openwrt firmware selector.

# Build using GitHub server
=> [Click this Templates](https://github.com/xiv3r/Xiaomi-Router-4C-OpenWRT-Image-Builder/generate)

=> Go to Actions => build => run workflows and wait until successful build 

=> The firmware is uploaded to your release page you can download and flash it.

### Custom build
> Edit the `.github/workflows/build.yml` from the repo and customize.

=> [ releases ] https://archive.openwrt.org/releases
```
wget https://archive.openwrt.org/releases/24.10.3/targets/ramips/mt76x8/openwrt-imagebuilder-24.10.3/ramips/mt76x8.Linux-x86_64.tar.zst

tar --zstd -xvf openwrt-imagebuilder-*.tar.zst

cd openwrt-imagebuilder-*/

make image PROFILE="xiaomi_mi-router-4c" PACKAGES="base-files ca-bundle dnsmasq dropbear firewall4 fstools kmod-gpio-button-hotplug kmod-leds-gpio kmod-mt7603 kmod-nft-offload libc libgcc libustream-mbedtls logd mtd netifd nftables odhcp6c odhcpd-ipv6only opkg ppp ppp-mod-pppoe swconfig uci uclient-fetch urandom-seed urngd wpad-basic-mbedtls uboot-envtools luci iw-full ip-full ethtool-full UDPspeeder zram-swap nano netdiscover nmap luci-app-ttyd"
```
> Specify the release tag
```
TAG_NAME="openwrt-SNAPSHOT-build-10-11-25-xiaomi-4c"
```
> Edit the Upload firmware file path 
```
downloads/openwrt-imagebuilder-24.10.3-ramips-mt76x8.Linux-x86_64/bin/targets/ramips/mt76x8/*.bin
```
=> The default package is located in the [firmware-selector.openwrt.org](https://firmware-selector.openwrt.org/?version=SNAPSHOT&target=ramips%2Fmt76x8&id=xiaomi_mi-router-4c) `Customize install package`

=> See the [Openwrt Image Builder](https://openwrt.org/docs/guide-user/additional-software/imagebuilder)

---------------
# Build Locally 
### Ubuntu/Debian Dependencies 
```
sudo apt update
sudo apt install build-essential file libncurses-dev zlib1g-dev gawk git gettext libssl-dev xsltproc rsync wget unzip python3 python3-full python3-venv -y
```
### Download image builder
> choose your desired version to build either a snapshot or the latest version from here: `https://archive.openwrt.org/releases/24.10.3/targets/ramips/mt76x8/`
```
wget https://archive.openwrt.org/releases/24.10.3/targets/ramips/mt76x8/openwrt-imagebuilder-24.10.3-ramips-mt76x8.Linux-x86_64.tar.zst
```
### Unpack
```
tar --zstd -xvf openwrt-imagebuilder-*.tar.zst
```
```
cd openwrt-imagebuilder-*/
```     
### Build
> you can add any package you want
```
make image PROFILE="xiaomi_mi-router-4c" PACKAGES="base-files ca-bundle dnsmasq dropbear firewall4 fstools kmod-gpio-button-hotplug kmod-leds-gpio kmod-mt7603 kmod-nft-offload libc libgcc libustream-mbedtls logd mtd netifd nftables odhcp6c odhcpd-ipv6only opkg ppp ppp-mod-pppoe swconfig uci uclient-fetch urandom-seed urngd wpad-basic-mbedtls uboot-envtools luci kmod-mt76 kmod-mtd-rw iw-full ethtool-full ip-full UDPspeeder zram-swap nano netdiscover"
```
### Firmware path
```
/bin/targets/ramips/mt76x8/firmware.bin
```
### Clean existing configuration
```sh
make clean
```
