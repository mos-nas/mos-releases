# MOS – a Minimal Operating System for Home Servers

_(No, it's not an acronym. Or maybe it is.)_

**MOS** is a lightweight operating system based on **[Devuan](https://www.devuan.org/)**, designed specifically for **small, energy‑efficient home servers**.

The primary goal of MOS is to provide a simple, reliable, and low‑overhead platform for self‑hosting, virtualization, and homelab environments.

This project started as a personal solution, and at some point I decided to **release it publicly to see if it resonates with others**.  
MOS is still evolving, but the core ideas are already in place.

---

## Features

By default, MOS comes with support for:

- **Docker**
- **LXC**
- **QEMU** (frontend still in development, API has almost full support)

Alongside a set of essential system tools, including:

- **Samba**
- **NFS**
- **NUT**
- **Cron**
- **...**

Remote networking and access services such as **Wireguard**, **Tailscale** and **Netbird** are also supported and can be managed via the **command line interface (CLI)**.

---

## Filesystem & Storage Support

By default, MOS ships with built‑in support for modern and flexible storage setups.

Included by default:

- **[mergerfs](https://github.com/trapexit/mergerfs)**  
  Allows combining multiple disks into a single unified filesystem, ideal for expandable storage setups.

- **[SnapRAID](https://www.snapraid.it/)**  
  Provides snapshot‑based parity protection for data disks, optimized for media and home server use cases.

This combination enables a flexible, efficient, and easy‑to‑manage storage solution without the complexity of traditional RAID.

---

### Additional Storage Drivers

Additional storage technologies are available via **MOS Hub** as optional driver plugins, including:

- **[NonRAID](https://github.com/qvr/nonraid)** (plugin)

This modular approach keeps the core system lightweight while allowing advanced storage features to be added when needed.

---

## Drivers & Plugins

MOS supports hardware drivers distributed as **optional plugins**, including:

- **NVIDIA drivers**
- **DVB drivers**

Additional drivers and plugins are planned and will be added over time.

---

## Open Source & Privacy

**MOS is and will always remain fully open source.**

**No data is collected.**  
There is **no telemetry, no tracking, and no usage reporting** of any kind.  
Everything runs locally and stays fully under your control.

---

## Project Status & Disclaimer

MOS is currently in a **very early stage of development**.

The operating system is provided **“as is”**.  
Bugs **can and will occur** at this stage.

While issues affecting the filesystem are not expected, you should **always keep backups of important data**.

If you encounter bugs, unexpected behavior, or crashes, please **open an Issue** in the appropriate repository so the problem can be investigated.

---

## Background & Motivation

MOS started as a personal project built out of necessity — I needed something that **just worked**, quickly and reliably.

Initially, MOS was nothing more than a **CLI‑only system**.  
Later, a friend asked if they could use it as well, which led to the development of a **REST API**. Over time, a **frontend** was added step by step.

What began as a small personal solution gradually evolved into a more complete operating system including (almost) full automation on GitHub.

---

## Target Audience

MOS is intended for:

- Homelab users
- Self‑hosters
- Developers
- Anyone looking for a minimal, efficient server OS with modern tooling

---

## Repositories & Documentation

Related repositories and components of the MOS ecosystem:

### MOS Documentation
- **[MOS Docs](https://github.com/ich777/mos-docs)**

### Frontende and API 
- **[MOS Frontend](https://github.com/ich777/mos-frontend)**
- **[MOS API](https://github.com/ich777/mos-api)**

### Base OS:
- **[MOS Kernel](https://github.com/ich777/mos-kernel)**
- **[MOS rootfs](https://github.com/ich777/mos-rootfs)**

### Base Packages:
- **[MOS Docker](https://github.com/ich777/mos-moby)**
- **[MOS LXC](https://github.com/ich777/mos-lxc)**
- **[MOS QEMU](https://github.com/ich777/mos-qemu)**

### MOS Specific Packages:
- **[MOS Notify](https://github.com/ich777/mos-notify)**
- **[MOS image-sha](https://github.com/ich777/mos-image-sha)**
- **[MOS mergerfs](https://github.com/ich777/mos-mergerfs)**
- **[MOS SnapRAID](https://github.com/ich777/mos-snapraid)**
- **[MOS docker-watchdog](https://github.com/ich777/mos-docker-watchdog)**

### MOS Misc Custom Repositories:
- **[MOS Boot Files](https://github.com/ich777/mos-boot-files)**
- **[MOS GRUB](https://github.com/ich777/mos-grub)**

---

## Minimum System Requirements

To run MOS reliably, the following minimum hardware requirements are recommended:

- **CPU:** x86_64 compatible processor
- **Memory:** 8 GB RAM
- **Storage:** A USB Flash device or HDD/SSD/NVME to install the OS (if you don't want to boot from the USB Flash device)
  (additional disks recommended for mergerfs / SnapRAID setups)
- **Network:** Ethernet or compatible network interface

These requirements ensure stable operation of containerized workloads, virtualization features, and storage services.

---

## TODO

MOS is at the very beginning of its journey.

There are **a lot of things left to do**, including missing features, improvements, refactoring, and documentation.  
While the project is still evolving, **breaking changes are intentionally avoided whenever possible** in order to maintain stability for early users.

If you are interested in contributing or experimenting with MOS at an early stage, feedback and contributions are highly appreciated.

---

## Contributing

Contributions, bug reports, and feature requests are welcome.  
Please use GitHub Issues to report bugs or discuss ideas before submitting larger changes.

---

## Design Philosophy

MOS favors simplicity, transparency, and modularity.

- No hidden services
- No telemetry
- No forced cloud dependencies
- Features can be added or removed via plugins (WIP)

---

## Repository scope
This repository is responsible for assembling and building MOS release artifacts.
It combines the MOS kernel, root filesystem, and drivers into bootable images
and ZIP archives.

---

## Licensing

The contents of this repository (build scripts, configuration files, and automation)
are licensed under the license specified in the `LICENSE` file.

Different MOS components and repositories may use different licenses.
This does **not** affect the licensing of third-party software included or packaged
by MOS, which always remains licensed under its original upstream licenses.

Please refer to the individual repositories for detailed licensing information.

---

## Third-Party Software

This repository builds and packages third-party open-source software.
The included components remain licensed under their original upstream licenses.
