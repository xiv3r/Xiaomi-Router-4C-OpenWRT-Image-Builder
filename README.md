## Openwrt Image Build Guide for Xiaomi Mi Router 4C

### Ubuntu/Debian Dependencies 
```sh
sudo apt install build-essential libncurses-dev zlib1g-dev gawk wget git gettext libssl-dev xsltproc rsync wget unzip python3 python3-distutils -y
```
## Download image builder:
   > choose your desired version to build either a snapshot or the latest version from here: `https://archive.openwrt.org/releases`
```sh
wget https://archive.openwrt.org/releases/22.03.7/targets/ramips/mt76x8/openwrt-imagebuilder-22.03.7-ramips-mt76x8.Linux-x86_64.tar.xz
```
## Unpack:
```sh
tar -J -x -f openwrt-imagebuilder-*.tar.xz
```
```sh
cd openwrt-imagebuilder-*/
```     
## List installed packages from Openwrt stable released.
```sh
echo $(opkg list-installed | sed -e "s/\s.*$//")
```
## Build:

`make image PROFILE="xiaomi_mi-router-4c" PACKAGES="aircrack-ng airmon-ng arp-scan base-files busybox ca-bundle cgi-io dnsmasq dropbear ethtool firewall4 fping fstools fwtool getrandom hostapd-common hping3 iw iwinfo jansson4 jshn jsonfilter kernel kmod-cfg80211 kmod-crypto-aead kmod-crypto-ccm kmod-crypto-cmac kmod-crypto-crc32c kmod-crypto-ctr kmod-crypto-gcm kmod-crypto-gf128 kmod-crypto-ghash kmod-crypto-hash kmod-crypto-hmac kmod-crypto-manager kmod-crypto-null kmod-crypto-rng kmod-crypto-seqiv kmod-crypto-sha256 kmod-gpio-button-hotplug kmod-leds-gpio kmod-lib-crc-ccitt kmod-lib-crc32c kmod-mac80211 kmod-mt76-core kmod-mt7603 kmod-nf-conntrack kmod-nf-conntrack6 kmod-nf-flow kmod-nf-log kmod-nf-log6 kmod-nf-nat kmod-nf-reject kmod-nf-reject6 kmod-nfnetlink kmod-nft-core kmod-nft-fib kmod-nft-nat kmod-nft-offload kmod-ppp kmod-pppoe kmod-pppox kmod-slhc libblobmsg-json20220515 libc libgcc1 libiwinfo-data libiwinfo-lua libiwinfo20210430 libjson-c5 libjson-script20220515 liblua5.1.5 liblucihttp-lua liblucihttp0 libmnl0 libncurses6 libnet-1.2.x libnftnl11 libnl-core200 libnl-genl200 libnl-nf200 libnl-route200 libnl-tiny1 libnl200 libopenssl1.1 libpcap1 libpcre libpthread libstdcpp6 libubox20220515 libubus-lua libubus20220601 libuci20130104 libuclient20201210 libucode20220812 libustream-wolfssl20201210 libwolfssl5.7.2.ee39414e logd lua luci luci-app-firewall luci-app-opkg luci-base luci-lib-base luci-lib-ip luci-lib-jsonc luci-lib-nixio luci-mod-admin-full luci-mod-network luci-mod-status luci-mod-system luci-proto-ipv6 luci-proto-ppp luci-ssl luci-theme-bootstrap mdk4 mtd netdiscover netifd nftables-json nmap odhcp6c odhcpd-ipv6only openwrt-keyring opkg ppp ppp-mod-pppoe procd procd-seccomp procd-ujail procps-ng px5g-wolfssl rpcd rpcd-mod-file rpcd-mod-iwinfo rpcd-mod-luci rpcd-mod-rrdns swconfig terminfo uboot-envtools ubox ubus ubusd uci uclient-fetch ucode ucode-mod-fs ucode-mod-ubus ucode-mod-uci uhttpd uhttpd-mod-ubus urandom-seed urngd usign wireless-regdb wireless-tools wpad-basic-wolfssl zlib"`
