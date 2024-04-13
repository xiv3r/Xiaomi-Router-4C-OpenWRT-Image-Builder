# Debian Linux

- Openwrt Image Build Guides for Xiaomi Mi Router 4C

### Steps;

 - install:

       sudo apt install build-essential libncurses-dev zlib1g-dev gawk wget git \
       gettext libssl-dev xsltproc rsync wget unzip python3 python3-distutils

- Download image builder:
  `Note`: choose your desired version to build either a snapshot or the latest version from here: `https://archive.openwrt.org/releases`

      wget https://archive.openwrt.org/releases/22.03.5/targets/ramips/mt76x8/openwrt-imagebuilder-22.03.5-ramips-mt76x8.Linux-x86_64.tar.xz

- Unpack:

      tar -J -x -f openwrt-imagebuilder-*.tar.xz

      cd openwrt-imagebuilder-*/

- Build:

      make image PROFILE="xiaomi_mi-router-4c" PACKAGES="base-files busybox ca-bundle cgi-io dnsmasq dropbear firewall4 fstools fwtool getrandom hostapd-common iw-full iwinfo jansson4 jshn jsonfilter kernel kmod-cfg80211 kmod-crypto-aead kmod-crypto-ccm kmod-crypto-cmac kmod-crypto-crc32c kmod-crypto-ctr kmod-crypto-gcm kmod-crypto-gf128 kmod-crypto-ghash kmod-crypto-hash kmod-crypto-hmac kmod-crypto-manager kmod-crypto-null kmod-crypto-rng kmod-crypto-seqiv kmod-crypto-sha256 kmod-gpio-button-hotplug kmod-leds-gpio kmod-lib-crc-ccitt kmod-lib-crc32c kmod-mac80211 kmod-mt76-core kmod-mt7603 kmod-nf-conntrack kmod-nf-conntrack kmod-nf-flow kmod-nf-log kmod-nf-log6 kmod-nf-nat kmod-nf-reject kmod-nf-reject6 kmod-nfnetlink kmod-nft-core kmod-nft-fib kmod-nft-nat kmod-nft-offload kmod-ppp kmod-pppoe kmod-pppox kmod-slhc libblobmsg-json libc libgcc libiwinfo-data libiwinfo-lua libiwinfo libjson-c libjson-script liblua liblucihttp-lua liblucihttp libmn libnftn libnl-tiny libpthread libubox libubus-lua libubus libuci libuclient libucode libustream-wolfssl libwolfssl logd lua luci luci-app-firewall luci-app-opkg luci-base luci-lib-base luci-lib-ip luci-lib-jsonc luci-lib-nixio luci-mod-admin-full luci-mod-network luci-mod-status luci-mod-system luci-proto-ipv6 luci-proto-ppp luci-ssl luci-theme-bootstrap mtd netifd nftables-json odhcp6c odhcpd-ipv6only openwrt-keyring opkg ppp ppp-mod-pppoe procd procd-seccomp procd-ujail px5g-wolfssl rpcd rpcd-mod-file rpcd-mod-iwinfo rpcd-mod-luci rpcd-mod-rrdns swconfig uboot-envtools ubox ubus ubusd uci uclient-fetch ucode ucode-mod-fs ucode-mod-ubus ucode-mod-uci uhttpd uhttpd-mod-ubus urandom-seed urngd usign wireless-regdb wpad-basic-wolfssl ip-full kmod-zram kmod-lib-lz4 zram-swap kmod-mt76 kmod-mt76x02"
