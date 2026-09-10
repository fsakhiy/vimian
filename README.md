# Lambo PHP OS

A custom Debian 13 (Trixie) live operating system built with `live-build`. This distribution features a customized XFCE desktop environment, a branded Calamares graphical installer, and an environment tailored for backend engineering with PHP, Node.js, and Go.

## Project Structure

*   `auto/` - Contains the `config` script to automate `lb config` flags and maintain build state.
*   `config/bootloaders/` - Custom GRUB and ISOLINUX splash images and menu text.
*   `config/hooks/live/` - Executable scripts that run inside the chroot environment during the build (e.g., setting default wallpapers).
*   `config/includes.chroot/` - Files mapped directly to the root `/` filesystem of the compiled OS. Includes OS release info, custom Calamares branding (`/etc/calamares/`), and default user skeleton configs (`/etc/skel/`).
*   `config/package-lists/` - Text files defining which `apt` packages are installed.

## Prerequisites

To compile this ISO, you need a Debian-based host (or VM) with at least 15GB of free disk space. 

Install the required build tools:
```bash
sudo apt update
sudo apt install live-build debootstrap squashfs-tools xorriso