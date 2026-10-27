*This project has been created as part of the 42 curriculum by sgaspari.*

# born2beroot

Rocky 10 VM setup using VirtualBox.

## Project description

The project requires setting up a Linux server in a virtual machine through VirtualBox. For this project, the flavour of Linux could be either Debian or Rocky. Since I already did this project with a Debian distro, this repository will describe the setup for a Rocky distribution. I chose to do this project again as an exercise to test the knowledge that I acquired by following the `RH124` and `RH134` course provided by Red Hat.

## Debian vs Rocky

The main differences between these two distros are regarding:

- **MAC:** Debian uses **AppArmor**, which confines programs through path-based profiles. Rocky uses **SELinux**, which assigns security contexts to every file, process and port. SELinux is more granular but harder to configure.
- **Firewall:** Debian uses **UFW**, a simple front-end for managing ports and protocols. Rocky uses **firewalld**, which is zone-based and distinguishes between runtime and permanent configuration.
- **Package manager:** Debian uses **apt** and `.deb` packages, while Rocky uses **dnf** and `.rpm` packages.

## Step by step setup

### VM Installation

After downloading the minimal `.iso` for Rocky 10, I created a new VM by using that image.

The VM has been created with the following hardware values:
- Base memory: `2048 MB`
- Processors: `1 CPU`
- Disk: `20GB`

In terms of VM configuration, I also added **Port Forwarding** with the following entry:

| Name | Protocol | Host IP | Host Port | Guest IP | Guest Port |
|------|----------|---------|-----------|----------|------------|
| `Rule 1` | `TCP` | | `4242` | | `4242`| 

### Rocky Installation

Through the Rocky Linux Minimal installation wizard, I set up:
- Language & Keyboard: `English (US)`
- Time & Date: `Europe/Berlin timezone`
- Users: `root` and `sgaspari`
- KDUMP: `disabled`
