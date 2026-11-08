# OpenWrt Custom Build for Banana Pi BPI-R4 Pro 8X (Klamath Custom Fork)

> *Note: This repository is a custom fork based on the work of [woziwrt/bpi-r4-deploy](https://github.com/woziwrt/bpi-r4-deploy), whose baseline work is gratefully acknowledged.*

This custom build is optimized and tested **exclusively on the Banana Pi BPI-R4 Pro 8X with the Wi-Fi 7 BE14000 card**.

---

## Custom Additions & Modifications

Compared to the upstream base, this fork introduces the following specific changes:

- **Purged Unneeded Stack:** Completely removed Docker runtime (`dockerd`, `containerd`, `runc`, `tini`), StrongSwan, SQM/QoS, UPnP, p910nd, tc-tiny, and legacy adblock.
- **Added Security & DNS Filtering:** 
  - `adguardhome` + `luci-app-adguardhome`
  - `banip` + `luci-app-banip`
  - `smartdns` + `luci-app-smartdns`
- **Added Time Synchronization:** 
  - `chrony-nts` + `luci-app-chrony` + `collectd-mod-chrony`
- **Native WireGuard:** Integrated native WireGuard kernel module, CLI tools, and LuCI support (`kmod-wireguard`, `wireguard-tools`, `luci-proto-wireguard`).

---

## Roadmap / Upcoming Features

- **Aurora Theme:** Integration of `luci-theme-aurora` via external feed in the next release cycle.
- **WireGuard Installer:** Integration of the automated setup script from [Coralesoft/openwrt-wireguard-installer](https://github.com/Coralesoft/openwrt-wireguard-installer).
