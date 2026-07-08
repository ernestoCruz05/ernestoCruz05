# Hi, I'm Ernesto Cruz
### Firmware Developer | Systems Programmer | Wayland Tooling

I write UEFI firmware (EDK II, DXE drivers) and Linux systems code in C and Rust. I contribute to the [Mango](https://github.com/mangowm/mango) Wayland compositor and build most of the tooling around it.

I run my own infrastructure. My portfolio is self-hosted on a home server I architected and configured from bare metal up.

<div align="center">

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-portfolio.faky.dev-2ea44f?style=for-the-badge)](https://portfolio.faky.dev)
[![Mail](https://img.shields.io/badge/📧_Contact-Email-0078D4?style=for-the-badge)](mailto:ernestobritocruz05@gmail.com)

</div>

---

### Stuff i do

| Domain | Technologies |
| :--- | :--- |
| **Firmware & UEFI** | ![C](https://img.shields.io/badge/-C-black?logo=c&logoColor=white) ![EDK II](https://img.shields.io/badge/-EDK_II-CC0000?logo=intel&logoColor=white) ![UEFI](https://img.shields.io/badge/-DXE_Drivers-4A4A4A?logo=upcloud&logoColor=white) ![RP2040](https://img.shields.io/badge/-Pico_W-A22846?logo=raspberrypi&logoColor=white) |
| **Systems & Wayland** | ![Rust](https://img.shields.io/badge/-Rust-black?logo=rust&logoColor=white) ![Wayland](https://img.shields.io/badge/-Wayland%2Fwlroots-FFBC00?logo=wayland&logoColor=black) ![Lua](https://img.shields.io/badge/-Lua-2C2D72?logo=lua&logoColor=white) ![Unix](https://img.shields.io/badge/-Unix%2FIPC-black?logo=linux&logoColor=white) |
| **Infrastructure & Ops** | ![Linux Admin](https://img.shields.io/badge/-SysAdmin-FCC624?logo=linux&logoColor=black) ![Docker](https://img.shields.io/badge/-Docker-2496ED?logo=docker&logoColor=white) ![Self Hosting](https://img.shields.io/badge/-HomeLab-999999?logo=server&logoColor=white) |

---

### Firmware & UEFI

#### [PicoBootGate](https://github.com/ernestoCruz05/bootgate)
> *C, EDK II, UEFI BDS, Raspberry Pi Pico W, MicroPython*

A pre-boot remote authorisation system: the machine won't boot until a network-issued ticket says it can. This is the reference implementation for an academic paper.

The host firmware hands all network operations (WiFi, TLS, HTTP) to a USB-attached Pico W, so the code running in UEFI stays small and auditable. An EDK II DXE driver finds the Pico over USB CDC-ACM, and a BDS-phase application checks the authorisation ticket against NVRAM state before it chain-loads the next boot option. On failure it drops into a recovery UI instead.

#### [PicoWifiDxe](https://github.com/ernestoCruz05/picodxe-showcase)
> *C, EDK II, USB, WiFi2 protocol*

A UEFI DXE driver that turns a €7 Raspberry Pi Pico W into a WiFi adapter for firmware with no native WiFi stack. It detects the Pico on the USB bus, drives it over bulk CDC-ACM transfers, and publishes the standard `EFI_WIRELESS_MAC_CONNECTION_II` protocol, so any UEFI application can scan and connect through it. Useful for pre-boot provisioning and lab setups where there's no vendor WiFi driver to be found.

---

### The Mango ecosystem

I contribute upstream to [Mango](https://github.com/mangowm/mango), a dwm-style Wayland compositor, and maintain a set of tools around it:

| Project | What it is |
| :--- | :--- |
| [**mango-ext**](https://github.com/ernestoCruz05/mango-ext) | My extension fork of Mango, with custom transition shaders and experimental features. |
| [**mplug**](https://github.com/ernestoCruz05/mplug) | Lightweight IPC-based plugin manager and Lua scripting engine for MangoWC. *(Rust)* |
| [**mdisplay**](https://github.com/ernestoCruz05/mdisplay) | GUI monitor layout manager for MangoWC. *(Rust)* |
| [**mlint**](https://github.com/ernestoCruz05/mlint) | Linter for mplug plugins. *(Rust)* |
| [**dunsh**](https://github.com/ernestoCruz05/dunsh) | Trying to make the most out of dunst. *(Lua)* |
| [**useful_plugins**](https://github.com/ernestoCruz05/useful_plugins) | The mplug plugins I run daily. |

---

### Earlier work

<details>
<summary><b>Older projects</b></summary>
<br>

* [**hwprofiler**](https://github.com/ernestoCruz05/hwprofiler) is a cross-platform hardware fingerprinting CLI in C, built with Meson for Linux, Windows, macOS, and the BSDs.
* [**InputRelay**](https://github.com/ernestoCruz05/InputRelay) translates controller inputs into keyboard and mouse events, in C.
* [**RustyRoom**](https://github.com/ernestoCruz05/RustyRoom) is a TCP text chat in Rust with a terminal UI.
* [**unix-topic-chat**](https://github.com/ernestoCruz05/unix-topic-chat) is a topic-based chat in C built on Unix IPC (pipes) with an ncurses interface.
* [**MyCOLL**](https://github.com/ernestoCruz05/MyCOLL) is a full-stack logistics app: .NET MAUI/Blazor client, .NET Web API, EF Core.

</details>

---

### My Home server
<details>
<summary><b>Home Server</b></summary>
<br>

**Hardware (Custom Build):**
* **Compute:** Intel Core i7-14700KF (20 Cores) @ 5.6 GHz
* **Memory:** 32GB DDR5 ECC (Error Correction Code)
* **Motherboard:** Gigabyte B860M
* **Networking:** 2.5 GbE Uplink

**Service Orchestration (Docker/Nginx):**
* **Core:** Nginx Proxy Manager, Portainer, Watchtower
* **Network:** Pi-hole (DNS/Adblock), WireGuard (VPN)
* **Storage & Productivity:** Nextcloud, Joplin, Glance
* **Gaming:** Dedicated Game Server containers

</details>

<div align="left">
  <a href="https://portfolio.faky.dev">
    <img src="https://img.shields.io/badge/Check_out_my_Full_Portfolio_Here-→-gray?style=flat&logo=firefox" height="28">
  </a>
</div>
