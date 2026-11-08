# OpenWrt Custom Build for Banana Pi BPI-R4 & BPI-R4 Pro 8X (Klamath Custom Fork)

This is a customized, stripped-down OpenWrt build optimized for the Banana Pi BPI-R4 and **BPI-R4 Pro 8X** (MT7988A, Wi-Fi 7). It removes unnecessary services (Docker, StrongSwan, SQM, QoS, UPnP, p910nd, tc-tiny, tini) to ensure a lean, high-performance router, while integrating advanced DNS filtering, ad blocking, and time-sync tools.

> **Tested hardware:** Banana Pi R4 Pro 8X · Wi-Fi 7

---

## What is in this custom build

- **Clean & Lightweight:** All Docker and container runtimes, VPN/SQM server bloat, and legacy services have been purged.
- **Advanced Networking & Security:**
  - **AdGuard Home** + `luci-app-adguardhome` (Network-wide ad blocking and DNS control)
  - **banIP** + `luci-app-banip` (Advanced IP/subnet banning and firewall security)
  - **SmartDNS** + `luci-app-smartdns` (High-performance local DNS server)
- **Precise Time Sync:**
  - **Chrony with NTS (Network Time Security)** + `luci-app-chrony` + `collectd-mod-chrony`
- **UI & Management:**
  - Standard LuCI interface (Note: *Aurora theme integration is scheduled for the upcoming release*).
  - Essential system utilities, `htop`, `iperf3`, `tcpdump`, and MediaTek hardware/crypto accelerators.

---

## Repository Customization & Build

Managed via GitHub Actions through this repository. To compile your own image:

1. Fork this repository and keep the name `bpi-r4-deploy`.
2. Ensure Workflow permissions are set to **Read and write** (`Settings > Actions > General`).
3. Run the workflow manually under **Actions** targeting your board variant.
