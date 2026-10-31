# Lux Monitor

Local-only Android app for LuxPower inverters (tested target: LXP-LB-EU 12k with 3x Pytes V5).
Reads live data straight from the WiFi dongle (TCP port 8000), no cloud and no Home Assistant.
Animated power-flow screen (solar, grid, battery, home) plus battery runtime estimate.

## Get the APK
1. Push this repo to GitHub (branch `main`).
2. Open the **Actions** tab, run **Build APK**, and download `LuxMonitor-debug-apk` from the run.
3. Or push a tag such as `v1.0` and the APK is attached to a GitHub Release.
4. Install on your phone (allow "install unknown apps").

## Setup in the app
Dongle IP, dongle serial (10 chars), inverter serial (10 chars), battery kWh (default 15.36), reserve SOC %.
Phone must be on the same network as the dongle.

## Notes
- Protocol is community-documented (lxp-bridge) and untested on real hardware. If no reply, set `PROTO = 1` in `LuxClient.kt`.
- Port 8000 must be enabled on the dongle; only one local client at a time.
- Runtime = usable battery energy / 5-min average load (no PV), 94% discharge efficiency.
