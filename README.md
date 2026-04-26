![DNX Waterfall](https://img.shields.io/badge/Waterfall-DNX-blue)
![noVNC](https://img.shields.io/badge/noVNC-Enabled-purple)
![Remote UI](https://img.shields.io/badge/Remote-Access-brightgreen)# OWRXP-DNX-noVNC

Public OpenWebRX+ DNX image variant with an integrated noVNC desktop layer.

This repo is the companion image to:

- [OWRXP-DNX](https://github.com/KanotixPinguin/OWRXP-DNX) for the lean web-only build

Use this repo if you want the DNX OpenWebRX+ overlay plus a public noVNC access layer with documented default credentials.

## Scope

- public OpenWebRX+ base from `luarvique/ppa`
- DNX overlay from the public `OWRXP-DNX` project structure
- integrated X11/VNC/noVNC stack
- documented default noVNC password
- no private LoRa station data

## DNX Waterfall Highlights

This noVNC variant includes the same DNX waterfall family as the base project:

- `Standard`
- `3D-Modern`
- `Std/3DM`
- `3D-Old`
- `Flip/Flop`
---

## 🌊 DNX Waterfall (Included)

This project includes the DNX Waterfall system.

For full details and standalone version:
👉 https://github.com/KanotixPinguin/OWRXP-DNX-Waterfall

### 📸 Preview

#### 🎨 3D Modern
![3D Modern](https://raw.githubusercontent.com/KanotixPinguin/OWRXP-DNX-Waterfall/main/docs/images/waterfall-3d-modern.png)

#### 🧩 Split Mode (Standard + 3D)
![Split](https://raw.githubusercontent.com/KanotixPinguin/OWRXP-DNX-Waterfall/main/docs/images/waterfall-split.png)

#### 🧊 3D Old
![3D Old](https://raw.githubusercontent.com/KanotixPinguin/OWRXP-DNX-Waterfall/main/docs/images/waterfall-3d-old.png)
So users can choose between the lean web-only image and the desktop-enabled image without losing the newer waterfall presentation.

## Default Ports

- OpenWebRX web UI: `8073`
- noVNC web UI: `6080`
- raw VNC: `5901`

## Default noVNC Access

- VNC display: `:1`
- default password: `changeme`

Change the password after first start.

## What This Variant Adds

Compared with the base `OWRXP-DNX` repo, this image adds:

- `Xvfb`
- `x11vnc`
- `noVNC`
- a lightweight X11 session
- a helper terminal inside the VNC desktop

## Standalone Waterfall Option

The waterfall work can also be published later as a separate repo or patch tool for people who only want:

- the DNX waterfall modes
- without the full DNX runtime overlay
- and without the noVNC layer

That would fit well as a future companion repo such as `OWRXP-DNX-Waterfall`.

## Public Safety

This repo keeps the same public restrictions as the base project:

- no private IPs
- no private receiver keys
- no LoRa-specific private station configuration
- no personal VNC passwords

## Build

```sh
docker build -f docker/Dockerfile -t owrxp-dnx-novnc:test .
```

## Run

```sh
docker run --rm -p 8073:8073 -p 6080:6080 -p 5901:5901 \
  -e OWRXP_DNX_VNC_PASSWORD=changeme \
  --name owrxp-dnx-novnc \
  owrxp-dnx-novnc:test
```

Then open:

- OpenWebRX+: `http://SERVER-IP:8073`
- noVNC: `http://SERVER-IP:6080`

## Status

This repo is the public noVNC companion variant. It is intentionally separate so users can choose:

- base image without noVNC
- noVNC image with the extra desktop layer

---

## ?? Included Third-Party Plugins

This setup includes additional OpenWebRX+ plugins that are not developed by me:

- https://github.com/0xAF/openwebrxplus-plugins/tree/main/receiver/colorful_spectrum
- https://github.com/0xAF/openwebrxplus-plugins/tree/main/receiver/freq_scanner

All credit goes to the original authors.

These plugins are included for convenience and integration with this environment.

